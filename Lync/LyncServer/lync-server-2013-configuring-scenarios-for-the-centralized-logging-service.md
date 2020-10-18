---
title: Lync Server 2013：配置集中日志记录服务的方案
description: Lync Server 2013：配置集中日志记录服务的方案。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring scenarios for the Centralized Logging Service
ms:assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688085(v=OCS.15)
ms:contentKeyID: 49733682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1bf3f569ae8d2596f735851ae3d5d6c55f022b09
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575858"
---
# <a name="configuring-scenarios-for-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="45de7-103">在 Lync Server 2013 中配置集中日志记录服务的方案</span><span class="sxs-lookup"><span data-stu-id="45de7-103">Configuring scenarios for the Centralized Logging Service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45de7-104">_**上次修改的主题：** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="45de7-104">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="45de7-105">方案定义了作用域 (即全局、站点、池或计算机) 以及要在集中日志记录服务中使用的提供程序。</span><span class="sxs-lookup"><span data-stu-id="45de7-105">Scenarios define the scope (that is, global, site, pool, or computer) and what providers to use in the Centralized Logging Service.</span></span> <span data-ttu-id="45de7-106">通过使用方案，可以启用或禁用对提供程序进行的跟踪（例如，S4、SIPStack、IM 和 Presence）。</span><span class="sxs-lookup"><span data-stu-id="45de7-106">By using scenarios, you enable or disable tracing on providers (for example, S4, SIPStack, IM, and Presence).</span></span> <span data-ttu-id="45de7-107">通过配置方案，可将针对给定逻辑集合的、满足某个特定问题条件的所有提供程序组合在一起。</span><span class="sxs-lookup"><span data-stu-id="45de7-107">By configuring a scenario, you can group all of the providers for a given logical collection that address a specific problem condition.</span></span> <span data-ttu-id="45de7-108">如果发现需要修改某个方案以满足故障排除和日志记录需求，Lync Server 2013 调试工具会为您提供一个名为 *ClsController* 的 Windows PowerShell 模块，其中包含名为 *Edit-new-csclsscenario*的函数。</span><span class="sxs-lookup"><span data-stu-id="45de7-108">If you find that a scenario needs to be modified to meet your troubleshooting and logging needs, the Lync Server 2013 Debug Tools provides you a Windows PowerShell module named *ClsController.psm1* that contains a function named *Edit-CsClsScenario*.</span></span> <span data-ttu-id="45de7-109">此模块的用途是编辑命名的方案的属性。</span><span class="sxs-lookup"><span data-stu-id="45de7-109">The purpose of the module is to edit the properties of the named scenario.</span></span> <span data-ttu-id="45de7-110">本主题提供了此模块的工作方式的示例。</span><span class="sxs-lookup"><span data-stu-id="45de7-110">Examples of how this module works are provided in this topic.</span></span> <span data-ttu-id="45de7-111">从以下链接下载 Lync Server 2013 调试工具： [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257)</span><span class="sxs-lookup"><span data-stu-id="45de7-111">The Lync Server 2013 Debug Tools are downloaded from the following link: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="45de7-112">对于任何给定的范围（站点、全局、池或计算机），您可以在任何给定时间最多运行两个方案。</span><span class="sxs-lookup"><span data-stu-id="45de7-112">For any given scope—site, global, pool or computer—you can run a maximum of two scenarios at any given time.</span></span> <span data-ttu-id="45de7-113">若要确定当前正在运行的方案，请使用 Windows PowerShell 和 <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario">new-csclsscenario</A>。</span><span class="sxs-lookup"><span data-stu-id="45de7-113">To determine which scenarios are currently running, use Windows PowerShell and <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario">Get-CsClsScenario</A>.</span></span> <span data-ttu-id="45de7-114">通过使用 Windows PowerShell 和 <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario">new-csclsscenario</A>，您可以动态更改正在运行的方案。</span><span class="sxs-lookup"><span data-stu-id="45de7-114">By using Windows PowerShell and <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario">Set-CsClsScenario</A>, you can dynamically change which scenarios are running.</span></span> <span data-ttu-id="45de7-115">可以在日志记录会话期间修改正在运行的方案，以调整或优化所收集的数据以及源提供程序。</span><span class="sxs-lookup"><span data-stu-id="45de7-115">You can modify which scenarios are running during a logging session to adjust or refine the data you are collecting and from which providers.</span></span>



</div>

<span data-ttu-id="45de7-116">若要使用 Lync Server 命令行管理程序运行集中式日志记录服务功能，您必须是 CsAdministrator 或 CsServerAdministrator 基于角色的访问控制 (RBAC) 安全组的成员，或者是包含这两个组中任一组的自定义 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="45de7-116">To run the Centralized Logging Service functions by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="45de7-117">若要返回此 cmdlet 已分配到的所有 RBAC 角色的列表，包括您自己创建的任何自定义 RBAC 角色，请从 Lync Server 命令行管理程序或 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="45de7-117">To return a list of all the RBAC roles this cmdlet has been assigned to, including any custom RBAC roles you have created yourself, run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="45de7-118">例如：</span><span class="sxs-lookup"><span data-stu-id="45de7-118">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<span data-ttu-id="45de7-119">本主题的其余部分重点说明了如何定义方案、修改方案、检索正在运行的方案、删除方案以及指定方案为优化故障排除而包含的内容。</span><span class="sxs-lookup"><span data-stu-id="45de7-119">The remainder of this topic focuses on how to define a scenario, modify a scenario, retrieve what scenarios are running, remove a scenario, and specify what a scenario contains to optimize your troubleshooting.</span></span> <span data-ttu-id="45de7-120">有两种方法可以发出集中式日志记录服务命令。</span><span class="sxs-lookup"><span data-stu-id="45de7-120">There are two ways to issue Centralized Logging Service commands.</span></span> <span data-ttu-id="45de7-121">默认情况下，您可以使用目录 C： \\ Program files \\ Common files The \\ Microsoft Lync Server 2013 CLSAgent 中的 CLSController.exe \\ 。</span><span class="sxs-lookup"><span data-stu-id="45de7-121">You can use the CLSController.exe that is located, by default, in the directory C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\CLSAgent.</span></span> <span data-ttu-id="45de7-122">或者，您可以使用 Lync Server 命令行管理程序发出 Windows PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="45de7-122">Or, you can use the Lync Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="45de7-123">重要区别在于，在命令行上使用 CLSController.exe 时，可供选择的可用方案是有限的。</span><span class="sxs-lookup"><span data-stu-id="45de7-123">The important distinction is that when you use CLSController.exe at the command line there is a finite selection of scenarios available.</span></span> <span data-ttu-id="45de7-124">使用 Windows PowerShell 时，可以定义在日志记录会话中使用的新方案。</span><span class="sxs-lookup"><span data-stu-id="45de7-124">When you use Windows PowerShell, you can define new scenarios for use in your logging sessions.</span></span>

<span data-ttu-id="45de7-125">如 [Lync Server 2013 中的集中日志记录服务概述](lync-server-2013-overview-of-the-centralized-logging-service.md)中所述，方案的元素为：</span><span class="sxs-lookup"><span data-stu-id="45de7-125">As introduced in [Overview of the Centralized Logging Service in Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), the elements of a scenario are:</span></span>

  - <span data-ttu-id="45de7-126">**提供程序**    如果您熟悉 OCSLogger，则提供程序是您选择的组件，用于告诉 OCSLogger 跟踪引擎应从什么方面收集日志。</span><span class="sxs-lookup"><span data-stu-id="45de7-126">**Providers**   If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="45de7-127">提供程序是一些相同的组件，在许多情况下，它们的名称与 OCSLogger 中组件的名称相同。</span><span class="sxs-lookup"><span data-stu-id="45de7-127">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="45de7-128">如果您不熟悉 OCSLogger，则提供程序是集中式日志记录服务可从中收集日志的特定于服务器角色的组件。</span><span class="sxs-lookup"><span data-stu-id="45de7-128">If you are not familiar with OCSLogger, providers are server role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="45de7-129">有关提供程序配置的详细信息，请参阅 [在 Lync Server 2013 中配置集中日志记录服务的提供程序](lync-server-2013-configuring-providers-for-centralized-logging-service.md)。</span><span class="sxs-lookup"><span data-stu-id="45de7-129">For details about the configuration of providers, see [Configuring providers for Centralized Logging Service in Lync Server 2013](lync-server-2013-configuring-providers-for-centralized-logging-service.md).</span></span>

  - <span data-ttu-id="45de7-130">**标识**    参数– Identity 设置方案的范围和名称。</span><span class="sxs-lookup"><span data-stu-id="45de7-130">**Identity**   The parameter –Identity sets the scope and name of the scenario.</span></span> <span data-ttu-id="45de7-131">例如，您可以设置“全局”范围并使用“LyssServiceScenario”标识方案。</span><span class="sxs-lookup"><span data-stu-id="45de7-131">For example, you could set a scope of “global” and identify the scenario with “LyssServiceScenario”.</span></span> <span data-ttu-id="45de7-132">在将二者组合在一起时，可以定义 Identity（例如“global/LyssServiceScenario”）。</span><span class="sxs-lookup"><span data-stu-id="45de7-132">When you combine the two, you define the Identity (for example, “global/LyssServiceScenario”).</span></span>
    
    <span data-ttu-id="45de7-p107">（可选）可以使用 –Name 和 –Parent 参数。定义 Name 参数可对方案进行唯一标识。如果使用 Name，则还必须使用 Parent 将方案添加到全局或站点范围中。</span><span class="sxs-lookup"><span data-stu-id="45de7-p107">Optionally, you can use the –Name and –Parent parameters. You define the Name parameter to uniquely identify the scenario. If you use Name, you must also use Parent to add the scenario to either global or site.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="45de7-136">如果使用 Name 和 Parent 参数，则无法使用 <STRONG>–Identity</STRONG> 参数。</span><span class="sxs-lookup"><span data-stu-id="45de7-136">If you use the Name and Parent parameters, you cannot use the <STRONG>–Identity</STRONG> parameter.</span></span>

    
    </div>

<div>

## <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="45de7-137">使用 New-CsClsScenario cmdlet 创建新的方案</span><span class="sxs-lookup"><span data-stu-id="45de7-137">To create a new scenario with the New-CsClsScenario cmdlet</span></span>

1.  <span data-ttu-id="45de7-138">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="45de7-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="45de7-139">若要为日志记录会话创建新的方案，请使用 [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider) 并定义方案的名称（即，对方案进行唯一标识的方式）。</span><span class="sxs-lookup"><span data-stu-id="45de7-139">To create a new scenario for a logging session, use [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider) and define the name of the scenario (that is, how it will be uniquely identified).</span></span> <span data-ttu-id="45de7-140">从 WPP 中选择日志记录格式的类型（即，Windows 软件跟踪预处理器和其默认值）、EventLog（即，Windows 事件日志格式）或 IISLog（即，基于 IIS 日志文件格式的 ASCII 格式文件）。</span><span class="sxs-lookup"><span data-stu-id="45de7-140">Choose a type of logging format from WPP (that is, Windows software tracing preprocessor and is the default), EventLog (that is, Windows event log format), or IISLog (that is, ASCII format file based on the IIS log file format).</span></span> <span data-ttu-id="45de7-141">然后，定义级别（如本主题中的“日志记录级别”下所述）和标志（如本主题中的“标志”下所述）。</span><span class="sxs-lookup"><span data-stu-id="45de7-141">Next, define Level (as the defined under Logging Levels in this topic), and Flags (as defined under Flags in this topic).</span></span>
    
    <span data-ttu-id="45de7-142">对于此示例方案，我们将 LyssProvider 用作示例提供程序变量。</span><span class="sxs-lookup"><span data-stu-id="45de7-142">For this example scenario, we use LyssProvider as the example provider variable.</span></span>
    
    <span data-ttu-id="45de7-143">若要使用定义的选项创建方案，请键入：</span><span class="sxs-lookup"><span data-stu-id="45de7-143">To create a scenario using the options defined, type:</span></span>
    
        New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
    
    <span data-ttu-id="45de7-144">例如：</span><span class="sxs-lookup"><span data-stu-id="45de7-144">For example:</span></span>
    
        New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
    
    <span data-ttu-id="45de7-145">使用 –Name 和 –Parent 的备用格式：</span><span class="sxs-lookup"><span data-stu-id="45de7-145">The alternate format using –Name and –Parent:</span></span>
    
        New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider

</div>

<div>

## <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="45de7-146">使用带 New-CsClsScenario cmdlet 的多个提供程序创建新的方案</span><span class="sxs-lookup"><span data-stu-id="45de7-146">To create a new scenario with multiple providers with the New-CsClsScenario cmdlet</span></span>

1.  <span data-ttu-id="45de7-147">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="45de7-147">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="45de7-148">每个范围只能有两个方案。</span><span class="sxs-lookup"><span data-stu-id="45de7-148">You are limited to two scenarios per scope.</span></span> <span data-ttu-id="45de7-149">但是，不限于设置的提供程序数。</span><span class="sxs-lookup"><span data-stu-id="45de7-149">However, you are not limited to a set number of providers.</span></span> <span data-ttu-id="45de7-150">在此示例中，假定我们已创建三个提供程序，并且您希望将所有这三个提供程序分配给所定义的方案。</span><span class="sxs-lookup"><span data-stu-id="45de7-150">In this example, assume that we have created three providers, and you want to assign all three to the scenario you are defining.</span></span> <span data-ttu-id="45de7-151">提供程序变量名称为 LyssProvider、ABServerProvider 和 SIPStackProvider。</span><span class="sxs-lookup"><span data-stu-id="45de7-151">The provider variable names are LyssProvider, ABServerProvider, and SIPStackProvider.</span></span> <span data-ttu-id="45de7-152">若要定义多个提供程序并将其分配给某个方案，请在 Lync Server 命令行管理程序或 Windows PowerShell 命令提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="45de7-152">To define and assign multiple providers to a scenario, type the following at a Lync Server Management Shell or Windows PowerShell command prompt:</span></span>
    
        New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="45de7-153">在 Windows PowerShell 中，创建使用的值的哈希表的约定 <CODE>@{&lt;variable&gt;=&lt;value1&gt;, &lt;value2&gt;, &lt;value&gt;...}</CODE> 称为 " <EM>展开</EM>"。</span><span class="sxs-lookup"><span data-stu-id="45de7-153">As it is known in Windows PowerShell, the convention for creating a hash table of values using <CODE>@{&lt;variable&gt;=&lt;value1&gt;, &lt;value2&gt;, &lt;value&gt;...}</CODE> is known as <EM>splatting</EM>.</span></span> <span data-ttu-id="45de7-154">有关 Windows PowerShell 中的展开的详细信息，请参阅 <A href="https://go.microsoft.com/fwlink/p/?linkid=267760">https://go.microsoft.com/fwlink/p/?LinkId=267760</A> 。</span><span class="sxs-lookup"><span data-stu-id="45de7-154">For details about splatting in Windows PowerShell, see <A href="https://go.microsoft.com/fwlink/p/?linkid=267760">https://go.microsoft.com/fwlink/p/?LinkId=267760</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a><span data-ttu-id="45de7-155">使用 Set-CsClsScenario cmdlet 修改现有方案</span><span class="sxs-lookup"><span data-stu-id="45de7-155">To modify an existing scenario with the Set-CsClsScenario cmdlet</span></span>

1.  <span data-ttu-id="45de7-156">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="45de7-156">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="45de7-p111">每个范围只能有两个方案。您可以随时更改正在运行的方案，即使日志记录捕获会话正在进行中也是如此。如果您重新定义正在运行的方案，则当前日志记录会话将停止使用已删除的方案，并开始使用新方案。但是，已通过删除的方案捕获到的日志记录信息将保留在捕获的日志中。若要定义新的方案，请执行下列命令（即，假定添加一个名为“S4Provider”的已定义的提供程序）：</span><span class="sxs-lookup"><span data-stu-id="45de7-p111">You are limited to two scenarios per scope. You can change which scenarios are running at any time, even when a logging capture session is in process. If you redefine the running scenarios, the current logging session will stop using the scenario that was removed and then begin using the new scenario. However, the logging information that was captured with the removed scenario remains in the captured logs. To define a new scenario, do the following (that is, assuming the addition of an already defined provider named “S4Provider”):</span></span>
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
    
    <span data-ttu-id="45de7-162">例如：</span><span class="sxs-lookup"><span data-stu-id="45de7-162">For example:</span></span>
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
    
    <span data-ttu-id="45de7-p112">若要替换提供程序，请定义一个提供程序或一个以逗号分隔的提供程序列表来替换当前集。如果您只需要替换多个提供程序之一，请将当前提供程序与新的提供程序一起添加以创建同时包含新提供程序和现有提供程序的新提供程序集。若要将所有提供程序替换为新集，请键入：</span><span class="sxs-lookup"><span data-stu-id="45de7-p112">If you want to replace providers, define a single provider or a comma separated list of providers to replace the current set. If you only want to replace one of many providers, add the current providers with the new providers to create a new set of providers that contains both new providers and existing providers. To replace all providers with a new set, type the following:</span></span>
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
    
    <span data-ttu-id="45de7-166">例如，将 $LyssProvider、$ABServerProvider 和 $SIPStackProvider 的当前集替换为 $LyssServiceProvider：</span><span class="sxs-lookup"><span data-stu-id="45de7-166">For example, to replace the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider:</span></span>
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
    
    <span data-ttu-id="45de7-167">若只将 $LyssProvider、$ABServerProvider 和 $SIPStackProvider 的当前集中的 $LyssProvider 提供程序替换为 $LyssServiceProvider，请键入：</span><span class="sxs-lookup"><span data-stu-id="45de7-167">To replace just the $LyssProvider provider from the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider, type the following:</span></span>
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}

</div>

<div>

## <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a><span data-ttu-id="45de7-168">使用 Remove-CsClsScenario cmdlet 删除现有方案</span><span class="sxs-lookup"><span data-stu-id="45de7-168">To remove an existing scenario with the Remove-CsClsScenario cmdlet</span></span>

1.  <span data-ttu-id="45de7-169">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="45de7-169">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="45de7-170">若要删除之前已定义的方案，请键入：</span><span class="sxs-lookup"><span data-stu-id="45de7-170">If you want to remove a scenario that has been previously defined, type the following:</span></span>
    
        Remove-CsClsScenario -Identity <name of scope and scenario>
    
    <span data-ttu-id="45de7-171">例如，删除定义的方案 site:Redmond/LyssServiceScenario：</span><span class="sxs-lookup"><span data-stu-id="45de7-171">For example, to remove the defined scenario site:Redmond/LyssServiceScenario:</span></span>
    
        Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"

<span data-ttu-id="45de7-172">**Remove-CsClsScenario** cmdlet 可删除指定的方案，但已捕获的跟踪信息仍将保留在日志中以供您搜索。</span><span class="sxs-lookup"><span data-stu-id="45de7-172">The **Remove-CsClsScenario** cmdlet removes the specified scenario, but the traces that have been captured are still available in the logs for you to search on.</span></span>

</div>

<div>

## <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clscontrollerpsm1-module"></a><span data-ttu-id="45de7-173">使用 ClsController.psm1 模块加载和卸载 Edit-CsClsScenario cmdlet</span><span class="sxs-lookup"><span data-stu-id="45de7-173">To load and unload the Edit-CsClsScenario cmdlet using the ClsController.psm1 module</span></span>

1.  <span data-ttu-id="45de7-174">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="45de7-174">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="45de7-175">ClsController.psm1 模块是作为单独的 Web 下载提供的。</span><span class="sxs-lookup"><span data-stu-id="45de7-175">The ClsController.psm1 module is provided as a separate Web download.</span></span> <span data-ttu-id="45de7-176">模块是 Lync Server 2013 调试工具的一部分。</span><span class="sxs-lookup"><span data-stu-id="45de7-176">The module is part of the Lync Server 2013 Debugging tools.</span></span> <span data-ttu-id="45de7-177">默认情况下，调试工具将安装到目录 C:\Program Files\Lync Server 2013\Debugging Tools 中。</span><span class="sxs-lookup"><span data-stu-id="45de7-177">By default, the debugging tools are installed in the directory C:\Program Files\Lync Server 2013\Debugging Tools.</span></span>

    
    </div>

2.  <span data-ttu-id="45de7-178">在 Windows PowerShell 中，键入：</span><span class="sxs-lookup"><span data-stu-id="45de7-178">From the Windows PowerShell, type:</span></span>
    
        Import-Module "C:\Program Files\Lync Server 2013\Debugging Tools\ClsController.psm1"
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="45de7-179">成功加载该模块后，将返回到 Windows PowerShell 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="45de7-179">Successful loading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="45de7-180">若要确认模块已加载且 Edit-CsClsScenario 可用，请键入 <CODE>Get-Help Edit-CsClsScenario</CODE> 。</span><span class="sxs-lookup"><span data-stu-id="45de7-180">To confirm that the module is loaded and that Edit-CsClsScenario is available, type <CODE>Get-Help Edit-CsClsScenario</CODE>.</span></span> <span data-ttu-id="45de7-181">您应看到 EditCsClsScenario 的语法的基本概要。</span><span class="sxs-lookup"><span data-stu-id="45de7-181">You should see the basic synopsis of the syntax for EditCsClsScenario.</span></span>

    
    </div>

3.  <span data-ttu-id="45de7-182">若要卸载模块，请键入：</span><span class="sxs-lookup"><span data-stu-id="45de7-182">To unload the modules, type:</span></span>
    
        Remove-Module ClsController
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="45de7-183">成功卸载该模块后，将返回到 Windows PowerShell 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="45de7-183">Successful unloading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="45de7-184">若要确认模块已卸载，请键入 <CODE>Get-Help Edit-CsClsScenario</CODE> 。</span><span class="sxs-lookup"><span data-stu-id="45de7-184">To confirm that the module is unloaded, type <CODE>Get-Help Edit-CsClsScenario</CODE>.</span></span> <span data-ttu-id="45de7-185">Windows PowerShell 将尝试查找 cmdlet 的帮助并失败。</span><span class="sxs-lookup"><span data-stu-id="45de7-185">Windows PowerShell will attempt to locate the help for the cmdlet and fail.</span></span>

    
    </div>

</div>

<div>

## <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="45de7-186">使用 Edit-ClsController 模块从方案中删除现有提供程序</span><span class="sxs-lookup"><span data-stu-id="45de7-186">To remove an existing provider from a scenario with the Edit-ClsController module</span></span>

1.  <span data-ttu-id="45de7-187">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="45de7-187">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="45de7-188">若要从 AlwaysOn 方案中删除提供程序，请键入：</span><span class="sxs-lookup"><span data-stu-id="45de7-188">To remove a provider from the AlwaysOn scenario, type:</span></span>
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
    
    <span data-ttu-id="45de7-189">例如：</span><span class="sxs-lookup"><span data-stu-id="45de7-189">For Example:</span></span>
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
    
    <span data-ttu-id="45de7-p116">参数 ScenarioName 和 ProviderName 是定位参数（也就是说，必须在命令行中的预期位置定义这两个参数）。如果相对于位置 1 的 cmdlet 的名称，方案名称位于位置 2 且提供程序位于位置 3，则无需显式定义参数名称。通过使用此信息，可以按以下形式键入上一个命令：</span><span class="sxs-lookup"><span data-stu-id="45de7-p116">The parameters ScenarioName and ProviderName are positional (that is, they must be defined in the expected position in the command line) parameters. The parameter name does not have to be explicitly defined if the scenario name is in position two and the provider is in position three, relative to the name of the cmdlet as position one. Using this information, the previous command would be typed as:</span></span>
    
        Edit-CsClsScenario AlwaysOn ChatServer -Remove
    
    <span data-ttu-id="45de7-p117">参数值的定位放置仅适用于 –Scenario 和 –Provider。必须显式定义所有其他参数。</span><span class="sxs-lookup"><span data-stu-id="45de7-p117">The positional placing of the parameter values applies only to –Scenario and –Provider. All other parameters must be explicitly defined.</span></span>

</div>

<div>

## <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="45de7-195">使用 Edit-ClsController 模块将提供程序添加到方案</span><span class="sxs-lookup"><span data-stu-id="45de7-195">To add a provider to a scenario with the Edit-ClsController module</span></span>

1.  <span data-ttu-id="45de7-196">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="45de7-196">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="45de7-197">若要将提供程序添加到 AlwaysOn 方案，请键入：</span><span class="sxs-lookup"><span data-stu-id="45de7-197">To add a provider to the AlwaysOn scenario, type:</span></span>
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
    
    <span data-ttu-id="45de7-198">例如：</span><span class="sxs-lookup"><span data-stu-id="45de7-198">For Example:</span></span>
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
    
    <span data-ttu-id="45de7-199">\-Loglevel 可以是 "致命"、"错误"、"警告"、"信息"、"详细"、"调试" 或 "全部"。</span><span class="sxs-lookup"><span data-stu-id="45de7-199">\-Loglevel can be of the type Fatal, Error, Warning, Info, Verbose, Debug, or All.</span></span> <span data-ttu-id="45de7-200">– Flags 可以是提供程序支持的任何标志，如 TF \_ COMPONENT、tf \_ 诊断。</span><span class="sxs-lookup"><span data-stu-id="45de7-200">–Flags can be any of the flags that the provider supports, such as TF\_COMPONENT, TF\_DIAG.</span></span> <span data-ttu-id="45de7-201">–Flags 的值可以为 ALL</span><span class="sxs-lookup"><span data-stu-id="45de7-201">–Flags can also be of value ALL</span></span>
    
    <span data-ttu-id="45de7-p119">还可以使用 cmdlet 的定位功能键入上一个示例。例如，若要将提供程序 ChatServer 添加到 AlwaysOn 方案，请键入：</span><span class="sxs-lookup"><span data-stu-id="45de7-p119">The previous example can also be typed using the positional feature of the cmdlet. For example, to add the provider ChatServer to the AlwaysOn scenario, type:</span></span>
    
        Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL

</div>

</div>

<span> </span>

</div>

</div>

</div>

