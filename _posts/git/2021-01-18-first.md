---
layout: blog
istop: true
title: "첫 번째 테스팅"
background-image: http://ot1cc1u9t.bkt.clouddn.com/17-7-16/38390376.jpg
date:  2021-01-18 23:45:56
category: git
tags:
- github
- Dev
- sw
---

# 이글은1
어쩌구저쩌구

# 이글은2
어쩌구저쩌구
```
touch .gitignore
```
## 이글은3
```
# 此为注释 – 将被 Git 忽略
 
*.a       # 忽略所有 .a 结尾的文件
!lib.a    # 但 lib.a 除外
/-liberxuesite     # 仅仅忽略项目根目录下的 liberxuesite 文件，不包括 subdir/liberxuesite
liberxue/    # 忽略 liberxue文件夹/ 目录下的所有文件以及文件夹本身
doc/*.txt # 会忽略 doc/notes.txt 但不包括 doc/server/arch.txt
```
## 이글은4

规则很简单，不做过多解释，但是有时候在项目开发过程中，突然心血来潮想把某些目录或文件加入忽略规则，按照上述方法定义后发现并未生效，原因是.gitignore只能忽略那些原来没有被track的文件，如果某些文件已经被纳入了版本管理中，则修改.gitignore是无效的。那么解决方法就是先把本地缓存删除（改变成未track状态），然后再提交：

```
git rm -r --cached .
git add .
git commit -m 'update .gitignore'

```