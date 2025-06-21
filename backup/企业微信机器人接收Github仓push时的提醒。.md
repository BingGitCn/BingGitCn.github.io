1. 企业微信群添加机器人，复制WBEHOOK地址。
2. 打开github对应仓库，进入Settings->Secrets and variables->Actions。
3. 添加`WECHAT_WEBHOOK_URL` ，内容为第一步复制的机器人WBEHOOK地址。
4. 进入Actions，创建新的workflow，创建名为`wechat-notify.yml` 的文件。
内容为：
```
name: Notify WeChat on Push

on: [push]

jobs:
  notify:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4  # 必须先 checkout 代码才能获取 Git 信息
      
      - name: Send WeChat Notification
        env:
          WEBHOOK_URL: ${{ secrets.WECHAT_WEBHOOK_URL }}  # 企业微信 Webhook URL
        run: |
          COMMIT_MSG=$(git log -1 --pretty=%B)
          REPO_NAME="$GITHUB_REPOSITORY"
          BRANCH="$GITHUB_REF"
          AUTHOR="$GITHUB_ACTOR"
          COMMIT_URL="https://github.com/$GITHUB_REPOSITORY/commit/$GITHUB_SHA"

          MESSAGE=$(cat <<EOF
          **新的代码推送通知**  
          仓库: \`${REPO_NAME}\`  
          分支: \`${BRANCH}\`  
          提交者: \`${AUTHOR}\`  
          提交信息: \`${COMMIT_MSG}\`  
          [查看变更](${COMMIT_URL})
          EOF
          )

          curl -X POST \
            -H "Content-Type: application/json" \
            -d "{\"msgtype\": \"markdown\", \"markdown\": {\"content\": \"${MESSAGE}\"}}" \
            "${WEBHOOK_URL}"
``` 
5. 后续当仓库发生push变动时，企业微信机器人即可接收相应提醒。