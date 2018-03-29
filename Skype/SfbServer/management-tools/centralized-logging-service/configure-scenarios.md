---
title: 配置 Skype for Business Server 2015 中的集中日志记录服务的方案
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
description: 摘要： 了解如何创建、 修改和删除在集中式日志记录服务 Skype 在业务服务器 2015年方案。
ms.openlocfilehash: e8b9575ed949e1769e867113be301deede981018
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-scenarios-for-the-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="944e4-103">配置 Skype for Business Server 2015 中的集中日志记录服务的方案</span><span class="sxs-lookup"><span data-stu-id="944e4-103">Configure scenarios for the Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="944e4-104">**摘要：**了解如何创建、 修改和删除在集中式日志记录服务 Skype 在业务服务器 2015年方案。</span><span class="sxs-lookup"><span data-stu-id="944e4-104">**Summary:** Learn how to create, modify, and remove scenarios for the Centralized Logging Service in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="944e4-105">方案定义的作用域 （即全局站点、 池或计算机） 和内容提供商在集中式日志记录服务中使用。</span><span class="sxs-lookup"><span data-stu-id="944e4-105">Scenarios define the scope (that is, global, site, pool, or computer) and what providers to use in the Centralized Logging Service.</span></span> <span data-ttu-id="944e4-106">通过使用方案，可以启用或禁用对提供程序进行的跟踪（例如，S4、SIPStack、IM 和 Presence）。</span><span class="sxs-lookup"><span data-stu-id="944e4-106">By using scenarios, you enable or disable tracing on providers (for example, S4, SIPStack, IM, and Presence).</span></span> <span data-ttu-id="944e4-107">通过配置方案，可将针对给定逻辑集合的、满足某个特定问题条件的所有提供程序组合在一起。</span><span class="sxs-lookup"><span data-stu-id="944e4-107">By configuring a scenario, you can group all of the providers for a given logical collection that address a specific problem condition.</span></span> <span data-ttu-id="944e4-108">如果您发现需要进行修改以满足故障诊断并记录需求的方案，为业务服务器 2015年调试工具 Skype 提供了一个名为 ClsScenarioEdit.psm1，其中包含函数的 namedEdit CsClsScenario 的 Windows PowerShell 模块。</span><span class="sxs-lookup"><span data-stu-id="944e4-108">If you find that a scenario needs to be modified to meet your troubleshooting and logging needs, the Skype for Business Server 2015 Debug Tools provides you a Windows PowerShell module named ClsScenarioEdit.psm1 that contains a function namedEdit-CsClsScenario.</span></span> <span data-ttu-id="944e4-109">此模块的用途是编辑命名的方案的属性。</span><span class="sxs-lookup"><span data-stu-id="944e4-109">The purpose of the module is to edit the properties of the named scenario.</span></span> <span data-ttu-id="944e4-110">本主题提供了此模块的工作方式的示例。</span><span class="sxs-lookup"><span data-stu-id="944e4-110">Examples of how this module works are provided in this topic.</span></span> <span data-ttu-id="944e4-111">在进行下一步之前业务服务器 2015年[的调试工具](https://go.microsoft.com/fwlink/p/?LinkId=285257)下载 Skype。</span><span class="sxs-lookup"><span data-stu-id="944e4-111">Download the Skype for Business Server 2015 [Debugging Tools](https://go.microsoft.com/fwlink/p/?LinkId=285257) before going any further.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="944e4-112">对于任何给定的范围（站点、全局、池或计算机），您可以在任何给定时间最多运行两个方案。</span><span class="sxs-lookup"><span data-stu-id="944e4-112">For any given scope—site, global, pool or computer—you can run a maximum of two scenarios at any given time.</span></span> <span data-ttu-id="944e4-113">若要确定当前正在运行的情况下，使用 Windows PowerShell 和[Get CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="944e4-113">To determine which scenarios are currently running, use Windows PowerShell and [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).</span></span> <span data-ttu-id="944e4-114">通过使用 Windows PowerShell 和[一组 CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps)，可以动态更改运行哪些方案。</span><span class="sxs-lookup"><span data-stu-id="944e4-114">By using Windows PowerShell and [Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps), you can dynamically change which scenarios are running.</span></span> <span data-ttu-id="944e4-115">可以在日志记录会话期间修改正在运行的方案，以调整或优化所收集的数据以及源提供程序。</span><span class="sxs-lookup"><span data-stu-id="944e4-115">You can modify which scenarios are running during a logging session to adjust or refine the data you are collecting and from which providers.</span></span> 
  
<span data-ttu-id="944e4-116">若要通过 Skype 业务服务器管理外壳程序运行的集中式日志记录服务功能，您必须是 CsAdministrator 或 CsServerAdministrator 基于角色的访问控制 (RBAC) 的安全组中，或自定义的 RBAC 角色的成员，包含这两个组之一。</span><span class="sxs-lookup"><span data-stu-id="944e4-116">To run the Centralized Logging Service functions by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="944e4-117">返回列表中的所有 RBAC 角色此 cmdlet 已指配给，包括自己，创建的任何自定义的 RBAC 角色运行下面的命令从 Skype 业务服务器管理外壳或者 Windows PowerShell 提示：</span><span class="sxs-lookup"><span data-stu-id="944e4-117">To return a list of all the RBAC roles this cmdlet has been assigned to, including any custom RBAC roles you have created yourself, run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="944e4-118">例如：</span><span class="sxs-lookup"><span data-stu-id="944e4-118">For example:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="944e4-119">本主题的其余部分重点说明了如何定义方案、修改方案、检索正在运行的方案、删除方案以及指定方案为优化故障排除而包含的内容。</span><span class="sxs-lookup"><span data-stu-id="944e4-119">The remainder of this topic focuses on how to define a scenario, modify a scenario, retrieve what scenarios are running, remove a scenario, and specify what a scenario contains to optimize your troubleshooting.</span></span> <span data-ttu-id="944e4-120">可以使用业务服务器管理外壳的 Skype 发布 Windows PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="944e4-120">You can use the Skype for Business Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="944e4-121">当您使用 Windows PowerShell 时，可以定义日志记录会话中使用的新方案。</span><span class="sxs-lookup"><span data-stu-id="944e4-121">When you use Windows PowerShell, you can define new scenarios for use in your logging sessions.</span></span>
  
<span data-ttu-id="944e4-122">由于介绍[业务 2015年的 Skype 在集中式日志记录服务](centralized-logging-service.md)，方案的要素包括：</span><span class="sxs-lookup"><span data-stu-id="944e4-122">As introduced in [Centralized Logging Service in Skype for Business 2015](centralized-logging-service.md), the elements of a scenario are:</span></span>
  
- <span data-ttu-id="944e4-123">**提供程序**如果您熟悉 OCSLogger，提供程序告诉 OCSLogger 跟踪引擎应收集日志从您选择的组件。</span><span class="sxs-lookup"><span data-stu-id="944e4-123">**Providers** If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="944e4-124">提供程序是一些相同的组件，在许多情况下，它们的名称与 OCSLogger 中组件的名称相同。</span><span class="sxs-lookup"><span data-stu-id="944e4-124">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="944e4-125">如果您还不熟悉 OCSLogger，提供程序特定服务器角色的组件中的集中式记录服务可以收集日志。</span><span class="sxs-lookup"><span data-stu-id="944e4-125">If you are not familiar with OCSLogger, providers are server role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="944e4-126">有关配置的提供程序的详细信息，请参阅[配置业务服务器 2015年的 Skype 在集中式日志记录服务的提供商](configure-providers.md)。</span><span class="sxs-lookup"><span data-stu-id="944e4-126">For details about the configuration of providers, see [Configure providers for Centralized Logging Service in Skype for Business Server 2015](configure-providers.md).</span></span>
    
- <span data-ttu-id="944e4-127">**标识**参数-标识设置范围和名称的方案。</span><span class="sxs-lookup"><span data-stu-id="944e4-127">**Identity** The parameter -Identity sets the scope and name of the scenario.</span></span> <span data-ttu-id="944e4-128">例如，可以设置的"全局"范围，确定与"LyssServiceScenario"的方案。</span><span class="sxs-lookup"><span data-stu-id="944e4-128">For example, you could set a scope of "global" and identify the scenario with "LyssServiceScenario".</span></span> <span data-ttu-id="944e4-129">当组合这两个时，您定义的标识 (例如，"全局/LyssServiceScenario")。</span><span class="sxs-lookup"><span data-stu-id="944e4-129">When you combine the two, you define the Identity (for example, "global/LyssServiceScenario").</span></span>
    
    <span data-ttu-id="944e4-130">或者，您可以使用-名称和父参数。</span><span class="sxs-lookup"><span data-stu-id="944e4-130">Optionally, you can use the -Name and -Parent parameters.</span></span> <span data-ttu-id="944e4-131">定义 Name 参数可对方案进行唯一标识。</span><span class="sxs-lookup"><span data-stu-id="944e4-131">You define the Name parameter to uniquely identify the scenario.</span></span> <span data-ttu-id="944e4-132">如果使用 Name，则还必须使用 Parent 将方案添加到全局或站点范围中。</span><span class="sxs-lookup"><span data-stu-id="944e4-132">If you use Name, you must also use Parent to add the scenario to either global or site.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="944e4-133">如果您使用参数的名称和父级，则无法使用**-标识**参数。</span><span class="sxs-lookup"><span data-stu-id="944e4-133">If you use the Name and Parent parameters, you cannot use the **-Identity** parameter.</span></span>
  
### <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="944e4-134">使用 New-CsClsScenario cmdlet 创建新的方案</span><span class="sxs-lookup"><span data-stu-id="944e4-134">To create a new scenario with the New-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="944e4-135">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="944e4-135">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="944e4-136">为日志记录会话创建一个新的方案，使用[New CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps) ，并定义 （即，如何那么将进行唯一标识） 的方案的名称。</span><span class="sxs-lookup"><span data-stu-id="944e4-136">To create a new scenario for a logging session, use [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps) and define the name of the scenario (that is, how it will be uniquely identified).</span></span> <span data-ttu-id="944e4-137">从 WPP 中选择日志记录格式的类型（即，Windows 软件跟踪预处理器和其默认值）、EventLog（即，Windows 事件日志格式）或 IISLog（即，基于 IIS 日志文件格式的 ASCII 格式文件）。</span><span class="sxs-lookup"><span data-stu-id="944e4-137">Choose a type of logging format from WPP (that is, Windows software tracing preprocessor and is the default), EventLog (that is, Windows event log format), or IISLog (that is, ASCII format file based on the IIS log file format).</span></span> <span data-ttu-id="944e4-138">然后，定义级别（如本主题中的“日志记录级别”下所述）和标志（如本主题中的“标志”下所述）。</span><span class="sxs-lookup"><span data-stu-id="944e4-138">Next, define Level (as the defined under Logging Levels in this topic), and Flags (as defined under Flags in this topic).</span></span>
    
    <span data-ttu-id="944e4-139">对于此示例方案，我们将 LyssProvider 用作示例提供程序变量。</span><span class="sxs-lookup"><span data-stu-id="944e4-139">For this example scenario, we use LyssProvider as the example provider variable.</span></span>
    
    <span data-ttu-id="944e4-140">若要使用定义的选项创建方案，请键入：</span><span class="sxs-lookup"><span data-stu-id="944e4-140">To create a scenario using the options defined, type:</span></span>
    
  ```
  New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
  ```

    <span data-ttu-id="944e4-141">例如：</span><span class="sxs-lookup"><span data-stu-id="944e4-141">For example:</span></span>
    
  ```
  New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
  ```

    <span data-ttu-id="944e4-142">备用格式使用的名和父：</span><span class="sxs-lookup"><span data-stu-id="944e4-142">The alternate format using -Name and -Parent:</span></span>
    
  ```
  New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider
  ```

### <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="944e4-143">使用带 New-CsClsScenario cmdlet 的多个提供程序创建新的方案</span><span class="sxs-lookup"><span data-stu-id="944e4-143">To create a new scenario with multiple providers with the New-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="944e4-144">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="944e4-144">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="944e4-145">每个范围只能有两个方案。</span><span class="sxs-lookup"><span data-stu-id="944e4-145">You are limited to two scenarios per scope.</span></span> <span data-ttu-id="944e4-146">但是，您并不限于一定数量的提供程序。</span><span class="sxs-lookup"><span data-stu-id="944e4-146">However, you are not limited to a set number of providers.</span></span> <span data-ttu-id="944e4-147">在此示例中，假定我们已经创建了三个供应商，您想要分配到方案定义的所有三个。</span><span class="sxs-lookup"><span data-stu-id="944e4-147">In this example, assume that we have created three providers, and you want to assign all three to the scenario you are defining.</span></span> <span data-ttu-id="944e4-148">提供程序变量名称是 LyssProvider、 ABServerProvider 和 SIPStackProvider。</span><span class="sxs-lookup"><span data-stu-id="944e4-148">The provider variable names are LyssProvider, ABServerProvider, and SIPStackProvider.</span></span> <span data-ttu-id="944e4-149">要定义并将多个供应商分配给方案，Skype 业务服务器管理外壳程序或 Windows PowerShell 命令提示符处键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="944e4-149">To define and assign multiple providers to a scenario, type the following at a Skype for Business Server Management Shell or Windows PowerShell command prompt:</span></span>
    
  ```
  New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
  ```

    > [!NOTE]
    > <span data-ttu-id="944e4-150">已知在 Windows PowerShell，用于创建使用的值的哈希表的约定`@{<variable>=<value1>, <value2>, <value>…}`称为 assplatting。</span><span class="sxs-lookup"><span data-stu-id="944e4-150">As it is known in Windows PowerShell, the convention for creating a hash table of values using  `@{<variable>=<value1>, <value2>, <value>…}` is known assplatting.</span></span> <span data-ttu-id="944e4-151">在 Windows PowerShell 展开有关详细信息，请参阅[https://go.microsoft.com/fwlink/p/?LinkId=267760](https://go.microsoft.com/fwlink/p/?LinkId=267760)。</span><span class="sxs-lookup"><span data-stu-id="944e4-151">For details about splatting in Windows PowerShell, see [https://go.microsoft.com/fwlink/p/?LinkId=267760](https://go.microsoft.com/fwlink/p/?LinkId=267760).</span></span> 
  
### <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a><span data-ttu-id="944e4-152">使用 Set-CsClsScenario cmdlet 修改现有方案</span><span class="sxs-lookup"><span data-stu-id="944e4-152">To modify an existing scenario with the Set-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="944e4-153">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="944e4-153">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="944e4-154">每个范围只能有两个方案。</span><span class="sxs-lookup"><span data-stu-id="944e4-154">You are limited to two scenarios per scope.</span></span> <span data-ttu-id="944e4-155">您可以随时更改正在运行的方案，即使日志记录捕获会话正在进行中也是如此。</span><span class="sxs-lookup"><span data-stu-id="944e4-155">You can change which scenarios are running at any time, even when a logging capture session is in process.</span></span> <span data-ttu-id="944e4-156">如果您重新定义正在运行的方案，则当前日志记录会话将停止使用已删除的方案，并开始使用新方案。</span><span class="sxs-lookup"><span data-stu-id="944e4-156">If you redefine the running scenarios, the current logging session will stop using the scenario that was removed and then begin using the new scenario.</span></span> <span data-ttu-id="944e4-157">但是，已通过删除的方案捕获到的日志记录信息将保留在捕获的日志中。</span><span class="sxs-lookup"><span data-stu-id="944e4-157">However, the logging information that was captured with the removed scenario remains in the captured logs.</span></span> <span data-ttu-id="944e4-158">若要定义一个新的方案，请执行以下操作 （即，假设名为"S4Provider"已定义提供程序添加）：</span><span class="sxs-lookup"><span data-stu-id="944e4-158">To define a new scenario, do the following (that is, assuming the addition of an already defined provider named "S4Provider"):</span></span>
    
  ```
  Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
  ```

    <span data-ttu-id="944e4-159">例如：</span><span class="sxs-lookup"><span data-stu-id="944e4-159">For example:</span></span>
    
  ```
  Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
  ```

    <span data-ttu-id="944e4-p112">若要替换提供程序，请定义一个提供程序或一个以逗号分隔的提供程序列表来替换当前集。如果您只需要替换多个提供程序之一，请将当前提供程序与新的提供程序一起添加以创建同时包含新提供程序和现有提供程序的新提供程序集。若要将所有提供程序替换为新集，请键入：</span><span class="sxs-lookup"><span data-stu-id="944e4-p112">If you want to replace providers, define a single provider or a comma separated list of providers to replace the current set. If you only want to replace one of many providers, add the current providers with the new providers to create a new set of providers that contains both new providers and existing providers. To replace all providers with a new set, type the following:</span></span>
    
  ```
  Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
  ```

    <span data-ttu-id="944e4-163">例如，将 $LyssProvider、$ABServerProvider 和 $SIPStackProvider 的当前集替换为 $LyssServiceProvider：</span><span class="sxs-lookup"><span data-stu-id="944e4-163">For example, to replace the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider:</span></span>
    
  ```
  Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
  ```

    <span data-ttu-id="944e4-164">若只将 $LyssProvider、$ABServerProvider 和 $SIPStackProvider 的当前集中的 $LyssProvider 提供程序替换为 $LyssServiceProvider，请键入：</span><span class="sxs-lookup"><span data-stu-id="944e4-164">To replace just the $LyssProvider provider from the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider, type the following:</span></span>
    
  ```
  Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}
  ```

### <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a><span data-ttu-id="944e4-165">使用 Remove-CsClsScenario cmdlet 删除现有方案</span><span class="sxs-lookup"><span data-stu-id="944e4-165">To remove an existing scenario with the Remove-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="944e4-166">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="944e4-166">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="944e4-167">若要删除之前已定义的方案，请键入：</span><span class="sxs-lookup"><span data-stu-id="944e4-167">If you want to remove a scenario that has been previously defined, type the following:</span></span>
    
  ```
  Remove-CsClsScenario -Identity <name of scope and scenario>
  ```

    <span data-ttu-id="944e4-168">例如，删除定义的方案 site:Redmond/LyssServiceScenario：</span><span class="sxs-lookup"><span data-stu-id="944e4-168">For example, to remove the defined scenario site:Redmond/LyssServiceScenario:</span></span>
    
  ```
  Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"
  ```

<span data-ttu-id="944e4-169">**删除 CsClsScenario** cmdlet 中移除指定的方案中，但仍可在日志中，您可以搜索已捕获的跟踪。</span><span class="sxs-lookup"><span data-stu-id="944e4-169">The **Remove-CsClsScenario** cmdlet removes the specified scenario, but the traces that have been captured are still available in the logs for you to search on.</span></span>
### <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clsscenarioeditpsm1-module"></a><span data-ttu-id="944e4-170">使用 ClsScenarioEdit.psm1 模块加载和卸载 Edit-CsClsScenario cmdlet</span><span class="sxs-lookup"><span data-stu-id="944e4-170">To load and unload the Edit-CsClsScenario cmdlet using the ClsScenarioEdit.psm1 module</span></span>

1. <span data-ttu-id="944e4-171">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="944e4-171">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="944e4-172">ClsScenarioEdit.psm1 模块是作为单独的 Web 下载提供的。</span><span class="sxs-lookup"><span data-stu-id="944e4-172">The ClsScenarioEdit.psm1 module is provided as a separate Web download.</span></span> <span data-ttu-id="944e4-173">该模块是业务服务器 2015年调试工具 Skype 的一部分。</span><span class="sxs-lookup"><span data-stu-id="944e4-173">The module is part of the Skype for Business Server 2015 Debugging tools.</span></span> <span data-ttu-id="944e4-174">默认情况下，调试工具将安装到目录 C:\Program Files\Skype for Business Server 2015\Debugging Tools 中。</span><span class="sxs-lookup"><span data-stu-id="944e4-174">By default, the debugging tools are installed in the directory C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> 
  
2. <span data-ttu-id="944e4-175">从 Windows PowerShell 中，请键入：</span><span class="sxs-lookup"><span data-stu-id="944e4-175">From the Windows PowerShell, type:</span></span>
    
  ```
  Import-Module "CDBurn\OCO\amd64\Support"
  ```

    > [!TIP]
    > <span data-ttu-id="944e4-176">成功加载的模块将返回到 Windows PowerShell 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="944e4-176">Successful loading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="944e4-177">若要确认在模块加载和编辑 CsClsScenario 是可用，请键入`Get-Help Edit-CsClsScenario`。</span><span class="sxs-lookup"><span data-stu-id="944e4-177">To confirm that the module is loaded and that Edit-CsClsScenario is available, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="944e4-178">您应看到 EditCsClsScenario 的语法的基本概要。</span><span class="sxs-lookup"><span data-stu-id="944e4-178">You should see the basic synopsis of the syntax for EditCsClsScenario.</span></span> 
  
3. <span data-ttu-id="944e4-179">若要卸载模块，请键入：</span><span class="sxs-lookup"><span data-stu-id="944e4-179">To unload the modules, type:</span></span>
    
  ```
  Remove-Module ClsController
  ```

    > [!TIP]
    > <span data-ttu-id="944e4-180">成功卸载模块返回您 Windows PowerShell 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="944e4-180">Successful unloading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="944e4-181">若要确认该模块被卸载，请键入`Get-Help Edit-CsClsScenario`。</span><span class="sxs-lookup"><span data-stu-id="944e4-181">To confirm that the module is unloaded, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="944e4-182">Windows PowerShell 将尝试找到该 cmdlet 的帮助并失败。</span><span class="sxs-lookup"><span data-stu-id="944e4-182">Windows PowerShell will attempt to locate the help for the cmdlet and fail.</span></span> 
  
### <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="944e4-183">使用 Edit-ClsController 模块从方案中删除现有提供程序</span><span class="sxs-lookup"><span data-stu-id="944e4-183">To remove an existing provider from a scenario with the Edit-ClsController module</span></span>

1. <span data-ttu-id="944e4-184">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="944e4-184">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="944e4-185">从 Windows PowerShell 中，请键入：</span><span class="sxs-lookup"><span data-stu-id="944e4-185">From the Windows PowerShell, type:</span></span>
    
  ```
  Import-Module "CDBurn\OCO\amd64\Support"
  ```

    > [!TIP]
    > <span data-ttu-id="944e4-186">成功加载的模块将返回到 Windows PowerShell 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="944e4-186">Successful loading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="944e4-187">若要确认在模块加载和编辑 CsClsScenario 是可用，请键入`Get-Help Edit-CsClsScenario`。</span><span class="sxs-lookup"><span data-stu-id="944e4-187">To confirm that the module is loaded and that Edit-CsClsScenario is available, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="944e4-188">您应看到 EditCsClsScenario 的语法的基本概要。</span><span class="sxs-lookup"><span data-stu-id="944e4-188">You should see the basic synopsis of the syntax for EditCsClsScenario.</span></span> 
  
3. <span data-ttu-id="944e4-189">若要从 AlwaysOn 方案中删除提供程序，请键入：</span><span class="sxs-lookup"><span data-stu-id="944e4-189">To remove a provider from the AlwaysOn scenario, type:</span></span>
    
  ```
  Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
  ```

  <span data-ttu-id="944e4-190">例如：</span><span class="sxs-lookup"><span data-stu-id="944e4-190">For Example:</span></span>
    
  ```
  Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
  ```

   <span data-ttu-id="944e4-p117">参数 ScenarioName 和 ProviderName 是定位参数（也就是说，必须在命令行中的预期位置定义这两个参数）。如果相对于位置 1 的 cmdlet 的名称，方案名称位于位置 2 且提供程序位于位置 3，则无需显式定义参数名称。通过使用此信息，可以按以下形式键入上一个命令：</span><span class="sxs-lookup"><span data-stu-id="944e4-p117">The parameters ScenarioName and ProviderName are positional (that is, they must be defined in the expected position in the command line) parameters. The parameter name does not have to be explicitly defined if the scenario name is in position two and the provider is in position three, relative to the name of the cmdlet as position one. Using this information, the previous command would be typed as:</span></span>
    
  ```
  Edit-CsClsScenario AlwaysOn ChatServer -Remove
  ```

  <span data-ttu-id="944e4-194">参数值的位置放置仅适用于的方案和提供程序。</span><span class="sxs-lookup"><span data-stu-id="944e4-194">The positional placing of the parameter values applies only to -Scenario and -Provider.</span></span> <span data-ttu-id="944e4-195">必须显式定义所有其他参数。</span><span class="sxs-lookup"><span data-stu-id="944e4-195">All other parameters must be explicitly defined.</span></span>
    
### <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="944e4-196">使用 Edit-ClsController 模块将提供程序添加到方案</span><span class="sxs-lookup"><span data-stu-id="944e4-196">To add a provider to a scenario with the Edit-ClsController module</span></span>

1. <span data-ttu-id="944e4-197">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="944e4-197">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="944e4-198">若要将提供程序添加到 AlwaysOn 方案，请键入：</span><span class="sxs-lookup"><span data-stu-id="944e4-198">To add a provider to the AlwaysOn scenario, type:</span></span>
    
  ```
  Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
  ```

    <span data-ttu-id="944e4-199">例如：</span><span class="sxs-lookup"><span data-stu-id="944e4-199">For Example:</span></span>
    
  ```
  Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
  ```

    <span data-ttu-id="944e4-200">-Loglevel 的类型可以是 Fatal、Error、Warning、Info、Verbose、Debug 或 All。</span><span class="sxs-lookup"><span data-stu-id="944e4-200">-Loglevel can be of the type Fatal, Error, Warning, Info, Verbose, Debug, or All.</span></span> <span data-ttu-id="944e4-201">标志可以是任何提供程序支持，如 TF_COMPONENT，TF_DIAG 的标志。</span><span class="sxs-lookup"><span data-stu-id="944e4-201">-Flags can be any of the flags that the provider supports, such as TF_COMPONENT, TF_DIAG.</span></span> <span data-ttu-id="944e4-202">标志还可以为所有的值</span><span class="sxs-lookup"><span data-stu-id="944e4-202">-Flags can also be of value ALL</span></span>
    
  <span data-ttu-id="944e4-p120">还可以使用 cmdlet 的定位功能键入上一个示例。例如，若要将提供程序 ChatServer 添加到 AlwaysOn 方案，请键入：</span><span class="sxs-lookup"><span data-stu-id="944e4-p120">The previous example can also be typed using the positional feature of the cmdlet. For example, to add the provider ChatServer to the AlwaysOn scenario, type:</span></span>
    
  ```
  Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL
  ```


