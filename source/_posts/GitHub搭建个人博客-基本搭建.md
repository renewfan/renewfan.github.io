---
title: GitHub搭建个人博客-基本搭建
date: 2018-08-20 16:54:34
tags:
	- hexo
	- github
	- node.js
categories: hexo
---
# GitHub搭建个人博客-基本搭建
<!-- toc -->
## 一、基本搭建
### 1、搭建环境
需要先按症状node.js和node.js环境（安装一直下一步即可）
检测是否安装成功：
在命令行（cmd或者git bash）输入下列命令
```
node -v  npm -v
```
显示 node.js npm的版本即为成功<br>
安装 git
### 2、Github新建项目
在自己的GitHub上新建仓库
> 仓库名：账户名.github.io

ps:必须使用自己GitHub账户名，不然会访问不到<br>
类型公开<br>
勾选  Initialize this repository with a README<br>
保存<br>
点击右侧setting下拉找到GitHub pages 找到所创建的项目的访问网址

```
http://账户名.github,io
```
### 3、安装hexo
在自己电脑合适的位置安装即可（打开git）

```
npm install hexo -g
```
检查是否安装成功

```
hexo -v
```
初始化安装hexo的文件夹
```
hexo init
```
最后显示“Start blogging with Hexo！”即为成功<br>
**安装所需组件**

```
npm install
```
使用 Hexo 生成静态文件

```
hexo generate
hexo g
```
启动hexo

```
hexo s
```
开启后窗口会显示一个本地网址，复制粘贴到浏览器即可访问
>http://localhost:4000
### 4、将hexo部署到GitHub
1. 配置git

```
git config --global user.email "you email"
git config --global user.name "you name"
```
2、生成密匙

```
ssh-keygen -t rsa -C “you email”
```
连续三个回车，生成密钥，最后得到了两个文件：
>id_rsa和id_rsa.pub

默认存储路径
>C:\用户\电脑用户名\.ssh

继续输入
```
eval "$(ssh-agent -s)"
```
添加密钥到ssh-agent，显示 Agent pid ***<br>
再输入
```
ssh-add ~/.ssh/id_rsa
```
添加生成的SSH key到ssh-agent<br>

3、GitHub 添加ssh
在之前创建的项目中<br>
点击右侧setting --> 选择左侧栏 Deploy keys -->Add deploy key

将
>C:\用户\电脑用户名\.ssh 中id_rsa.pub文件里的内容复制

测试添加 ssh 是否成功

```
ssh -T git@github.com
```
运行后看到你自己的用户名即为成功

4、配置 hexo<br>
在hexo安装目录找到 **_config.yml**

搜索**deploy**，设置如下：

```
deploy:
  type: git
  repository: 项目ssh链接
  branch: master
```
项目ssh链接来自GitHub项目 
>Clone and download

安装扩展

```
npm install hexo-deployer-git --save
```
### 5、新间文章并部署
创建文章

```
hexo new post “文章名”
```
在hexo\source\_posts可以找到创建的文件

生成+部署

```
$ hexo g -d
$ hexo d -g
```
访问你的地址：http://用户名.github.io;可以看到生成的文章