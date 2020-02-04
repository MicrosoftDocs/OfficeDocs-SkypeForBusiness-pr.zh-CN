---
title: Lync Server 2013：IPv6 的迁移和共存注意事项
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
ms.openlocfilehash: d5785b270aa3070c2b1592112ab4d5ae582e52bc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766023"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-and-coexistence-considerations-for-ipv6-in-lync-server-2013"></a>Lync Server 2013 中 IPv6 的迁移和共存注意事项

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-06-14_

Lync Server 2010 或 Office 通信服务器不支持 IP 版本6（IPv6）。 出于试验目的，你可以测试 Lync Server 2010 和 Lync Server 2013 双重堆栈共存。 我们建议在对任何池启用 IPv6 （双栈网络）之前，将给定中心站点的所有池升级到 Lync Server 2013。 如果您需要为池配置仅 IPv6，则建议您在实验室环境中设置仅 IPv6 以进行测试。

迁移和共存期间支持下列方案：

  - Lync Server 2013、Lync Server 2010 和 Office 通信服务器2007在 IPv4 模式下与 Lync Server 2013 在双堆栈模式下共存的 R2 池。

  - 仅限 IPv6 模式下的 Lync Server 2013 池（如果仅限 IPv6 的池是孤立的池）。

</div>

<span> </span>

</div>

</div>

</div>

