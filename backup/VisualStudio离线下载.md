1. 下载   Visual Studio 2022 Professional，[vs_professional.exe](https://aka.ms/vs/17/release/vs_professional.exe) 到 D 盘 VisualStudio 文件夹。
2. 创建离线安装布局，打开已安装的VS Installer，选择导出配置，将导出的配置文件 .vsconfig 复制到 D 盘 VisualStudio 文件夹内。
3. 管理员打开 CMD，输入 `d:` ，输入 ` cd visualstudio` 。
4. 输入 `vs_professional.exe --layout D:\VisualStudio --config "D:\VisualStudio\.vsconfig" --lang Zh-cn en-US` 即可开始下载。