# 说明
> 本项目是基于hexo搭建的个人博客，主要用于记录学习笔记和生活感悟，欢迎大家访问。
- 主页 www.tingfeng.cc
- 博客 blog.tingfeng.cc
- 网盘 pan.tingfeng.cc

--- 

> 为了保存数据, 新建一个分支 blog_workspace 用于保存博客源码, 此分支为手动上传数据
> main分支/master分支 用于保存博客生成的静态文件, 此分支为hexo自动上传数据

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