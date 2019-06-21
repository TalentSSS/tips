#### Q1 git 拉取仓库中的子目录

[Is it possible to clone only part of a git project?](https://unix.stackexchange.com/questions/233327/is-it-possible-to-clone-only-part-of-a-git-project)

假设我有一个repo里面有非常多的文件目录

https://github.com/TalentSSS/grammars-v4

全部clone下来特别慢，我只需要里面的golang目录

首先我先创建好本地的仓库

```bash
$ git init && cd g4
```

然后连接远程

```bash
$ git remote add origin https://github.com/TalentSSS/grammars-v4
```

设置如下选项，来允许部分checkout

```bash
$ git config core.sparseCheckout true
```

通过git中变量配置，设置需要拷贝的目录`golang`

```bash
$ echo "golang/" >> .git/info/sparse-checkout
```

直接拉取代码

```bash
$ git pull origin master
```



