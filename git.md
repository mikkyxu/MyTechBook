# create a new repository on the command line

```bash
echo "# MyTechBook" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/mikkyxu/MyTechBook.git
git push -u origin master
```

# push an existing repository from the command line

```bash
git remote add origin https://github.com/mikkyxu/MyTechBook.git
git push -u origin master
```

# gh-pages
有时候我们需要在Git下创建一个空分支,怎样安全的进行这项操作,我们需要建一个“孤立”的空分支，为了尽可能的保证数据安全，最好还是重新clone一份代码。

```bash
$git clone https://github.com/user/repo.git

$cd repo

# 创建一个orphan的分支，这个分支是独立的
$ git checkout --orphan gh-pages

# 删除原来代码树下的所有文件
$ git rm -rf .
rm '.gitignore'
注意这个时候你用git branch命令是看不见当前分支的名字的，除非你进行了第一次commit。

下面我们开始添加一些代码文件，例如这里新增了一个index.html
$ echo \"My GitHub Page\" > index.html
$ git add .
$ git commit -a -m \"First pages commit\"
$ git push origin gh-pages
在commit操作之后，你就可以用git branch命令看到新分支的名字了，然后push到远程仓库。
```
