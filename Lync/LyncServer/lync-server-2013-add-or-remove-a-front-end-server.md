---
title: Lync Server 2013：添加或删除前端服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add or remove a Front End Server
ms:assetid: ab748733-6bad-4c93-8dda-db8d5271653d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205153(v=OCS.15)
ms:contentKeyID: 48185050
ms.date: 01/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 078c3d8eed34e7fb6fd98d2d7c12014b87a0497b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724012"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-or-remove-a-front-end-server-in-lync-server-2013"></a>Add or remove a Front End Server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2016-01-21_

将前端服务器添加到池中或从池中删除前端服务器时，您需要重新启动池。 若要防止向用户提供任何服务中断，请在添加或删除前端服务器时使用以下过程。

<div>


> [!NOTE]  
> 如果将新服务器添加到池，请将您的新池服务器更新为与池中的现有服务器相同的累积更新级别。



</div>

<div>

## <a name="to-add-or-remove-front-end-servers"></a>添加或删除前端服务器

1.  如果您要删除任何前端服务器，请首先停止与这些服务器的新连接。 为此，您可以使用以下 cmdlet：
    
        Stop-CsWindowsServices -Graceful

2.  当要删除的服务器没有当前会话时，请在这些服务器上停止 Lync Server 服务。

3.  打开拓扑生成器，然后添加或删除必要的服务器。

4.  发布拓扑。

5.  如果池已有两个前端服务器的两个前端服务器，或者从两个以上的服务器到两个服务器，则需要键入以下 cmdlet：
    
        Reset-CsPoolRegistrarState-ResetType FullReset -PoolFqdn <PoolFqdn>
    
    如果池具有三个或更多个服务器，则在键入此 cmdlet 时，至少有三个服务器必须处于运行状态。

6.  重新启动池中的所有前端服务器，一次一个。

</div>

</div>

<span> </span>

</div>

</div>

</div>

