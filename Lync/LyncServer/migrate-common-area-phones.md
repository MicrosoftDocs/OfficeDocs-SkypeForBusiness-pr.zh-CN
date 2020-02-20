---
title: 迁移公共区域电话
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Common Area Phones
ms:assetid: 31bd26fc-861b-45c6-8221-18df16e575de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688015(v=OCS.15)
ms:contentKeyID: 49733604
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69b34458f9bfc11f25cc204104b43b2b01bb59f0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148921"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-common-area-phones"></a>迁移公共区域电话

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-29_

公共区域电话是最常位于共享工作区或公共区域（例如会议厅、厨房或工厂车间）的 IP 电话。 公用区域电话不需要连接到计算机以提供 Lync Server UC 功能。 将 Lync Server 2010 部署迁移到 Lync Server 2013 之后，您还必须迁移与旧版公用区域电话关联的 contact 对象。 使用 Lync Server 命令行管理程序，将首先检索与 Lync Server 2010 公共区域电话关联的所有 contact 对象，然后将这些对象移到 Lync Server 2013 池。

**迁移公共区域电话**

1.  在 Lync Server 2013 前端服务器中，打开 Lync Server 命令行管理程序。

2.  从命令行键入：
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net

3.  若要验证是否已将所有 contact 对象移至 Lync Server 2013 池，请在 Lync Server 命令行管理程序中键入以下命令：
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
    
    验证所有 contact 对象现在是否与 Lync Server 2013 池相关联。

</div>

<span> </span>

</div>

</div>

</div>

