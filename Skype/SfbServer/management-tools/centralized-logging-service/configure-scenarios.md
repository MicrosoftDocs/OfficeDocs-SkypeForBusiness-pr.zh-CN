---
title: 配置 Skype for Business Server 2015 中的集中日志记录服务的方案
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
description: 摘要：了解如何在 Skype for business Server 2015 中创建、修改和删除集中日志记录服务的方案。
ms.openlocfilehash: 9a6ce9a760255275c3ad265cdd6c58fa964f8e43
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991597"
---
# <a name="configure-scenarios-for-the-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="51181-103">配置 Skype for Business Server 2015 中的集中日志记录服务的方案</span><span class="sxs-lookup"><span data-stu-id="51181-103">Configure scenarios for the Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="51181-104">**摘要：** 了解如何在 Skype for business Server 2015 中创建、修改和删除集中式日志记录服务的方案。</span><span class="sxs-lookup"><span data-stu-id="51181-104">**Summary:** Learn how to create, modify, and remove scenarios for the Centralized Logging Service in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="51181-105">方案定义了范围（即全局、网站、池或计算机）以及要在集中日志记录服务中使用的提供程序。</span><span class="sxs-lookup"><span data-stu-id="51181-105">Scenarios define the scope (that is, global, site, pool, or computer) and what providers to use in the Centralized Logging Service.</span></span> <span data-ttu-id="51181-106">通过使用方案，可以启用或禁用对提供程序进行的跟踪（例如，S4、SIPStack、IM 和 Presence）。</span><span class="sxs-lookup"><span data-stu-id="51181-106">By using scenarios, you enable or disable tracing on providers (for example, S4, SIPStack, IM, and Presence).</span></span> <span data-ttu-id="51181-107">通过配置方案，可将针对给定逻辑集合的、满足某个特定问题条件的所有提供程序组合在一起。</span><span class="sxs-lookup"><span data-stu-id="51181-107">By configuring a scenario, you can group all of the providers for a given logical collection that address a specific problem condition.</span></span> <span data-ttu-id="51181-108">如果你发现需要修改方案以满足你的疑难解答和日志记录需求，则 Skype for Business Server 2015 调试工具将向你提供名为 ClsScenarioEdit 的 Windows PowerShell 模块，该模块包含 namedEdit-CsClsScenario 函数的 psm1。</span><span class="sxs-lookup"><span data-stu-id="51181-108">If you find that a scenario needs to be modified to meet your troubleshooting and logging needs, the Skype for Business Server 2015 Debug Tools provides you a Windows PowerShell module named ClsScenarioEdit.psm1 that contains a function namedEdit-CsClsScenario.</span></span> <span data-ttu-id="51181-109">此模块的用途是编辑命名的方案的属性。</span><span class="sxs-lookup"><span data-stu-id="51181-109">The purpose of the module is to edit the properties of the named scenario.</span></span> <span data-ttu-id="51181-110">本主题提供了此模块的工作方式的示例。</span><span class="sxs-lookup"><span data-stu-id="51181-110">Examples of how this module works are provided in this topic.</span></span> <span data-ttu-id="51181-111">下载 Skype for Business Server 2015[调试工具](https://go.microsoft.com/fwlink/p/?LinkId=285257)，然后再继续。</span><span class="sxs-lookup"><span data-stu-id="51181-111">Download the Skype for Business Server 2015 [Debugging Tools](https://go.microsoft.com/fwlink/p/?LinkId=285257) before going any further.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="51181-112">对于任何给定的范围（站点、全局、池或计算机），您可以在任何给定时间最多运行两个方案。</span><span class="sxs-lookup"><span data-stu-id="51181-112">For any given scope—site, global, pool or computer—you can run a maximum of two scenarios at any given time.</span></span> <span data-ttu-id="51181-113">若要确定当前正在运行的方案，请使用 Windows PowerShell 和[CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="51181-113">To determine which scenarios are currently running, use Windows PowerShell and [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).</span></span> <span data-ttu-id="51181-114">通过使用 Windows PowerShell 和[CsClsScenario 设置](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps)，你可以动态更改正在运行的方案。</span><span class="sxs-lookup"><span data-stu-id="51181-114">By using Windows PowerShell and [Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps), you can dynamically change which scenarios are running.</span></span> <span data-ttu-id="51181-115">可以在日志记录会话期间修改正在运行的方案，以调整或优化所收集的数据以及源提供程序。</span><span class="sxs-lookup"><span data-stu-id="51181-115">You can modify which scenarios are running during a logging session to adjust or refine the data you are collecting and from which providers.</span></span> 
  
<span data-ttu-id="51181-116">若要使用 Skype for Business Server Management Shell 运行集中式日志记录服务功能，您必须是 CsAdministrator 或 CsServerAdministrator 基于角色的访问控制（RBAC）安全组的成员，或者是一个自定义的 RBAC 角色，包含这两个组中的任何一个。</span><span class="sxs-lookup"><span data-stu-id="51181-116">To run the Centralized Logging Service functions by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="51181-117">若要返回此 cmdlet 已分配到的所有 RBAC 角色的列表，包括你自己创建的任何自定义 RBAC 角色，请从 Skype for Business Server Management Shell 或 Windows PowerShell 提示中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="51181-117">To return a list of all the RBAC roles this cmdlet has been assigned to, including any custom RBAC roles you have created yourself, run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="51181-118">例如：</span><span class="sxs-lookup"><span data-stu-id="51181-118">For example:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="51181-119">本主题的其余部分重点说明了如何定义方案、修改方案、检索正在运行的方案、删除方案以及指定方案为优化故障排除而包含的内容。</span><span class="sxs-lookup"><span data-stu-id="51181-119">The remainder of this topic focuses on how to define a scenario, modify a scenario, retrieve what scenarios are running, remove a scenario, and specify what a scenario contains to optimize your troubleshooting.</span></span> <span data-ttu-id="51181-120">你可以使用 Skype for Business Server Management Shell 颁发 Windows PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="51181-120">You can use the Skype for Business Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="51181-121">使用 Windows PowerShell 时，可以定义要在日志记录会话中使用的新方案。</span><span class="sxs-lookup"><span data-stu-id="51181-121">When you use Windows PowerShell, you can define new scenarios for use in your logging sessions.</span></span>
  
<span data-ttu-id="51181-122">在[Skype For business 2015 的集中式日志记录服务](centralized-logging-service.md)中引入时，方案的元素如下所示：</span><span class="sxs-lookup"><span data-stu-id="51181-122">As introduced in [Centralized Logging Service in Skype for Business 2015](centralized-logging-service.md), the elements of a scenario are:</span></span>
  
- <span data-ttu-id="51181-123">**提供商**如果你熟悉 OCSLogger，则提供的组件是你选择的组件，用于告诉 OCSLogger 跟踪引擎应从哪些内容收集日志。</span><span class="sxs-lookup"><span data-stu-id="51181-123">**Providers** If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="51181-124">提供程序是一些相同的组件，在许多情况下，它们的名称与 OCSLogger 中组件的名称相同。</span><span class="sxs-lookup"><span data-stu-id="51181-124">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="51181-125">如果您不熟悉 OCSLogger，则提供商是集中式日志记录服务可以从中收集日志的服务器角色特定组件。</span><span class="sxs-lookup"><span data-stu-id="51181-125">If you are not familiar with OCSLogger, providers are server role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="51181-126">有关提供程序配置的详细信息，请参阅[在 Skype for Business Server 2015 中配置用于集中日志记录服务的提供商](configure-providers.md)。</span><span class="sxs-lookup"><span data-stu-id="51181-126">For details about the configuration of providers, see [Configure providers for Centralized Logging Service in Skype for Business Server 2015](configure-providers.md).</span></span>
    
- <span data-ttu-id="51181-127">**标识**参数标识设置方案的范围和名称。</span><span class="sxs-lookup"><span data-stu-id="51181-127">**Identity** The parameter -Identity sets the scope and name of the scenario.</span></span> <span data-ttu-id="51181-128">例如，你可以设置 "global" 的范围并使用 "LyssServiceScenario" 标识方案。</span><span class="sxs-lookup"><span data-stu-id="51181-128">For example, you could set a scope of "global" and identify the scenario with "LyssServiceScenario".</span></span> <span data-ttu-id="51181-129">组合两个时，定义标识（例如，"global/LyssServiceScenario"）。</span><span class="sxs-lookup"><span data-stu-id="51181-129">When you combine the two, you define the Identity (for example, "global/LyssServiceScenario").</span></span>
    
    <span data-ttu-id="51181-130">或者，你可以使用-Name 和-Parent 参数。</span><span class="sxs-lookup"><span data-stu-id="51181-130">Optionally, you can use the -Name and -Parent parameters.</span></span> <span data-ttu-id="51181-131">定义 Name 参数可对方案进行唯一标识。</span><span class="sxs-lookup"><span data-stu-id="51181-131">You define the Name parameter to uniquely identify the scenario.</span></span> <span data-ttu-id="51181-132">如果使用 Name，则还必须使用 Parent 将方案添加到全局或站点范围中。</span><span class="sxs-lookup"><span data-stu-id="51181-132">If you use Name, you must also use Parent to add the scenario to either global or site.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="51181-133">如果使用 Name 和 Parent 参数，则不能使用 **-Identity**参数。</span><span class="sxs-lookup"><span data-stu-id="51181-133">If you use the Name and Parent parameters, you cannot use the **-Identity** parameter.</span></span>
  
### <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="51181-134">使用 New-CsClsScenario cmdlet 创建新的方案</span><span class="sxs-lookup"><span data-stu-id="51181-134">To create a new scenario with the New-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="51181-135">启动 Skype for Business Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\* 和“Skype for Business 2015”\*\*\*\*，然后单击“Skype for Business Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="51181-135">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="51181-p108">若要为日志记录会话创建新的方案，请使用 [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps) 并定义方案的名称（即，对方案进行唯一标识的方式）。从 WPP 中选择日志记录格式的类型（即，Windows 软件跟踪预处理器和其默认值）、EventLog（即，Windows 事件日志格式）或 IISLog（即，基于 IIS 日志文件格式的 ASCII 格式文件）。然后，定义级别（如本主题中的“日志记录级别”下所述）和标志（如本主题中的“标志”下所述）。</span><span class="sxs-lookup"><span data-stu-id="51181-p108">To create a new scenario for a logging session, use [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps) and define the name of the scenario (that is, how it will be uniquely identified). Choose a type of logging format from WPP (that is, Windows software tracing preprocessor and is the default), EventLog (that is, Windows event log format), or IISLog (that is, ASCII format file based on the IIS log file format). Next, define Level (as the defined under Logging Levels in this topic), and Flags (as defined under Flags in this topic).</span></span>
    
    <span data-ttu-id="51181-139">对于此示例方案，我们将 LyssProvider 用作示例提供程序变量。</span><span class="sxs-lookup"><span data-stu-id="51181-139">For this example scenario, we use LyssProvider as the example provider variable.</span></span>
    
    <span data-ttu-id="51181-140">若要使用定义的选项创建方案，请键入：</span><span class="sxs-lookup"><span data-stu-id="51181-140">To create a scenario using the options defined, type:</span></span>
    
   ```PowerShell
   New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
   ```

    <span data-ttu-id="51181-141">例如：</span><span class="sxs-lookup"><span data-stu-id="51181-141">For example:</span></span>
    
   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
   ```

    <span data-ttu-id="51181-142">使用-Name 和-Parent 的备用格式：</span><span class="sxs-lookup"><span data-stu-id="51181-142">The alternate format using -Name and -Parent:</span></span>
    
   ```PowerShell
   New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider
   ```

### <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="51181-143">使用带 New-CsClsScenario cmdlet 的多个提供程序创建新的方案</span><span class="sxs-lookup"><span data-stu-id="51181-143">To create a new scenario with multiple providers with the New-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="51181-144">启动 Skype for Business Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\* 和“Skype for Business 2015”\*\*\*\*，然后单击“Skype for Business Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="51181-144">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="51181-145">每个范围只能有两个方案。</span><span class="sxs-lookup"><span data-stu-id="51181-145">You are limited to two scenarios per scope.</span></span> <span data-ttu-id="51181-146">但是，你不受限于一组提供程序的数量限制。</span><span class="sxs-lookup"><span data-stu-id="51181-146">However, you are not limited to a set number of providers.</span></span> <span data-ttu-id="51181-147">在此示例中，假设我们创建了三个提供程序，并且你希望将所有三个提供程序分配给你定义的方案。</span><span class="sxs-lookup"><span data-stu-id="51181-147">In this example, assume that we have created three providers, and you want to assign all three to the scenario you are defining.</span></span> <span data-ttu-id="51181-148">提供程序变量名称为 LyssProvider、ABServerProvider 和 SIPStackProvider。</span><span class="sxs-lookup"><span data-stu-id="51181-148">The provider variable names are LyssProvider, ABServerProvider, and SIPStackProvider.</span></span> <span data-ttu-id="51181-149">若要定义多个提供程序并将其分配给某个方案，请在 Skype for Business 服务器命令行管理程序或 Windows PowerShell 命令提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="51181-149">To define and assign multiple providers to a scenario, type the following at a Skype for Business Server Management Shell or Windows PowerShell command prompt:</span></span>
    
   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
   ```

    > [!NOTE]
    > <span data-ttu-id="51181-150">正如 Windows PowerShell 中已知的那样，创建值的哈希表的约定`@{<variable>=<value1>, <value2>, <value>…}`是已知的 assplatting。</span><span class="sxs-lookup"><span data-stu-id="51181-150">As it is known in Windows PowerShell, the convention for creating a hash table of values using  `@{<variable>=<value1>, <value2>, <value>…}` is known assplatting.</span></span> <span data-ttu-id="51181-151">有关 Windows PowerShell 中的 splatting 的详细信息[https://go.microsoft.com/fwlink/p/?LinkId=267760](https://go.microsoft.com/fwlink/p/?LinkId=267760)，请参阅。</span><span class="sxs-lookup"><span data-stu-id="51181-151">For details about splatting in Windows PowerShell, see [https://go.microsoft.com/fwlink/p/?LinkId=267760](https://go.microsoft.com/fwlink/p/?LinkId=267760).</span></span> 
  
### <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a><span data-ttu-id="51181-152">使用 Set-CsClsScenario cmdlet 修改现有方案</span><span class="sxs-lookup"><span data-stu-id="51181-152">To modify an existing scenario with the Set-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="51181-153">启动 Skype for Business Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\* 和“Skype for Business 2015”\*\*\*\*，然后单击“Skype for Business Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="51181-153">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="51181-154">每个范围只能有两个方案。</span><span class="sxs-lookup"><span data-stu-id="51181-154">You are limited to two scenarios per scope.</span></span> <span data-ttu-id="51181-155">您可以随时更改正在运行的方案，即使日志记录捕获会话正在进行中也是如此。</span><span class="sxs-lookup"><span data-stu-id="51181-155">You can change which scenarios are running at any time, even when a logging capture session is in process.</span></span> <span data-ttu-id="51181-156">如果您重新定义正在运行的方案，则当前日志记录会话将停止使用已删除的方案，并开始使用新方案。</span><span class="sxs-lookup"><span data-stu-id="51181-156">If you redefine the running scenarios, the current logging session will stop using the scenario that was removed and then begin using the new scenario.</span></span> <span data-ttu-id="51181-157">但是，已通过删除的方案捕获到的日志记录信息将保留在捕获的日志中。</span><span class="sxs-lookup"><span data-stu-id="51181-157">However, the logging information that was captured with the removed scenario remains in the captured logs.</span></span> <span data-ttu-id="51181-158">若要定义新方案，请执行下列操作（即假设添加了名为 "S4Provider" 的已定义提供程序）：</span><span class="sxs-lookup"><span data-stu-id="51181-158">To define a new scenario, do the following (that is, assuming the addition of an already defined provider named "S4Provider"):</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
   ```

    <span data-ttu-id="51181-159">例如：</span><span class="sxs-lookup"><span data-stu-id="51181-159">For example:</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
   ```

    <span data-ttu-id="51181-p112">若要替换提供程序，请定义一个提供程序或一个以逗号分隔的提供程序列表来替换当前集。如果您只需要替换多个提供程序之一，请将当前提供程序与新的提供程序一起添加以创建同时包含新提供程序和现有提供程序的新提供程序集。若要将所有提供程序替换为新集，请键入：</span><span class="sxs-lookup"><span data-stu-id="51181-p112">If you want to replace providers, define a single provider or a comma separated list of providers to replace the current set. If you only want to replace one of many providers, add the current providers with the new providers to create a new set of providers that contains both new providers and existing providers. To replace all providers with a new set, type the following:</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
   ```

    <span data-ttu-id="51181-163">例如，将 $LyssProvider、$ABServerProvider 和 $SIPStackProvider 的当前集替换为 $LyssServiceProvider：</span><span class="sxs-lookup"><span data-stu-id="51181-163">For example, to replace the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider:</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
   ```

    <span data-ttu-id="51181-164">若只将 $LyssProvider、$ABServerProvider 和 $SIPStackProvider 的当前集中的 $LyssProvider 提供程序替换为 $LyssServiceProvider，请键入：</span><span class="sxs-lookup"><span data-stu-id="51181-164">To replace just the $LyssProvider provider from the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider, type the following:</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}
   ```

### <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a><span data-ttu-id="51181-165">使用 Remove-CsClsScenario cmdlet 删除现有方案</span><span class="sxs-lookup"><span data-stu-id="51181-165">To remove an existing scenario with the Remove-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="51181-166">启动 Skype for Business Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\* 和“Skype for Business 2015”\*\*\*\*，然后单击“Skype for Business Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="51181-166">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="51181-167">若要删除之前已定义的方案，请键入：</span><span class="sxs-lookup"><span data-stu-id="51181-167">If you want to remove a scenario that has been previously defined, type the following:</span></span>
    
   ```PowerShell
   Remove-CsClsScenario -Identity <name of scope and scenario>
   ```

    <span data-ttu-id="51181-168">例如，删除定义的方案 site:Redmond/LyssServiceScenario：</span><span class="sxs-lookup"><span data-stu-id="51181-168">For example, to remove the defined scenario site:Redmond/LyssServiceScenario:</span></span>
    
   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"
   ```

<span data-ttu-id="51181-169">**Remove-CsClsScenario** cmdlet 可删除指定的方案，但已捕获的跟踪信息仍将保留在日志中以供您搜索。</span><span class="sxs-lookup"><span data-stu-id="51181-169">The **Remove-CsClsScenario** cmdlet removes the specified scenario, but the traces that have been captured are still available in the logs for you to search on.</span></span>
### <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clsscenarioeditpsm1-module"></a><span data-ttu-id="51181-170">使用 ClsScenarioEdit.psm1 模块加载和卸载 Edit-CsClsScenario cmdlet</span><span class="sxs-lookup"><span data-stu-id="51181-170">To load and unload the Edit-CsClsScenario cmdlet using the ClsScenarioEdit.psm1 module</span></span>

1. <span data-ttu-id="51181-171">启动 Skype for Business Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\* 和“Skype for Business 2015”\*\*\*\*，然后单击“Skype for Business Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="51181-171">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="51181-172">ClsScenarioEdit.psm1 模块是作为单独的 Web 下载提供的。</span><span class="sxs-lookup"><span data-stu-id="51181-172">The ClsScenarioEdit.psm1 module is provided as a separate Web download.</span></span> <span data-ttu-id="51181-173">该模块是 Skype for Business Server 2015 调试工具的一部分。</span><span class="sxs-lookup"><span data-stu-id="51181-173">The module is part of the Skype for Business Server 2015 Debugging tools.</span></span> <span data-ttu-id="51181-174">默认情况下，调试工具将安装到目录 C:\Program Files\Skype for Business Server 2015\Debugging Tools 中。</span><span class="sxs-lookup"><span data-stu-id="51181-174">By default, the debugging tools are installed in the directory C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> 
  
2. <span data-ttu-id="51181-175">在 Windows PowerShell 中，键入：</span><span class="sxs-lookup"><span data-stu-id="51181-175">From the Windows PowerShell, type:</span></span>
    
   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > <span data-ttu-id="51181-176">成功加载该模块后，将返回到 Windows PowerShell 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="51181-176">Successful loading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="51181-177">若要确认是否已加载模块且 CsClsScenario 可用的编辑，请键入`Get-Help Edit-CsClsScenario`。</span><span class="sxs-lookup"><span data-stu-id="51181-177">To confirm that the module is loaded and that Edit-CsClsScenario is available, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="51181-178">您应看到 EditCsClsScenario 的语法的基本概要。</span><span class="sxs-lookup"><span data-stu-id="51181-178">You should see the basic synopsis of the syntax for EditCsClsScenario.</span></span> 
  
3. <span data-ttu-id="51181-179">若要卸载模块，请键入：</span><span class="sxs-lookup"><span data-stu-id="51181-179">To unload the modules, type:</span></span>
    
   ```PowerShell
   Remove-Module ClsController
   ```

    > [!TIP]
    > <span data-ttu-id="51181-180">成功卸载该模块后，将返回到 Windows PowerShell 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="51181-180">Successful unloading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="51181-181">若要确认卸载了该模块，请`Get-Help Edit-CsClsScenario`键入。</span><span class="sxs-lookup"><span data-stu-id="51181-181">To confirm that the module is unloaded, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="51181-182">Windows PowerShell 将尝试查找 cmdlet 的帮助并失败。</span><span class="sxs-lookup"><span data-stu-id="51181-182">Windows PowerShell will attempt to locate the help for the cmdlet and fail.</span></span> 
  
### <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="51181-183">使用 Edit-ClsController 模块从方案中删除现有提供程序</span><span class="sxs-lookup"><span data-stu-id="51181-183">To remove an existing provider from a scenario with the Edit-ClsController module</span></span>

1. <span data-ttu-id="51181-184">启动 Skype for Business Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\* 和“Skype for Business 2015”\*\*\*\*，然后单击“Skype for Business Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="51181-184">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="51181-185">在 Windows PowerShell 中，键入：</span><span class="sxs-lookup"><span data-stu-id="51181-185">From the Windows PowerShell, type:</span></span>
    
   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > <span data-ttu-id="51181-186">成功加载该模块后，将返回到 Windows PowerShell 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="51181-186">Successful loading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="51181-187">若要确认是否已加载模块且 CsClsScenario 可用的编辑，请键入`Get-Help Edit-CsClsScenario`。</span><span class="sxs-lookup"><span data-stu-id="51181-187">To confirm that the module is loaded and that Edit-CsClsScenario is available, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="51181-188">您应看到 EditCsClsScenario 的语法的基本概要。</span><span class="sxs-lookup"><span data-stu-id="51181-188">You should see the basic synopsis of the syntax for EditCsClsScenario.</span></span> 
  
3. <span data-ttu-id="51181-189">若要从 AlwaysOn 方案中删除提供程序，请键入：</span><span class="sxs-lookup"><span data-stu-id="51181-189">To remove a provider from the AlwaysOn scenario, type:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
   ```

   <span data-ttu-id="51181-190">例如：</span><span class="sxs-lookup"><span data-stu-id="51181-190">For Example:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
   ```

   <span data-ttu-id="51181-p117">参数 ScenarioName 和 ProviderName 是定位参数（也就是说，必须在命令行中的预期位置定义这两个参数）。如果相对于位置 1 的 cmdlet 的名称，方案名称位于位置 2 且提供程序位于位置 3，则无需显式定义参数名称。通过使用此信息，可以按以下形式键入上一个命令：</span><span class="sxs-lookup"><span data-stu-id="51181-p117">The parameters ScenarioName and ProviderName are positional (that is, they must be defined in the expected position in the command line) parameters. The parameter name does not have to be explicitly defined if the scenario name is in position two and the provider is in position three, relative to the name of the cmdlet as position one. Using this information, the previous command would be typed as:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Remove
   ```

   <span data-ttu-id="51181-194">参数值的放置位置仅适用于-方案和-提供程序。</span><span class="sxs-lookup"><span data-stu-id="51181-194">The positional placing of the parameter values applies only to -Scenario and -Provider.</span></span> <span data-ttu-id="51181-195">必须显式定义所有其他参数。</span><span class="sxs-lookup"><span data-stu-id="51181-195">All other parameters must be explicitly defined.</span></span>
    
### <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="51181-196">使用 Edit-ClsController 模块将提供程序添加到方案</span><span class="sxs-lookup"><span data-stu-id="51181-196">To add a provider to a scenario with the Edit-ClsController module</span></span>

1. <span data-ttu-id="51181-197">启动 Skype for Business Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\* 和“Skype for Business 2015”\*\*\*\*，然后单击“Skype for Business Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="51181-197">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="51181-198">若要将提供程序添加到 AlwaysOn 方案，请键入：</span><span class="sxs-lookup"><span data-stu-id="51181-198">To add a provider to the AlwaysOn scenario, type:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
   ```

    <span data-ttu-id="51181-199">例如：</span><span class="sxs-lookup"><span data-stu-id="51181-199">For Example:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
   ```

    <span data-ttu-id="51181-200">-Loglevel 的类型可以是 Fatal、Error、Warning、Info、Verbose、Debug 或 All。</span><span class="sxs-lookup"><span data-stu-id="51181-200">-Loglevel can be of the type Fatal, Error, Warning, Info, Verbose, Debug, or All.</span></span> <span data-ttu-id="51181-201">-标志可以是提供程序支持的任何标志，例如 TF_COMPONENT、TF_DIAG。</span><span class="sxs-lookup"><span data-stu-id="51181-201">-Flags can be any of the flags that the provider supports, such as TF_COMPONENT, TF_DIAG.</span></span> <span data-ttu-id="51181-202">-标志也可以是 "全部" 值</span><span class="sxs-lookup"><span data-stu-id="51181-202">-Flags can also be of value ALL</span></span>
    
   <span data-ttu-id="51181-p120">还可以使用 cmdlet 的定位功能键入上一个示例。例如，若要将提供程序 ChatServer 添加到 AlwaysOn 方案，请键入：</span><span class="sxs-lookup"><span data-stu-id="51181-p120">The previous example can also be typed using the positional feature of the cmdlet. For example, to add the provider ChatServer to the AlwaysOn scenario, type:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL
   ```
