
### 上传到github账户

github 上新建项目，复制项目路径（https）

本地新建文件夹，运行以下命令：

``` bash

git init
git remote add origin https://github.com/extendsWind/.spacemacs.d.git
git pull origin master

git add .
git commit -m "first commit"
git push -u origin master

```

当文件夹已有项目代码和git仓库，并已经git add 和git commit后，git pull origin master会报错如下：

> fatal: refusing to merge unrelated histories

此时pull需要使用：

` git pull origin master --allow-unrelated-histories`

