# zyBLOG - 一个简易的博客程序

**此项目的另一分支 [lite](https://github.com/Athenavi/zb/tree/lite) 现已支持*vercel*,无需繁琐配置**

*此项目 [zb](https://github.com/Athenavi/zb) 基于项目 [zyBLOG](https://github.com/Athenavi/zyBLOG) 更新优化，以提升过去版本的安全性和响应速度*

## 简介

[zyBLOG](https://github.com/Athenavi/zyBLOG) 是一个基于 Python Flask 和 WSGI 的简易博客程序

（以下demo网址非最新特性）
demo https://237127.xyz

## 功能特点

<details>
<summary>TODO List</summary>


- [x] 提供文章分类和标签功能，方便用户组织和浏览文章。
- [x] 界面适应手机 
- [x] SEO优化
- [x] 支持创建、编辑和删除博客文章。
- [x] 提供评论功能，让用户可以与其他用户进行交流和互动。
- [x] 用户可以注册和登录，以便管理他们的博客文章。
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
2. 克隆或下载 zyBLOG 代码库到本地。创建一个数据库，导入本项目里的 *sql* 文件（注意sql版本），复制 *config_example.ini* 文件到 *config.ini* ，配置 *config.ini*
3. 在终端中进入项目根目录，并执行以下命令的顺序执行以启动 zyBLOG 博客程序：

```bash
$ pip install -r requirements.txt
$ python wsgi.py
```

5. 在浏览器中访问 `http://localhost:5000`，即可进入 zyBLOG。
6. 默认管理员账号 'test' 默认密码 '123456'

## 无法运行？

首先升级你的python至3.10及更高版本

下述以Ubuntu系统中 python3.9升级到3.10为例
要将Ubuntu中的Python 3.9升级到Python 3.10，可以按照以下步骤进行操作：

1. 确保系统已经更新到最新版本：

   ```
   sudo apt update
   sudo apt upgrade
   ```

2. 添加deadsnakes PPA（Personal Package Archive）：

   ```
   sudo add-apt-repository ppa:deadsnakes/ppa
   ```

3. 更新软件包列表：

   ```
   sudo apt update
   ```

4. 安装Python 3.10：

   ```
   sudo apt install python3.10
   ```

5. 验证安装是否成功：

   ```
   python --version
   ```

现在，你的系统中应该已经成功安装了Python 3.10
此时你可以重新安装依赖以及启动程序

仍然无法运行？建议使用python虚拟环境

尝试使用Python的虚拟环境来隔离你的应用程序和系统环境。首先，安装venv模块（如果尚未安装）：

```bash
$ sudo apt install python3-venv
#创建一个新的虚拟环境：
$ python3.10 -m venv myenv
#激活虚拟环境：
$ source myenv/bin/activate
```

现在你可以在虚拟环境下重新安装依赖以及启动程序

## 鸣谢

 由 https://7trees.cn 提供API支持

 API可参阅 https://7trees.cn 菜单选项 API

## 免责声明

zyBLOG 是一个个人项目，并未经过详尽测试和完善，因此不对其能力和稳定性做出任何保证。使用 zyBLOG 时请注意自己的数据安全和程序稳定性。任何由于使用 zyBLOG 造成的数据丢失、损坏或其他问题，作者概不负责。

**请谨慎使用 zyBLOG，并在使用之前备份你的数据。**

# 开发文档

## 概述

欢迎使用，在开始开发 zyBLOG 之前，你应该对 html、JavaScript、Python、MySql 数据库、服务器等有基本的认识。本文档是建立在这些基础知识之上的。

## 模板开发

在开发模板之前，先做好zyBLOG的环境搭建

### 模板的组成

一个完整的模板，文件内容如下：

```
newtemplate
├── index.html
├── screenshot.png
└── template.ini
```

其中 `index.html` 、 `screenshot.png` 、`template.ini` 是模板的必须文件，一个模板最少由这三个文件组成。


`index.html` : 网站首页的模板
`screenshot.png` : 后台的模板缩略图
`template.ini` 模板的配置信息

提示
当我们开始开发一个新的模板的时候，可以先用这三个文件，打包成 zip 包之后，通过 zyBLOG 后台进行上传安装。

或者可以把 NewTemplate 文件夹直接复制到 zyBLOG 的 templates/theme 目录下也等同于安装。

模板的配置文件 template.ini 内容如下

``` ini
[default]
id = 'cn.7trees.2024'
title = '2024Theme'
description = '2024Theme_for_zyBLOG'
author = '7trees'
authorWebsite = 'http://7trees.cn'
version = '1.0'
versionCode = '1'
updateUrl = ''
screenshot = 'screenshot.png'
```

``` ini
[default]
# id ：模板ID，全网唯一，建议用 域名+名称 的命名方式
# title ：模板名称
# description ：模板简介
# author ：模板作者
# authorWebsite ：模板作者的官网
# version ：版本（不添加默认为1.0.0）
# versionCode ：版本号（只能是数字，不填写默认为1）
# screenshot ：此模板的缩略图图片（不填写默认为：screenshot.png）`
```

`当至少我们拥有这三个文件之后 刷新我们的程序 那么新的模板 就会出现在后台模板中`

## API 接口

### 获取城市代码

接口信息：
访问路径： `/api/get_city_code`

请求参数：`city_name`

| 参数名称  | 数据类型 | 是否必须 | 提交方式 | 描述     |
| --------- | -------- | -------- | -------- | -------- |
| city_name | str      | 是       | post/get | 城市名称 |

请求示例
 /api/get_city_code?city_name=北京

### 获取城市天气信息

接口信息：
访问路径：`/api/weather/<city_code>`

在上述接口的基础上可以得到城市代码，然后获取城市代码天气信息

