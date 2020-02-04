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
ms.openlocfilehash: 44111dbdec945e525b1ef54d910e1cf7f3b5a5d0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730342"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-registrar-relationships-in-lync-server-2013"></a>Lync Server 2013 中的备份注册器关系

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-06-28_

除了提供灾难恢复功能外，两个配对的池彼此用作对方的备份注册器。 在 Lync Server 2013 中，前端池之间的备份注册机构关系始终是1:1 和互惠。 这意味着如果 P1 是 P2 的备份，则 P2 必须是 P1 的备份，并且两者都不能是任何其他前端池的备份。 这是 Lync Server 2010 的更改，在这种情况下，前端池备份关系可能是多个。

即使两个前端池之间的备份关系必须是1:1 和对称的，每个前端池也可以是任意数量的 Survivable 分支装置的备份注册机构，就像在 Lync Server 2010 中一样。

请注意，Lync Server 2013 不会将灾难恢复支持扩展到托管在 Survivable 分支设备上的用户。 如果充当 Survivable 分支设备备份的前端池已关闭，则登录到 Survivable 分支设备的用户即使在前端池上的用户故障转移到备份前端池后也会处于复原模式。

</div>

<span> </span>

</div>

</div>

</div>

