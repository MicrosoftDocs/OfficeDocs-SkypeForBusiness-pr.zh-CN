---
title: 管理 XMPP 联盟
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating XMPP federation
ms:assetid: b8d2b4b9-d0ed-4b48-820a-2c257fbdd2fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721861(v=OCS.15)
ms:contentKeyID: 49733794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b72dabd60ea42a84fcf9b15d1d739bc063ddf1c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762870"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-xmpp-federation"></a>管理 XMPP 联盟

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-19_

以前版本的 Lync Server 和 Office 通信服务器提供了可扩展消息和状态协议（XMPP）网关，可将其部署为单独的服务器角色，以允许与 XMPP 部署进行联盟。 在 Lync Server 2013 中，XMPP 功能可以部署为功能。 XMPP 功能安装在两个部分中：作为在 Lync Server 2013 Edge 服务器上运行的 XMPP 代理，以及在 Lync Server 2013 前端服务器上运行的 XMPP 网关。

从迁移的角度来看，Lync 服务器用户帐户可以移到 Lync Server 2013 池，并继续使用旧版 XMPP 网关。 仅当未在 Lync Server 2013 中配置 XMPP 联盟合作伙伴时，才可以这样做。

总而言之，如果已部署 Lync Server 2010 的 Office 通信服务器 2007 R2 XMPP 网关，并且 XMPP 联盟已针对旧版 Lync Server 2010 用户启用，则要将 XMPP 联合迁移到 Lync Server 2013，请执行以下操作：

1.  部署 Lync Server 2013 池。

2.  部署 Lync Server 2013 Edge 服务器。

3.  将所有用户移到 Lync Server 2013 池

4.  为 Edge 服务器创建 XMPP 访问策略和证书。

5.  在 Lync Server 2013 中启用 XMPP 联合身份验证。 

6.  将 DNS 条目更新为指向 Lync Server 2013 XMPP 网关。

</div>

<span> </span>

</div>

</div>

</div>

