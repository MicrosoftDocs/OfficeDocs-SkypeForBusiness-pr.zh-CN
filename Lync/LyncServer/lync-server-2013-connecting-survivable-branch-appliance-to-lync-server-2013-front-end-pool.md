---
title: 将 Survivable Branch Appliance 连接到 Lync Server 2013 前端池
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool
ms:assetid: 3c7ca33f-5295-4d82-9152-41d8bc6f35cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688026(v=OCS.15)
ms:contentKeyID: 49733616
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77d22a71272ae7dd3c426b0439f7a3765ca6848c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837145"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool"></a>将 Survivable Branch Appliance 连接到 Lync Server 2013 前端池

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-05_

每个 Survivable 分支装置 (SBA) 都与一个前端池相关联, 后者充当 SBA 的备份注册机构。 当前端池升级到 Lync Server 2013 时, 在升级前端池时, SBA 必须与前端池解除关联。 升级前端池后, SBA 可以与前端池 reassociated。 这包括从拓扑生成器的拓扑中删除 SBA, 然后再次将 SBA 添加到拓扑生成器。 在从拓扑结构中删除 SBA 之前, 必须将驻留在 SBA 上的用户移动到另一个前端池。 将 SBA 添加回拓扑后, 这些用户可以移回 SBA。

下面总结了这些步骤:

1.  将驻留在 SBA 上的分支用户移到另一个前端池。

2.  从拓扑中删除 SBA, 以将现有的前端池与备份注册机构解除关联。

3.  将前端池升级到 Microsoft Lync Server 2013。

4.  将 SBA 添加回拓扑。

5.  将新的前端池与 SBA 作为备份注册机构相关联。

6.  将分支用户移回 SBA。

<div>

## <a name="in-this-section"></a>本节内容

  - [将 Lync Server 2013 Survivable Branch Appliance 分支站点添加到您的拓扑](lync-server-2013-add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology.md)

  - [将 Lync Server 2010 Survivable Branch Appliance 分支站点添加到您的拓扑](lync-server-2013-add-lync-server-2010-survivable-branch-appliance-branch-site-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

