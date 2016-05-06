# git add commit之后的撤销操作 #
## 流程 ##

## 如果进行了add commit 误提交##

![图片](../pictures/git进行add或者commit之后的撤销操作/image001.png)

## 1.我需要进行git  reflog操作找到之前没有进行add操作的log ##
![图片](../pictures/git进行add或者commit之后的撤销操作/image003.png)

## 2.找到相应的没有经过add或者commit操作的版本，使用git reset --mixed 版本号 回退到某个版本，只保留源码，回退commit和index信息 例如git reset --mixed 20fdb3f##
![图片](../pictures/git进行add或者commit之后的撤销操作/image005.png)

##3.此时，重新进行 git status操作 ##
![图片](../pictures/git进行add或者commit之后的撤销操作/image007.png)

##4.你会发现原来git add之后的信息回退到原来的版本，此时可以重新使用 git add进行操作 ##