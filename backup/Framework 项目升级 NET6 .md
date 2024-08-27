[官方文档](https://dotnet.microsoft.com/zh-cn/platform/upgrade-assistant/tutorial/install-upgrade-assistant)

1. **备份项目先！！！**
2. 安装升级助手：**cmd** 全局安装`dotnet tool install -g upgrade-assistant`
3. **cmd** 运行：`dotnet dev-certs https --trust`
4. 项目所在文件夹，按住 **shift** 右键打开 **powershell**
5. 输入升级的 **sln** 文件：`upgrade-assistant upgrade .\WpfApp2.sln`
6. 如果提示需要安装运行时，根据提示点击链接下载安装桌面运行时即可
7. 键盘上下键选择：这里选择仅更新项目 **SDK style**，而不是更新整个项目。
    ![](https://cdn.jsdelivr.net/gh/BingGitCn/BingGitCn.github.io/images/202408271.png)
8. 等待升级完成，双击项目文件可以查看最新，这里添加 C# 版本（一步到位直接添加10.0，或latest注意，仅让编译器忽略错误）：
    ![](https://cdn.jsdelivr.net/gh/BingGitCn/BingGitCn.github.io/images/202408272.png)
9. 这里升级后的执行目录为：`bin\Debug\net472`，具体看对应的 **Framework** 版本

<!-- ##{"timestamp":1684575105}## -->