---
title: The tools can be used to create a personal blog
tags: Blog about
categories: Blog about
---
## hexo  
it is a fast,simple&powerful blog framework,powered by Node.js.
### Advantages
1. Blazing fast generating  
2. Github Markdown support, and most Octopress plugins  
3. One-command deploy to Github,Heroku,etc.  
4. Powerful plugins system
### Installation and quick start
1. Installation:`$ npm install hexo-cli -g`  
2. Setup your blog:`$ hexo init blog`  `$ cd blog`  
3. Start the server:`$ hexo server`  
4. Create a new post:`$ hexo new "Hello Hexo"`  
5. Generate static files:`$ hexo generate`
### Internet support
1. Read the [documentation](https://hexo.io/)  
2. Find solutions in [troubleshooting](https://hexo.io/docs/troubleshooting.html)  
3. See the [plugin list](https://hexo.io/plugins/) and the [theme list](https://hexo.io/themes/) on wiki

## WPCMD
WPCMD(WordPress command)is a blog command line deployment tool.We using WordPress XML-RPC port create,update our local blog.  
In brief,WPCMD is a cmd used in WorldPress.By the way,there is no GUI interface.
### Advantages
1. Using Markdown  
2. GitHub support,you can optional choose your favorite version management to keep your blog.  
3. Dont have to open the background to finish all things,like creating,updating.  
4. Fenced Code Extra support
5. Manage multiple blogs at the same time
### Installation and quick start
1. Installation:`pip3 install wpcmd`  
if you are in China,you can use image source in China university of science and technology.  
`pip3 install -i https://mirrors.ustc.edu.cn/pypi/web/simple wpcmd`  
2. Setup:`wpcmd -h`
3. Blogs management:`wpcmd show --site site1 -t option`
4. Quick use:`wpcmd new` `wpcmd update` `wpcmd show` `wpcmd util`  
  
This blog just a brief introduction,if you want to learn how to create a blog with WPCMD,you can read this blog.