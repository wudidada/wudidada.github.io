---
publish: true
typora: true
categories:
- 文章
- 计算机
tags:
- github
title: github pages使用个人域名
date: 2022-11-12 13:00:03 +0800
author: jusbin
---
github pages默认情况下域名为`<user>.github.io`，可以修改为自己的域名。

## 前置条件
- github pages已经可以通过`github.io`进行访问
- [可选]注册的个人域名申请了ssl证书，以便开启https访问，通常都能申请免费的证书
	- [阿里云域名免费申请ssl证书教程](https://developer.aliyun.com/article/768459)
## github pages配置
- settings中添加自己的域名
- 此时会自动在repo根目录下创建一个名为`CNAME`的文件并提交。但是如果构建来源为github actions，则不会自动创建。
	- 自己创建一个`CNAME`文件，其中的内容填写自己的域名。
	- [**建议**]修改构建来源，让github自动创建，之后再该回去
- 如果个人域名没有ssl证书，则取消`Enforce HTTPS`勾选
  
  ![image-20221112132031586](/assets/image-20221112132031586.png){:height 823, :width 780}
## 修改域名解析

![image-20221112132612660](/assets/image-20221112132612660.png)

增加一条域名解析，类型为`CNAME`，使得相应的域名指向之前的github pages域名。
## 查看是否解析成功

```shell
dig www.jusbin.cn
```

![image-20221112135652423](/assets/image-20221112135652423.png)

能从个人域名解析出github pages的域名，说明一切正常。

剩下的就是静静的等待，github上仍然会显示`improperly configured`，不用管，这是由于dns扩散存在一定的延迟，需要等待一段时间。实测不到一个小时就能通过新的域名访问。
