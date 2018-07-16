# git-subtree-test

## git substree用法
https://www.jianshu.com/p/3096069e9b72

    1. git subtree add --prefix=<S项目的相对路径> <S项目git地址> <分支> --squash
        
        （--squash可选，表示将commit log压缩到一次log）
        
    2. git subtree push --prefix=<S项目的相对路径> <S项目git地址> <分支>
    
    3. git subtree pull --prefix=<S项目的相对路径> <S项目git地址> <分支> --squash
    
eg:
    
    1. 添加subtree子项目
    git subtree add --prefix=python-learn git@github.com:Castlebin/python-learn.git master --squash
    
    2. 本地在对python-learn目录中代码做了一些修改后，需要push到远程的python-learn的git repo中
    git subtree push --prefix=python-learn git@github.com:Castlebin/python-learn.git master
    
    3. 远程python-learn的git repo经过其他人修改后，需要pull变化到本地的subtree子项目中
    git subtree pull --prefix=python-learn git@github.com:Castlebin/python-learn.git master --squash
    

说明：以上命令中--squash均为可选 ( git subtree push 加上--squash并没有什么卵用 )

## git子模块使用之git submodule与 git subtree比较
https://blog.csdn.net/liusf1993/article/details/72765131

submodule与subtree的差异
1. 核心区别 
git submodule类似于引用，而git subtree类似于拷贝，比如你在一篇博客中想用到你另一篇博客的内容，git submodule是使用那篇博客的链接，而git subtree则是将内容完全copy过来。
