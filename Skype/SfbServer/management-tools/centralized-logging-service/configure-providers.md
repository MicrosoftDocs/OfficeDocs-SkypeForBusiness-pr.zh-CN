---
title: 配置 Skype for Business Server 2015 中的集中日志记录服务的提供程序
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
description: 摘要： 了解如何在 Skype 为业务服务器 2015年配置方案提供集中式日志记录服务。
ms.openlocfilehash: a609d7406f59702aeb906a21132eff5f861ce037
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-providers-for-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="75b7d-103">配置 Skype for Business Server 2015 中的集中日志记录服务的提供程序</span><span class="sxs-lookup"><span data-stu-id="75b7d-103">Configure providers for Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="75b7d-104">**摘要：**了解如何在 Skype 为业务服务器 2015年配置方案提供集中式日志记录服务。</span><span class="sxs-lookup"><span data-stu-id="75b7d-104">**Summary:** Learn how to configure scenario providers for the Centralized Logging Service in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="75b7d-105">概念和集中式日志记录服务的提供商的配置是一种最重要的是抓住。</span><span class="sxs-lookup"><span data-stu-id="75b7d-105">The concepts and configuration of providers in Centralized Logging Service is one of the most important to grasp.</span></span> <span data-ttu-id="75b7d-106">Theproviders 直接映射到业务服务器服务器角色中的组件的业务服务器跟踪模型 Skype 的 Skype。</span><span class="sxs-lookup"><span data-stu-id="75b7d-106">Theproviders map directly to Skype for Business Server server role components in the Skype for Business Server tracing model.</span></span> <span data-ttu-id="75b7d-107">提供程序定义了业务服务器 2015 将描摹的消息 （例如，致命错误或警告） 为收集，以及标志 （例如，TF_Connection 或 TF_Diag） 的类型 Skype 的组成部分。</span><span class="sxs-lookup"><span data-stu-id="75b7d-107">The provider defines the components of a Skype for Business Server 2015 that will be traced, the type of messages (for example, fatal, error, or warning) to collect, and the flags (for example, TF_Connection or TF_Diag).</span></span> <span data-ttu-id="75b7d-108">提供程序是在每个 Skype 业务服务器服务器角色可跟踪组件。</span><span class="sxs-lookup"><span data-stu-id="75b7d-108">Providers are the traceable components in each Skype for Business Server server role.</span></span> <span data-ttu-id="75b7d-109">通过使用提供程序，可以定义对组件进行的跟踪的级别和类型（例如，S4、SIPStack、IM 和 Presence）。</span><span class="sxs-lookup"><span data-stu-id="75b7d-109">By using providers, you define the level and type of tracing on components (for example, S4, SIPStack, IM and Presence).</span></span> <span data-ttu-id="75b7d-110">可在方案中使用所定义的提供程序将针对给定逻辑集合的、满足某个特定问题条件的所有提供程序组合在一起。</span><span class="sxs-lookup"><span data-stu-id="75b7d-110">The defined provider is used in a scenario to group all of the providers for a given logical collection that address a specific problem condition.</span></span>
  
<span data-ttu-id="75b7d-111">若要运行使用 Skype 业务服务器管理外壳的集中式日志记录服务功能，您必须是 CsAdministrator 或 CsServerAdministrator 基于角色的访问控制 (RBAC) 的安全组中，或自定义的 RBAC 角色的成员，包含这两个组之一。</span><span class="sxs-lookup"><span data-stu-id="75b7d-111">To run the Centralized Logging Service functions using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="75b7d-112">若要返回列表中的所有已分配给 （包括您自己创建的任何自定义的 RBAC 角色），此 cmdlet 的基于角色的访问控制 (RBAC) 角色运行下面的命令从 Skype 业务服务器管理外壳程序或 Windows PowerShell提示：</span><span class="sxs-lookup"><span data-stu-id="75b7d-112">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="75b7d-113">例如：</span><span class="sxs-lookup"><span data-stu-id="75b7d-113">For example:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="75b7d-114">本主题的其余部分将重点说明如何定义提供程序、修改提供程序以及提供程序定义为优化您的疑难解答所包含的内容。</span><span class="sxs-lookup"><span data-stu-id="75b7d-114">The remainder of this topic focuses on how to define providers, modify a provider and what a provider definition contains to optimize your troubleshooting.</span></span> <span data-ttu-id="75b7d-115">有两种方法将集中式日志记录服务命令。</span><span class="sxs-lookup"><span data-stu-id="75b7d-115">There are two ways to issue Centralized Logging Service commands.</span></span> <span data-ttu-id="75b7d-116">默认情况下，可使用位于目录 C:\Program Files\Common Files\Skype for Business Server 2015\CLSAgent 中的 CLSController.exe。</span><span class="sxs-lookup"><span data-stu-id="75b7d-116">You can use the CLSController.exe that is located, by default, in the directory C:\Program Files\Common Files\Skype for Business Server 2015\CLSAgent.</span></span> <span data-ttu-id="75b7d-117">或者，您可以使用业务服务器管理外壳的 Skype 发布 Windows PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="75b7d-117">Or, you can use the Skype for Business Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="75b7d-118">通过使用 Windows PowerShell，可以定义新的提供程序，用于在您的日志记录会话，和完全控制其创建，它们的收集，以及在哪个级别，它们收集的数据。</span><span class="sxs-lookup"><span data-stu-id="75b7d-118">By using Windows PowerShell, you can define new providers for use in your logging sessions, and have complete control over their creation, what they collect, and at what level they collect data.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="75b7d-p104">如前所述，提供程序的功能十分强大。但是，方案的功能更为强大，因为方案是对提供程序表示的组件进行设置并执行跟踪所需的所有信息的具体体现。由于方案将包含一组提供程序，因此将运行一个包含几百条用于收集大量信息的命令的批处理文件与在命令行中一次性发出几百条命令相比是不受限制的。</span><span class="sxs-lookup"><span data-stu-id="75b7d-p104">As mentioned, providers are very powerful. However, scenarios are more powerful because they contain the embodiment of all information needed to set and execute tracing on the components that the providers represent. With scenarios being a collection of providers, this could be loosely compared to running a batch file containing hundreds of commands to collect a lot of information versus issuing hundreds of commands, one at a time, at the command line.</span></span> 
  
<span data-ttu-id="75b7d-122">而不是需要深挖到的提供程序的详细信息，集中式日志记录服务为您提供了一些已定义的方案。</span><span class="sxs-lookup"><span data-stu-id="75b7d-122">Instead of requiring you to dig deeply into the details of providers, the Centralized Logging Service provides a number of scenarios that are already defined for you.</span></span> <span data-ttu-id="75b7d-123">提供的方案涵盖了绝大多数您可能会遇到的问题。</span><span class="sxs-lookup"><span data-stu-id="75b7d-123">The provided scenarios cover the vast majority of possible issues that you will encounter.</span></span> <span data-ttu-id="75b7d-124">在极少数情况下，您可能需要创建和定义提供程序并将其分配给方案。</span><span class="sxs-lookup"><span data-stu-id="75b7d-124">In rare cases, you may need to create and define providers and assign them to scenarios.</span></span> <span data-ttu-id="75b7d-125">强烈建议您先熟悉提供的每个方案，然后再调查有关创建新的提供程序和方案的需求。</span><span class="sxs-lookup"><span data-stu-id="75b7d-125">We strongly recommend that you become familiar with each of the scenarios provided before you investigate the need to create new providers and scenarios.</span></span> <span data-ttu-id="75b7d-126">虽然您可以通过此处提供的有关创建提供程序的信息来熟悉方案如何使用提供程序元素来收集跟踪信息，但此时不提供有关提供程序本身的详细信息。</span><span class="sxs-lookup"><span data-stu-id="75b7d-126">While information about creating providers is found here to familiarize you with how the scenarios use the provider elements to collect trace information, details on the providers themselves are not provided at this time.</span></span> 
  
<span data-ttu-id="75b7d-127">引入[业务 2015年的 Skype 在集中式日志记录服务](centralized-logging-service.md)中，在方案中定义的提供程序使用的关键要素包括：</span><span class="sxs-lookup"><span data-stu-id="75b7d-127">Introduced in [Centralized Logging Service in Skype for Business 2015](centralized-logging-service.md), the key elements of defining a provider for use in a scenario are:</span></span>
  
- <span data-ttu-id="75b7d-128">**提供程序**如果您熟悉 OCSLogger，提供程序告诉 OCSLogger 跟踪引擎应收集日志从您选择的组件。</span><span class="sxs-lookup"><span data-stu-id="75b7d-128">**Providers** If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="75b7d-129">提供程序是一些相同的组件，在许多情况下，它们的名称与 OCSLogger 中组件的名称相同。</span><span class="sxs-lookup"><span data-stu-id="75b7d-129">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="75b7d-130">如果您还不熟悉 OCSLogger，提供程序服务器角色从记录集中的记录服务可以收集的特定组件。</span><span class="sxs-lookup"><span data-stu-id="75b7d-130">If you are not familiar with OCSLogger, providers are server-role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="75b7d-131">在集中式日志记录服务，CLSAgent 是集中式日志记录服务的正在执行的操作将跟踪您的提供程序配置中定义的组件的体系结构的一部分。</span><span class="sxs-lookup"><span data-stu-id="75b7d-131">In the case of the Centralized Logging Service, the CLSAgent is the architectural part of the Centralized Logging Service that is doing the tracing of the components that you define in the providers configuration.</span></span>
    
- <span data-ttu-id="75b7d-132">**日志记录级别**OCSLogger 提供的选项可供选择数收集到的数据的详细程度。</span><span class="sxs-lookup"><span data-stu-id="75b7d-132">**Logging levels** OCSLogger provided the option to choose a number of levels of detail for the data collected.</span></span> <span data-ttu-id="75b7d-133">此功能是不可或缺的组成部分集中式日志记录服务和方案，并由**类型**参数定义。</span><span class="sxs-lookup"><span data-stu-id="75b7d-133">This feature is an integral part of the Centralized Logging Service and scenarios, and is defined by the **Type** parameter.</span></span> <span data-ttu-id="75b7d-134">您可以选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="75b7d-134">You can choose from the following:</span></span>
    
  - <span data-ttu-id="75b7d-135">**所有**收集跟踪定义的提供程序类型致命的消息、 错误、 警告、 详细，和调试信息记录到日志。</span><span class="sxs-lookup"><span data-stu-id="75b7d-135">**All** Collects trace messages of type fatal, error, warning, verbose, and debug info to the log for the defined provider.</span></span>
    
  - <span data-ttu-id="75b7d-136">**致命**收集仅跟踪消息定义为"严重"。</span><span class="sxs-lookup"><span data-stu-id="75b7d-136">**Fatal** Collects only the trace messages defined as "Fatal."</span></span>
    
  - <span data-ttu-id="75b7d-137">**错误**收集仅跟踪消息定义为"错误"或"严重"。</span><span class="sxs-lookup"><span data-stu-id="75b7d-137">**Error** Collects only the trace messages defined as "Error" or "Fatal."</span></span>
    
  - <span data-ttu-id="75b7d-138">**警告**收集跟踪消息将类型的"警告，""错误"和"致命"。</span><span class="sxs-lookup"><span data-stu-id="75b7d-138">**Warning** Collects only the trace messages of type "Warning," "Error" and "Fatal."</span></span>
    
  - <span data-ttu-id="75b7d-139">**信息**收集指示定义提供程序，加上严重的信息性消息、 错误和警告消息的跟踪消息。</span><span class="sxs-lookup"><span data-stu-id="75b7d-139">**Info** Collects only the trace messages that indicate an informational message for the defined provider, plus fatal, error, and warning messages.</span></span>
    
  - <span data-ttu-id="75b7d-140">**详细**收集所有跟踪消息的类型，错误，警告和详细的定义提供程序。</span><span class="sxs-lookup"><span data-stu-id="75b7d-140">**Verbose** Collects all trace messages of type fatal, error, warning and verbose for the defined provider.</span></span>
    
  - <span data-ttu-id="75b7d-141">这是本质上的相当于**调试**为全部的致命错误，错误，警告，信息、 详细和调试类型的收集跟踪定义提供程序。</span><span class="sxs-lookup"><span data-stu-id="75b7d-141">**Debug** this is essentially an equivalent of 'All' - collects traces of type Fatal, Error, Warning, Info, Verbose and Debug for the defined provider.</span></span>
    
- <span data-ttu-id="75b7d-142">**标志**OCSLogger 提供的选项若要定义哪种类型的信息可以从跟踪文件检索每个提供程序选择标志。</span><span class="sxs-lookup"><span data-stu-id="75b7d-142">**Flags** OCSLogger provided the option to choose flags for each provider that defined what type of information you could retrieve from the trace files.</span></span> <span data-ttu-id="75b7d-143">可以根据提供程序选择以下标志：</span><span class="sxs-lookup"><span data-stu-id="75b7d-143">You can chose the following flags, based on the provider:</span></span>
    
  - <span data-ttu-id="75b7d-144">**TF_Connection**提供与连接相关的日志条目。</span><span class="sxs-lookup"><span data-stu-id="75b7d-144">**TF_Connection** Provides connection-related log entries.</span></span> <span data-ttu-id="75b7d-145">这些日志包括与特定组件建立的连接的相关信息。</span><span class="sxs-lookup"><span data-stu-id="75b7d-145">These logs include information about connections established to and from a particular component.</span></span> <span data-ttu-id="75b7d-146">这可能还包括大量网络级信息（即针对组件，但不包括连接的概念）。</span><span class="sxs-lookup"><span data-stu-id="75b7d-146">This may also include significant network-level information (that is, for components without the concept of a connection).</span></span>
    
  - <span data-ttu-id="75b7d-147">**TF_Security**提供所有与安全相关的事件/日志条目。</span><span class="sxs-lookup"><span data-stu-id="75b7d-147">**TF_Security** Provides all events/log entries related to security.</span></span> <span data-ttu-id="75b7d-148">例如，对于 SipStack，它们是一些安全事件（例如，域验证失败和客户端身份验证/授权失败）。</span><span class="sxs-lookup"><span data-stu-id="75b7d-148">For example, for SipStack, these are security events such as domain validation failure, and client authentication/authorization failures.</span></span>
    
  - <span data-ttu-id="75b7d-149">**TF_Diag**提供可用于诊断或排除组件故障的诊断事件。</span><span class="sxs-lookup"><span data-stu-id="75b7d-149">**TF_Diag** Provides diagnostics events that you can use to diagnose or troubleshoot the component.</span></span> <span data-ttu-id="75b7d-150">例如，对于 SipStack，它们是证书失败或 DNS 警告/错误。</span><span class="sxs-lookup"><span data-stu-id="75b7d-150">For example, for SipStack, these are certificate failures, or DNS warnings/errors.</span></span>
    
  - <span data-ttu-id="75b7d-151">**TF_Protocol**提供如结合社区编解码器包和 SIP 消息的协议消息。</span><span class="sxs-lookup"><span data-stu-id="75b7d-151">**TF_Protocol** Provides protocol messages such as SIP and Combined Community Codec Pack messages.</span></span>
    
  - <span data-ttu-id="75b7d-152">**TF_Component**启用登录指定的提供程序的一部分的组件。</span><span class="sxs-lookup"><span data-stu-id="75b7d-152">**TF_Component** Enables logging on the components specified as part of the providers.</span></span>
    
  - <span data-ttu-id="75b7d-153">**所有**设置提供程序可用的所有可用标志。</span><span class="sxs-lookup"><span data-stu-id="75b7d-153">**All** Sets all available flags available for the provider.</span></span>
    
### <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a><span data-ttu-id="75b7d-154">若要查看有关现有的集中式日志记录服务方案提供的信息</span><span class="sxs-lookup"><span data-stu-id="75b7d-154">To review information about existing Centralized Logging Service scenario providers</span></span>

1. <span data-ttu-id="75b7d-155">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="75b7d-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="75b7d-156">若要查看现有提供程序的配置，请键入：</span><span class="sxs-lookup"><span data-stu-id="75b7d-156">To review the configuration of existing providers, type the following:</span></span>
    
  ```
  Get-CsClsScenario -Identity <scope and scenario name>
  ```

    <span data-ttu-id="75b7d-157">例如，若要查看有关全局会议助理的信息，请键入：</span><span class="sxs-lookup"><span data-stu-id="75b7d-157">For example, to review information about the global conferencing attendant, type:</span></span>
    
  ```
  Get-CsClsScenario -Identity "global/CAA"
  ```

    <span data-ttu-id="75b7d-158">此命令显示具有关联的标志、设置和组件的提供程序的列表。</span><span class="sxs-lookup"><span data-stu-id="75b7d-158">The command displays a list of providers with the associated flags, settings, and components.</span></span> <span data-ttu-id="75b7d-159">如果显示的信息是不足够或列表默认 Windows PowerShell 列表格式太长，您可以通过定义不同的输出方法来显示其他信息。</span><span class="sxs-lookup"><span data-stu-id="75b7d-159">If the information displayed is not enough or the list is too long for the default Windows PowerShell list format, you can display additional information by defining a different output method.</span></span> <span data-ttu-id="75b7d-160">为此，请键入：</span><span class="sxs-lookup"><span data-stu-id="75b7d-160">To do this, type:</span></span>
    
  ```
  Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
  ```

    <span data-ttu-id="75b7d-161">此命令的输出显示用五行格式显示的每个提供程序，以及提供程序名称、日志记录类型、日志记录级别、标志、GUID 和角色（每个提供程序位于一个单独的行上）。</span><span class="sxs-lookup"><span data-stu-id="75b7d-161">The output of this command displays each provider displayed in a five line format with the provider name, type of logging, logging level, flags, GUID, and role, each one on a separate line.</span></span> 
    
### <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a><span data-ttu-id="75b7d-162">若要定义新的集中式日志记录服务方案提供商</span><span class="sxs-lookup"><span data-stu-id="75b7d-162">To define a new Centralized Logging Service scenario provider</span></span>

1. <span data-ttu-id="75b7d-163">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="75b7d-163">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="75b7d-p113">方案提供程序包含要跟踪的组件、要使用的标志和要收集的详细信息级别。通过键入以下内容可完成此操作：</span><span class="sxs-lookup"><span data-stu-id="75b7d-p113">A scenario provider consists of a component to trace, flags to use, and a level of detail to collect. You do this by typing:</span></span>
    
  ```
  $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
  ```

    <span data-ttu-id="75b7d-166">例如，定义要从 Lyss 提供程序收集的内容和详细信息级别的跟踪提供程序定义与以下内容类似：</span><span class="sxs-lookup"><span data-stu-id="75b7d-166">For example, a trace provider definition that defines what to collect and to what level of detail from the Lyss provider looks like the following:</span></span>
    
  ```
  $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"
  ```

<span data-ttu-id="75b7d-167">-级别收集致死，错误、 警告和信息消息。</span><span class="sxs-lookup"><span data-stu-id="75b7d-167">The -Level collects fatal, error, warning, and information messages.</span></span> <span data-ttu-id="75b7d-168">使用的标志是所有这些定义的 Lyss 提供者，包括 TF_Connection、 TF_Diag 和 TF_Protocol.After 定义变量 $LyssProvider，您可以使用它与**新建 CsClsScenario** cmdlet 来跟踪收集 Lyss 提供程序。</span><span class="sxs-lookup"><span data-stu-id="75b7d-168">The flags used are all of those defined for the Lyss provider, and include TF_Connection, TF_Diag and TF_Protocol.After the variable $LyssProvider is defined, you can use it with the **New-CsClsScenario** cmdlet to collect traces from the Lyss provider.</span></span> <span data-ttu-id="75b7d-169">若要创建提供程序并将其分配给新的方案，请键入：</span><span class="sxs-lookup"><span data-stu-id="75b7d-169">To complete the creation and assignment of the provider to a new scenario, type:</span></span>

```
New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
```

<span data-ttu-id="75b7d-170">其中，$LyssProvider 是包含定义的方案使用**New CsClsProvider**创建的变量。</span><span class="sxs-lookup"><span data-stu-id="75b7d-170">Where $LyssProvider is the variable containing the defined scenario created with **New-CsClsProvider**.</span></span>
### <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a><span data-ttu-id="75b7d-171">若要更改现有的集中式日志记录服务方案提供商</span><span class="sxs-lookup"><span data-stu-id="75b7d-171">To change an existing Centralized Logging Service scenario provider</span></span>

1. <span data-ttu-id="75b7d-172">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="75b7d-172">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="75b7d-173">若要更新或更改现有提供程序的配置，请键入：</span><span class="sxs-lookup"><span data-stu-id="75b7d-173">To update or change the configuration of an existing provider, type:</span></span>
    
  ```
  $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
  ```

    <span data-ttu-id="75b7d-174">然后，通过键入以下内容来更新方案以分配提供程序：</span><span class="sxs-lookup"><span data-stu-id="75b7d-174">You then update the scenario to assign the provider by typing the following:</span></span>
    
  ```
  Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
  ```

<span data-ttu-id="75b7d-175">此命令的最终结果是方案 site:Redmond/RedmondLyssInfo 将获得提供程序的更新标志和级别。</span><span class="sxs-lookup"><span data-stu-id="75b7d-175">The end result of the command is that the scenario site:Redmond/RedmondLyssInfo will have updated flags and level for the provider assigned to it.</span></span> <span data-ttu-id="75b7d-176">可通过使用 Get-CsClsScenario 查看新方案。</span><span class="sxs-lookup"><span data-stu-id="75b7d-176">You can view the new scenario by using Get-CsClsScenario.</span></span> <span data-ttu-id="75b7d-177">有关详细信息，请参阅[获取 CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="75b7d-177">For details, see [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).</span></span>
> [!CAUTION]
> <span data-ttu-id="75b7d-178">**新建 ClsCsProvider**不会检查以确定是否为有效的标志。</span><span class="sxs-lookup"><span data-stu-id="75b7d-178">**New-ClsCsProvider** does not check to determine whether the flags are valid.</span></span> <span data-ttu-id="75b7d-179">请确保标志（例如，TF_DIAG 或 TF_CONNECTION）的拼写正确。</span><span class="sxs-lookup"><span data-stu-id="75b7d-179">Make sure that the spelling of the flags (for example, TF_DIAG or TF_CONNECTION) is spelled correctly.</span></span> <span data-ttu-id="75b7d-180">如果标志的拼写不正确，则提供程序无法返回预期日志信息。</span><span class="sxs-lookup"><span data-stu-id="75b7d-180">If the flags are not spelled correctly, the provider cannot return the expected log information.</span></span>
  
<span data-ttu-id="75b7d-181">若要将其他提供程序添加到此方案，请键入：</span><span class="sxs-lookup"><span data-stu-id="75b7d-181">If you want to add additional providers to this scenario, type the following:</span></span>

```
Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}
```

<span data-ttu-id="75b7d-182">在使用定义的每个提供程序添加指令已定义使用**New CsClsProvider**过程。</span><span class="sxs-lookup"><span data-stu-id="75b7d-182">Where each provider defined with the Add directive has already been defined using the **New-CsClsProvider** process.</span></span>
### <a name="to-remove-a-scenario-provider"></a><span data-ttu-id="75b7d-183">删除方案提供程序</span><span class="sxs-lookup"><span data-stu-id="75b7d-183">To remove a scenario provider</span></span>

1. <span data-ttu-id="75b7d-184">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="75b7d-184">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="75b7d-185">可利用提供的 cmdlet 更新现有提供程序并创建新的提供程序。</span><span class="sxs-lookup"><span data-stu-id="75b7d-185">The cmdlets provided allow you to update existing providers and create new providers.</span></span> <span data-ttu-id="75b7d-186">若要删除提供商，必须使用替换指令**集 CsClsScenario**的提供程序参数。</span><span class="sxs-lookup"><span data-stu-id="75b7d-186">To remove a provider, you must use the Replace directive for the Provider parameter to **Set-CsClsScenario**.</span></span> <span data-ttu-id="75b7d-187">完全删除提供程序的唯一方式是，将提供程序替换为具有相同名称的重定义的提供程序并使用 Update 指令。</span><span class="sxs-lookup"><span data-stu-id="75b7d-187">The only way to completely remove a provider is to replace it with a redefined provider of the same name and use the Update directive.</span></span> <span data-ttu-id="75b7d-188">例如，使用 WPP 将提供程序 LyssProvider 定义为日志类型，将级别设置为“Debug”，则标志集为 TF_CONNECTION 和 TF_DIAG。</span><span class="sxs-lookup"><span data-stu-id="75b7d-188">For example, our provider LyssProvider is defined with WPP as the log type, level set to Debug, and flags set are TF_CONNECTION and TF_DIAG.</span></span> <span data-ttu-id="75b7d-189">您需要更改标志的"全部"。</span><span class="sxs-lookup"><span data-stu-id="75b7d-189">You need to change the flags to "All".</span></span> <span data-ttu-id="75b7d-190">若要更改提供程序，请键入：</span><span class="sxs-lookup"><span data-stu-id="75b7d-190">To change the provider, type the following:</span></span>
    
  ```
  $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"
  ```

  ```
  Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}
  ```

3. <span data-ttu-id="75b7d-191">若要完全删除方案及其关联的提供程序，请键入：</span><span class="sxs-lookup"><span data-stu-id="75b7d-191">If you want to completely remove a scenario and the providers associated with it, type the following:</span></span>
    
  ```
  Remove-CsClsScenario -Identity <scope and name of scenario>
  ```

    <span data-ttu-id="75b7d-192">例如：</span><span class="sxs-lookup"><span data-stu-id="75b7d-192">For example:</span></span>
    
  ```
  Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
  ```

    > [!CAUTION]
    > <span data-ttu-id="75b7d-193">该 cmdlet**删除 CsClsScenario**不提示您进行确认。</span><span class="sxs-lookup"><span data-stu-id="75b7d-193">The cmdlet **Remove-CsClsScenario** does not prompt you for confirmation.</span></span> <span data-ttu-id="75b7d-194">方案将连同已分配给它的提供程序一起被删除。</span><span class="sxs-lookup"><span data-stu-id="75b7d-194">The scenario is deleted, along with the providers that were assigned to it.</span></span> <span data-ttu-id="75b7d-195">可通过重新运行最初用于创建方案的命令来重新创建方案。</span><span class="sxs-lookup"><span data-stu-id="75b7d-195">You can recreate the scenario by re-running the commands used to create it initially.</span></span> <span data-ttu-id="75b7d-196">没有用于恢复已删除的方案或提供程序的过程。</span><span class="sxs-lookup"><span data-stu-id="75b7d-196">There is no procedure to recover removed scenarios or providers.</span></span>
  
<span data-ttu-id="75b7d-197">当您删除一个方案通过**删除 CsClsScenario** cmdlet 时，您完全方案从范围中移除。</span><span class="sxs-lookup"><span data-stu-id="75b7d-197">When you remove a scenario by using the **Remove-CsClsScenario** cmdlet, you completely remove the scenario from the scope.</span></span> <span data-ttu-id="75b7d-198">若要使用已创建的方案以及作为该方案的一部分的提供程序，可以创建新的提供程序并将其分配给新方案。</span><span class="sxs-lookup"><span data-stu-id="75b7d-198">To use the scenarios that you created and the providers that were a part of the scenario, you create new providers and assign them to a new scenario.</span></span>
## <a name="see-also"></a><span data-ttu-id="75b7d-199">另请参阅</span><span class="sxs-lookup"><span data-stu-id="75b7d-199">See also</span></span>

#### 

[<span data-ttu-id="75b7d-200">获得 CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="75b7d-200">Get-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="75b7d-201">新 CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="75b7d-201">New-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="75b7d-202">删除 CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="75b7d-202">Remove-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="75b7d-203">一组 CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="75b7d-203">Set-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="75b7d-204">新 CsClsProvider</span><span class="sxs-lookup"><span data-stu-id="75b7d-204">New-CsClsProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps)

