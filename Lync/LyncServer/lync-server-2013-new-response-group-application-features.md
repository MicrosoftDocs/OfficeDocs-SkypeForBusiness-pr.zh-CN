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
ms.openlocfilehash: bddf1f670ef2a0a246100564962b2f69db741186
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755896"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-response-group-application-features-in-lync-server-2013"></a>Lync Server 2013 中新的响应组应用程序功能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-29_

使用 "响应组" 应用程序，您可以将传入呼叫路由和排队给指定人员进行特殊用途，例如客户服务、内部技术支持或部门的常规电话支持。

以下响应组应用程序功能是 Lync Server 2013 中的新增功能：

  - **经理角色**
    
    Lync Server 2013 引入了新的 "响应组管理器" 角色。 现在，响应组有两个管理角色： "响应组管理器" 和 "响应组管理员"。 虽然响应组管理员仍然可以为任何响应组配置任何元素，但管理器只能配置特定元素，而不是其拥有的响应组。
    
    管理模型的这种改进提高了响应组的可伸缩性，尤其是对于大型部署方案。

  - **高可用性**
    
    在 Lync Server 2013 的高可用性的整体配置和部署中，对响应组应用程序的高可用性支持（以 SQL Server 镜像的形式）被启用。 如果为高可用性进行配置，并且失去了与主后端服务器的连接，则使用镜像后端服务器不会影响响应组功能。
    
    无法在整个 Lync Server 2013 高可用性配置之外单独启用或配置对响应组应用程序的 SQL Server 镜像的支持。

  - **灾难恢复**
    
    对响应组应用程序的灾难恢复支持启用为已配对的前端池的配置和部署的一部分，这是整个 Lync Server 2013 灾难恢复配置的一部分。 此外，"响应组导入" 和 "导出" cmdlet 支持将备份池和故障回复进程的故障转移过程转移到主池或新池。 如果主池中出现中断，则响应组可以故障转移到备份池，然后在中断结束时返回到主池或新池。

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

