---
title: Lync Server 2013 备份注册器关系
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup Registrar relationships
ms:assetid: 7e078271-84b9-4666-989c-c4507a0cdf4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205033(v=OCS.15)
ms:contentKeyID: 48184631
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2b7dbf410aaf5ab6bedd322d018abab76a8324e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-registrar-relationships-in-lync-server-2013"></a>Lync Server 2013 中的备份注册器关系

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-06-28_

除了提供灾难恢复功能外，两个配对的池彼此用作对方的备份注册器。 在 Lync Server 2013 中，前端池之间的备份注册器关系始终为1:1 和互惠。 这意味着，如果 P1 是 P2 的备份，则 P2 必须为 P1 的备份，两者均不能成为任何其他前端池的备份。 这是 Lync Server 2010 的更改，在这种情况下，前端池备份关系可能是多到一。

尽管两个前端池之间的备份关系必须为1:1 和对称关系，但每个前端池仍可以是任意数量的 Survivable 分支设备的备份注册器，就像在 Lync Server 2010 中一样。

请注意，Lync Server 2013 不会将灾难恢复支持扩展到驻留在 Survivable 分支设备上的用户。 如果前端池用作 Survivable 分支设备的备份，则登录到 Survivable 分支设备的用户将进入恢复模式，即使在前端池上驻留的用户故障转移到备份前端池之后也是如此。

</div>

<span> </span>

</div>

</div>

</div>

