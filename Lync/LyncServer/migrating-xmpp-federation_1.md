---
title: 迁移 XMPP 联盟
TOCTitle: 迁移 XMPP 联盟
ms:assetid: 7368ee8f-a201-4d3a-b4e8-68396b156d4d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688093(v=OCS.15)
ms:contentKeyID: 49888465
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 迁移 XMPP 联盟

 

_**上一次修改主题：** 2012-10-16_

早期版本的 Office Communications Server 提供了可扩展消息传递和状态协议 (XMPP) 网关，可将该网关部署为单独服务器角色以允许与 XMPP 部署联盟。在 Lync Server 2013 中，XMPP 功能可作为功能部署。XMPP 功能的安装为两部分：作为在 Lync Server 2013 边缘服务器上运行的 XMPP 代理和在 Lync Server 2013 前端服务器上运行的 XMPP 网关。

从迁移的角度来看，可将 Office Communications Server 2007 R2 用户帐户移至 Lync Server 2013 池，并且该帐户可继续使用 Office Communications Server 2007 R2 XMPP 网关。仅当未在 Lync Server 2013 中配置 XMPP 联盟伙伴时可执行此操作。

总而言之，如果为 Office Communications Server 部署了 Office Communications Server 2007 R2 XMPP 网关，并且对旧的 Office Communications Server 2007 R2 用户启用了 XMPP 联盟，则要将 XMPP 联盟迁移到 Lync Server 2013，请执行以下操作：

1.  部署 Lync Server 2013 池。

2.  部署 Lync Server 2013 边缘服务器。

3.  将所有用户移至 Lync Server 2013 池。

4.  为边缘服务器创建 XMPP 访问策略和证书。

5.  在 Lync Server 2013 中启用 XMPP 联盟。

6.  更新 DNS 条目以指向 Lync Server 2013 XMPP 网关。

