
# ArmSom-SDK 发布
ArmSom发布的产品都会有配套的linux和Android版本的SDK，默认存放在百度网盘里面，这里以armsom-cm5io为例来介绍如何获取SDK以及编译固件

## 获取SDK
点击进入链接: [github](https://github.com/ArmSoM/rk3576-andriod-sdk/releases/tag/rk3576_Android14RKR6)
将所有分区压缩包下载至pc端

## 解压SDK
件分区压缩包放在同一目录下，执行下面命令解压：
```bash
cat rk3576_android14.tar.bz2.a* | tar xj
cd rk3576_android14
```

## 配置产品SDK
上述SDK解压完成之后可以看到git提交记录：

这份SDK是RK3576通用的代码，可以针对sige5和cm5io构建出固件，在上述的固件链接中存放了关于cm5io的补丁，执行命令合并它
```bash
git am /path/to/your/patches/*.patch
```

## 编译SDK
拿到SDK之后按照下面的操作编译：

```
source build/envsetup.sh

lunch

./build.sh -AUKup
```

执行完lunch之后选择cm5io的userdebug版本


## 编译问题
拿到SDK之后按照操作编译可能会遇到问题，可以在[论坛](https://forum.armsom.org/tag/sdk)提问或者查找已知问题


Linux系统的SDK操作可以参考armsom发布的博客：
https://blog.csdn.net/nb124667390/category_12589795.html
