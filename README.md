# vue-my-blog

> A Vue.js project

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).

# git  操作
第一步：添加文件新增的文件到git本地库
> git add *   //*提交所有的新增文件

第二部：提交修改的文件到git本地库
> git commit -m "第一次提交" //-m 提交的备注

第三步：连理本地库与github库的连接
> git remote add origin git@github.com:bailiubai/vue-my-blog.git    

第四步：提交代码到github
>git push -u origin master  //提交到master分支（主分支）

第五步：拉取github代码
>1. git fetch
>2. git pull


# //第三方拉去代码
第一步：git remote add origin git@github.com:bailiubai/vue-my-blog.git 
第二步：生产SSH密钥
> ssh-keygen -t rsa -C "你github的邮箱"
> 生产id_rsa.pub文件
第三步：github中添加SSH keys
第四步：拉取
> 1. git fetch
  2. git pull orgin master
第五步：提交新增的文件
> git add "文件名"
第六步：提交文件到本地库
> git commit -m "提交"
第七步：提交代码到远程
> git push -u origin master 

