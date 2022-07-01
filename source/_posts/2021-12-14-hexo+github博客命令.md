## hexo+github博客命令

### 两个分支

master和backups

master存放修改博客后的静态文件

backups存放博客其他文件

### git命令

```js
//下载hexo
npm install -g hexo-cli
//安装 hexo-deployer-git。
npm install hexo-deployer-git --save
//清除缓存文件 db.json 和已生成的静态文件 public
hexo clean
//生成网站静态文件到默认设置的 public 文件夹(hexo generate 的缩写)
hexo g
//自动生成网站静态文件，并部署到设定的仓库(hexo deploy 的缩写)
hexo d
//启动本地服务器
hexo s
//查看远程分支
git branch -a
//创建分支并切换到v0.9rc1分支
git checkout -b v0.9rc1 origin/v0.9rc1
//切换分支
git checkout <分支名>

git add --all

git commit -m "提交说明"
//提交到backups分支
git push --set -upstream origin backups 
//下载backup分支下的代码
git clone -b backups https://github.com/Peng-zihao/Blog.github.io.git

git push origin back
```

