# 目标：本地有个测试分支，弗吉利亚也有个测试分支，将远程的分支拉下来，和本地合并再提交

## 添加新远程仓库
git remote add us-east-1-codecommit https://git-codecommit.ap-southeast-1.amazonaws.com/v1/repos/xxx

## 拉取远程分支
git fetch us-east-1-codecommit test:us-east-1-codecommit-test

## 切换到本地的test分支
git checkout test

## 将弗吉利亚test分支合并到本地的test分支
git merge us-east-1-codecommit-test

## 提交分支
git commit -m "xxx"

## push分支
git push
