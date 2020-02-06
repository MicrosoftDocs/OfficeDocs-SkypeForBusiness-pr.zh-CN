---
title: 在 Skype for Business Server 2015 中管理集中日志记录服务配置设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 摘要：了解如何在 Skype for business Server 2015 中检索、更新和创建集中日志记录服务的配置设置。
ms.openlocfilehash: 95aa05cfcd31acda8e78927d674f3a19dff7ef56
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816581"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="25184-103">在 Skype for Business Server 2015 中管理集中日志记录服务配置设置</span><span class="sxs-lookup"><span data-stu-id="25184-103">Manage Centralized Logging Service configuration settings in Skype for Business Server 2015</span></span>

<span data-ttu-id="25184-104">**摘要：** 了解如何在 Skype for business Server 2015 中检索、更新和创建集中日志记录服务的配置设置。</span><span class="sxs-lookup"><span data-stu-id="25184-104">**Summary:** Learn how to retrieve, update, and create configuration settings for the Centralized Logging Service in Skype for Business Server 2015.</span></span>

<span data-ttu-id="25184-105">集中式日志记录服务由由集中日志记录服务控制器（CLSController）创建并使用的设置和参数进行控制和配置，以便向单个计算机的集中式日志记录服务代理发送命令（CLSAgent).</span><span class="sxs-lookup"><span data-stu-id="25184-105">The Centralized Logging Service is controlled and configured by settings and parameters that are created and used by the Centralized Logging Service Controller (CLSController) to send commands to the individual computer's Centralized Logging Service Agent (CLSAgent).</span></span> <span data-ttu-id="25184-106">该代理处理发送给它的命令，并（如果是启动命令）根据提供的配置信息使用方案、提供程序、跟踪持续时间和标志的配置开始收集跟踪日志。</span><span class="sxs-lookup"><span data-stu-id="25184-106">The agent processes the commands that are sent to it and (in the case of a Start command) uses the configuration of the scenarios, providers, trace duration, and flags to begin collecting trace logs according to the configuration information provided.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="25184-107">并非所有针对集中式日志记录服务列出的 Windows PowerShell cmdlet 均可用于 Skype for Business Server 2015 本地部署。</span><span class="sxs-lookup"><span data-stu-id="25184-107">Not all Windows PowerShell cmdlets listed for the Centralized Logging Service are intended for use with Skype for Business Server 2015 on-premises deployments.</span></span> <span data-ttu-id="25184-108">虽然它们看起来很有效，但以下 cmdlet 并非设计为与 Skype for business Server 2015 本地部署一起工作：</span><span class="sxs-lookup"><span data-stu-id="25184-108">Although they may appear to work, the following cmdlets are not designed to function with Skype for Business Server 2015 on-premises deployments:</span></span>

-  <span data-ttu-id="25184-109">**CsClsRegion cmdlet：** [CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) 、[Set-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps)、 [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps)和[Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="25184-109">**CsClsRegion cmdlets:** [Get-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps), [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps), and [Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps).</span></span>
-  <span data-ttu-id="25184-110">**CsClsSearchTerm cmdlet：** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps)和[Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="25184-110">**CsClsSearchTerm cmdlets:** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) and [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).</span></span>
-  <span data-ttu-id="25184-111">**CsClsSecurityGroup cmdlet：** [CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps)、 [Set-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps)、 [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)和[Remove-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="25184-111">**CsClsSecurityGroup cmdlets:** [Get-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [Set-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps),  [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps), and [Remove-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).</span></span>

<span data-ttu-id="25184-112">这些 cmdlet 中定义的设置不会妨碍或导致任何不利行为，但它们专用于 Microsoft Office 365，并且不会在本地部署中产生预期的结果。</span><span class="sxs-lookup"><span data-stu-id="25184-112">The settings defined in these cmdlets will not hinder or cause any adverse behavior, but they are designed for use with Microsoft Office 365 and will not yield the expected results in on-premises deployments.</span></span> <span data-ttu-id="25184-113">这并不是说在内部部署中没有使用这些 cmdlet，而是其使用是一个更高级的主题，在本文档中没有概述。</span><span class="sxs-lookup"><span data-stu-id="25184-113">This is not to say that there is no use for these cmdlets in on-premises deployments, but their use is a more advanced topic that is not covered in this documentation.</span></span>

<span data-ttu-id="25184-114">集中式日志记录服务可以在包含单个计算机或计算机池的范围内运行，在网站范围内（即定义的网站（如网站 Redmond），其中包含你的部署中的计算机和池集合，或者在全局范围内、部署中的所有计算机和池）。</span><span class="sxs-lookup"><span data-stu-id="25184-114">The Centralized Logging Service can be run at a scope that includes a single computer or a pool of computers, at a site scope (that is, a defined site such as the site Redmond that contains a collection of computer and pools in your deployment), or at a global scope (that is, all computers and pools in your deployment).</span></span>

<span data-ttu-id="25184-115">若要使用 Skype for Business Server Management Shell 配置集中日志记录服务范围，你必须是 CsAdministrator 或 CsServerAdministrator 角色的访问控制（RBAC）安全组的成员，或者是一个自定义的 RBAC 角色，包含这两个组中的任何一个。</span><span class="sxs-lookup"><span data-stu-id="25184-115">To configure the Centralized Logging Service scope by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="25184-116">若要返回此 cmdlet 已分配到的所有 RBAC 角色的列表（包括你自己创建的任何自定义 RBAC 角色），请从 Skype for Business Server Management Shell 或 Windows PowerShell 提示中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="25184-116">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

<span data-ttu-id="25184-117">例如：</span><span class="sxs-lookup"><span data-stu-id="25184-117">For example:</span></span>

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> <span data-ttu-id="25184-118">可以在 Windows PowerShell 或 CLSController 中运行的命令行命令之间存在基本差异。</span><span class="sxs-lookup"><span data-stu-id="25184-118">There are fundamental differences between the command-line commands that you can run in Windows PowerShell or CLSController.</span></span> <span data-ttu-id="25184-119">Windows PowerShell 提供了一种丰富的方法来配置和定义方案，并以一种有意义的方式重复使用这些方案来解决你的故障排除方案。</span><span class="sxs-lookup"><span data-stu-id="25184-119">Windows PowerShell provides a rich method to configure and define scenarios, and to reuse those scenarios in a meaningful way for your troubleshooting scenarios.</span></span> <span data-ttu-id="25184-120">尽管 CLSController 提供了快速有效的发出命令和获得结果的方法，但 CLSController 的命令集受到您从命令行获得的有限数量的命令的限制。</span><span class="sxs-lookup"><span data-stu-id="25184-120">While CLSController does provide a fast and efficient way to issue commands and get results, the command set for CLSController is limited by the finite commands that you have available from the command line.</span></span> <span data-ttu-id="25184-121">与 Windows PowerShell cmdlet 不同，CLSController 无法定义新方案、网站或全局级别的管理范围，以及无法动态配置的有限命令集的许多其他限制。</span><span class="sxs-lookup"><span data-stu-id="25184-121">Unlike the Windows PowerShell cmdlets, CLSController cannot define new scenarios, manage scope at a site or global level, and many other limitations of a finite command set that cannot be dynamically configured.</span></span> <span data-ttu-id="25184-122">虽然 CLSController 提供快速执行的方法，但 Windows PowerShell 提供了一种方法来扩展集中式日志记录服务功能，而不是 CLSController 的可能性。</span><span class="sxs-lookup"><span data-stu-id="25184-122">While CLSController provides a means for fast execution, Windows PowerShell provides a means to extend the Centralized Logging Service functionality beyond what is possible with CLSController.</span></span>

<span data-ttu-id="25184-123">可以在执行[搜索 CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps)、[显示 CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps)、[启动-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps)、 [Stop CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps)、 [Sync-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps)和[更新-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps)命令时使用-计算机参数定义单个计算机范围。</span><span class="sxs-lookup"><span data-stu-id="25184-123">A single computer scope can be defined during the execution of a [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps), [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps), [Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps), [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) and [Update-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) command using the -Computers parameter.</span></span> <span data-ttu-id="25184-124">-计算机参数接受目标计算机的完全限定的域名（Fqdn）的逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="25184-124">The -Computers parameter accepts a comma separated list of fully qualified domain names (FQDNs) for the target computer.</span></span>

> [!TIP]
> <span data-ttu-id="25184-125">你还可以定义池和要对其运行日志记录命令的池的逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="25184-125">You can also define -Pools and a comma separated list of pools that you want to run the logging commands on.</span></span>

<span data-ttu-id="25184-126">站点和全局范围在**新**的、**集的**和**删除**集中的日志记录服务 cmdlet 中定义。</span><span class="sxs-lookup"><span data-stu-id="25184-126">Site and Global scopes are defined in the **New-**, **Set-**, and **Remove-** Centralized Logging Service cmdlets.</span></span> <span data-ttu-id="25184-127">以下示例演示了如何设置站点和全局作用域。</span><span class="sxs-lookup"><span data-stu-id="25184-127">The following examples demonstrate how to set a site and a global scope.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="25184-128">显示的命令可能包含其他章节中涵盖的参数和概念。</span><span class="sxs-lookup"><span data-stu-id="25184-128">The commands shown may contain parameters and concepts that are covered in other sections.</span></span> <span data-ttu-id="25184-129">示例命令旨在演示如何使用 **-Identity**参数来定义作用域，并包含其他参数以实现完整性和指定范围。</span><span class="sxs-lookup"><span data-stu-id="25184-129">The example commands are intended to demonstrate the use of the **-Identity** parameter to define scope, and the other parameters are included for completeness and to specify the scope.</span></span> <span data-ttu-id="25184-130">有关 **Set-CsClsConfiguration** cmdlet 的详细信息，请参阅操作文档中的 [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="25184-130">For details about the **Set-CsClsConfiguration** cmdlets, see [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) in the Operations documentation.</span></span>

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="25184-131">检索当前集中式日志记录服务配置</span><span class="sxs-lookup"><span data-stu-id="25184-131">To retrieve the current Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="25184-132">启动 Skype for Business Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\* 和“Skype for Business 2015”\*\*\*\*，然后单击“Skype for Business Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="25184-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="25184-133">在命令行提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="25184-133">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Get-CsClsConfiguration
   ```

<span data-ttu-id="25184-134">使用**CsClsConfiguration**和**CsClsConfiguration** cmdlet 创建新配置或更新现有配置。当你运行**CsClsConfiguration**时，它将显示类似于以下屏幕截图的信息，其中部署当前具有默认全局配置，但未定义网站配置：</span><span class="sxs-lookup"><span data-stu-id="25184-134">Use the **New-CsClsConfiguration** and **Set-CsClsConfiguration** cmdlets to create a new configuration or to update an existing configuration.When you run **Get-CsClsConfiguration**, it displays information similar to the following screen shot, where the deployment currently has the default Global configuration, but no site configurations defined:</span></span>

![来自 Get-CsClsConfiguration 的示例输出。](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a><span data-ttu-id="25184-136">从计算机本地应用商店检索当前集中式日志记录服务配置</span><span class="sxs-lookup"><span data-stu-id="25184-136">To retrieve the current Centralized Logging Service configuration from the computer local store</span></span>

1. <span data-ttu-id="25184-137">启动 Skype for Business Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\* 和“Skype for Business 2015”\*\*\*\*，然后单击“Skype for Business Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="25184-137">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="25184-138">在命令行提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="25184-138">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Get-CsClsConfiguration -LocalStore
   ```

<span data-ttu-id="25184-139">使用**CsClsConfiguration**未指定任何参数的第一个示例时，该命令将引用数据的中央管理存储。</span><span class="sxs-lookup"><span data-stu-id="25184-139">When you use the first example where **Get-CsClsConfiguration** does not specify any parameters, the command references the Central Management store for the data.</span></span> <span data-ttu-id="25184-140">如果你指定参数 LocalStore，该命令将引用计算机 LocalStore，而不是中央管理存储。</span><span class="sxs-lookup"><span data-stu-id="25184-140">If you specify the parameter -LocalStore, the command references the computer LocalStore instead of the Central Management store.</span></span>
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a><span data-ttu-id="25184-141">检索当前定义的方案的列表</span><span class="sxs-lookup"><span data-stu-id="25184-141">To retrieve a listing of scenarios currently defined</span></span>

1. <span data-ttu-id="25184-142">启动 Skype for Business Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\* 和“Skype for Business 2015”\*\*\*\*，然后单击“Skype for Business Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="25184-142">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="25184-143">在命令行提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="25184-143">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
   ```

    <span data-ttu-id="25184-144">例如，检索在全局作用域定义的方案：</span><span class="sxs-lookup"><span data-stu-id="25184-144">For example, to retrieve the scenarios that is defined at the global scope:</span></span>

   ```PowerShell
   Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
   ```

<span data-ttu-id="25184-145">Cmdlet **CsClsConfiguration**始终显示属于给定范围的配置的方案。</span><span class="sxs-lookup"><span data-stu-id="25184-145">The cmdlet **Get-CsClsConfiguration** always displays the scenarios that are a part of a given scope's configuration.</span></span> <span data-ttu-id="25184-146">在大多数情况下，不会显示所有方案，而会截断它们。</span><span class="sxs-lookup"><span data-stu-id="25184-146">In most cases, all scenarios are not displayed, and are truncated.</span></span> <span data-ttu-id="25184-147">此处使用的命令列出所有方案和有关所使用的提供程序、设置和标记的部分信息。</span><span class="sxs-lookup"><span data-stu-id="25184-147">The command used here lists all of the scenarios and partial information about what providers, settings, and flags are used.</span></span>
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="25184-148">使用 Windows PowerShell 更新集中日志记录服务的全局范围</span><span class="sxs-lookup"><span data-stu-id="25184-148">To update a global scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1. <span data-ttu-id="25184-149">启动 Skype for Business Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\* 和“Skype for Business 2015”\*\*\*\*，然后单击“Skype for Business Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="25184-149">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="25184-150">在命令行提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="25184-150">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   <span data-ttu-id="25184-151">例如：</span><span class="sxs-lookup"><span data-stu-id="25184-151">For example:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
   ```

<span data-ttu-id="25184-p111">该命令指示部署中的每个计算机和池中的 CLSAgent 将跟踪文件上的滚动值的大小设置为 40 MB。所有站点中的计算机和池都受该命令的影响，并且会将其已配置的跟踪日志滚动值设置为 40 MB。</span><span class="sxs-lookup"><span data-stu-id="25184-p111">The command tells the CLSAgent on each computer and pool in the deployment to set the size of the rollover value on the tracing file to 40 megabytes. Computers and pools in all sites are affected by the command, and will set their configured trace log rollover value to 40 megabytes.</span></span>
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="25184-154">使用 Windows PowerShell 更新集中日志记录服务的网站范围</span><span class="sxs-lookup"><span data-stu-id="25184-154">To update a site scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1. <span data-ttu-id="25184-155">启动 Skype for Business Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\* 和“Skype for Business 2015”\*\*\*\*，然后单击“Skype for Business Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="25184-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="25184-156">在命令行提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="25184-156">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   <span data-ttu-id="25184-157">例如：</span><span class="sxs-lookup"><span data-stu-id="25184-157">For example:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40
   ```

> [!NOTE]
> <span data-ttu-id="25184-p112">如示例中所示，日志文件的默认位置是 %TEMP%\Tracing。但是，由于实际上是 CLSAgent 写入该文件，而且 CLSAgent 以 Network Service 的身份运行，因此 %TEMP% 变量将展开到 %WINDIR%\ServiceProfiles\NetworkService\AppData\Local。</span><span class="sxs-lookup"><span data-stu-id="25184-p112">As noted in the example, the default location of the log files is %TEMP%\Tracing. However, because it is actually CLSAgent that is writing the file and CSLAgent runs as Network Service, the %TEMP% variable expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span></span>

<span data-ttu-id="25184-p113">该命令指示 Redmond 站点中的每个计算机和池中的 CLSAgent 将跟踪文件上的滚动值的大小设置为 40 MB。其他站点中的计算机和池不会受该命令的影响，并将继续使用当前配置的跟踪日志滚动值（默认定义的 (20 MB) 或在日志记录会话开始时定义的）。</span><span class="sxs-lookup"><span data-stu-id="25184-p113">The command tells the CLSAgent on each computer and pool in the site Redmond to set the size of the rollover value on the tracing file to 40 megabytes. Computers and pools in other sites will not be affected by the command, and will continue to use the currently configured trace log rollover value defined either by default (20 megabytes) or during the start of the logging session.</span></span>
### <a name="to-create-a-new-centralized-logging-service-configuration"></a><span data-ttu-id="25184-162">创建新的集中式日志记录服务配置</span><span class="sxs-lookup"><span data-stu-id="25184-162">To create a new Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="25184-163">启动 Skype for Business Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\* 和“Skype for Business 2015”\*\*\*\*，然后单击“Skype for Business Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="25184-163">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="25184-164">在命令行提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="25184-164">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > <span data-ttu-id="25184-165">利用 New-CsClsConfiguration，可以访问大量可选配置设置。</span><span class="sxs-lookup"><span data-stu-id="25184-165">New-CsClsConfiguration provides access to a large number of optional configuration settings.</span></span> <span data-ttu-id="25184-166">有关配置选项的详细信息，请参阅[CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)和[了解集中日志记录服务配置设置](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx)。</span><span class="sxs-lookup"><span data-stu-id="25184-166">For details about the configuration options, see [Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) and [Understanding Centralized Logging Service Configuration Settings](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx).</span></span>

<span data-ttu-id="25184-167">例如，要创建用于定义缓存文件的网络文件夹、日志文件的滚动时间段和日志文件的滚动大小的新配置，您将键入：</span><span class="sxs-lookup"><span data-stu-id="25184-167">For example, to create a new configuration that defines a network folder for cache files, rollover time period for the log files and rollover size for the log files, you would type:</span></span>

  ```PowerShell
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

<span data-ttu-id="25184-168">你应该仔细规划新配置的创建以及如何为集中式日志记录服务定义新属性。</span><span class="sxs-lookup"><span data-stu-id="25184-168">You should carefully plan the creation of new configurations and how you define new properties for the Centralized Logging Service.</span></span> <span data-ttu-id="25184-169">您在进行更改时应格外小心，并应确保了解对您正确记录问题方案的能力的影响。</span><span class="sxs-lookup"><span data-stu-id="25184-169">You should be cautious about making changes and make sure you understand the impact on your ability to properly log problem scenarios.</span></span> <span data-ttu-id="25184-170">您应更改配置，提高管理日志大小和滚动周期（允许在问题发生时予以解决）的能力。</span><span class="sxs-lookup"><span data-stu-id="25184-170">You should make changes to the configuration that will enhance your ability to manage logs to a size and a rollover period that will allow problem solving when it arises.</span></span>
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a><span data-ttu-id="25184-171">删除现有的集中日志记录服务配置</span><span class="sxs-lookup"><span data-stu-id="25184-171">To remove an existing Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="25184-172">启动 Skype for Business Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\* 和“Skype for Business 2015”\*\*\*\*，然后单击“Skype for Business Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="25184-172">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="25184-173">在命令行提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="25184-173">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

<span data-ttu-id="25184-174">例如，若要删除你创建的集中日志记录服务配置以增加日志文件滚动更新时间，请增加滚动更新日志文件大小，并将日志文件缓存位置设置为网络共享，如下所示：</span><span class="sxs-lookup"><span data-stu-id="25184-174">For example, to remove a Centralized Logging Service configuration that you created to increase the log file rollover time, increase the rollover log file size, and set the log file cache location to a network share as follows:</span></span>

  ```PowerShell
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> <span data-ttu-id="25184-175">这是在 "创建新的集中日志记录服务配置" 过程中创建的新配置。</span><span class="sxs-lookup"><span data-stu-id="25184-175">This is the new configuration that was created in the procedure "To create a new Centralized Logging Service configuration."</span></span>

<span data-ttu-id="25184-176">如果选择删除站点级配置，站点将使用全局设置。</span><span class="sxs-lookup"><span data-stu-id="25184-176">If you choose to remove a site-level configuration, the site will use the global settings.</span></span>
## <a name="see-also"></a><span data-ttu-id="25184-177">另请参阅</span><span class="sxs-lookup"><span data-stu-id="25184-177">See also</span></span>

[<span data-ttu-id="25184-178">配置 Skype for Business Server 2015 中的集中日志记录服务的提供程序</span><span class="sxs-lookup"><span data-stu-id="25184-178">Configure providers for Centralized Logging Service in Skype for Business Server 2015</span></span>](configure-providers.md)

[<span data-ttu-id="25184-179">配置 Skype for Business Server 2015 中的集中日志记录服务的方案</span><span class="sxs-lookup"><span data-stu-id="25184-179">Configure scenarios for the Centralized Logging Service in Skype for Business Server 2015</span></span>](configure-scenarios.md)

[<span data-ttu-id="25184-180">Centralized Logging Service in Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="25184-180">Centralized Logging Service in Skype for Business 2015</span></span>](centralized-logging-service.md)

[<span data-ttu-id="25184-181">Set-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="25184-181">Set-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="25184-182">Get-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="25184-182">Get-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="25184-183">New-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="25184-183">New-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="25184-184">Remove-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="25184-184">Remove-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)
