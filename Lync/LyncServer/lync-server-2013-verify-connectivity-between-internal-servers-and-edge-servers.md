---
title: 验证内部服务器与边缘服务器之间的连接
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify connectivity between internal servers and Edge Servers
ms:assetid: 219f706e-2b8a-46c5-b394-c384240eef50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398292(v=OCS.15)
ms:contentKeyID: 48183602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8165781f9604b84f5b846ebda8679f9110262b88
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42113305"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-connectivity-between-internal-servers-and-edge-servers-in-lync-server-2013"></a>验证 Lync Server 2013 中的内部服务器与边缘服务器之间的连接

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-08_

在 Lync Server 2013 中，可使用单独的验证向导来帮助验证边缘服务器和内部服务器之间的连接。 在 Lync Server 2013 中，连接的验证是在您安装边缘服务器时自动完成的。

您可以通过在中央管理存储所在的内部计算机上运行 Windows PowerShell **get-csmanagementstorereplicationstatus** cmdlet （或安装了 Lync Server 2013 核心组件（OcsCore）的任何加入域的计算机）来验证配置信息到边缘的复制。 初始结果可能指示复制的状态为“False”而非“True”。 如果是这样，则运行 **Invoke-CsManagementStoreReplication** cmdlet，并在再次运行 **Get-CsManagementStoreReplicationStatus** 前为完成复制留出时间。

可以单独验证外部用户连接，包括使用 Office Communications Server 远程连接分析器验证远程用户连接。 有关详细信息，请参阅[在 Lync Server 2013 中验证外部用户的连接性](lync-server-2013-verify-connectivity-for-external-users.md)。

</div>

<span> </span>

</div>

</div>

</div>

