---
title: Lync Server 2013：为集中日志记录服务配置提供程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring providers for Centralized Logging Service
ms:assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688082(v=OCS.15)
ms:contentKeyID: 49733678
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec5d280d05089c4f1efc4fd8c54ab4841d24621d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534999"
---
# <a name="configuring-providers-for-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="596c6-102">在 Lync Server 2013 中配置集中日志记录服务的提供程序</span><span class="sxs-lookup"><span data-stu-id="596c6-102">Configuring providers for Centralized Logging Service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="596c6-103">_**上次修改的主题：** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="596c6-103">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="596c6-104">集中日志记录服务中 *提供程序* 的概念和配置是最重要的一项。</span><span class="sxs-lookup"><span data-stu-id="596c6-104">The concepts and configuration of *providers* in Centralized Logging Service is one of the most important to grasp.</span></span> <span data-ttu-id="596c6-105">*提供程序*直接映射到 lync server 跟踪模型中的 lync server 服务器角色组件。</span><span class="sxs-lookup"><span data-stu-id="596c6-105">The *providers* map directly to Lync Server server role components in the Lync Server tracing model.</span></span> <span data-ttu-id="596c6-106">提供程序定义要跟踪的 Lync Server 2013 的组件、要收集的邮件的类型、要收集的) 的 (、严重、错误或警告，以及 flags (例如，TF \_ Connection 或 TF settings \_) 。</span><span class="sxs-lookup"><span data-stu-id="596c6-106">The provider defines the components of a Lync Server 2013 that will be traced, the type of messages (for example, fatal, error, or warning) to collect, and the flags (for example, TF\_Connection or TF\_Diag).</span></span> <span data-ttu-id="596c6-107">提供程序是每个 Lync Server 服务器角色中的可跟踪组件。</span><span class="sxs-lookup"><span data-stu-id="596c6-107">Providers are the traceable components in each Lync Server server role.</span></span> <span data-ttu-id="596c6-108">通过使用提供程序，可以定义对组件进行的跟踪的级别和类型（例如，S4、SIPStack、IM 和 Presence）。</span><span class="sxs-lookup"><span data-stu-id="596c6-108">By using providers, you define the level and type of tracing on components (for example, S4, SIPStack, IM and Presence).</span></span> <span data-ttu-id="596c6-109">可在方案中使用所定义的提供程序将针对给定逻辑集合的、满足某个特定问题条件的所有提供程序组合在一起。</span><span class="sxs-lookup"><span data-stu-id="596c6-109">The defined provider is used in a scenario to group all of the providers for a given logical collection that address a specific problem condition.</span></span>

<span data-ttu-id="596c6-110">若要使用 Lync Server 命令行管理程序运行集中式日志记录服务功能，您必须是 CsAdministrator 或 CsServerAdministrator 基于角色的访问控制 (RBAC) 安全组的成员，或者是包含这两个组中任一组的自定义 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="596c6-110">To run the Centralized Logging Service functions using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="596c6-111">若要返回所有基于角色的访问控制的列表 (RBAC) 角色已将此 cmdlet 分配给 (包括您自己创建的任何自定义 RBAC 角色) ，请从 Lync Server 命令行管理程序或 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="596c6-111">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="596c6-112">例如：</span><span class="sxs-lookup"><span data-stu-id="596c6-112">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<span data-ttu-id="596c6-113">本主题的其余部分将重点说明如何定义提供程序、修改提供程序以及提供程序定义为优化您的疑难解答所包含的内容。</span><span class="sxs-lookup"><span data-stu-id="596c6-113">The remainder of this topic focuses on how to define providers, modify a provider and what a provider definition contains to optimize your troubleshooting.</span></span> <span data-ttu-id="596c6-114">有两种方法可以发出集中式日志记录服务命令。</span><span class="sxs-lookup"><span data-stu-id="596c6-114">There are two ways to issue Centralized Logging Service commands.</span></span> <span data-ttu-id="596c6-115">默认情况下，您可以使用目录 C： \\ Program files \\ Common files The \\ Microsoft Lync Server 2013 CLSAgent 中的 CLSController.exe \\ 。</span><span class="sxs-lookup"><span data-stu-id="596c6-115">You can use the CLSController.exe that is located, by default, in the directory C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\CLSAgent.</span></span> <span data-ttu-id="596c6-116">或者，您可以使用 Lync Server 命令行管理程序发出 Windows PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="596c6-116">Or, you can use the Lync Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="596c6-117">重要区别在于，在命令行中使用 CLSController.exe 时，可供选择的可用方案是有限的，在这些方案中，提供程序已被定义且不可更改，但您可以定义日志级别。</span><span class="sxs-lookup"><span data-stu-id="596c6-117">The important distinction is that when you use CLSController.exe at the command line there is a finite selection of scenarios available in which the providers are already defined and are not changeable, but you can define the log level.</span></span> <span data-ttu-id="596c6-118">通过使用 Windows PowerShell，可以定义在日志记录会话中使用的新提供程序，并能够完全控制自己的创建、收集的内容以及它们收集数据的级别。</span><span class="sxs-lookup"><span data-stu-id="596c6-118">By using Windows PowerShell, you can define new providers for use in your logging sessions, and have complete control over their creation, what they collect, and at what level they collect data.</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="596c6-p104">如前所述，提供程序的功能十分强大。但是，方案的功能更为强大，因为方案是对提供程序表示的组件进行设置并执行跟踪所需的所有信息的具体体现。由于方案将包含一组提供程序，因此将运行一个包含几百条用于收集大量信息的命令的批处理文件与在命令行中一次性发出几百条命令相比是不受限制的。</span><span class="sxs-lookup"><span data-stu-id="596c6-p104">As mentioned, providers are very powerful. However, scenarios are more powerful because they contain the embodiment of all information needed to set and execute tracing on the components that the providers represent. With scenarios being a collection of providers, this could be loosely compared to running a batch file containing hundreds of commands to collect a lot of information versus issuing hundreds of commands, one at a time, at the command line.</span></span><BR><span data-ttu-id="596c6-122">集中日志记录服务提供了许多已为您定义的方案，而不是要求您深入了解提供程序的详细信息。</span><span class="sxs-lookup"><span data-stu-id="596c6-122">Instead of requiring you to dig deeply into the details of providers, the Centralized Logging Service provides a number of scenarios that are already defined for you.</span></span> <span data-ttu-id="596c6-123">提供的方案涵盖了绝大多数您可能会遇到的问题。</span><span class="sxs-lookup"><span data-stu-id="596c6-123">The provided scenarios cover the vast majority of possible issues that you will encounter.</span></span> <span data-ttu-id="596c6-124">在极少数情况下，您可能需要创建和定义提供程序并将其分配给方案。</span><span class="sxs-lookup"><span data-stu-id="596c6-124">In rare cases, you may need to create and define providers and assign them to scenarios.</span></span> <span data-ttu-id="596c6-125">强烈建议您先熟悉提供的每个方案，然后再调查有关创建新的提供程序和方案的需求。</span><span class="sxs-lookup"><span data-stu-id="596c6-125">We strongly recommend that you become familiar with each of the scenarios provided before you investigate the need to create new providers and scenarios.</span></span> <span data-ttu-id="596c6-126">虽然您可以通过此处提供的有关创建提供程序的信息来熟悉方案如何使用提供程序元素来收集跟踪信息，但此时不提供有关提供程序本身的详细信息。</span><span class="sxs-lookup"><span data-stu-id="596c6-126">While information about creating providers is found here to familiarize you with how the scenarios use the provider elements to collect trace information, details on the providers themselves are not provided at this time.</span></span>



</div>

<span data-ttu-id="596c6-127">在 [Lync Server 2013 中的集中日志记录服务概述](lync-server-2013-overview-of-the-centralized-logging-service.md)中，定义在方案中使用的提供程序的关键元素包括：</span><span class="sxs-lookup"><span data-stu-id="596c6-127">Introduced in [Overview of the Centralized Logging Service in Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), the key elements of defining a provider for use in a scenario are:</span></span>

  - <span data-ttu-id="596c6-128">**提供程序**    如果您熟悉 OCSLogger，则提供程序是您选择的组件，用于告诉 OCSLogger 跟踪引擎应从什么方面收集日志。</span><span class="sxs-lookup"><span data-stu-id="596c6-128">**Providers**   If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="596c6-129">提供程序是一些相同的组件，在许多情况下，它们的名称与 OCSLogger 中组件的名称相同。</span><span class="sxs-lookup"><span data-stu-id="596c6-129">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="596c6-130">如果您不熟悉 OCSLogger，则提供程序是集中式日志记录服务可从中收集日志的特定于服务器角色的组件。</span><span class="sxs-lookup"><span data-stu-id="596c6-130">If you are not familiar with OCSLogger, providers are server-role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="596c6-131">在集中日志记录服务的情况下，CLSAgent 是集中日志记录服务的体系结构部分，该组件将跟踪您在提供程序配置中定义的组件。</span><span class="sxs-lookup"><span data-stu-id="596c6-131">In the case of the Centralized Logging Service, the CLSAgent is the architectural part of the Centralized Logging Service that is doing the tracing of the components that you define in the providers configuration.</span></span>

  - <span data-ttu-id="596c6-132">**日志记录级别**    OCSLogger 提供了选择收集的数据的多个级别的详细信息的选项。</span><span class="sxs-lookup"><span data-stu-id="596c6-132">**Logging levels**   OCSLogger provided the option to choose a number of levels of detail for the data collected.</span></span> <span data-ttu-id="596c6-133">此功能是集中日志记录服务和方案不可或缺的一部分，由 **Type** 参数定义。</span><span class="sxs-lookup"><span data-stu-id="596c6-133">This feature is an integral part of the Centralized Logging Service and scenarios, and is defined by the **Type** parameter.</span></span> <span data-ttu-id="596c6-134">您可以选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="596c6-134">You can choose from the following:</span></span>
    
      - <span data-ttu-id="596c6-135">**所有**    将类型为致命、错误、警告和信息的跟踪消息收集到定义的提供程序的日志中。</span><span class="sxs-lookup"><span data-stu-id="596c6-135">**All**   Collects trace messages of type fatal, error, warning, and info to the log for the defined provider.</span></span>
    
      - <span data-ttu-id="596c6-136">**致命**    仅收集指示定义的提供程序发生故障的跟踪消息。</span><span class="sxs-lookup"><span data-stu-id="596c6-136">**Fatal**   Collects only the trace messages that indicate a failure for the defined provider.</span></span>
    
      - <span data-ttu-id="596c6-137">**错误**    仅收集指示定义的提供程序的错误以及致命消息的跟踪消息。</span><span class="sxs-lookup"><span data-stu-id="596c6-137">**Error**   Collects only the trace messages that indicate an error for the defined provider, plus fatal messages.</span></span>
    
      - <span data-ttu-id="596c6-138">**警告**    仅收集指示定义的提供程序的警告的跟踪消息，以及致命错误和错误消息。</span><span class="sxs-lookup"><span data-stu-id="596c6-138">**Warning**   Collects only the trace messages that indicate a warning for the defined provider, plus fatal and error messages.</span></span>
    
      - <span data-ttu-id="596c6-139">**信息**    仅收集指示定义的提供程序的信息性消息的跟踪消息，以及致命错误和警告消息。</span><span class="sxs-lookup"><span data-stu-id="596c6-139">**Info**   Collects only the trace messages that indicate an informational message for the defined provider, plus fatal, error, and warning messages.</span></span>
    
      - <span data-ttu-id="596c6-140">**详细**    收集定义的提供程序的所有类型为致命错误、错误、警告和信息的跟踪消息。</span><span class="sxs-lookup"><span data-stu-id="596c6-140">**Verbose**   Collects all trace messages of type fatal, error, warning and info for the defined provider.</span></span>

  - <span data-ttu-id="596c6-141">**标志**    OCSLogger 提供了选择每个提供程序的标记的选项，这些提供程序定义了可从跟踪文件中检索的信息类型。</span><span class="sxs-lookup"><span data-stu-id="596c6-141">**Flags**   OCSLogger provided the option to choose flags for each provider that defined what type of information you could retrieve from the trace files.</span></span> <span data-ttu-id="596c6-142">可以根据提供程序选择以下标志：</span><span class="sxs-lookup"><span data-stu-id="596c6-142">You can chose the following flags, based on the provider:</span></span>
    
      - <span data-ttu-id="596c6-143">**TF \_连接**     提供与连接相关的日志条目。</span><span class="sxs-lookup"><span data-stu-id="596c6-143">**TF\_Connection**   Provides connection-related log entries.</span></span> <span data-ttu-id="596c6-144">这些日志包括与特定组件建立的连接的相关信息。</span><span class="sxs-lookup"><span data-stu-id="596c6-144">These logs include information about connections established to and from a particular component.</span></span> <span data-ttu-id="596c6-145">这可能还包括大量网络级信息（即针对组件，但不包括连接的概念）。</span><span class="sxs-lookup"><span data-stu-id="596c6-145">This may also include significant network-level information (that is, for components without the concept of a connection).</span></span>
    
      - <span data-ttu-id="596c6-146">**TF \_安全性**     提供与安全性相关的所有事件/日志条目。</span><span class="sxs-lookup"><span data-stu-id="596c6-146">**TF\_Security**   Provides all events/log entries related to security.</span></span> <span data-ttu-id="596c6-147">例如，对于 SipStack，它们是一些安全事件（例如，域验证失败和客户端身份验证/授权失败）。</span><span class="sxs-lookup"><span data-stu-id="596c6-147">For example, for SipStack, these are security events such as domain validation failure, and client authentication/authorization failures.</span></span>
    
      - <span data-ttu-id="596c6-148">**TF \_诊断**     提供可用于诊断或排除组件故障的诊断事件。</span><span class="sxs-lookup"><span data-stu-id="596c6-148">**TF\_Diag**   Provides diagnostics events that you can use to diagnose or troubleshoot the component.</span></span> <span data-ttu-id="596c6-149">例如，对于 SipStack，它们是证书失败或 DNS 警告/错误。</span><span class="sxs-lookup"><span data-stu-id="596c6-149">For example, for SipStack, these are certificate failures, or DNS warnings/errors.</span></span>
    
      - <span data-ttu-id="596c6-150">**TF \_协议**     提供协议消息，如 SIP 和组合的社区编解码器包消息。</span><span class="sxs-lookup"><span data-stu-id="596c6-150">**TF\_Protocol**   Provides protocol messages such as SIP and Combined Community Codec Pack messages.</span></span>
    
      - <span data-ttu-id="596c6-151">**TF \_组件**     可在指定为提供程序的一部分的组件上启用日志记录。</span><span class="sxs-lookup"><span data-stu-id="596c6-151">**TF\_Component**   Enables logging on the components specified as part of the providers.</span></span>
    
      - <span data-ttu-id="596c6-152">**所有**    设置可用于提供程序的所有可用标志。</span><span class="sxs-lookup"><span data-stu-id="596c6-152">**All**   Sets all available flags available for the provider.</span></span>

<div>

## <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a><span data-ttu-id="596c6-153">查看有关现有集中日志记录服务方案提供程序的信息</span><span class="sxs-lookup"><span data-stu-id="596c6-153">To review information about existing Centralized Logging Service scenario providers</span></span>

1.  <span data-ttu-id="596c6-154">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="596c6-154">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="596c6-155">若要查看现有提供程序的配置，请键入：</span><span class="sxs-lookup"><span data-stu-id="596c6-155">To review the configuration of existing providers, type the following:</span></span>
    
        Get-CsClsScenario -Identity <scope and scenario name> 
    
    <span data-ttu-id="596c6-156">例如，若要查看有关全局会议助理的信息，请键入：</span><span class="sxs-lookup"><span data-stu-id="596c6-156">For example, to review information about the global conferencing attendant, type:</span></span>
    
        Get-CsClsScenario -Identity "global/CAA"
    
    <span data-ttu-id="596c6-157">此命令显示具有关联的标志、设置和组件的提供程序的列表。</span><span class="sxs-lookup"><span data-stu-id="596c6-157">The command displays a list of providers with the associated flags, settings, and components.</span></span> <span data-ttu-id="596c6-158">如果显示的信息不足，或者列表对默认 Windows PowerShell 列表格式来说太长，则可以通过定义不同的输出方法来显示其他信息。</span><span class="sxs-lookup"><span data-stu-id="596c6-158">If the information displayed is not enough or the list is too long for the default Windows PowerShell list format, you can display additional information by defining a different output method.</span></span> <span data-ttu-id="596c6-159">为此，请键入：</span><span class="sxs-lookup"><span data-stu-id="596c6-159">To do this, type:</span></span>
    
        Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
    
    <span data-ttu-id="596c6-160">此命令的输出显示用五行格式显示的每个提供程序，以及提供程序名称、日志记录类型、日志记录级别、标志、GUID 和角色（每个提供程序位于一个单独的行上）。</span><span class="sxs-lookup"><span data-stu-id="596c6-160">The output of this command displays each provider displayed in a five line format with the provider name, type of logging, logging level, flags, GUID, and role, each one on a separate line.</span></span>

</div>

<div>

## <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a><span data-ttu-id="596c6-161">定义新的集中日志记录服务方案提供程序</span><span class="sxs-lookup"><span data-stu-id="596c6-161">To define a new Centralized Logging Service scenario provider</span></span>

1.  <span data-ttu-id="596c6-162">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="596c6-162">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="596c6-p113">方案提供程序包含要跟踪的组件、要使用的标志和要收集的详细信息级别。通过键入以下内容可完成此操作：</span><span class="sxs-lookup"><span data-stu-id="596c6-p113">A scenario provider consists of a component to trace, flags to use, and a level of detail to collect. You do this by typing:</span></span>
    
        $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
    
    <span data-ttu-id="596c6-165">例如，定义要从 Lyss 提供程序收集的内容和详细信息级别的跟踪提供程序定义与以下内容类似：</span><span class="sxs-lookup"><span data-stu-id="596c6-165">For example, a trace provider definition that defines what to collect and to what level of detail from the Lyss provider looks like the following:</span></span>
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"

<span data-ttu-id="596c6-166">–Level 收集重要消息、错误消息、警告消息和信息性消息。</span><span class="sxs-lookup"><span data-stu-id="596c6-166">The –Level collects fatal, error, warning, and information messages.</span></span> <span data-ttu-id="596c6-167">使用的标志都是为 Lyss 提供程序定义的所有标志，并包括 TF \_ Connection、tf \_ 诊断和 tf \_ 协议。</span><span class="sxs-lookup"><span data-stu-id="596c6-167">The flags used are all of those defined for the Lyss provider, and include TF\_Connection, TF\_Diag and TF\_Protocol.</span></span>

<span data-ttu-id="596c6-168">在定义变量 $LyssProvider 之后，可将其与 **New-CsClsScenario** cmdlet 结合使用以从 Lyss 提供程序中收集跟踪信息。</span><span class="sxs-lookup"><span data-stu-id="596c6-168">After the variable $LyssProvider is defined, you can use it with the **New-CsClsScenario** cmdlet to collect traces from the Lyss provider.</span></span> <span data-ttu-id="596c6-169">若要创建提供程序并将其分配给新的方案，请键入：</span><span class="sxs-lookup"><span data-stu-id="596c6-169">To complete the creation and assignment of the provider to a new scenario, type:</span></span>

    New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

<span data-ttu-id="596c6-170">其中 $LyssProvider 是包含使用 **New-CsClsProvider** 创建的定义的方案的变量。</span><span class="sxs-lookup"><span data-stu-id="596c6-170">Where $LyssProvider is the variable containing the defined scenario created with **New-CsClsProvider**.</span></span>

</div>

<div>

## <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a><span data-ttu-id="596c6-171">更改现有的集中日志记录服务方案提供程序</span><span class="sxs-lookup"><span data-stu-id="596c6-171">To change an existing Centralized Logging Service scenario provider</span></span>

1.  <span data-ttu-id="596c6-172">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="596c6-172">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="596c6-173">若要更新或更改现有提供程序的配置，请键入：</span><span class="sxs-lookup"><span data-stu-id="596c6-173">To update or change the configuration of an existing provider, type:</span></span>
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
    
    <span data-ttu-id="596c6-174">然后，通过键入以下内容来更新方案以分配提供程序：</span><span class="sxs-lookup"><span data-stu-id="596c6-174">You then update the scenario to assign the provider by typing the following:</span></span>
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

<span data-ttu-id="596c6-175">此命令的最终结果是方案 site:Redmond/RedmondLyssInfo 将获得提供程序的更新标志和级别。</span><span class="sxs-lookup"><span data-stu-id="596c6-175">The end result of the command is that the scenario site:Redmond/RedmondLyssInfo will have updated flags and level for the provider assigned to it.</span></span> <span data-ttu-id="596c6-176">可通过使用 Get-CsClsScenario 查看新方案。</span><span class="sxs-lookup"><span data-stu-id="596c6-176">You can view the new scenario by using Get-CsClsScenario.</span></span> <span data-ttu-id="596c6-177">有关详细信息，请参阅 [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario)。</span><span class="sxs-lookup"><span data-stu-id="596c6-177">For details, see [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario).</span></span>

<div class="">


> [!WARNING]  
> <span data-ttu-id="596c6-178"><STRONG>New-ClsCsProvider</STRONG> 不会检查以确定标志是否有效。</span><span class="sxs-lookup"><span data-stu-id="596c6-178"><STRONG>New-ClsCsProvider</STRONG> does not check to determine whether the flags are valid.</span></span> <span data-ttu-id="596c6-179">请确保标志（例如，TF_DIAG 或 TF_CONNECTION）的拼写正确。</span><span class="sxs-lookup"><span data-stu-id="596c6-179">Make sure that the spelling of the flags (for example, TF_DIAG or TF_CONNECTION) is spelled correctly.</span></span> <span data-ttu-id="596c6-180">如果标志的拼写不正确，则提供程序无法返回预期日志信息。</span><span class="sxs-lookup"><span data-stu-id="596c6-180">If the flags are not spelled correctly, the provider cannot return the expected log information.</span></span>



</div>

<span data-ttu-id="596c6-181">若要将其他提供程序添加到此方案，请键入：</span><span class="sxs-lookup"><span data-stu-id="596c6-181">If you want to add additional providers to this scenario, type the following:</span></span>

    Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}

<span data-ttu-id="596c6-182">其中，将通过已使用 **New-CsClsProvider** 过程定义的 Add 指令来定义每个提供程序。</span><span class="sxs-lookup"><span data-stu-id="596c6-182">Where each provider defined with the Add directive has already been defined using the **New-CsClsProvider** process.</span></span>

</div>

<div>

## <a name="to-remove-a-scenario-provider"></a><span data-ttu-id="596c6-183">删除方案提供程序</span><span class="sxs-lookup"><span data-stu-id="596c6-183">To remove a scenario provider</span></span>

1.  <span data-ttu-id="596c6-184">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="596c6-184">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="596c6-185">可利用提供的 cmdlet 更新现有提供程序并创建新的提供程序。</span><span class="sxs-lookup"><span data-stu-id="596c6-185">The cmdlets provided allow you to update existing providers and create new providers.</span></span> <span data-ttu-id="596c6-186">若要删除提供程序，您必须对 **Set-CsClsScenario** 的 Provider 参数使用 Replace 指令。</span><span class="sxs-lookup"><span data-stu-id="596c6-186">To remove a provider, you must use the Replace directive for the Provider parameter to **Set-CsClsScenario**.</span></span> <span data-ttu-id="596c6-187">完全删除提供程序的唯一方式是，将提供程序替换为具有相同名称的重定义的提供程序并使用 Update 指令。</span><span class="sxs-lookup"><span data-stu-id="596c6-187">The only way to completely remove a provider is to replace it with a redefined provider of the same name and use the Update directive.</span></span> <span data-ttu-id="596c6-188">例如，我们的提供商 LyssProvider 使用 WPP 作为日志类型进行定义，将 level 设置为 Debug，而 flags set 为 TF \_ CONNECTION 和 TF settings \_ 。</span><span class="sxs-lookup"><span data-stu-id="596c6-188">For example, our provider LyssProvider is defined with WPP as the log type, level set to Debug, and flags set are TF\_CONNECTION and TF\_DIAG.</span></span> <span data-ttu-id="596c6-189">您需要将标志更改为“All”。</span><span class="sxs-lookup"><span data-stu-id="596c6-189">You need to change the flags to “All”.</span></span> <span data-ttu-id="596c6-190">若要更改提供程序，请键入：</span><span class="sxs-lookup"><span data-stu-id="596c6-190">To change the provider, type the following:</span></span>
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"

     &nbsp;
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}

3.  <span data-ttu-id="596c6-191">若要完全删除方案及其关联的提供程序，请键入：</span><span class="sxs-lookup"><span data-stu-id="596c6-191">If you want to completely remove a scenario and the providers associated with it, type the following:</span></span>
    
        Remove-CsClsScenario -Identity <scope and name of scenario>
    
    <span data-ttu-id="596c6-192">例如：</span><span class="sxs-lookup"><span data-stu-id="596c6-192">For example:</span></span>
    
        Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
    
    <div class="">
    

    > [!WARNING]  
    > <span data-ttu-id="596c6-193">cmdlet <STRONG>Remove-CsClsScenario</STRONG> 不会提示您进行确认。</span><span class="sxs-lookup"><span data-stu-id="596c6-193">The cmdlet <STRONG>Remove-CsClsScenario</STRONG> does not prompt you for confirmation.</span></span> <span data-ttu-id="596c6-194">方案将连同已分配给它的提供程序一起被删除。</span><span class="sxs-lookup"><span data-stu-id="596c6-194">The scenario is deleted, along with the providers that were assigned to it.</span></span> <span data-ttu-id="596c6-195">可通过重新运行最初用于创建方案的命令来重新创建方案。</span><span class="sxs-lookup"><span data-stu-id="596c6-195">You can recreate the scenario by re-running the commands used to create it initially.</span></span> <span data-ttu-id="596c6-196">没有用于恢复已删除的方案或提供程序的过程。</span><span class="sxs-lookup"><span data-stu-id="596c6-196">There is no procedure to recover removed scenarios or providers.</span></span>

    
    </div>

<span data-ttu-id="596c6-197">在使用 **Remove-CsClsScenario** cmdlet 删除一个方案时，可以从作用域中完全删除此方案。</span><span class="sxs-lookup"><span data-stu-id="596c6-197">When you remove a scenario by using the **Remove-CsClsScenario** cmdlet, you completely remove the scenario from the scope.</span></span> <span data-ttu-id="596c6-198">若要使用已创建的方案以及作为该方案的一部分的提供程序，可以创建新的提供程序并将其分配给新方案。</span><span class="sxs-lookup"><span data-stu-id="596c6-198">To use the scenarios that you created and the providers that were a part of the scenario, you create new providers and assign them to a new scenario.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="596c6-199">另请参阅</span><span class="sxs-lookup"><span data-stu-id="596c6-199">See Also</span></span>


[<span data-ttu-id="596c6-200">New-csclsscenario</span><span class="sxs-lookup"><span data-stu-id="596c6-200">Get-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario)  
[<span data-ttu-id="596c6-201">新 New-csclsscenario</span><span class="sxs-lookup"><span data-stu-id="596c6-201">New-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClsScenario)  
[<span data-ttu-id="596c6-202">New-csclsscenario</span><span class="sxs-lookup"><span data-stu-id="596c6-202">Remove-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsClsScenario)  
[<span data-ttu-id="596c6-203">New-csclsscenario</span><span class="sxs-lookup"><span data-stu-id="596c6-203">Set-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario)  
[<span data-ttu-id="596c6-204">新 CsClsProvider</span><span class="sxs-lookup"><span data-stu-id="596c6-204">New-CsClsProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

