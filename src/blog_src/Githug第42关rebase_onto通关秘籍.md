[Githug](https://github.com/Gazler/githug)是一个用来了解、熟悉Git的一个非常好的游戏。

目前网站上收录的都是之前只有55关的解题方法，没有新增的rebase_onto这一关的内容。现在Githug一共有56关。现将新增的42关的解答内容更新如下：

第42关的题目如下:
```
Name: rebase_onto
Level: 41
Difficulty: **

You have created your branch from `wrong_branch` and already made some commits, and you realise that you needed to create your branch from `master`. Rebase your commits onto `master` branch so that you don't have `wrong_branch` commits.
```

通过查找，在git rebase中有以下用法：
```
Here is how you would transplant a topic branch based on one branch to another, to pretend that you forked the topic
       branch from the latter branch, using rebase --onto.

       First let's assume your topic is based on branch next. For example, a feature developed in topic depends on some
       functionality which is found in next.

               o---o---o---o---o  master
                    \
                     o---o---o---o---o  next
                                      \
                                       o---o---o  topic

       We want to make topic forked from branch master; for example, because the functionality on which topic depends was
       merged into the more stable master branch. We want our tree to look like this:

               o---o---o---o---o  master
                   |            \
                   |             o'--o'--o'  topic
                    \
                     o---o---o---o---o  next

       We can get this using the following command:

           git rebase --onto master next topic
```

所以，第42关的通关方法如下：
```
 git rebase --onto master wrong_branch readme-update
```

祝通关顺利！

[!https://github.com/sahadev/blog/blob/master/src/image_src/tsinghua.jpg]
