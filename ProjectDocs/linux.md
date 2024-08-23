# rocky（Linux），挂载yum源

把rocky镜像传入opt目录

mount 镜像 /mnt

cd /etc/yum.repos.d

rm -rf rocky-addons.repo rocky-extras.repo rocky.repo

vi rocky-devel.repo

![图片](https://mmbiz.qpic.cn/mmbiz_jpg/ATXX3o2qelichhfDfbx5TCpWGTBUZGlSS1dBmXxygOibbTl59OfXgXWoia0V3ib19NiclfVINJeHsRwCQIfxsWSbcYQ/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

把其他的删了只留下devel，把gpgcheck=1改成0，enabled=0改成1，注释mirrorlist...

在下面加一行

baseurl=file:///mnt/BaseOS

复制出devel2

baseurl=file:///mnt/AppStream

wq保存退出即可

yum clean all

yum makecache