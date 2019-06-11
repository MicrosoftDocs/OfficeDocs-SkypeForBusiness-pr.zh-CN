---
title: 管理 XMPP 联盟
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrating XMPP federation
ms:assetid: 7368ee8f-a201-4d3a-b4e8-68396b156d4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688093(v=OCS.15)
ms:contentKeyID: 49733692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9764554cf9984ceb35878b87032194a51aec3b7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845211"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-xmpp-federation"></a>管理 XMPP 联盟

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-16_

以前版本的 Office 通信服务器提供了可扩展消息和状态协议 (XMPP) 网关, 可将其部署为单独的服务器角色, 以便允许与 XMPP 部署进行联盟。 在 Lync Server 2013 中, XMPP 功能可以部署为功能。 XMPP 功能安装在两个部分中: 作为在 Lync Server 2013 Edge 服务器上运行的 XMPP 代理, 以及在 Lync Server 2013 前端服务器上运行的 XMPP 网关。

从迁移角度来看, 可以将 Office 通信服务器 2007 R2 用户帐户移动到 Lync Server 2013 池, 并继续使用 Office 通信服务器 2007 R2 XMPP 网关。 仅当未在 Lync Server 2013 中配置 XMPP 联盟合作伙伴时, 才可以这样做。

总而言之, 如果 Office 通信服务器已与 Office 通信服务器 2007 R2 XMPP 网关一起部署, 并且已为旧版 Office 通信服务器 2007 R2 用户启用了 XMPP 联合身份验证, 则将 XMPP 联合迁移到 Lync Server 2013:

1.  部署 Lync Server 2013 池。

2.  部署 Lync Server 2013 Edge 服务器。

3.  将所有用户移至 Lync Server 2013 池。

4.  为 Edge 服务器创建 XMPP 访问策略和证书。

5.  在 Lync Server 2013 中启用 XMPP 联合身份验证。 

6.  将 DNS 条目更新为指向 Lync Server 2013 XMPP 网关。

</div>

<span> </span>

</div>

</div>

</div>

