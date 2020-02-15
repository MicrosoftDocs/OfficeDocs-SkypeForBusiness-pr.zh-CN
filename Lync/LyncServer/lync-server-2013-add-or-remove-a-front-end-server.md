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
ms.openlocfilehash: 1a13a7d618b7d7f8883d43e6aed7ac456bb5ab6c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008838"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-or-remove-a-front-end-server-in-lync-server-2013"></a>在 Lync Server 2013 中添加或删除前端服务器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2016-01-21_

将前端服务器添加到池，或者从池中删除前端服务器时，您需要重新启动池。为了防止对用户的服务造成任何中断，在添加或删除前端服务器时，请使用以下过程。

<div>


> [!NOTE]  
> 如果要将新服务器添加到池，请将新的池服务器更新为与池中现有服务器相同的累积更新级别。



</div>

<div>

## <a name="to-add-or-remove-front-end-servers"></a>添加或删除前端服务器

1.  如果要删除任何前端服务器，请首先停止与这些服务器的新连接。为此，您可以使用以下 cmdlet：
    
        Stop-CsWindowsServices -Graceful

2.  当所删除的服务器没有当前会话时，请停止这些服务器上的 Lync Server 服务。

3.  打开拓扑生成器，然后添加或删除所需的服务器。

4.  发布拓扑。

5.  如果池已从两个前端服务器到两个以上，或者从两个以上的服务器到两个以上，则需要键入以下 cmdlet：
    
        Reset-CsPoolRegistrarState-ResetType FullReset -PoolFqdn <PoolFqdn>
    
    如果池具有三个或更多的服务器，则在键入此 cmdlet 时，其中必须至少有三个服务器正在运行。

6.  重新启动池中的所有前端服务器，一次一台。

</div>

</div>

<span> </span>

</div>

</div>

</div>

