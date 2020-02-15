---
title: Lync Server 2013： IPv6 的迁移和共存注意事项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration and coexistence considerations for IPv6
ms:assetid: 8c769c4f-c8a9-4cbf-9080-beee3be9848a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205068(v=OCS.15)
ms:contentKeyID: 48184751
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f4a042089c0961eb8ea8313b78bbfcafa72c999
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033341"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-and-coexistence-considerations-for-ipv6-in-lync-server-2013"></a>Lync Server 2013 中 IPv6 的迁移和共存注意事项

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-06-14_

Lync Server 2010 或 Office 通信服务器上不支持 IP 版本6（IPv6）。 出于试验目的，您可以测试 Lync Server 2010 和 Lync Server 2013 双堆栈共存。 我们建议将给定中央站点的所有池升级到 Lync Server 2013，然后再对任何池启用 IPv6 （双堆栈网络）。 如果您需要为池配置仅 IPv6，则建议您在实验室环境中设置仅 IPv6 以进行测试。

迁移和共存期间支持下列方案：

  - Lync Server 2013、Lync Server 2010 和 Office 通信2007服务器在 IPv4 模式下与 Lync Server 2013 共存在双堆栈模式中。

  - 仅 IPv6 模式下的 Lync Server 2013 池（如果仅 IPv6 池是孤立的）。

</div>

<span> </span>

</div>

</div>

</div>

