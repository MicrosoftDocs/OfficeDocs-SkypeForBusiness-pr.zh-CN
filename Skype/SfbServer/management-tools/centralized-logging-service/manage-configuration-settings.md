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
ms.openlocfilehash: ed75aab211f2d2abbf0a2007fd83e5be8bb70404
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221172"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="dc39b-103">在 Skype for Business Server 2015 中管理集中日志记录服务配置设置</span><span class="sxs-lookup"><span data-stu-id="dc39b-103">Manage Centralized Logging Service configuration settings in Skype for Business Server 2015</span></span>

<span data-ttu-id="dc39b-104">**摘要：** 了解如何检索、更新和创建 Skype for Business Server 2015 中的集中日志记录服务的配置设置。</span><span class="sxs-lookup"><span data-stu-id="dc39b-104">**Summary:** Learn how to retrieve, update, and create configuration settings for the Centralized Logging Service in Skype for Business Server 2015.</span></span>

<span data-ttu-id="dc39b-105">集中日志记录服务由集中日志记录服务控制器（CLSController）创建和使用的设置和参数进行控制和配置，以将命令发送到单个计算机的集中日志记录服务代理（CLSAgent）。</span><span class="sxs-lookup"><span data-stu-id="dc39b-105">The Centralized Logging Service is controlled and configured by settings and parameters that are created and used by the Centralized Logging Service Controller (CLSController) to send commands to the individual computer's Centralized Logging Service Agent (CLSAgent).</span></span> <span data-ttu-id="dc39b-106">代理会处理发送给它的命令，（在启动命令的情况下）使用方案、提供程序、跟踪持续时间和标志的配置，根据提供的配置信息开始收集跟踪日志。</span><span class="sxs-lookup"><span data-stu-id="dc39b-106">The agent processes the commands that are sent to it and (in the case of a Start command) uses the configuration of the scenarios, providers, trace duration, and flags to begin collecting trace logs according to the configuration information provided.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="dc39b-107">并不是所有列出的集中日志记录服务的 Windows PowerShell cmdlet 都可用于 Skype for Business Server 2015 本地部署。</span><span class="sxs-lookup"><span data-stu-id="dc39b-107">Not all Windows PowerShell cmdlets listed for the Centralized Logging Service are intended for use with Skype for Business Server 2015 on-premises deployments.</span></span> <span data-ttu-id="dc39b-108">虽然看起来似乎可行，但以下 cmdlet 不是为在 Skype for business Server 2015 本地部署中运行而设计的：</span><span class="sxs-lookup"><span data-stu-id="dc39b-108">Although they may appear to work, the following cmdlets are not designed to function with Skype for Business Server 2015 on-premises deployments:</span></span>

-  <span data-ttu-id="dc39b-109">**CsClsRegion cmdlet：** [CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) 、[Set-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps)、 [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps)和[Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="dc39b-109">**CsClsRegion cmdlets:** [Get-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps), [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps), and [Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps).</span></span>
-  <span data-ttu-id="dc39b-110">**CsClsSearchTerm cmdlet：** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) 和 [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="dc39b-110">**CsClsSearchTerm cmdlets:** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) and [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).</span></span>
-  <span data-ttu-id="dc39b-111">**CsClsSecurityGroup cmdlet：** [CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps)、 [Set-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps)、 [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)和[Remove-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="dc39b-111">**CsClsSecurityGroup cmdlets:** [Get-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [Set-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps),  [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps), and [Remove-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).</span></span>

<span data-ttu-id="dc39b-112">这些 cmdlet 中定义的设置不会妨碍或导致任何不利行为，但它们设计为与 Microsoft 365 或 Office 365 配合使用，并且不会在本地部署中生成预期结果。</span><span class="sxs-lookup"><span data-stu-id="dc39b-112">The settings defined in these cmdlets will not hinder or cause any adverse behavior, but they are designed for use with Microsoft 365 or Office 365 and will not yield the expected results in on-premises deployments.</span></span> <span data-ttu-id="dc39b-113">这并不是说在内部部署中没有使用这些 cmdlet，而是其使用是一个更高级的主题，在本文档中没有概述。</span><span class="sxs-lookup"><span data-stu-id="dc39b-113">This is not to say that there is no use for these cmdlets in on-premises deployments, but their use is a more advanced topic that is not covered in this documentation.</span></span>

<span data-ttu-id="dc39b-114">集中日志记录服务可在包含单个计算机或计算机池的范围内运行，在站点范围（即在部署中包含计算机和池集合的网站 Redmond）中，或在全局范围内（即部署中的所有计算机和池）。</span><span class="sxs-lookup"><span data-stu-id="dc39b-114">The Centralized Logging Service can be run at a scope that includes a single computer or a pool of computers, at a site scope (that is, a defined site such as the site Redmond that contains a collection of computer and pools in your deployment), or at a global scope (that is, all computers and pools in your deployment).</span></span>

<span data-ttu-id="dc39b-115">若要使用 Skype for Business Server 命令行管理程序配置集中日志记录服务作用域，您必须是 CsAdministrator 或 CsServerAdministrator 基于角色的访问控制（RBAC）安全组的成员，或者是包含这两个组中任一组的自定义 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="dc39b-115">To configure the Centralized Logging Service scope by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="dc39b-116">若要返回此 cmdlet 已分配到的所有 RBAC 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Skype for Business Server 命令行管理程序或 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="dc39b-116">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

<span data-ttu-id="dc39b-117">例如：</span><span class="sxs-lookup"><span data-stu-id="dc39b-117">For example:</span></span>

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> <span data-ttu-id="dc39b-118">可以在 Windows PowerShell 或 CLSController 中运行的命令行命令之间存在根本区别。</span><span class="sxs-lookup"><span data-stu-id="dc39b-118">There are fundamental differences between the command-line commands that you can run in Windows PowerShell or CLSController.</span></span> <span data-ttu-id="dc39b-119">Windows PowerShell 提供了一种丰富的方法来配置和定义方案，并以一种有意义的方式在故障排除方案中重用这些方案。</span><span class="sxs-lookup"><span data-stu-id="dc39b-119">Windows PowerShell provides a rich method to configure and define scenarios, and to reuse those scenarios in a meaningful way for your troubleshooting scenarios.</span></span> <span data-ttu-id="dc39b-120">虽然 CLSController 提供了一种快速有效的方式来发出命令和获取结果，但 CLSController 的命令集受您在命令行中可用的有限命令的限制。</span><span class="sxs-lookup"><span data-stu-id="dc39b-120">While CLSController does provide a fast and efficient way to issue commands and get results, the command set for CLSController is limited by the finite commands that you have available from the command line.</span></span> <span data-ttu-id="dc39b-121">与 Windows PowerShell cmdlet 不同，CLSController 无法定义新方案、网站或全局级别的管理作用域，以及无法动态配置的有限命令集的许多其他限制。</span><span class="sxs-lookup"><span data-stu-id="dc39b-121">Unlike the Windows PowerShell cmdlets, CLSController cannot define new scenarios, manage scope at a site or global level, and many other limitations of a finite command set that cannot be dynamically configured.</span></span> <span data-ttu-id="dc39b-122">虽然 CLSController 提供了快速执行的一种方法，但 Windows PowerShell 提供了一种方法来扩展集中日志记录服务的功能，而不是使用 CLSController 可能的功能。</span><span class="sxs-lookup"><span data-stu-id="dc39b-122">While CLSController provides a means for fast execution, Windows PowerShell provides a means to extend the Centralized Logging Service functionality beyond what is possible with CLSController.</span></span>

<span data-ttu-id="dc39b-123">可以使用-computer 参数在[搜索 search-csclslogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps)、 [Show-search-csclslogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps)、 [Start-search-csclslogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps)、 [Stop-search-csclslogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps)、 [Sync-search-csclslogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps)和[search-csclslogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps)命令的执行过程中定义单个计算机范围。</span><span class="sxs-lookup"><span data-stu-id="dc39b-123">A single computer scope can be defined during the execution of a [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps), [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps), [Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps), [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) and [Update-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) command using the -Computers parameter.</span></span> <span data-ttu-id="dc39b-124">-Computer 参数接受目标计算机的完全限定域名（Fqdn）的逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="dc39b-124">The -Computers parameter accepts a comma separated list of fully qualified domain names (FQDNs) for the target computer.</span></span>

> [!TIP]
> <span data-ttu-id="dc39b-125">您还可以定义池和要在其上运行日志记录命令的池的逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="dc39b-125">You can also define -Pools and a comma separated list of pools that you want to run the logging commands on.</span></span>

<span data-ttu-id="dc39b-126">站点和全局作用域是在**新**的、**集**的和**删除**集中的日志记录服务 cmdlet 中定义的。</span><span class="sxs-lookup"><span data-stu-id="dc39b-126">Site and Global scopes are defined in the **New-**, **Set-**, and **Remove-** Centralized Logging Service cmdlets.</span></span> <span data-ttu-id="dc39b-127">下面的示例演示如何设置站点和全局作用域。</span><span class="sxs-lookup"><span data-stu-id="dc39b-127">The following examples demonstrate how to set a site and a global scope.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dc39b-128">所显示的命令可能包含其他部分中所涉及的参数和概念。</span><span class="sxs-lookup"><span data-stu-id="dc39b-128">The commands shown may contain parameters and concepts that are covered in other sections.</span></span> <span data-ttu-id="dc39b-129">示例命令旨在演示如何使用 **-Identity**参数定义作用域，并包含其他参数以实现完整性并指定作用域。</span><span class="sxs-lookup"><span data-stu-id="dc39b-129">The example commands are intended to demonstrate the use of the **-Identity** parameter to define scope, and the other parameters are included for completeness and to specify the scope.</span></span> <span data-ttu-id="dc39b-130">有关**new-csclsconfiguration** cmdlet 的详细信息，请参阅操作文档中的[new-csclsconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) 。</span><span class="sxs-lookup"><span data-stu-id="dc39b-130">For details about the **Set-CsClsConfiguration** cmdlets, see [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) in the Operations documentation.</span></span>

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="dc39b-131">检索当前的集中日志记录服务配置</span><span class="sxs-lookup"><span data-stu-id="dc39b-131">To retrieve the current Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="dc39b-132">启动 Skype for Business Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **skype for business 2015**"，然后单击 " **skype for business Server Management Shell**"。</span><span class="sxs-lookup"><span data-stu-id="dc39b-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="dc39b-133">在命令行提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="dc39b-133">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Get-CsClsConfiguration
   ```

<span data-ttu-id="dc39b-134">使用**new-csclsconfiguration**和**new-csclsconfiguration** cmdlet 创建新配置或更新现有配置。运行**new-csclsconfiguration**时，它会显示类似于以下屏幕截图的信息，其中部署当前具有默认全局配置，但未定义网站配置：</span><span class="sxs-lookup"><span data-stu-id="dc39b-134">Use the **New-CsClsConfiguration** and **Set-CsClsConfiguration** cmdlets to create a new configuration or to update an existing configuration.When you run **Get-CsClsConfiguration**, it displays information similar to the following screen shot, where the deployment currently has the default Global configuration, but no site configurations defined:</span></span>

![New-csclsconfiguration 中的示例输出。](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a><span data-ttu-id="dc39b-136">从计算机本地存储中检索当前的集中日志记录服务配置</span><span class="sxs-lookup"><span data-stu-id="dc39b-136">To retrieve the current Centralized Logging Service configuration from the computer local store</span></span>

1. <span data-ttu-id="dc39b-137">启动 Skype for Business Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **skype for business 2015**"，然后单击 " **skype for business Server Management Shell**"。</span><span class="sxs-lookup"><span data-stu-id="dc39b-137">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="dc39b-138">在命令行提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="dc39b-138">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Get-CsClsConfiguration -LocalStore
   ```

<span data-ttu-id="dc39b-139">如果使用的第一个示例中的**new-csclsconfiguration**未指定任何参数，则该命令将引用数据的中央管理存储。</span><span class="sxs-lookup"><span data-stu-id="dc39b-139">When you use the first example where **Get-CsClsConfiguration** does not specify any parameters, the command references the Central Management store for the data.</span></span> <span data-ttu-id="dc39b-140">如果指定 LocalStore 参数，该命令将引用计算机 LocalStore 而不是中央管理存储。</span><span class="sxs-lookup"><span data-stu-id="dc39b-140">If you specify the parameter -LocalStore, the command references the computer LocalStore instead of the Central Management store.</span></span>
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a><span data-ttu-id="dc39b-141">检索当前定义的方案列表</span><span class="sxs-lookup"><span data-stu-id="dc39b-141">To retrieve a listing of scenarios currently defined</span></span>

1. <span data-ttu-id="dc39b-142">启动 Skype for Business Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **skype for business 2015**"，然后单击 " **skype for business Server Management Shell**"。</span><span class="sxs-lookup"><span data-stu-id="dc39b-142">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="dc39b-143">在命令行提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="dc39b-143">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
   ```

    <span data-ttu-id="dc39b-144">例如，若要检索在全局范围内定义的方案，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="dc39b-144">For example, to retrieve the scenarios that is defined at the global scope:</span></span>

   ```PowerShell
   Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
   ```

<span data-ttu-id="dc39b-145">Cmdlet **new-csclsconfiguration**始终显示属于给定作用域的配置的方案。</span><span class="sxs-lookup"><span data-stu-id="dc39b-145">The cmdlet **Get-CsClsConfiguration** always displays the scenarios that are a part of a given scope's configuration.</span></span> <span data-ttu-id="dc39b-146">在大多数情况下，不会显示所有方案，并且会被截断。</span><span class="sxs-lookup"><span data-stu-id="dc39b-146">In most cases, all scenarios are not displayed, and are truncated.</span></span> <span data-ttu-id="dc39b-147">此处使用的命令列出了有关使用哪些提供程序、设置和标志的所有方案和部分信息。</span><span class="sxs-lookup"><span data-stu-id="dc39b-147">The command used here lists all of the scenarios and partial information about what providers, settings, and flags are used.</span></span>
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="dc39b-148">使用 Windows PowerShell 为集中日志记录服务更新全局作用域</span><span class="sxs-lookup"><span data-stu-id="dc39b-148">To update a global scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1. <span data-ttu-id="dc39b-149">启动 Skype for Business Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **skype for business 2015**"，然后单击 " **skype for business Server Management Shell**"。</span><span class="sxs-lookup"><span data-stu-id="dc39b-149">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="dc39b-150">在命令行提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="dc39b-150">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   <span data-ttu-id="dc39b-151">例如：</span><span class="sxs-lookup"><span data-stu-id="dc39b-151">For example:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
   ```

<span data-ttu-id="dc39b-152">该命令将告知部署中每台计算机和池中的 CLSAgent，以将跟踪文件上的滚动值的大小设置为 40 mb。</span><span class="sxs-lookup"><span data-stu-id="dc39b-152">The command tells the CLSAgent on each computer and pool in the deployment to set the size of the rollover value on the tracing file to 40 megabytes.</span></span> <span data-ttu-id="dc39b-153">所有站点中的计算机和池受命令影响，并将其配置的跟踪日志滚动更新值设置为 40 mb。</span><span class="sxs-lookup"><span data-stu-id="dc39b-153">Computers and pools in all sites are affected by the command, and will set their configured trace log rollover value to 40 megabytes.</span></span>
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="dc39b-154">使用 Windows PowerShell 为集中日志记录服务更新站点范围</span><span class="sxs-lookup"><span data-stu-id="dc39b-154">To update a site scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1. <span data-ttu-id="dc39b-155">启动 Skype for Business Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **skype for business 2015**"，然后单击 " **skype for business Server Management Shell**"。</span><span class="sxs-lookup"><span data-stu-id="dc39b-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="dc39b-156">在命令行提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="dc39b-156">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   <span data-ttu-id="dc39b-157">例如：</span><span class="sxs-lookup"><span data-stu-id="dc39b-157">For example:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40
   ```

> [!NOTE]
> <span data-ttu-id="dc39b-158">如示例中所述，日志文件的默认位置是%TEMP%\Tracing。</span><span class="sxs-lookup"><span data-stu-id="dc39b-158">As noted in the example, the default location of the log files is %TEMP%\Tracing.</span></span> <span data-ttu-id="dc39b-159">但是，由于实际上是 CLSAgent 正在写入文件，而 Clsagent 作为网络服务运行，因此% TEMP% 变量扩展为%Windir%\serviceprofiles\networkservice\appdata\local。</span><span class="sxs-lookup"><span data-stu-id="dc39b-159">However, because it is actually CLSAgent that is writing the file and CSLAgent runs as Network Service, the %TEMP% variable expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span></span>

<span data-ttu-id="dc39b-160">该命令将告知网站 Redmond 中的每台计算机和池中的 CLSAgent，以将跟踪文件上的滚动值的大小设置为 40 mb。</span><span class="sxs-lookup"><span data-stu-id="dc39b-160">The command tells the CLSAgent on each computer and pool in the site Redmond to set the size of the rollover value on the tracing file to 40 megabytes.</span></span> <span data-ttu-id="dc39b-161">该命令不会影响其他站点中的计算机和池，并且将继续使用当前配置的跟踪日志滚动更新值（默认为 20 mb）或在日志记录会话的启动过程中定义。</span><span class="sxs-lookup"><span data-stu-id="dc39b-161">Computers and pools in other sites will not be affected by the command, and will continue to use the currently configured trace log rollover value defined either by default (20 megabytes) or during the start of the logging session.</span></span>
### <a name="to-create-a-new-centralized-logging-service-configuration"></a><span data-ttu-id="dc39b-162">创建新的集中日志记录服务配置</span><span class="sxs-lookup"><span data-stu-id="dc39b-162">To create a new Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="dc39b-163">启动 Skype for Business Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **skype for business 2015**"，然后单击 " **skype for business Server Management Shell**"。</span><span class="sxs-lookup"><span data-stu-id="dc39b-163">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="dc39b-164">在命令行提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="dc39b-164">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > <span data-ttu-id="dc39b-165">New-csclsconfiguration 提供对大量可选配置设置的访问权限。</span><span class="sxs-lookup"><span data-stu-id="dc39b-165">New-CsClsConfiguration provides access to a large number of optional configuration settings.</span></span> <span data-ttu-id="dc39b-166">有关配置选项的详细信息，请参阅[new-csclsconfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)和[了解集中日志记录服务配置设置](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx)。</span><span class="sxs-lookup"><span data-stu-id="dc39b-166">For details about the configuration options, see [Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) and [Understanding Centralized Logging Service Configuration Settings](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx).</span></span>

<span data-ttu-id="dc39b-167">例如，若要创建为缓存文件定义网络文件夹的新配置、滚动日志文件的时间段以及日志文件的滚动时间大小，请键入：</span><span class="sxs-lookup"><span data-stu-id="dc39b-167">For example, to create a new configuration that defines a network folder for cache files, rollover time period for the log files and rollover size for the log files, you would type:</span></span>

  ```PowerShell
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

<span data-ttu-id="dc39b-168">您应仔细规划新配置的创建以及如何为集中日志记录服务定义新属性。</span><span class="sxs-lookup"><span data-stu-id="dc39b-168">You should carefully plan the creation of new configurations and how you define new properties for the Centralized Logging Service.</span></span> <span data-ttu-id="dc39b-169">在进行更改时应谨慎，并确保了解对您正确记录问题方案的能力的影响。</span><span class="sxs-lookup"><span data-stu-id="dc39b-169">You should be cautious about making changes and make sure you understand the impact on your ability to properly log problem scenarios.</span></span> <span data-ttu-id="dc39b-170">您应对配置进行更改，以增强您管理日志的大小和滚动期，以便在出现问题时能够解决问题。</span><span class="sxs-lookup"><span data-stu-id="dc39b-170">You should make changes to the configuration that will enhance your ability to manage logs to a size and a rollover period that will allow problem solving when it arises.</span></span>
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a><span data-ttu-id="dc39b-171">删除现有的集中日志记录服务配置</span><span class="sxs-lookup"><span data-stu-id="dc39b-171">To remove an existing Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="dc39b-172">启动 Skype for Business Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **skype for business 2015**"，然后单击 " **skype for business Server Management Shell**"。</span><span class="sxs-lookup"><span data-stu-id="dc39b-172">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="dc39b-173">在命令行提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="dc39b-173">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

<span data-ttu-id="dc39b-174">例如，若要删除您创建的集中日志记录服务配置以增加日志文件滚动时间，请增加滚动更新日志文件大小，并将日志文件缓存位置设置为网络共享，如下所示：</span><span class="sxs-lookup"><span data-stu-id="dc39b-174">For example, to remove a Centralized Logging Service configuration that you created to increase the log file rollover time, increase the rollover log file size, and set the log file cache location to a network share as follows:</span></span>

  ```PowerShell
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> <span data-ttu-id="dc39b-175">这是在 "创建新的集中日志记录服务配置" 过程中创建的新配置。</span><span class="sxs-lookup"><span data-stu-id="dc39b-175">This is the new configuration that was created in the procedure "To create a new Centralized Logging Service configuration."</span></span>

<span data-ttu-id="dc39b-176">如果选择删除网站级别的配置，则网站将使用全局设置。</span><span class="sxs-lookup"><span data-stu-id="dc39b-176">If you choose to remove a site-level configuration, the site will use the global settings.</span></span>
## <a name="see-also"></a><span data-ttu-id="dc39b-177">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dc39b-177">See also</span></span>

[<span data-ttu-id="dc39b-178">为 Skype for Business Server 2015 中的集中日志记录服务配置提供程序</span><span class="sxs-lookup"><span data-stu-id="dc39b-178">Configure providers for Centralized Logging Service in Skype for Business Server 2015</span></span>](configure-providers.md)

[<span data-ttu-id="dc39b-179">在 Skype for Business Server 2015 中配置集中日志记录服务的方案</span><span class="sxs-lookup"><span data-stu-id="dc39b-179">Configure scenarios for the Centralized Logging Service in Skype for Business Server 2015</span></span>](configure-scenarios.md)

[<span data-ttu-id="dc39b-180">Skype for Business 2015 中的集中日志记录服务</span><span class="sxs-lookup"><span data-stu-id="dc39b-180">Centralized Logging Service in Skype for Business 2015</span></span>](centralized-logging-service.md)

[<span data-ttu-id="dc39b-181">New-csclsconfiguration</span><span class="sxs-lookup"><span data-stu-id="dc39b-181">Set-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="dc39b-182">New-csclsconfiguration</span><span class="sxs-lookup"><span data-stu-id="dc39b-182">Get-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="dc39b-183">新 New-csclsconfiguration</span><span class="sxs-lookup"><span data-stu-id="dc39b-183">New-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="dc39b-184">New-csclsconfiguration</span><span class="sxs-lookup"><span data-stu-id="dc39b-184">Remove-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)
