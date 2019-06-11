---
title: 管理集中式日志记录服务配置设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing the Centralized Logging Service configuration settings
ms:assetid: f455c3aa-0061-413d-bdfb-a3e78f82723d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721938(v=OCS.15)
ms:contentKeyID: 49733875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1ce13f34a5a48c80c1f825e225a20c96ebfa2db
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827737"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-the-centralized-logging-service-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中管理集中式日志记录服务配置设置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-11-01_

集中式日志记录服务由由集中日志记录服务控制器 (CLSController) 创建并使用的设置和参数进行控制和配置, 以便向单个计算机的集中式日志记录服务代理发送命令 (CLSAgent). 代理将处理发送给它的命令和 (在启动命令的情况下) 使用方案、提供程序、日志大小、跟踪持续时间和标志的配置, 以根据所提供的配置信息开始收集跟踪日志。

<div>


> [!IMPORTANT]
> 并非所有针对集中式日志记录服务列出的 Windows PowerShell cmdlet 均可用于 Lync Server 2013 本地部署。 虽然它们看起来很有效, 但以下 cmdlet 并非设计为在 Lync Server 2013 本地部署中运行: 
> <UL>
> <LI>
> <P><STRONG>CsClsRegion cmdlet:</STRONG><A href="https://technet.microsoft.com/en-us/library/JJ204879(v=OCS.15)">CsClsRegion</A>、 <A href="https://technet.microsoft.com/en-us/library/JJ204746(v=OCS.15)">Set-CsClsRegion</A>、 <A href="https://technet.microsoft.com/en-us/library/JJ204658(v=OCS.15)">New-CsClsRegion</A>和<A href="https://technet.microsoft.com/en-us/library/JJ204971(v=OCS.15)">Remove-CsClsRegion</A>。</P>
> <LI>
> <P><STRONG>CsClsSearchTerm cmdlet:</STRONG><A href="https://technet.microsoft.com/en-us/library/JJ205061(v=OCS.15)">CsClsSearchTerm</A>和<A href="https://technet.microsoft.com/en-us/library/JJ204911(v=OCS.15)">Set-CsClsSearchTerm</A>。</P>
> <LI>
> <P><STRONG>CsClsSecurityGroup cmdlet:</STRONG><A href="https://technet.microsoft.com/en-us/library/JJ205285(v=OCS.15)">CsClsSecurityGroup</A>、 <A href="https://technet.microsoft.com/en-us/library/JJ204700(v=OCS.15)">Set-CsClsSecurityGroup</A>、 <A href="https://technet.microsoft.com/en-us/library/JJ205359(v=OCS.15)">New-CsClsSecurityGroup</A>和<A href="https://technet.microsoft.com/en-us/library/JJ204958(v=OCS.15)">Remove-CsClsSecurityGroup</A>。</P></LI></UL>这些 cmdlet 中定义的设置不会妨碍或导致任何不利行为, 但它们专用于 Microsoft Office 365, 并且不会在本地部署中产生预期的结果。 这并不是说在内部部署中没有使用这些 cmdlet，而是其使用是一个更高级的主题，在本文档中没有概述。



</div>

<div>

## <a name="in-this-section"></a>本节内容

本部分中的主题定义集中式日志记录服务的配置选项、参数和设置。 以下主题介绍了如何配置集中式日志记录服务、如何检索配置设置、方案的创建、用于集中式日志记录服务的安全组的管理、搜索以及其他内容。

  - [在 Lync Server 2013 中管理计算机、站点和全局集中日志记录服务配置](lync-server-2013-managing-computer-site-and-global-centralized-logging-service-configuration.md)

  - [在 Lync Server 2013 中配置集中式日志记录服务的提供商](lync-server-2013-configuring-providers-for-centralized-logging-service.md)

  - [在 Lync Server 2013 中配置集中式日志记录服务的方案](lync-server-2013-configuring-scenarios-for-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的集中式日志记录服务概述](lync-server-2013-overview-of-the-centralized-logging-service.md)  
[Lync Server 2013 中的集中式日志记录 cmdlet](lync-server-2013-centralized-logging-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

