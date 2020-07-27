# father

## git subtree 实现一个仓库作为其他仓库的子库


## git subtree的主要命令有：

  `git subtree add   --prefix=<prefix> <commit>
  
  git subtree add   --prefix=<prefix> <repository> <ref>
  
  git subtree pull  --prefix=<prefix> <repository> <ref>
  
  git subtree push  --prefix=<prefix> <repository> <ref>
  
  git subtree merge --prefix=<prefix> <commit>
  
  git subtree split --prefix=<prefix> [OPTIONS] [<commit>]`
  
  
 ### 在父仓库中新增子仓库

  git subtree add --prefix=sub/son https://github.com/readingtfsc/son.git master --squash
  
  --squash参数表示不拉取历史信息，而只生成一条commit信息
  
  
  ### 从源仓库拉取更新
  git subtree pull --prefix=sub/son https://github.com/readingtfsc/son.git master --squash
 
 ### 推送修改到源仓库
  git subtree push --prefix=sub/son https://github.com/readingtfsc/son.git maste


### 简化git subtree命令
我们已经知道了git subtree 的命令的基本用法，但是上述几个命令还是显得有点复杂，特别是子仓库的源仓库地址，特别不方便记忆。
这里我们把子仓库的地址作为一个remote，方便记忆：

git remote add -f son https://github.com/readingtfsc/son.git

然后可以这样来使用git subtree命令：

`git subtree add --prefix=sub/son son master --squash

git subtree pull --prefix=sub/son son master --squash

git subtree push --prefix=sub/son son master`





  
  
  





