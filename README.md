## PHP技术QQ群`174303524`
---
官方博客：[good-partner.github.io](https://good-partner.github.io)

### 环境搭建

1. 参照[jekyll文档](http://jekyllrb.com/docs/installation/)
2. 搭好环境后，cd到代码根目录，执行：
```bash
$ jekyll s
```
3. 打开浏览器访问`http://localhost:4000`即可看到效果。

### 如何同步更新代码？

1. 登陆github，进入fork的代码仓库
2. 发起合并请求，左边选择自己的相应分支，右侧选择organization相应的分支。

![Alt text](/images/2017/0516/update-code.png "更新代码")
3. 发起请求后，页面会出现`Merge pull request`绿色按钮，点击后即可完成更新。

![Alt text](/images/2017/0516/merge-pull.png "接受更新")

### 如何向organization贡献自己的代码

1. fetch自己github上的远程代码，pull更新后开始修改。
2. commit后push到自己的远程github仓库。
2. 发起合并请求，左边选择organization的相应分支，右侧选择自己的相应的分支（同更新相反）。
