---
title: Lync Server 2013：边缘组件支持的服务器并置
TOCTitle: 边缘组件支持的服务器并置
ms:assetid: 435c4dd8-36af-4b71-9b88-3ffcf0fc5c65
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425934(v=OCS.15)
ms:contentKeyID: 49312679
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中边缘组件支持的服务器并置

 

_**上一次修改主题：** 2012-09-08_

访问边缘服务、Web 会议边缘服务、A/V 边缘服务和 XMPP 代理服务并置在同一台 边缘服务器上。以下服务器提供外部用户访问所需的功能，必须部署为专用服务器：

  - 边缘服务器

  - 控制器（可选）

  - 反向代理

> [!IMPORTANT]
> 反向代理不需要专用于仅为 Lync Server 2013 提供服务。例如，您可以提供服务来发布 Lync Server Web 服务，并同时为另一个与 Lync Server 完全不相关的网站提供已发布的网站。如果在外围网络中已有反向代理服务器来支持其他服务，则可以将其用于 Lync Server 2013。

