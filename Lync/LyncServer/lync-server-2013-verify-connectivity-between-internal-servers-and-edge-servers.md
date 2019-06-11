---
title: 验证内部服务器与边缘服务器之间的连接
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify connectivity between internal servers and Edge Servers
ms:assetid: 219f706e-2b8a-46c5-b394-c384240eef50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398292(v=OCS.15)
ms:contentKeyID: 48183602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e3868462036312be97484e41c69b51ae022b57c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845387"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-connectivity-between-internal-servers-and-edge-servers-in-lync-server-2013"></a>在 Lync Server 2013 中验证内部服务器与边缘服务器之间的连接

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-08_

在 Lync Server 2013 中, 可使用单独的验证向导来帮助验证边缘服务器与内部服务器之间的连接。 在 Lync Server 2013 中, 连接的验证是在安装边缘服务器时自动完成的。

你可以通过在中央管理存储所在的内部计算机 (或加入的任何域) 上运行 Windows PowerShell **CsManagementStoreReplicationStatus** cmdlet 来验证配置信息到边缘的复制。安装了 Lync Server 2013 核心组件 (OcsCore) 的计算机。 初始结果可能表明状态为 "False", 而不是 "True" 用于复制。 如果是这样, 请运行**CsManagementStoreReplication** cmdlet 并等待复制完成, 然后再再次运行**Get CsManagementStoreReplicationStatus** 。

你可以单独验证外部用户连接, 包括使用 Office 通信服务器远程连接分析器验证远程用户连接。 有关详细信息, 请参阅[在 Lync Server 2013 中验证外部用户的连接](lync-server-2013-verify-connectivity-for-external-users.md)。

</div>

<span> </span>

</div>

</div>

</div>

