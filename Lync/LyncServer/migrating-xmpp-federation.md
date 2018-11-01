---
title: 管理 XMPP 联盟
TOCTitle: 管理 XMPP 联盟
ms:assetid: b8d2b4b9-d0ed-4b48-820a-2c257fbdd2fb
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721861(v=OCS.15)
ms:contentKeyID: 49888578
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 管理 XMPP 联盟

 

_**上一次修改主题：** 2012-10-19_

Lync Server 和 Office Communications Server 的以前版本提供了可扩展消息传递和状态协议 (XMPP) 网关，该网关可作为单独的服务器角色进行部署，以允许与 XMPP 部署进行联盟。在 Lync Server 2013 中，可以将 XMPP 功能作为一项特性进行部署。XMPP 功能分两部分安装：作为在 Lync Server 2013 边缘服务器上运行的 XMPP 代理，以及在 Lync Server 2013 前端服务器上运行的 XMPP 网关。

从迁移的角度来看， Lync Server 用户帐户可以移动到 Lync Server 2013 池，并继续使用旧的 XMPP 网关。仅当在 Lync Server 2013 中没有配置 XMPP 联盟伙伴时，才可以这样做。

总而言之，如果为 Lync Server 2010 部署了 Office Communications Server 2007 R2 XMPP 网关，并且对旧的 Lync Server 2010 用户启用了 XMPP 联盟，则要将 XMPP 联盟迁移到 Lync Server 2013，请执行以下操作：

1.  部署 Lync Server 2013 池。

2.  部署 Lync Server 2013 边缘服务器。

3.  将所有用户移动到 Lync Server 2013 池。

4.  为边缘服务器创建 XMPP 访问策略和证书。

5.  在 Lync Server 2013 中启用 XMPP 联盟。

6.  更新 DNS 条目以指向 Lync Server 2013 XMPP 网关。

