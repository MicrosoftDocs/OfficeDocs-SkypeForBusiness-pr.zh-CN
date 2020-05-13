---
title: 管理集中日志记录服务配置设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing the Centralized Logging Service configuration settings
ms:assetid: f455c3aa-0061-413d-bdfb-a3e78f82723d
ms:mtpsurl: https://technet.microsoft.com/library/JJ721938(v=OCS.15)
ms:contentKeyID: 49733875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c6e156fbae7147b650c7360394cbd0d277b937b
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221596"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-the-centralized-logging-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="b4037-102">在 Lync Server 2013 中管理集中日志记录服务配置设置</span><span class="sxs-lookup"><span data-stu-id="b4037-102">Managing the Centralized Logging Service configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4037-103">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="b4037-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="b4037-104">集中日志记录服务由集中日志记录服务控制器（CLSController）创建和使用的设置和参数进行控制和配置，以将命令发送到单个计算机的集中日志记录服务代理（CLSAgent）。</span><span class="sxs-lookup"><span data-stu-id="b4037-104">The Centralized Logging Service is controlled and configured by settings and parameters that are created and used by the Centralized Logging Service Controller (CLSController) to send commands to the individual computer’s Centralized Logging Service Agent (CLSAgent).</span></span> <span data-ttu-id="b4037-105">该代理处理发送给它的命令，并（如果是启动命令）根据提供的配置信息使用方案、提供程序、日志大小、跟踪持续时间和标志的配置开始收集跟踪日志。</span><span class="sxs-lookup"><span data-stu-id="b4037-105">The agent processes the commands that are sent to it and (in the case of a Start command) uses the configuration of the scenarios, providers, log size, trace duration, and flags to begin collecting trace logs according to the configuration information provided.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="b4037-106">并不是所有列出的集中日志记录服务的 Windows PowerShell cmdlet 都可用于 Lync Server 2013 本地部署。</span><span class="sxs-lookup"><span data-stu-id="b4037-106">Not all Windows PowerShell cmdlets listed for the Centralized Logging Service are intended for use with Lync Server 2013 on-premises deployments.</span></span> <span data-ttu-id="b4037-107">虽然看起来似乎可行，但以下 cmdlet 不适合在 Lync Server 2013 本地部署中运行：</span><span class="sxs-lookup"><span data-stu-id="b4037-107">Although they may appear to work, the following cmdlets are not designed to function with Lync Server 2013 on-premises deployments:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="b4037-108"><STRONG>CsClsRegion cmdlet：</STRONG> <A href="https://technet.microsoft.com/library/JJ204879(v=OCS.15)">Get-CsClsRegion</A>、<A href="https://technet.microsoft.com/library/JJ204746(v=OCS.15)">Set-CsClsRegion</A>、<A href="https://technet.microsoft.com/library/JJ204658(v=OCS.15)">New-CsClsRegion</A> 和 <A href="https://technet.microsoft.com/library/JJ204971(v=OCS.15)">Remove-CsClsRegion</A>。</span><span class="sxs-lookup"><span data-stu-id="b4037-108"><STRONG>CsClsRegion cmdlets:</STRONG> <A href="https://technet.microsoft.com/library/JJ204879(v=OCS.15)">Get-CsClsRegion</A>, <A href="https://technet.microsoft.com/library/JJ204746(v=OCS.15)">Set-CsClsRegion</A>, <A href="https://technet.microsoft.com/library/JJ204658(v=OCS.15)">New-CsClsRegion</A>, and <A href="https://technet.microsoft.com/library/JJ204971(v=OCS.15)">Remove-CsClsRegion</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="b4037-109"><STRONG>CsClsSearchTerm cmdlet：</STRONG> <A href="https://technet.microsoft.com/library/JJ205061(v=OCS.15)">Get-CsClsSearchTerm</A> 和 <A href="https://technet.microsoft.com/library/JJ204911(v=OCS.15)">Set-CsClsSearchTerm</A>。</span><span class="sxs-lookup"><span data-stu-id="b4037-109"><STRONG>CsClsSearchTerm cmdlets:</STRONG> <A href="https://technet.microsoft.com/library/JJ205061(v=OCS.15)">Get-CsClsSearchTerm</A> and <A href="https://technet.microsoft.com/library/JJ204911(v=OCS.15)">Set-CsClsSearchTerm</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="b4037-110"><STRONG>CsClsSecurityGroup cmdlet：</STRONG> <A href="https://technet.microsoft.com/library/JJ205285(v=OCS.15)">Get-CsClsSecurityGroup</A>、<A href="https://technet.microsoft.com/library/JJ204700(v=OCS.15)">Set-CsClsSecurityGroup</A>、<A href="https://technet.microsoft.com/library/JJ205359(v=OCS.15)">New-CsClsSecurityGroup</A> 和 <A href="https://technet.microsoft.com/library/JJ204958(v=OCS.15)">Remove-CsClsSecurityGroup</A>。</span><span class="sxs-lookup"><span data-stu-id="b4037-110"><STRONG>CsClsSecurityGroup cmdlets:</STRONG> <A href="https://technet.microsoft.com/library/JJ205285(v=OCS.15)">Get-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/library/JJ204700(v=OCS.15)">Set-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/library/JJ205359(v=OCS.15)">New-CsClsSecurityGroup</A>, and <A href="https://technet.microsoft.com/library/JJ204958(v=OCS.15)">Remove-CsClsSecurityGroup</A>.</span></span></P></LI></UL><span data-ttu-id="b4037-111">这些 cmdlet 中定义的设置不会妨碍或导致任何不利行为，但它们设计为与 Microsoft 365 配合使用，并且不会在本地部署中生成预期结果。</span><span class="sxs-lookup"><span data-stu-id="b4037-111">The settings defined in these cmdlets will not hinder or cause any adverse behavior, but they are designed for use with Microsoft 365 and will not yield the expected results in on-premises deployments.</span></span> <span data-ttu-id="b4037-112">这并不是说在内部部署中没有使用这些 cmdlet，而是其使用是一个更高级的主题，在本文档中没有概述。</span><span class="sxs-lookup"><span data-stu-id="b4037-112">This is not to say that there is no use for these cmdlets in on-premises deployments, but their use is a more advanced topic that is not covered in this documentation.</span></span>


</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b4037-113">本部分内容</span><span class="sxs-lookup"><span data-stu-id="b4037-113">In This Section</span></span>

<span data-ttu-id="b4037-114">本节中的主题定义了集中日志记录服务的配置选项、参数和设置。</span><span class="sxs-lookup"><span data-stu-id="b4037-114">The topics in this section define the configuration options, parameters, and settings for the Centralized Logging Service.</span></span> <span data-ttu-id="b4037-115">以下主题介绍了有关如何配置集中日志记录服务、如何检索配置设置、应用场景创建、安全组管理、集中日志记录服务、搜索等主题的信息。</span><span class="sxs-lookup"><span data-stu-id="b4037-115">Information about how to configure the Centralized Logging Service, how to retrieve the configuration settings, creation of scenarios, management of security groups for Centralized Logging Service, searching, and more is contained in the following topics.</span></span>

  - [<span data-ttu-id="b4037-116">在 Lync Server 2013 中管理计算机、站点和全局集中日志记录服务配置</span><span class="sxs-lookup"><span data-stu-id="b4037-116">Managing computer, site and global Centralized Logging Service configuration in Lync Server 2013</span></span>](lync-server-2013-managing-computer-site-and-global-centralized-logging-service-configuration.md)

  - [<span data-ttu-id="b4037-117">在 Lync Server 2013 中配置集中日志记录服务的提供程序</span><span class="sxs-lookup"><span data-stu-id="b4037-117">Configuring providers for Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-configuring-providers-for-centralized-logging-service.md)

  - [<span data-ttu-id="b4037-118">在 Lync Server 2013 中配置集中日志记录服务的方案</span><span class="sxs-lookup"><span data-stu-id="b4037-118">Configuring scenarios for the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-configuring-scenarios-for-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b4037-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b4037-119">See Also</span></span>


[<span data-ttu-id="b4037-120">Lync Server 2013 中的集中日志记录服务概述</span><span class="sxs-lookup"><span data-stu-id="b4037-120">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  
[<span data-ttu-id="b4037-121">Lync Server 2013 中的集中日志记录 cmdlet</span><span class="sxs-lookup"><span data-stu-id="b4037-121">Centralized Logging cmdlets in Lync Server 2013</span></span>](lync-server-2013-centralized-logging-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

