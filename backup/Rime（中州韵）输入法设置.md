![PixPin_2024-08-27_13-26-57.png](https://cdn.jsdelivr.net/gh/BingGitCn/BingGitCn.github.io/images/PixPin_2024-08-27_13-26-57.png)

Rime 全名是「中州韵输入法引擎」，Rime 不是一种输入法。是从各种常见键盘输入法中提炼出来的抽象的输入算法框架，需要搭配输入方案来使用。

## Step1：安装输入法框架
rime输入法[下载](https://rime.im/download/)
- Windows下载小狼毫。
- ios下载仓输入法。
- 同文或小企鹅

## Step2：安装雾凇拼音方案（双拼+全拼）
[雾凇拼音](https://github.com/iDvel/rime-ice?tab=readme-ov-file)（拼音方案）：
1. 安装git。
2. 输入法设置=>安装更多方案，输入：`iDvel/rime-ice:others/recipes/full` 等待下载。

## Step3：字体设置
[下载](https://github.com/lxgw/LxgwWenKai)右键安装霞鹜文楷。
字体名称是：`LXGW WenKai` 

## Step4：样式设置
字体调整：
右键托盘，打开用户文件夹，找到`weasel_custom.yaml` 文件，编辑字体后保存，然后重新部署即可。
```
customization:
  distribution_code_name: Weasel
  distribution_version: 0.16.1
  generator: "Weasel::UIStyleSettings"
  modified_time: "Fri Aug  9 16:07:47 2024"
  rime_version: 1.11.2
patch:
  "style/color_scheme": brisk
  "style/font_face": "Segoe UI Emoji, LXGW WenKai, SF Pro, Noto Color Emoji"
  "style/label_font_face": "LXGW WenKai"       # 标签字体
  "style/comment_font_face": "LXGW WenKai"     # 注释字体
  "style/horizontal": true                         # 候选项横排：true；false
  "style/vertical_text": false                     # 竖排文本：true；false
```


显示双拼字母而不是全拼字母：
用户文件夹找到`double_pinyin_flypy.schema.yaml`文件。
将` preedit_format`改成`[]`

## Step5：皮肤设置
[仿微信键盘皮肤](https://github.com/rime/weasel/wiki/%E7%A4%BA%E4%BE%8B#%E5%BE%AE%E4%BF%A1%E8%BE%93%E5%85%A5%E6%B3%95%E9%A3%8E%E6%A0%BC)
打开用户文件夹，打开`weasel.custom.yaml`文件，添加如下：
```
customization:
  distribution_code_name: Weasel
  distribution_version: 0.16.1
  generator: "Weasel::UIStyleSettings"
  modified_time: "Tue Aug 20 12:25:49 2024"
  rime_version: 1.11.2
patch:
  "preset_color_schemes/+":
    wechat: {back_color: 0xFFFFFF, border_color: 0xFFFFFF, candidate_text_color: 0x3c3c3c, comment_text_color: 0x999999, hilited_back_color: 0x79af22, hilited_candidate_back_color: 0x79af22, hilited_comment_text_color: 0xFFFFFF, hilited_label_color: 0xFFFFFF, hilited_text_color: 0xFFFFFF, label_color: 0x999999, name: "微信／Wechat", shadow_color: 0x20000000, text_color: 0x424242}
  "style/+":
    color_scheme: wechat
    comment_font_point: 11
    font_point: 13
    horizontal: true
    inline_preedit: true
    label_font_point: 13
    label_format: "%s"
    layout: {candidate_spacing: 24, corner_radius: 8, hilite_padding: 3, hilite_padding_x: 5, hilite_spacing: 6, margin_x: 10, margin_y: 6, max_height: 0, max_width: 1200, min_width: 10, round_corner: 8, shadow_radius: 4}
  "style/color_scheme": wechat
  "style/comment_font_face": "LXGW WenKai"
  "style/font_face": "Segoe UI Emoji, LXGW WenKai, SF Pro, Noto Color Emoji"
  "style/horizontal": true
  "style/label_font_face": "LXGW WenKai"
  "style/layout/hilite_padding_x": 7
  "style/layout/round_corner": 7
  "style/vertical_text": false
```
## Step6：同步
配置目录下的`installation.yaml`文件会在第一次部署后会自动生成；在这里可以编辑当前设备的ID和同步目录
使用坚果云，
```
installation_id: "RimeSync"
sync_dir: 'C:\Users\UserName\Nutstore\1\我的坚果云\Syncs\Rime'
```

## Step7：快捷键 
ctrl + ` 或者 f4，切换简繁等操作。 