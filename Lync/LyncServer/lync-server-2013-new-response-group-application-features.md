---
title: Lync Server 2013：新的响应组应用程序功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Response Group application features
ms:assetid: 569544b4-fa97-429b-97e6-568afab6c19b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398373(v=OCS.15)
ms:contentKeyID: 48184196
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2538c6698875a0a96ce4e7dc7a46aa7cb9ed8e1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153562"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-response-group-application-features-in-lync-server-2013"></a>Lync Server 2013 中新的响应组应用程序功能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-29_

通过响应组应用程序，可以按特定用途将传入呼叫路由和排列到指定人员，例如客户服务、内部技术支持或部门的常规电话支持。

以下响应组应用程序功能是 Lync Server 2013 中的新增功能：

  - **Manager 角色**
    
    Lync Server 2013 引入了新的响应组管理器角色。 目前有两个响应组管理角色：响应组管理器和响应组管理员。 虽然响应组管理员仍可以为任何响应组配置任何元素，但管理者只能为其拥有的响应组配置特定元素。
    
    针对管理模型的此改进可提高响应组的可伸缩性，尤其是在大型部署方案中。

  - **高可用性**
    
    以 SQL Server 镜像的形式，对响应组应用程序的高可用性支持作为对 Lync Server 2013 的高可用性的总体配置和部署的一部分进行启用。 如果您配置高可用性但丢失与主后端服务器的连接，则利用镜像后端服务器不会影响响应组功能。
    
    对响应组应用程序的 SQL Server 镜像的支持无法在整个 Lync Server 2013 高可用性配置之外单独启用或配置。

  - **灾难恢复**
    
    响应组应用程序的灾难恢复支持作为成对前端池的配置和部署的一部分启用，这是整个 Lync Server 2013 灾难恢复配置的一部分。 此外，响应组导入和导出 cmdlet 支持故障转移到备份池的过程以及故障回复到主池或新池的过程。 如果主池中出现中断情况，可将响应组故障转移到备份池，然后在中断停止后将响应组故障回复到主池或新池。

<div id="sectionSection0" class="section">

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中规划响应组](lync-server-2013-planning-for-response-groups.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

