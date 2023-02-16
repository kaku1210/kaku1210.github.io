---
title: hexo_create_and_optimize
date: 2023-02-17 03:54:43
tags:
---

> 为了保存数据, 新建一个分支 blog_workspace 用于保存博客源码, 此分支为手动上传数据
> main分支/master分支 用于保存博客生成的静态文件, 此分支为hexo自动上传数据

# 工作流程

[Hexo官网](https://hexo.io/zh-cn/docs/)

## 创建
1. 安装 Node.js (nodejs.org)](https://nodejs.org/en/)

   > node -v
   >
   > npm -v
   >
   > 查看版本号, 检查是否安装成功

2. 安装 git

3. 安装 Hexo 

   ```
   npm install -g hexo-cli
   ```

   > !!! **需要管理员打开终端 否则失败**

   > hexo -v 验证安装

4. 初始化工作区

   ```bash
   # 初始化文件夹
   hexo init
   # 安装组件
   npm install
   # 安装扩展
   npm i hexo-deployer-git
   ```

5. 创建github仓库

   > 仓库名必须为 用户名.github.io
   >
   > 必须Public
   >
   > 就可以在  Settings - Pages  最上面看到提示 (不是立刻就有的 可能要等会儿)
   >
   > *Your site is live at https://xxx.github.io/*

6. 连接github

   博客根目录的 `_config.yml` 文件

   ```bash
   deploy:
     type: git
     repository: https://github.com/xxx/xxx.github.io
     branch: master 或者 main # 具体填写哪个看自己的仓库
   ```

7. 绑定域名

   - 域名解析

     只需要将需要的域名 解析为 ***CNAME*** 即可

   - 在github 的仓库 Settings - Pages -  Custom domain位置,  填写对应域名

   - 正常情况下, 仓库根目录会出现一个 CNAME 文件, 如果没有的话, 就手动创建一个, 里面只有一行文本 就是域名.

8. 使用

   ```bash
   # 新建文章 --> source/_posts目录下会增加 一个文件夹(存放图片等数据) 一个.md文件(文章)
   hexo new post "name"
   # 生成博客静态网页文件
   hexo g
   # 打开本地服务器, 本地预览. 可通过 http://localhost:4000/ 访问
   hexo s
   # 上传网页文件到github对应分支
   hexo d
   ```

   





> 根目录配置文件`_config.yml`和主题目录配置文件`_config.yml`中修改个人信息。
>
> 根目录配置文件中修改`deploy`一栏的`repository`。
>
> 根目录配置文件中修改`baidu_url_submit`一栏的`token`。
>
> 主题配置文件中修改`gitalk`一栏

```txt

```



# 切换工作环境
1. git clone 源码(blog_workspace分支)
2. 初始化hexo
```bash
git clone xxxxx
cd xxxxx
npm install hexo
npm install hexo-deployer-git -save

hexo new post_name
```

# 注意事项
> 确保 hexo deploy 推送的是 主分支(master or main)
--> hexo 目录下 _config.yml 文件对应的目标路径
```
deploy:
  type: git
  repo: https://github.com/xxx/xxx.github.io.git
  branch: master
```