## 自由构建OpenWrt

项目特别简单，你只需要修改 【.github/workflows/build.yml】文件里的几处信息，即可实现自由生产。
<br>

1、IMAGEBUILDER_URL：值来自：https://downloads.immortalwrt.org/releases/25.12.1/targets/x86/64/ 在此页面，你直接搜索【.zst】就可以找到这个【imagebuilder】，为什么讲出来，因为方便你们去理解，并且将来这个zst的最新包在哪里，怎么获取。

2、EXTRA_PACKAGES：默认插件包的名字，包是否存在，包名是否合法，可以去 https://mirrors.sjtug.sjtu.edu.cn/immortalwrt/releases/25.12.1/packages/x86_64/luci/ 查，99%的生产失败，都是包名不存在造成的。

3、ROOTFS_PARTSIZE：包磁盘大小，我默认写的1024，也就是包磁盘容量有1G可折腾，根据你们实际情况去修改或不改（够用）。

4、默认网络配置：写上自己的内网地址，不去赘述了。

5、项目的【APK】文件夹里，存放的是一些第三方的插件，比如你需要带上一些immortalwrt不自带的一些插件，可以获取插件，放到这个文件夹里，但是，要清楚，你想放的这个插件.apk是否存在其他依赖，需要把其他依赖.apk都放进来才能顺利生产。这点就需要你们具备一些专业性的常识，就是有些插件就是单独一个.apk即可，有些插件需要几个其他的插件依赖，比如dae它就必须要 vmlinux-btf.apk 这个依赖。

<br>
好了，明白了以上几点，就开始【fork】->【Actions】->【Build】吧。
