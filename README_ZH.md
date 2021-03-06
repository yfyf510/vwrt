# vwrt

[1]: https://img.shields.io/badge/license-MIT-brightgreen.svg?style=plastic
[2]: /LICENSE
[3]: https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=plastic
[4]: https://github.com/zhaojh329/vwrt/pulls
[5]: https://img.shields.io/badge/Issues-welcome-brightgreen.svg?style=plastic
[6]: https://github.com/zhaojh329/vwrt/issues/new

[![license][1]][2]
[![PRs Welcome][3]][4]
[![Issue Welcome][5]][6]

[vue.js]: https://github.com/vuejs/vue
[iview]: https://github.com/iview/iview
[LuCI2]: https://git.openwrt.org/?p=project/luci2/ui.git
[ubus]: https://wiki.openwrt.org/doc/techref/ubus
[uhttpd-mod-ubus]: https://wiki.openwrt.org/doc/techref/ubus#access_to_ubus_over_http

![](/screen-be6656a.gif)

OpenWrt后台管理界面，使用[vue.js]和[iview]实现，灵感来自于[LuCI2]。

vwrt通过ubus和OpenWrt子系统通信。通过[ubus]存取各种系统数据(通过[uhttpd-mod-ubus]提供基于HTTP的接口API)。

# 依赖

构建vwrt需要以下软件包

* Node.js >= 8.11

# 如何使用
在"feeds.conf.default"里面添加新的feed:
    
    src-git vwrt https://gitee.com/zhaojh329/vwrt.git

安装vwrt软件包:
    
    ./scripts/feeds update vwrt
    ./scripts/feeds install -a -p vwrt

在menuconfig里面选择vwrt软件包然后编译新固件.

    vwrt  --->
        <*>  vwrt-ui-base..................... VWRT UI

另外，你可以使用已经安装在主机中的nodejs(Nodejs仅仅用来编译代码)

[通过包过滤器安装Node.js](https://nodejs.org/en/download/package-manager/)

    <*> vwrt-ui-core
        Configuration  --->
            [*] Use existing nodejs installation on the host system

# 如何开发和调试
首先克隆代码到你的系统，然后执行如下操作

	cd vwrt/vwrt-ui-core/src

然后根据自己的环境修改配置。您可能需要修改 proxy。

	vi vue.config.js

然后执行如下命令运行调试服务器

	npm run serve

# [捐赠](https://gitee.com/zhaojh329/vwrt#project-donate-overview)

# 贡献代码
如果你想帮助[vwrt](https://github.com/zhaojh329/vwrt) 变得更好，请参考
[CONTRIBUTING_ZH.md](/CONTRIBUTING_ZH.md)。

# 技术交流
QQ群：153530783
