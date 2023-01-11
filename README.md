# Nigate

一款支持苹果芯片的Free NTFS for Mac小工具软件。由[homebrew](https://github.com/Homebrew)、[oxfuse](https://osxfuse.github.io)、[ntfs-3g](https://github.com/osxfuse/osxfuse/wiki/NTFS-3G#installation)方案集成整合。

## 使用与个性化演示

[实机视频](https://www.bilibili.com/video/BV1XG4y1f79N)

![Watch the video](https://fastly.jsdelivr.net/gh/hoochanlon/free-mac-ntfs/shashin/example.png)

<details><summary> NTFS个性化 Geek Style </summary>
 
 ##### 需用 `diskutil list` 查看挂载盘ID方可对应操作。

 **重命名**
 
![](https://fastly.jsdelivr.net/gh/hoochanlon/free-mac-ntfs/shashin/rename.png)
 
 
 ```shell
 sudo umount /dev/disk4s2
 ```
 
 ```shell
 sudo ntfslabel /dev/disk4s2 carsh
 ```
 
**格式化**

![](https://fastly.jsdelivr.net/gh/hoochanlon/Free-NTFS-for-Mac/shashin/formatntfs.png)
 
```shell
 sudo diskutil unmount /dev/disk4s1
```
 
```shell
 sudo mkntfs -f /dev/disk4s1
```

</details>

## 快速开始

苹果生态新手还是建议先使用[nigate软件版](https://github.com/hoochanlon/Free-NTFS-for-Mac/releases/download/v1.1/nigate.dmg)。Mac老鸟或IT人士可使用以下任意指令一键起飞。

 shell

 ```
 /bin/bash -c "$(curl -fsSL https://cdn.statically.io/gh/hoochanlon/Free-NTFS-for-Mac/main/nigate.sh)"
 ```

 python

 ```
 python3 -c "$(curl -fsSL https://fastly.jsdelivr.net/gh/hoochanlon/Free-NTFS-for-Mac/nigate.py)"
 ```


## 使用须知

安装homebrew与python3（软件会自动检测依赖环境安装）

```shell
/bin/bash -c "$(curl -fsSL https://gitee.com/ineo6/homebrew-install/raw/master/install.sh)" && brew install python
```

[关闭SIP与“允许任何来源”](http://www.downza.cn/mac/10419030.html)，以及用以下命令解除[苹果对软件迁移安装的门禁](https://blog.csdn.net/Alexander_Wei/article/details/111149103)。

```shell
sudo xattr -d com.apple.quarantine /Applications/nigate.app
```

软件内核扩展未加载问题，[其他问题转，答疑中心，issues#9](https://github.com/hoochanlon/Free-NTFS-for-Mac/issues/9)

 ```shell
 sudo /usr/bin/kmutil unload -b io.macfuse.filesystems.macfuse
 ```

## 进阶技巧

全速热爱中...

 ## 感谢

* [ezntfs](https://github.com/lezgomatt/ezntfs/issues/8#issuecomment-1374428139)
* [kevintao0417](https://github.com/hoochanlon/Free-NTFS-for-Mac/issues/3)

提供的支持与帮助。
