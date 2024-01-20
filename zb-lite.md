# zyBLOG - 一个简易的博客程序


*此项目 [lite](https://github.com/Athenavi/zb) 基于项目 [zyBLOG](https://github.com/Athenavi/zyBLOG) 轻量化版本,支持**vercel**上的部署*
## 简介

[zyBLOG](https://github.com/Athenavi/zyBLOG) 是一个基于 Python Flask 和 WSGI 的简易博客程序

（以下demo网址非最新特性）
demo https://lite.237127.xyz
## 功能特点

<details>
<summary>TODO List</summary>

- [x] 提供文章分类和标签功能，方便用户组织和浏览文章。
- [x] 界面适应手机 
- [x] SEO优化
- [x] 博客文章可以包含图片、视频和代码片段。
- [x] 支持搜索功能，使用户可以快速找到感兴趣的文章。 

</details>

## 技术组成

zyBLOG 使用以下技术组成：

- **Python Flask**: 作为 Web 框架，提供了构建网页应用的基础功能。
- **WSGI**: 作为 Python Web 应用程序与 Web 服务器之间的接口标准，实现了 Web 应用程序与服务器之间的通信。
- **HTML/CSS**: 用于构建博客界面的前端技术。
- **MySQL**: 作为数据库，用于存储用户、文章评论等数据。

## 如何运行
1. 确保你的系统已经安装了 Python 和 pip。
2. 克隆或下载 zyBLOG 代码库到本地。复制 *config_example.ini* 文件到 *config.ini* ，配置 *config.ini*
3. 在终端中进入项目根目录，并执行以下命令的顺序执行以启动 zyBLOG 博客程序：

```bash
$ pip install -r requirements.txt
$ python wsgi.py
```

## 鸣谢

 由 https://7trees.cn 提供API支持

 API可参阅 https://7trees.cn 菜单选项 API

## 免责声明

zyBLOG 是一个个人项目，并未经过详尽测试和完善，因此不对其能力和稳定性做出任何保证。使用 zyBLOG 时请注意自己的数据安全和程序稳定性。任何由于使用 zyBLOG 造成的数据丢失、损坏或其他问题，作者概不负责。

**请谨慎使用 zyBLOG，并在使用之前备份你的数据。**

## vercel
[![Deploy to Vercel](https://vercel.com/button)](https://vercel.com/import/project?template=https://github.com/Athenavi/zb/blob/lite)
