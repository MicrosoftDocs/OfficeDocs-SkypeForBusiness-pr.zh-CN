---
title: 在 Skype for Business Server 2015 中配置集中日志记录服务的提供程序
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
description: 摘要：了解如何在 Skype for Business Server 2015 中为集中日志记录服务配置方案提供程序。
ms.openlocfilehash: c96a87ea76930dbd99341667852a9731e56b88b5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835162"
---
# <a name="configure-providers-for-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="118f9-103">在 Skype for Business Server 2015 中配置集中日志记录服务的提供程序</span><span class="sxs-lookup"><span data-stu-id="118f9-103">Configure providers for Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="118f9-104">**摘要：** 了解如何在 Skype for Business Server 2015 中为集中日志记录服务配置方案提供程序。</span><span class="sxs-lookup"><span data-stu-id="118f9-104">**Summary:** Learn how to configure scenario providers for the Centralized Logging Service in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="118f9-105">集中日志记录服务中的提供程序的概念和配置是必须掌握的最重要的概念之一。</span><span class="sxs-lookup"><span data-stu-id="118f9-105">The concepts and configuration of providers in Centralized Logging Service is one of the most important to grasp.</span></span> <span data-ttu-id="118f9-106">Providers 直接映射到 Skype for Business Server 跟踪模型中的 Skype for Business Server 服务器角色组件。</span><span class="sxs-lookup"><span data-stu-id="118f9-106">Theproviders map directly to Skype for Business Server server role components in the Skype for Business Server tracing model.</span></span> <span data-ttu-id="118f9-107">提供商定义将跟踪的 Skype for Business Server 2015 的组件、要收集的消息类型 (例如，严重、错误或警告) ，以及标志 (例如 TF_Connection 或 TF_Diag) 。</span><span class="sxs-lookup"><span data-stu-id="118f9-107">The provider defines the components of a Skype for Business Server 2015 that will be traced, the type of messages (for example, fatal, error, or warning) to collect, and the flags (for example, TF_Connection or TF_Diag).</span></span> <span data-ttu-id="118f9-108">提供程序是每个 Skype for Business Server 服务器角色中的可跟踪组件。</span><span class="sxs-lookup"><span data-stu-id="118f9-108">Providers are the traceable components in each Skype for Business Server server role.</span></span> <span data-ttu-id="118f9-109">通过使用提供程序，可以定义对组件进行的跟踪的级别和类型（例如，S4、SIPStack、IM 和 Presence）。</span><span class="sxs-lookup"><span data-stu-id="118f9-109">By using providers, you define the level and type of tracing on components (for example, S4, SIPStack, IM and Presence).</span></span> <span data-ttu-id="118f9-110">可在方案中使用所定义的提供程序将针对给定逻辑集合的、满足某个特定问题条件的所有提供程序组合在一起。</span><span class="sxs-lookup"><span data-stu-id="118f9-110">The defined provider is used in a scenario to group all of the providers for a given logical collection that address a specific problem condition.</span></span>
  
<span data-ttu-id="118f9-111">若要使用 Skype for Business Server 命令行管理程序运行集中日志记录服务功能，您必须是基于 CsAdministrator 或 CsServerAdministrator 角色的访问控制 (RBAC) 安全组的成员，或者是包含这两个组之一的自定义 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="118f9-111">To run the Centralized Logging Service functions using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="118f9-112">若要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表 (包括您自己创建的任何自定义 RBAC 角色) ，请从 Skype for Business Server 命令行管理程序 或 Windows PowerShell 提示符运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="118f9-112">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="118f9-113">例如：</span><span class="sxs-lookup"><span data-stu-id="118f9-113">For example:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="118f9-114">本主题的其余部分将重点说明如何定义提供程序、修改提供程序以及提供程序定义为优化您的疑难解答所包含的内容。</span><span class="sxs-lookup"><span data-stu-id="118f9-114">The remainder of this topic focuses on how to define providers, modify a provider and what a provider definition contains to optimize your troubleshooting.</span></span> <span data-ttu-id="118f9-115">有两种方法可以发出集中日志记录服务命令。</span><span class="sxs-lookup"><span data-stu-id="118f9-115">There are two ways to issue Centralized Logging Service commands.</span></span> <span data-ttu-id="118f9-116">默认情况下，CLSController.exe C：\Program Files\Common Files\Skype for Business Server 2015\CLSAgent 目录中的目录。</span><span class="sxs-lookup"><span data-stu-id="118f9-116">You can use the CLSController.exe that is located, by default, in the directory C:\Program Files\Common Files\Skype for Business Server 2015\CLSAgent.</span></span> <span data-ttu-id="118f9-117">或者，您可以使用 Skype for Business Server 命令行管理程序发出Windows PowerShell命令。</span><span class="sxs-lookup"><span data-stu-id="118f9-117">Or, you can use the Skype for Business Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="118f9-118">通过使用 Windows PowerShell，您可以定义用于日志记录会话的新提供程序，并完全控制其创建、收集内容以及收集数据的级别。</span><span class="sxs-lookup"><span data-stu-id="118f9-118">By using Windows PowerShell, you can define new providers for use in your logging sessions, and have complete control over their creation, what they collect, and at what level they collect data.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="118f9-p104">如前所述，提供程序的功能十分强大。但是，方案的功能更为强大，因为方案是对提供程序表示的组件进行设置并执行跟踪所需的所有信息的具体体现。由于方案将包含一组提供程序，因此将运行一个包含几百条用于收集大量信息的命令的批处理文件与在命令行中一次性发出几百条命令相比是不受限制的。</span><span class="sxs-lookup"><span data-stu-id="118f9-p104">As mentioned, providers are very powerful. However, scenarios are more powerful because they contain the embodiment of all information needed to set and execute tracing on the components that the providers represent. With scenarios being a collection of providers, this could be loosely compared to running a batch file containing hundreds of commands to collect a lot of information versus issuing hundreds of commands, one at a time, at the command line.</span></span> 
  
<span data-ttu-id="118f9-122">集中日志记录服务提供许多已定义的方案，而不是要求深入了解提供程序的详细信息。</span><span class="sxs-lookup"><span data-stu-id="118f9-122">Instead of requiring you to dig deeply into the details of providers, the Centralized Logging Service provides a number of scenarios that are already defined for you.</span></span> <span data-ttu-id="118f9-123">提供的方案涵盖了绝大多数您可能会遇到的问题。</span><span class="sxs-lookup"><span data-stu-id="118f9-123">The provided scenarios cover the vast majority of possible issues that you will encounter.</span></span> <span data-ttu-id="118f9-124">在极少数情况下，您可能需要创建和定义提供程序并将其分配给方案。</span><span class="sxs-lookup"><span data-stu-id="118f9-124">In rare cases, you may need to create and define providers and assign them to scenarios.</span></span> <span data-ttu-id="118f9-125">强烈建议您先熟悉提供的每个方案，然后再调查有关创建新的提供程序和方案的需求。</span><span class="sxs-lookup"><span data-stu-id="118f9-125">We strongly recommend that you become familiar with each of the scenarios provided before you investigate the need to create new providers and scenarios.</span></span> <span data-ttu-id="118f9-126">虽然您可以通过此处提供的有关创建提供程序的信息来熟悉方案如何使用提供程序元素来收集跟踪信息，但此时不提供有关提供程序本身的详细信息。</span><span class="sxs-lookup"><span data-stu-id="118f9-126">While information about creating providers is found here to familiarize you with how the scenarios use the provider elements to collect trace information, details on the providers themselves are not provided at this time.</span></span> 
  
<span data-ttu-id="118f9-127">在 [Skype for Business 2015](centralized-logging-service.md)的集中日志记录服务中引入，定义要用于方案的提供程序的关键元素包括：</span><span class="sxs-lookup"><span data-stu-id="118f9-127">Introduced in [Centralized Logging Service in Skype for Business 2015](centralized-logging-service.md), the key elements of defining a provider for use in a scenario are:</span></span>
  
- <span data-ttu-id="118f9-128">**提供程序** 如果您熟悉 OCSLogger，则提供程序是选择告诉 OCSLogger 跟踪引擎应从哪些组件收集日志的组件。</span><span class="sxs-lookup"><span data-stu-id="118f9-128">**Providers** If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="118f9-129">提供程序是一些相同的组件，在许多情况下，它们的名称与 OCSLogger 中组件的名称相同。</span><span class="sxs-lookup"><span data-stu-id="118f9-129">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="118f9-130">如果您不熟悉 OCSLogger，则提供程序是集中日志记录服务可以从中收集日志的服务器角色特定组件。</span><span class="sxs-lookup"><span data-stu-id="118f9-130">If you are not familiar with OCSLogger, providers are server-role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="118f9-131">对于集中日志记录服务，CLSAgent 是集中日志记录服务的体系结构部分，用于跟踪提供程序配置中定义的组件。</span><span class="sxs-lookup"><span data-stu-id="118f9-131">In the case of the Centralized Logging Service, the CLSAgent is the architectural part of the Centralized Logging Service that is doing the tracing of the components that you define in the providers configuration.</span></span>
    
- <span data-ttu-id="118f9-132">**日志记录级别** OCSLogger 提供了为收集的数据选择多个级别的详细信息的选项。</span><span class="sxs-lookup"><span data-stu-id="118f9-132">**Logging levels** OCSLogger provided the option to choose a number of levels of detail for the data collected.</span></span> <span data-ttu-id="118f9-133">此功能是集中日志记录服务和方案的组成部分，由 **Type** 参数定义。</span><span class="sxs-lookup"><span data-stu-id="118f9-133">This feature is an integral part of the Centralized Logging Service and scenarios, and is defined by the **Type** parameter.</span></span> <span data-ttu-id="118f9-134">您可以选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="118f9-134">You can choose from the following:</span></span>
    
  - <span data-ttu-id="118f9-135">**全部** 将类型为 fatal、error、warning、verbose 和 debug 的信息的跟踪消息收集到定义的提供程序的日志中。</span><span class="sxs-lookup"><span data-stu-id="118f9-135">**All** Collects trace messages of type fatal, error, warning, verbose, and debug info to the log for the defined provider.</span></span>
    
  - <span data-ttu-id="118f9-136">**Fatal** 仅收集定义为"Fatal"的跟踪消息。</span><span class="sxs-lookup"><span data-stu-id="118f9-136">**Fatal** Collects only the trace messages defined as "Fatal."</span></span>
    
  - <span data-ttu-id="118f9-137">**错误** 仅收集定义为"Error"或"Fatal"的跟踪消息。</span><span class="sxs-lookup"><span data-stu-id="118f9-137">**Error** Collects only the trace messages defined as "Error" or "Fatal."</span></span>
    
  - <span data-ttu-id="118f9-138">**警告** 仅收集类型为"Warning"、"Error"和"Fatal"的跟踪消息。</span><span class="sxs-lookup"><span data-stu-id="118f9-138">**Warning** Collects only the trace messages of type "Warning," "Error" and "Fatal."</span></span>
    
  - <span data-ttu-id="118f9-139">**信息** 仅收集指示定义的提供程序的信息性消息的跟踪消息，以及致命、错误和警告消息。</span><span class="sxs-lookup"><span data-stu-id="118f9-139">**Info** Collects only the trace messages that indicate an informational message for the defined provider, plus fatal, error, and warning messages.</span></span>
    
  - <span data-ttu-id="118f9-140">**详细** 收集定义提供程序的类型为 fatal、error、warning 和 verbose 的所有跟踪消息。</span><span class="sxs-lookup"><span data-stu-id="118f9-140">**Verbose** Collects all trace messages of type fatal, error, warning and verbose for the defined provider.</span></span>
    
  - <span data-ttu-id="118f9-141">**调试** 它本质上等同于"全部"- 收集定义提供程序的 Fatal、Error、Warning、Info、Verbose 和 Debug 类型的跟踪。</span><span class="sxs-lookup"><span data-stu-id="118f9-141">**Debug** this is essentially an equivalent of 'All' - collects traces of type Fatal, Error, Warning, Info, Verbose and Debug for the defined provider.</span></span>
    
- <span data-ttu-id="118f9-142">**Flags** OCSLogger 提供了用于为定义可以从跟踪文件中检索的信息类型的每个提供程序选择标志的选项。</span><span class="sxs-lookup"><span data-stu-id="118f9-142">**Flags** OCSLogger provided the option to choose flags for each provider that defined what type of information you could retrieve from the trace files.</span></span> <span data-ttu-id="118f9-143">可以根据提供程序选择以下标志：</span><span class="sxs-lookup"><span data-stu-id="118f9-143">You can chose the following flags, based on the provider:</span></span>
    
  - <span data-ttu-id="118f9-144">**TF_Connection** 提供与连接相关的日志条目。</span><span class="sxs-lookup"><span data-stu-id="118f9-144">**TF_Connection** Provides connection-related log entries.</span></span> <span data-ttu-id="118f9-145">这些日志包括与特定组件建立的连接的相关信息。</span><span class="sxs-lookup"><span data-stu-id="118f9-145">These logs include information about connections established to and from a particular component.</span></span> <span data-ttu-id="118f9-146">这可能还包括大量网络级信息（即针对组件，但不包括连接的概念）。</span><span class="sxs-lookup"><span data-stu-id="118f9-146">This may also include significant network-level information (that is, for components without the concept of a connection).</span></span>
    
  - <span data-ttu-id="118f9-147">**TF_Security** 提供与安全相关的所有事件/日志条目。</span><span class="sxs-lookup"><span data-stu-id="118f9-147">**TF_Security** Provides all events/log entries related to security.</span></span> <span data-ttu-id="118f9-148">例如，对于 SipStack，它们是一些安全事件（例如，域验证失败和客户端身份验证/授权失败）。</span><span class="sxs-lookup"><span data-stu-id="118f9-148">For example, for SipStack, these are security events such as domain validation failure, and client authentication/authorization failures.</span></span>
    
  - <span data-ttu-id="118f9-149">**TF_Diag** 提供可用于诊断组件或对组件进行故障排除的诊断事件。</span><span class="sxs-lookup"><span data-stu-id="118f9-149">**TF_Diag** Provides diagnostics events that you can use to diagnose or troubleshoot the component.</span></span> <span data-ttu-id="118f9-150">例如，对于 SipStack，它们是证书失败或 DNS 警告/错误。</span><span class="sxs-lookup"><span data-stu-id="118f9-150">For example, for SipStack, these are certificate failures, or DNS warnings/errors.</span></span>
    
  - <span data-ttu-id="118f9-151">**TF_Protocol** 提供协议消息，如 SIP 和组合社区编解码器包消息。</span><span class="sxs-lookup"><span data-stu-id="118f9-151">**TF_Protocol** Provides protocol messages such as SIP and Combined Community Codec Pack messages.</span></span>
    
  - <span data-ttu-id="118f9-152">**TF_Component** 对指定为提供程序一部分的组件启用日志记录。</span><span class="sxs-lookup"><span data-stu-id="118f9-152">**TF_Component** Enables logging on the components specified as part of the providers.</span></span>
    
  - <span data-ttu-id="118f9-153">**全部** 设置可用于提供程序的所有可用标志。</span><span class="sxs-lookup"><span data-stu-id="118f9-153">**All** Sets all available flags available for the provider.</span></span>
    
### <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a><span data-ttu-id="118f9-154">查看有关现有集中日志记录服务方案提供程序的信息</span><span class="sxs-lookup"><span data-stu-id="118f9-154">To review information about existing Centralized Logging Service scenario providers</span></span>

1. <span data-ttu-id="118f9-155">启动 Skype for Business Server命令行管理程序：单击"开始"，**单击"所有** 程序"，再单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="118f9-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="118f9-156">若要查看现有提供程序的配置，请键入：</span><span class="sxs-lookup"><span data-stu-id="118f9-156">To review the configuration of existing providers, type the following:</span></span>
    
   ```PowerShell
   Get-CsClsScenario -Identity <scope and scenario name>
   ```

    <span data-ttu-id="118f9-157">例如，若要查看有关全局会议助理的信息，请键入：</span><span class="sxs-lookup"><span data-stu-id="118f9-157">For example, to review information about the global conferencing attendant, type:</span></span>
    
   ```PowerShell
   Get-CsClsScenario -Identity "global/CAA"
   ```

    <span data-ttu-id="118f9-158">此命令显示具有关联的标志、设置和组件的提供程序的列表。</span><span class="sxs-lookup"><span data-stu-id="118f9-158">The command displays a list of providers with the associated flags, settings, and components.</span></span> <span data-ttu-id="118f9-159">如果显示的信息不足或列表对于默认列表格式Windows PowerShell过长，则可以通过定义其他输出方法来显示其他信息。</span><span class="sxs-lookup"><span data-stu-id="118f9-159">If the information displayed is not enough or the list is too long for the default Windows PowerShell list format, you can display additional information by defining a different output method.</span></span> <span data-ttu-id="118f9-160">为此，请键入：</span><span class="sxs-lookup"><span data-stu-id="118f9-160">To do this, type:</span></span>
    
   ```PowerShell
   Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
   ```

    <span data-ttu-id="118f9-161">此命令的输出显示用五行格式显示的每个提供程序，以及提供程序名称、日志记录类型、日志记录级别、标志、GUID 和角色（每个提供程序位于一个单独的行上）。</span><span class="sxs-lookup"><span data-stu-id="118f9-161">The output of this command displays each provider displayed in a five line format with the provider name, type of logging, logging level, flags, GUID, and role, each one on a separate line.</span></span> 
    
### <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a><span data-ttu-id="118f9-162">定义新的集中日志记录服务方案提供程序</span><span class="sxs-lookup"><span data-stu-id="118f9-162">To define a new Centralized Logging Service scenario provider</span></span>

1. <span data-ttu-id="118f9-163">启动 Skype for Business Server命令行管理程序：单击"开始"，**单击"所有** 程序"，再单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="118f9-163">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="118f9-p113">方案提供程序包含要跟踪的组件、要使用的标志和要收集的详细信息级别。通过键入以下内容可完成此操作：</span><span class="sxs-lookup"><span data-stu-id="118f9-p113">A scenario provider consists of a component to trace, flags to use, and a level of detail to collect. You do this by typing:</span></span>
    
   ```PowerShell
   $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
   ```

    <span data-ttu-id="118f9-166">例如，定义要从 Lyss 提供程序收集的内容和详细信息级别的跟踪提供程序定义与以下内容类似：</span><span class="sxs-lookup"><span data-stu-id="118f9-166">For example, a trace provider definition that defines what to collect and to what level of detail from the Lyss provider looks like the following:</span></span>
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"
   ```

<span data-ttu-id="118f9-167">-Level 收集致命消息、错误消息、警告消息和信息消息。</span><span class="sxs-lookup"><span data-stu-id="118f9-167">The -Level collects fatal, error, warning, and information messages.</span></span> <span data-ttu-id="118f9-168">使用的标志都是为 Lyss 提供程序定义的标志，包括 TF_Connection、TF_Diag 和 TF_Protocol。定义变量 $LyssProvider 后，可以与 **New-CsClsScenario** cmdlet 一起使用它从 Lyss 提供程序收集跟踪。</span><span class="sxs-lookup"><span data-stu-id="118f9-168">The flags used are all of those defined for the Lyss provider, and include TF_Connection, TF_Diag and TF_Protocol.After the variable $LyssProvider is defined, you can use it with the **New-CsClsScenario** cmdlet to collect traces from the Lyss provider.</span></span> <span data-ttu-id="118f9-169">若要创建提供程序并将其分配给新的方案，请键入：</span><span class="sxs-lookup"><span data-stu-id="118f9-169">To complete the creation and assignment of the provider to a new scenario, type:</span></span>

```PowerShell
New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
```

<span data-ttu-id="118f9-170">其中 $LyssProvider 是包含使用 **New-CsClsProvider** 创建的定义的方案的变量。</span><span class="sxs-lookup"><span data-stu-id="118f9-170">Where $LyssProvider is the variable containing the defined scenario created with **New-CsClsProvider**.</span></span>
### <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a><span data-ttu-id="118f9-171">更改现有的集中日志记录服务方案提供程序</span><span class="sxs-lookup"><span data-stu-id="118f9-171">To change an existing Centralized Logging Service scenario provider</span></span>

1. <span data-ttu-id="118f9-172">启动 Skype for Business Server命令行管理程序：单击"开始"，**单击"所有** 程序"，再单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="118f9-172">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="118f9-173">若要更新或更改现有提供程序的配置，请键入：</span><span class="sxs-lookup"><span data-stu-id="118f9-173">To update or change the configuration of an existing provider, type:</span></span>
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
   ```

    <span data-ttu-id="118f9-174">然后，通过键入以下内容来更新方案以分配提供程序：</span><span class="sxs-lookup"><span data-stu-id="118f9-174">You then update the scenario to assign the provider by typing the following:</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
   ```

<span data-ttu-id="118f9-175">此命令的最终结果是方案 site:Redmond/RedmondLyssInfo 将获得提供程序的更新标志和级别。</span><span class="sxs-lookup"><span data-stu-id="118f9-175">The end result of the command is that the scenario site:Redmond/RedmondLyssInfo will have updated flags and level for the provider assigned to it.</span></span> <span data-ttu-id="118f9-176">可通过使用 Get-CsClsScenario 查看新方案。</span><span class="sxs-lookup"><span data-stu-id="118f9-176">You can view the new scenario by using Get-CsClsScenario.</span></span> <span data-ttu-id="118f9-177">有关详细信息，请参阅 [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="118f9-177">For details, see [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).</span></span>
> [!CAUTION]
> <span data-ttu-id="118f9-178">**New-ClsCsProvider** 不会检查以确定标志是否有效。</span><span class="sxs-lookup"><span data-stu-id="118f9-178">**New-ClsCsProvider** does not check to determine whether the flags are valid.</span></span> <span data-ttu-id="118f9-179">请确保标志（例如，TF_DIAG 或 TF_CONNECTION）的拼写正确。</span><span class="sxs-lookup"><span data-stu-id="118f9-179">Make sure that the spelling of the flags (for example, TF_DIAG or TF_CONNECTION) is spelled correctly.</span></span> <span data-ttu-id="118f9-180">如果标志的拼写不正确，则提供程序无法返回预期日志信息。</span><span class="sxs-lookup"><span data-stu-id="118f9-180">If the flags are not spelled correctly, the provider cannot return the expected log information.</span></span>
  
<span data-ttu-id="118f9-181">若要将其他提供程序添加到此方案，请键入：</span><span class="sxs-lookup"><span data-stu-id="118f9-181">If you want to add additional providers to this scenario, type the following:</span></span>

```PowerShell
Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}
```

<span data-ttu-id="118f9-182">其中，将通过已使用 **New-CsClsProvider** 过程定义的 Add 指令来定义每个提供程序。</span><span class="sxs-lookup"><span data-stu-id="118f9-182">Where each provider defined with the Add directive has already been defined using the **New-CsClsProvider** process.</span></span>
### <a name="to-remove-a-scenario-provider"></a><span data-ttu-id="118f9-183">删除方案提供程序</span><span class="sxs-lookup"><span data-stu-id="118f9-183">To remove a scenario provider</span></span>

1. <span data-ttu-id="118f9-184">启动 Skype for Business Server命令行管理程序：单击"开始"，**单击"所有** 程序"，再单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="118f9-184">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="118f9-185">可利用提供的 cmdlet 更新现有提供程序并创建新的提供程序。</span><span class="sxs-lookup"><span data-stu-id="118f9-185">The cmdlets provided allow you to update existing providers and create new providers.</span></span> <span data-ttu-id="118f9-186">若要删除提供程序，您必须对 **Set-CsClsScenario** 的 Provider 参数使用 Replace 指令。</span><span class="sxs-lookup"><span data-stu-id="118f9-186">To remove a provider, you must use the Replace directive for the Provider parameter to **Set-CsClsScenario**.</span></span> <span data-ttu-id="118f9-187">完全删除提供程序的唯一方式是，将提供程序替换为具有相同名称的重定义的提供程序并使用 Update 指令。</span><span class="sxs-lookup"><span data-stu-id="118f9-187">The only way to completely remove a provider is to replace it with a redefined provider of the same name and use the Update directive.</span></span> <span data-ttu-id="118f9-188">例如，使用 WPP 将提供程序 LyssProvider 定义为日志类型，将级别设置为“Debug”，则标志集为 TF_CONNECTION 和 TF_DIAG。</span><span class="sxs-lookup"><span data-stu-id="118f9-188">For example, our provider LyssProvider is defined with WPP as the log type, level set to Debug, and flags set are TF_CONNECTION and TF_DIAG.</span></span> <span data-ttu-id="118f9-189">您需要将标志更改为"All"。</span><span class="sxs-lookup"><span data-stu-id="118f9-189">You need to change the flags to "All".</span></span> <span data-ttu-id="118f9-190">若要更改提供程序，请键入：</span><span class="sxs-lookup"><span data-stu-id="118f9-190">To change the provider, type the following:</span></span>
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"
   ```

   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}
   ```

3. <span data-ttu-id="118f9-191">若要完全删除方案及其关联的提供程序，请键入：</span><span class="sxs-lookup"><span data-stu-id="118f9-191">If you want to completely remove a scenario and the providers associated with it, type the following:</span></span>
    
   ```PowerShell
   Remove-CsClsScenario -Identity <scope and name of scenario>
   ```

    <span data-ttu-id="118f9-192">例如：</span><span class="sxs-lookup"><span data-stu-id="118f9-192">For example:</span></span>
    
   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
   ```

    > [!CAUTION]
    > <span data-ttu-id="118f9-193">cmdlet **Remove-CsClsScenario** 不会提示您进行确认。</span><span class="sxs-lookup"><span data-stu-id="118f9-193">The cmdlet **Remove-CsClsScenario** does not prompt you for confirmation.</span></span> <span data-ttu-id="118f9-194">方案将连同已分配给它的提供程序一起被删除。</span><span class="sxs-lookup"><span data-stu-id="118f9-194">The scenario is deleted, along with the providers that were assigned to it.</span></span> <span data-ttu-id="118f9-195">可通过重新运行最初用于创建方案的命令来重新创建方案。</span><span class="sxs-lookup"><span data-stu-id="118f9-195">You can recreate the scenario by re-running the commands used to create it initially.</span></span> <span data-ttu-id="118f9-196">没有用于恢复已删除的方案或提供程序的过程。</span><span class="sxs-lookup"><span data-stu-id="118f9-196">There is no procedure to recover removed scenarios or providers.</span></span>
  
<span data-ttu-id="118f9-197">在使用 **Remove-CsClsScenario** cmdlet 删除一个方案时，可以从作用域中完全删除此方案。</span><span class="sxs-lookup"><span data-stu-id="118f9-197">When you remove a scenario by using the **Remove-CsClsScenario** cmdlet, you completely remove the scenario from the scope.</span></span> <span data-ttu-id="118f9-198">若要使用已创建的方案以及作为该方案的一部分的提供程序，可以创建新的提供程序并将其分配给新方案。</span><span class="sxs-lookup"><span data-stu-id="118f9-198">To use the scenarios that you created and the providers that were a part of the scenario, you create new providers and assign them to a new scenario.</span></span>
## <a name="see-also"></a><span data-ttu-id="118f9-199">另请参阅</span><span class="sxs-lookup"><span data-stu-id="118f9-199">See also</span></span>

[<span data-ttu-id="118f9-200">Get-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="118f9-200">Get-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="118f9-201">New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="118f9-201">New-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="118f9-202">Remove-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="118f9-202">Remove-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="118f9-203">Set-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="118f9-203">Set-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="118f9-204">New-CsClsProvider</span><span class="sxs-lookup"><span data-stu-id="118f9-204">New-CsClsProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps)
