---
title: 将 Survivable Branch Appliance 连接到 Lync Server 2013 前端池
description: 将 Survivable 分支设备连接到 Lync Server 2013 前端池。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool
ms:assetid: 3c7ca33f-5295-4d82-9152-41d8bc6f35cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688026(v=OCS.15)
ms:contentKeyID: 49733616
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ef917d3db6a1d653ac716d6c078e1df240fb31d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571658"
---
# <a name="connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool"></a>将 Survivable Branch Appliance 连接到 Lync Server 2013 前端池

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-05_

每个 Survivable 分支设备 (SBA) 都与一个前端池相关联，后者充当 SBA 的备份注册器。 将前端池升级到 Lync Server 2013 时，在升级前端池时，SBA 必须与前端池解除关联。 在升级前端池之后，可以使用前端池 reassociated SBA。 这涉及到使用拓扑生成器删除拓扑中的 SBA，然后将 SBA 重新添加到拓扑生成器。 在从拓扑中删除 SBA 之前，必须将驻留在 SBA 上的用户移至另一个前端池。 将 SBA 添加回拓扑后，可将这些用户移回 SBA。

这些步骤概括如下：

1.  将驻留在 SBA 上的分支用户移动到另一个前端池。

2.  从拓扑中删除 SBA，以将现有的前端池与备份注册器解除关联。

3.  将前端池升级到 Microsoft Lync Server 2013。

4.  将 SBA 添加回拓扑。

5.  将新的前端池与 SBA 作为备份注册器相关联。

6.  将分支用户移回 SBA。

<div>

## <a name="in-this-section"></a>本部分内容

  - [将 Lync Server 2013 Survivable 分支装置分支站点添加到您的拓扑](lync-server-2013-add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology.md)

  - [将 Lync Server 2010 Survivable 分支装置分支站点添加到您的拓扑](lync-server-2013-add-lync-server-2010-survivable-branch-appliance-branch-site-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

