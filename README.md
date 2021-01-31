# NaboPi R4S固件，自动编译更新插件和内核版本

使用 SSH远程 GitHub Actions 云编译Openwrt固件
（目前在建，后续开放）

### 默认编译

- 用户名：root 密码：password 管理IP：192.168.2.1
- 已开启SSH，可自定义选择编译，自动生成`.config`
# 在线升级

目前在建设中~

# 离线升级

## 需要的软件
WinScp 下载链接 https://wws.lanzous.com/ivi2ql56mod

# 请将需要使用的固件只支持squashfs固件格式，是ext4格式请不要使用此方法（img格式，不是压缩包！压缩包请先解压成img）存在本地你记得住的一个文件夹

首先，打开WinScp。登陆教程自己~~百度~~谷歌，懂？

切换到 /tmp 文件夹。在左边选择img镜像所在路径，拖到tmp文件夹里面。

等待复制完成，就点...返回根目录。

在这里，按下快捷键Shift+Ctrl+T，输入以下代码。

注意，<>内的内容请根据img文件名自行修改

```
sysupgrade tmp/<你的文件名>.img
```

点击执行，稍等几秒会出现一个弹窗。在弹窗中，选择确定。

现在，你可以泡一杯咖啡，等大概三分钟，更新就完成了。而且，与以往不同，你的配置在新固件内会被保留，所以基本不需要设置了。但是，我还是建议你检查一下配置，以防万一。

如果出现各种奇奇怪怪的问题，那么我还是劝你重新卡刷，耗子尾汁，不要搞窝里斗。
 
### (离线升级由[thomaswcy](https://github.com/thomaswcy/op-direct-upgrade "thomaswcy")提供，非常感谢！)

### 提示

在你的存储库介绍中添加一些你构建的固件的元信息（比如固件体系结构和安装的软件包），这样可以节省其他人的时间。

### 版本日志 1.18号

-  待机超10天无法上网,需要重启才解决（已修复）

- 再次增强DHCP稳定性，增加多种协议（已优化） 

- 优化DNS在加载情况下无法启动进后台（已增强） 

- 降级到DDNS版本，最新版有问题（已降级，不清楚没试过） 

- 再次添poeee拔号多种协议（后期提高拔号稳定） 

- 优化部分内核代码重新优化一下 

- 更新rk3399驱动（友善官网提供） 

- 更新网卡驱动 

- 修复了其他小问题

### 版本日志 1.30号

- 增新了ipv6客户端，快速获取ipv6；

- 修复了ipv6情况下节点有时断开，提高上网质量；

- 修复了adguardhome插件无法启动问题，改为Lienol源码仓库的插件；

- 通过本地编译增加了华为拔号仿真（华为开源挖来的）提高任何协议拔号速度。

## 后续更新

