---
title: 迁移 XMPP 联合
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating XMPP federation
ms:assetid: 7368ee8f-a201-4d3a-b4e8-68396b156d4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688093(v=OCS.15)
ms:contentKeyID: 49733692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 761b0835eb8c1db84b8b969479ad329e7f75e033
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148791"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-xmpp-federation"></a>迁移 XMPP 联合

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-16_

早期版本的 Office 通信服务器提供了可扩展消息和状态协议（XMPP）网关，可将其作为单独的服务器角色进行部署，以允许与 XMPP 部署进行联盟。 在 Lync Server 2013 中，可以将 XMPP 功能部署为功能。 XMPP 功能安装在两个部分中：作为运行在 Lync Server 2013 边缘服务器上的 XMPP 代理，以及在 Lync Server 2013 前端服务器上运行的 XMPP 网关。

从迁移的角度来看，可以将 Office 通信服务器 2007 R2 用户帐户移动到 Lync Server 2013 池，并继续使用 Office 通信服务器 2007 R2 XMPP 网关。 仅当未在 Lync Server 2013 中配置 XMPP 联盟伙伴时，才可以这样做。

总而言之，如果 Office 通信服务器已部署到 Office 通信服务器 2007 R2 XMPP 网关，并且已为旧版 Office 通信服务器 2007 R2 用户启用 XMPP 联盟，则将 XMPP 联合迁移到 Lync Server 2013：

1.  部署 Lync Server 2013 池。

2.  部署 Lync Server 2013 边缘服务器。

3.  将所有用户移动到 Lync Server 2013 池。

4.  为边缘服务器创建 XMPP 访问策略和证书。

5.  在 Lync Server 2013 中启用 XMPP 联合身份验证。 

6.  将 DNS 条目更新为指向 Lync Server 2013 XMPP 网关。

</div>

<span> </span>

</div>

</div>

</div>

