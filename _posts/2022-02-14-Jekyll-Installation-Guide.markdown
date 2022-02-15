---
layout: post
title:  "Jekyll & HEXO installation guide (Ubuntu)"
date:   2022-02-14 0:00:00 +0800
image:  blog-main.jpg
tags:   Blog
---

#### 記錄 Jekyll & HEXO 安裝 (For Ubuntu) 過程  

<strong>環境部署</strong>  

```bash
sudo apt install -y git nodejs npm ruby ruby-dev  
```

(When finish)  
<br>
<br>
<strong>HEXO 部分</strong>  

```bsh
npm install -g hexo  
hexo init blog  # 初始化创建，会创建blog文件夹  
npm install   # 进一步安装hexo所需文件
```
<br>
<br>
<strong>Jekyll 部分</strong>  

```bash
gem install jekyll bundler  
jekyll new my-awesome-site  
bundle install  
bundle exec jekyll serve  
```
<br>
<br>
<strong>Github & Gitee 遠程部署部分</strong>  

```bash
git config --global user.email *********@qq.com # 设置邮箱  
git config --global user.name '****'   # 设置用户名  
ssh-keygen -t rsa -C "xxxxx@xxxxx.com"  
（按照提示完成三次回车，即可生成 ssh key）  

~/.ssh/id_rsa.pub  
     #查看SSH-KEY  
復制去Github、Gitee有關頁面粘貼  

ssh -T git@gitee.com  
測試Gitee是否成功連接  

ssh -T git@github.com  
測試Github是否成功連接  
<br><br>
<strong>HEXO 發布部署部分</strong>  

```bash
npm install hexo-deployer-git --save  #部署工具下載  
hexo clean  
hexo g  
hexo d  
```
<br><br>
<strong>Jekyll 發布部署部分</strong>  
```zsh
cd demo  
git init   
git remote add origin <项目的.git地址>  
git pull origin master  
jekyll new . --force #会重新下載Jekyll 文件，可跳過。  
git add .  
git commit -m "jekyll"  
git push origin master  
编辑_config.yml，添加这一行  
```
<br><br>
*以上就是Jekyll & HEXO 安裝 (For Ubuntu) 過程*  
