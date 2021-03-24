---
title: Manage Centralized Logging Service configuration settings in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
description: 摘要：了解如何在 Skype for Business Server 2015 中检索、更新和创建集中日志记录服务的配置设置。
ms.openlocfilehash: fb2d66e6ff72bc5fb5a4c8c987713f3ca7030ab5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098858"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="48b2f-103">Manage Centralized Logging Service configuration settings in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="48b2f-103">Manage Centralized Logging Service configuration settings in Skype for Business Server 2015</span></span>

<span data-ttu-id="48b2f-104">**摘要：** 了解如何在 Skype for Business Server 2015 中检索、更新和创建集中日志记录服务的配置设置。</span><span class="sxs-lookup"><span data-stu-id="48b2f-104">**Summary:** Learn how to retrieve, update, and create configuration settings for the Centralized Logging Service in Skype for Business Server 2015.</span></span>

<span data-ttu-id="48b2f-105">集中日志记录服务由集中日志记录服务控制器 (CLSController) 创建和使用的设置和参数进行控制和配置，以将命令发送到单台计算机的集中日志记录服务代理 (CLSAgent) 。</span><span class="sxs-lookup"><span data-stu-id="48b2f-105">The Centralized Logging Service is controlled and configured by settings and parameters that are created and used by the Centralized Logging Service Controller (CLSController) to send commands to the individual computer's Centralized Logging Service Agent (CLSAgent).</span></span> <span data-ttu-id="48b2f-106">代理处理发送给它的命令 (如果启动命令) 则使用方案、提供程序、跟踪持续时间和标志的配置开始根据提供的配置信息收集跟踪日志。</span><span class="sxs-lookup"><span data-stu-id="48b2f-106">The agent processes the commands that are sent to it and (in the case of a Start command) uses the configuration of the scenarios, providers, trace duration, and flags to begin collecting trace logs according to the configuration information provided.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="48b2f-107">并非为Windows PowerShell日志记录服务列出的所有 cmdlet 都用于 Skype for Business Server 2015 本地部署。</span><span class="sxs-lookup"><span data-stu-id="48b2f-107">Not all Windows PowerShell cmdlets listed for the Centralized Logging Service are intended for use with Skype for Business Server 2015 on-premises deployments.</span></span> <span data-ttu-id="48b2f-108">尽管它们看起来可能正常运行，但以下 cmdlet 并非设计为与 Skype for Business Server 2015 本地部署一起运行：</span><span class="sxs-lookup"><span data-stu-id="48b2f-108">Although they may appear to work, the following cmdlets are not designed to function with Skype for Business Server 2015 on-premises deployments:</span></span>

-  <span data-ttu-id="48b2f-109">**CsClsRegion** cmdlet：Get-CsClsRegion、Set-CsClsRegion、New-CsClsRegion 和 [Remove-CsClsRegion。](/powershell/module/skype/remove-csclsregion?view=skype-ps) [](/powershell/module/skype/get-csclsregion?view=skype-ps) [](/powershell/module/skype/set-csclsregion?view=skype-ps) [](/powershell/module/skype/new-csclsregion?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="48b2f-109">**CsClsRegion cmdlets:** [Get-CsClsRegion](/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set-CsClsRegion](/powershell/module/skype/set-csclsregion?view=skype-ps), [New-CsClsRegion](/powershell/module/skype/new-csclsregion?view=skype-ps), and [Remove-CsClsRegion](/powershell/module/skype/remove-csclsregion?view=skype-ps).</span></span>
-  <span data-ttu-id="48b2f-110">**CsClsSearchTerm cmdlet：** [Get-CsClsSearchTerm](/powershell/module/skype/get-csclssearchterm?view=skype-ps) 和 [Set-CsClsSearchTerm](/powershell/module/skype/set-csclssearchterm?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="48b2f-110">**CsClsSearchTerm cmdlets:** [Get-CsClsSearchTerm](/powershell/module/skype/get-csclssearchterm?view=skype-ps) and [Set-CsClsSearchTerm](/powershell/module/skype/set-csclssearchterm?view=skype-ps).</span></span>
-  <span data-ttu-id="48b2f-111">**CsClsSecurityGroup** cmdlet：Get-CsClsSecurityGroup、Set-CsClsSecurityGroup、New-CsClsSecurityGroup 和 [Remove-CsClsSecurityGroup。](/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps) [](/powershell/module/skype/get-csclssecuritygroup?view=skype-ps) [](/powershell/module/skype/set-csclssecuritygroup?view=skype-ps) [](/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="48b2f-111">**CsClsSecurityGroup cmdlets:** [Get-CsClsSecurityGroup](/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [Set-CsClsSecurityGroup](/powershell/module/skype/set-csclssecuritygroup?view=skype-ps),  [New-CsClsSecurityGroup](/powershell/module/skype/new-csclssecuritygroup?view=skype-ps), and [Remove-CsClsSecurityGroup](/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).</span></span>

<span data-ttu-id="48b2f-112">这些 cmdlet 中定义的设置不会阻碍或导致任何不良行为，但它们设计为与 Microsoft 365 或 Office 365 一同使用，不会在本地部署中产生预期结果。</span><span class="sxs-lookup"><span data-stu-id="48b2f-112">The settings defined in these cmdlets will not hinder or cause any adverse behavior, but they are designed for use with Microsoft 365 or Office 365 and will not yield the expected results in on-premises deployments.</span></span> <span data-ttu-id="48b2f-113">这并不是说在内部部署中没有使用这些 cmdlet，而是其使用是一个更高级的主题，在本文档中没有概述。</span><span class="sxs-lookup"><span data-stu-id="48b2f-113">This is not to say that there is no use for these cmdlets in on-premises deployments, but their use is a more advanced topic that is not covered in this documentation.</span></span>

<span data-ttu-id="48b2f-114">集中日志记录服务可在包括单台计算机或计算机池的作用域、站点作用域 (（即，在部署) 中包含计算机和池集合的已定义站点（如站点 Redmond）或全局范围 (（即部署) 中所有计算机和池）运行。</span><span class="sxs-lookup"><span data-stu-id="48b2f-114">The Centralized Logging Service can be run at a scope that includes a single computer or a pool of computers, at a site scope (that is, a defined site such as the site Redmond that contains a collection of computer and pools in your deployment), or at a global scope (that is, all computers and pools in your deployment).</span></span>

<span data-ttu-id="48b2f-115">若要使用 Skype for Business Server 命令行管理程序配置集中日志记录服务作用域，您必须是基于 CsAdministrator 或 CsServerAdministrator 角色的访问控制 (RBAC) 安全组的成员，或者是包含这两个组之一的自定义 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="48b2f-115">To configure the Centralized Logging Service scope by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="48b2f-116">要返回分配了此 cmdlet 的所有 RBAC 角色的列表 (包括您自己创建的任何自定义 RBAC 角色) 请从 Skype for Business Server 命令行管理程序 或 Windows PowerShell 提示符运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="48b2f-116">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

<span data-ttu-id="48b2f-117">例如：</span><span class="sxs-lookup"><span data-stu-id="48b2f-117">For example:</span></span>

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> <span data-ttu-id="48b2f-118">可以在 Windows PowerShell 或 CLSController 中运行的命令行命令之间存在基本差异。</span><span class="sxs-lookup"><span data-stu-id="48b2f-118">There are fundamental differences between the command-line commands that you can run in Windows PowerShell or CLSController.</span></span> <span data-ttu-id="48b2f-119">Windows PowerShell提供了一种丰富的方法来配置和定义方案，并针对故障排除方案以有意义的方式重用这些方案。</span><span class="sxs-lookup"><span data-stu-id="48b2f-119">Windows PowerShell provides a rich method to configure and define scenarios, and to reuse those scenarios in a meaningful way for your troubleshooting scenarios.</span></span> <span data-ttu-id="48b2f-120">虽然 CLSController 提供了一种快速有效的发出命令和获取结果的方法，但 CLSController 的命令集受命令行提供的有限命令限制。</span><span class="sxs-lookup"><span data-stu-id="48b2f-120">While CLSController does provide a fast and efficient way to issue commands and get results, the command set for CLSController is limited by the finite commands that you have available from the command line.</span></span> <span data-ttu-id="48b2f-121">与 Windows PowerShell cmdlet 不同，CLSController 无法定义新方案、在站点或全局级别管理范围，以及无法动态配置的有限命令集的许多其他限制。</span><span class="sxs-lookup"><span data-stu-id="48b2f-121">Unlike the Windows PowerShell cmdlets, CLSController cannot define new scenarios, manage scope at a site or global level, and many other limitations of a finite command set that cannot be dynamically configured.</span></span> <span data-ttu-id="48b2f-122">CLSController 提供了一种快速执行方法，Windows PowerShell提供了一种扩展集中日志记录服务功能的方式，超出了 CLSController 的可能范围。</span><span class="sxs-lookup"><span data-stu-id="48b2f-122">While CLSController provides a means for fast execution, Windows PowerShell provides a means to extend the Centralized Logging Service functionality beyond what is possible with CLSController.</span></span>

<span data-ttu-id="48b2f-123">在执行 Search-CsClsLogging、Show-CsClsLogging、Start-CsClsLogging、Stop-CsClsLogging、Sync-CsClsLogging 和[](/powershell/module/skype/stop-csclslogging?view=skype-ps)[](/powershell/module/skype/start-csclslogging?view=skype-ps)[](/powershell/module/skype/search-csclslogging?view=skype-ps)[](/powershell/module/skype/show-csclslogging?view=skype-ps)[Update-CsClsLogging](/powershell/module/skype/update-csclslogging?view=skype-ps)命令期间，可以使用 -Computers 参数定义单个计算机作用域。 [](/powershell/module/skype/sync-csclslogging?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="48b2f-123">A single computer scope can be defined during the execution of a [Search-CsClsLogging](/powershell/module/skype/search-csclslogging?view=skype-ps), [Show-CsClsLogging](/powershell/module/skype/show-csclslogging?view=skype-ps), [Start-CsClsLogging](/powershell/module/skype/start-csclslogging?view=skype-ps), [Stop-CsClsLogging](/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync-CsClsLogging](/powershell/module/skype/sync-csclslogging?view=skype-ps) and [Update-CsClsLogging](/powershell/module/skype/update-csclslogging?view=skype-ps) command using the -Computers parameter.</span></span> <span data-ttu-id="48b2f-124">-Computers 参数接受目标计算机的完全限定域名 (FQDN) 逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="48b2f-124">The -Computers parameter accepts a comma separated list of fully qualified domain names (FQDNs) for the target computer.</span></span>

> [!TIP]
> <span data-ttu-id="48b2f-125">还可以定义 -Pools 和要运行日志记录命令的以逗号分隔的池列表。</span><span class="sxs-lookup"><span data-stu-id="48b2f-125">You can also define -Pools and a comma separated list of pools that you want to run the logging commands on.</span></span>

<span data-ttu-id="48b2f-126">站点和全局范围在 **New-、Set-** 和 **Remove-** Centralized Logging Service cmdlet 中定义。</span><span class="sxs-lookup"><span data-stu-id="48b2f-126">Site and Global scopes are defined in the **New-**, **Set-**, and **Remove-** Centralized Logging Service cmdlets.</span></span> <span data-ttu-id="48b2f-127">以下示例演示如何设置站点和全局范围。</span><span class="sxs-lookup"><span data-stu-id="48b2f-127">The following examples demonstrate how to set a site and a global scope.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="48b2f-128">显示的命令可能包含其他部分中介绍的参数和概念。</span><span class="sxs-lookup"><span data-stu-id="48b2f-128">The commands shown may contain parameters and concepts that are covered in other sections.</span></span> <span data-ttu-id="48b2f-129">示例命令旨在演示如何使用 **-Identity** 参数定义范围，并包括其他参数以用于完成和指定范围。</span><span class="sxs-lookup"><span data-stu-id="48b2f-129">The example commands are intended to demonstrate the use of the **-Identity** parameter to define scope, and the other parameters are included for completeness and to specify the scope.</span></span> <span data-ttu-id="48b2f-130">有关 **Set-CsClsConfiguration** cmdlet 的详细信息，请参阅操作文档中的 [Set-CsClsConfiguration。](/powershell/module/skype/set-csclsconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="48b2f-130">For details about the **Set-CsClsConfiguration** cmdlets, see [Set-CsClsConfiguration](/powershell/module/skype/set-csclsconfiguration?view=skype-ps) in the Operations documentation.</span></span>

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="48b2f-131">检索当前的集中日志记录服务配置</span><span class="sxs-lookup"><span data-stu-id="48b2f-131">To retrieve the current Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="48b2f-132">启动 Skype for Business Server命令行管理程序：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="48b2f-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="48b2f-133">在命令行提示符下键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="48b2f-133">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Get-CsClsConfiguration
   ```

<span data-ttu-id="48b2f-134">使用 **New-CsClsConfiguration** 和 **Set-CsClsConfiguration** cmdlet 创建新配置或更新现有配置。运行 **Get-CsClsConfiguration** 时，将显示类似于以下屏幕截图的信息，其中部署当前具有默认的全局配置，但没有定义站点配置：</span><span class="sxs-lookup"><span data-stu-id="48b2f-134">Use the **New-CsClsConfiguration** and **Set-CsClsConfiguration** cmdlets to create a new configuration or to update an existing configuration.When you run **Get-CsClsConfiguration**, it displays information similar to the following screen shot, where the deployment currently has the default Global configuration, but no site configurations defined:</span></span>

![Get-CsClsConfiguration 的示例输出。](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a><span data-ttu-id="48b2f-136">从计算机本地存储检索当前集中日志记录服务配置</span><span class="sxs-lookup"><span data-stu-id="48b2f-136">To retrieve the current Centralized Logging Service configuration from the computer local store</span></span>

1. <span data-ttu-id="48b2f-137">启动 Skype for Business Server命令行管理程序：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="48b2f-137">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="48b2f-138">在命令行提示符下键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="48b2f-138">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Get-CsClsConfiguration -LocalStore
   ```

<span data-ttu-id="48b2f-139">使用第一个示例（其中 **Get-CsClsConfiguration** 未指定任何参数）时，该命令将引用数据的中央管理存储。</span><span class="sxs-lookup"><span data-stu-id="48b2f-139">When you use the first example where **Get-CsClsConfiguration** does not specify any parameters, the command references the Central Management store for the data.</span></span> <span data-ttu-id="48b2f-140">如果指定参数 -LocalStore，该命令将引用计算机 LocalStore，而不是中央管理存储。</span><span class="sxs-lookup"><span data-stu-id="48b2f-140">If you specify the parameter -LocalStore, the command references the computer LocalStore instead of the Central Management store.</span></span>
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a><span data-ttu-id="48b2f-141">检索当前定义的方案列表</span><span class="sxs-lookup"><span data-stu-id="48b2f-141">To retrieve a listing of scenarios currently defined</span></span>

1. <span data-ttu-id="48b2f-142">启动 Skype for Business Server命令行管理程序：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="48b2f-142">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="48b2f-143">在命令行提示符下键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="48b2f-143">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
   ```

    <span data-ttu-id="48b2f-144">例如，若要检索在全局范围定义的方案：</span><span class="sxs-lookup"><span data-stu-id="48b2f-144">For example, to retrieve the scenarios that is defined at the global scope:</span></span>

   ```PowerShell
   Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
   ```

<span data-ttu-id="48b2f-145">cmdlet **Get-CsClsConfiguration** 始终显示属于给定范围的配置的一部分的方案。</span><span class="sxs-lookup"><span data-stu-id="48b2f-145">The cmdlet **Get-CsClsConfiguration** always displays the scenarios that are a part of a given scope's configuration.</span></span> <span data-ttu-id="48b2f-146">在大多数情况下，不会显示所有方案，并且将被截断。</span><span class="sxs-lookup"><span data-stu-id="48b2f-146">In most cases, all scenarios are not displayed, and are truncated.</span></span> <span data-ttu-id="48b2f-147">此处使用的命令列出了所有方案和有关使用哪些提供程序、设置和标志的部分信息。</span><span class="sxs-lookup"><span data-stu-id="48b2f-147">The command used here lists all of the scenarios and partial information about what providers, settings, and flags are used.</span></span>
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="48b2f-148">使用日志记录服务更新集中日志记录服务的全局Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="48b2f-148">To update a global scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1. <span data-ttu-id="48b2f-149">启动 Skype for Business Server命令行管理程序：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="48b2f-149">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="48b2f-150">在命令行提示符下键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="48b2f-150">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   <span data-ttu-id="48b2f-151">例如：</span><span class="sxs-lookup"><span data-stu-id="48b2f-151">For example:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
   ```

<span data-ttu-id="48b2f-152">该命令指示部署中每台计算机和池上的 CLSAgent 将跟踪文件上的滚动值大小设置为 40 MB。</span><span class="sxs-lookup"><span data-stu-id="48b2f-152">The command tells the CLSAgent on each computer and pool in the deployment to set the size of the rollover value on the tracing file to 40 megabytes.</span></span> <span data-ttu-id="48b2f-153">命令影响所有站点中的计算机和池，并且将配置跟踪日志滚动值设置为 40 MB。</span><span class="sxs-lookup"><span data-stu-id="48b2f-153">Computers and pools in all sites are affected by the command, and will set their configured trace log rollover value to 40 megabytes.</span></span>
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="48b2f-154">使用集中日志记录服务更新站点Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="48b2f-154">To update a site scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1. <span data-ttu-id="48b2f-155">启动 Skype for Business Server命令行管理程序：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="48b2f-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="48b2f-156">在命令行提示符下键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="48b2f-156">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   <span data-ttu-id="48b2f-157">例如：</span><span class="sxs-lookup"><span data-stu-id="48b2f-157">For example:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40
   ```

> [!NOTE]
> <span data-ttu-id="48b2f-158">如示例中所示，日志文件的默认位置为 %TEMP%\Tracing。</span><span class="sxs-lookup"><span data-stu-id="48b2f-158">As noted in the example, the default location of the log files is %TEMP%\Tracing.</span></span> <span data-ttu-id="48b2f-159">但是，由于编写文件实际上是 CLSAgent，并且 CSLAgent 作为网络服务运行，%TEMP% 变量将展开到 %WINDIR%\ServiceProfiles\NetworkService\AppData\Local。</span><span class="sxs-lookup"><span data-stu-id="48b2f-159">However, because it is actually CLSAgent that is writing the file and CSLAgent runs as Network Service, the %TEMP% variable expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span></span>

<span data-ttu-id="48b2f-160">该命令指示站点 Redmond 中每台计算机和池上的 CLSAgent 将跟踪文件上的滚动值大小设置为 40 MB。</span><span class="sxs-lookup"><span data-stu-id="48b2f-160">The command tells the CLSAgent on each computer and pool in the site Redmond to set the size of the rollover value on the tracing file to 40 megabytes.</span></span> <span data-ttu-id="48b2f-161">其他站点中的计算机和池不会受该命令的影响，将继续使用当前配置的跟踪日志滚动值（默认为 (20 MB) 或在日志记录会话开始时定义）。</span><span class="sxs-lookup"><span data-stu-id="48b2f-161">Computers and pools in other sites will not be affected by the command, and will continue to use the currently configured trace log rollover value defined either by default (20 megabytes) or during the start of the logging session.</span></span>
### <a name="to-create-a-new-centralized-logging-service-configuration"></a><span data-ttu-id="48b2f-162">创建新的集中日志记录服务配置</span><span class="sxs-lookup"><span data-stu-id="48b2f-162">To create a new Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="48b2f-163">启动 Skype for Business Server命令行管理程序：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="48b2f-163">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="48b2f-164">在命令行提示符下键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="48b2f-164">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > <span data-ttu-id="48b2f-165">New-CsClsConfiguration提供对大量可选配置设置的访问权限。</span><span class="sxs-lookup"><span data-stu-id="48b2f-165">New-CsClsConfiguration provides access to a large number of optional configuration settings.</span></span> <span data-ttu-id="48b2f-166">有关配置选项的详细信息，请参阅[Get-CsClsConfiguration](/powershell/module/skype/get-csclsconfiguration?view=skype-ps)和[Understanding Centralized Logging Service Configuration Settings。](/previous-versions/office/lync-server-2013/lync-server-2013-understanding-centralized-logging-service-configuration-settings)</span><span class="sxs-lookup"><span data-stu-id="48b2f-166">For details about the configuration options, see [Get-CsClsConfiguration](/powershell/module/skype/get-csclsconfiguration?view=skype-ps) and [Understanding Centralized Logging Service Configuration Settings](/previous-versions/office/lync-server-2013/lync-server-2013-understanding-centralized-logging-service-configuration-settings).</span></span>

<span data-ttu-id="48b2f-167">例如，若要创建定义缓存文件网络文件夹、日志文件滚动时间段和日志文件滚动大小的新配置，应键入：</span><span class="sxs-lookup"><span data-stu-id="48b2f-167">For example, to create a new configuration that defines a network folder for cache files, rollover time period for the log files and rollover size for the log files, you would type:</span></span>

  ```PowerShell
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

<span data-ttu-id="48b2f-168">您应仔细规划新配置的创建以及如何为集中日志记录服务定义新属性。</span><span class="sxs-lookup"><span data-stu-id="48b2f-168">You should carefully plan the creation of new configurations and how you define new properties for the Centralized Logging Service.</span></span> <span data-ttu-id="48b2f-169">应谨慎进行更改，并确保了解对正确记录问题方案的能力的影响。</span><span class="sxs-lookup"><span data-stu-id="48b2f-169">You should be cautious about making changes and make sure you understand the impact on your ability to properly log problem scenarios.</span></span> <span data-ttu-id="48b2f-170">应更改配置，以增强管理日志的能力，使其适应大小和滚动周期，以便问题出现时能够解决问题。</span><span class="sxs-lookup"><span data-stu-id="48b2f-170">You should make changes to the configuration that will enhance your ability to manage logs to a size and a rollover period that will allow problem solving when it arises.</span></span>
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a><span data-ttu-id="48b2f-171">删除现有的集中日志记录服务配置</span><span class="sxs-lookup"><span data-stu-id="48b2f-171">To remove an existing Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="48b2f-172">启动 Skype for Business Server命令行管理程序：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="48b2f-172">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="48b2f-173">在命令行提示符下键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="48b2f-173">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

<span data-ttu-id="48b2f-174">例如，若要删除为增加 日志文件 滚动时间而创建的集中日志记录服务配置，请增加 日志文件 滚动大小，将 日志文件 缓存位置设置为网络共享，如下所示：</span><span class="sxs-lookup"><span data-stu-id="48b2f-174">For example, to remove a Centralized Logging Service configuration that you created to increase the log file rollover time, increase the rollover log file size, and set the log file cache location to a network share as follows:</span></span>

  ```PowerShell
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> <span data-ttu-id="48b2f-175">这是在"创建新的集中日志记录服务配置"过程中创建的新配置。</span><span class="sxs-lookup"><span data-stu-id="48b2f-175">This is the new configuration that was created in the procedure "To create a new Centralized Logging Service configuration."</span></span>

<span data-ttu-id="48b2f-176">如果选择删除站点级别的配置，则站点将使用全局设置。</span><span class="sxs-lookup"><span data-stu-id="48b2f-176">If you choose to remove a site-level configuration, the site will use the global settings.</span></span>
## <a name="see-also"></a><span data-ttu-id="48b2f-177">另请参阅</span><span class="sxs-lookup"><span data-stu-id="48b2f-177">See also</span></span>

[<span data-ttu-id="48b2f-178">Configure providers for Centralized Logging Service in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="48b2f-178">Configure providers for Centralized Logging Service in Skype for Business Server 2015</span></span>](configure-providers.md)

[<span data-ttu-id="48b2f-179">Configure scenarios for the Centralized Logging Service in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="48b2f-179">Configure scenarios for the Centralized Logging Service in Skype for Business Server 2015</span></span>](configure-scenarios.md)

[<span data-ttu-id="48b2f-180">Skype for Business 2015 中的集中日志记录服务</span><span class="sxs-lookup"><span data-stu-id="48b2f-180">Centralized Logging Service in Skype for Business 2015</span></span>](centralized-logging-service.md)

[<span data-ttu-id="48b2f-181">Set-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="48b2f-181">Set-CsClsConfiguration</span></span>](/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="48b2f-182">Get-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="48b2f-182">Get-CsClsConfiguration</span></span>](/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="48b2f-183">New-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="48b2f-183">New-CsClsConfiguration</span></span>](/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="48b2f-184">Remove-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="48b2f-184">Remove-CsClsConfiguration</span></span>](/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)