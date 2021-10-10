# github使用指北

## 1. 拷贝一个 Git 仓库到本地

参考教程 https://www.runoob.com/git/git-clone.html

```
git clone [url]
```

## 2. 上传代码到git

参考博客 https://blog.csdn.net/ai1362425349/article/details/82119889

```
git init
git remote add origin [url]
git pull origin master
## 加入需要上传的代码
git add .
git commit -m "First Upload"
## 如果是第一次上传就用下面代码，如果不是就用  git push origin main
git push -u origin main
```

📢上传时要注意自己上传的目标分支，要注意区分main和master

参考博客 https://blog.csdn.net/m0_46419510/article/details/112543544

```
git push -u origin [分支名]
```

### 报错解决❌→✅

#### <u>报错1❌</u>

```
git fatal: 远程 origin 已经存在
```

需要重新添加远程配置

参考博客 https://www.cnblogs.com/leinuo2016/p/6547818.html

此时只需要将远程配置删除，重新添加即可；

```
git remote rm origin
git remote add origin [url]
```

#### <u>报错2❌</u>

```
git pull "fatal: 拒绝合并无关的历史"
```

参考博客 https://blog.csdn.net/xidianzxm/article/details/106369818

在pull 时候, 添加–allow-unrelated-histories参数 即可

```
git pull origin master --allow-unrelated-histories
```

#### <u>报错3❌</u>

```
remote: Support for password authentication was removed on August 13, 2021. Please use a personal access token instead.
```

需要生成自己的token来作为密码输入

参考博客 https://blog.csdn.net/weixin_41010198/article/details/119698015

以下是我的token ，到时作为密码粘贴即可

```
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
```

📢注意Username是输入的是github上的邮箱账而非ID账号

参考博客 https://www.cnblogs.com/xieqijiang/p/12420276.html

#### <u>报错4❌</u>

```
error: 源引用规格 main 没有匹配
error: 推送一些引用到 ‘https://github.com/***.git’ 失败
```

需要修改分支名称

参考教程 https://www.runoob.com/git/git-branch.html

参考博客 https://blog.csdn.net/songyuc/article/details/115251254

```
## 列出当前分支
git branch
## 修改当前分支名臣
git branch -m <name>
## 列出当前分支
git branch
## 例如 ：通过调试我们发现当前分支名称是master，所以需要先将当前分支重命名为main，与准备同步的远程repo的名称一致
git branch -m main
## 然后就可以进行git pull和push操作了
```