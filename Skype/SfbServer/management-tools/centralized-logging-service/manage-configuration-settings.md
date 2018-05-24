---
title: 在 Skype for Business Server 2015 中管理集中日志记录服务配置设置
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
description: 摘要： 了解如何检索、 更新和为业务服务器 2015 Skype 创建 the Centralized Logging Service 配置设置。
ms.openlocfilehash: 8fe02cc4d2c04f9433736c4bced429f84f84d915
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2018
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="86eb8-103">在 Skype for Business Server 2015 中管理集中日志记录服务配置设置</span><span class="sxs-lookup"><span data-stu-id="86eb8-103">Manage Centralized Logging Service configuration settings in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="86eb8-104">**摘要：** 了解如何检索、 更新和为业务服务器 2015 Skype 创建 the Centralized Logging Service 配置设置。</span><span class="sxs-lookup"><span data-stu-id="86eb8-104">**Summary:** Learn how to retrieve, update, and create configuration settings for the Centralized Logging Service in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="86eb8-105">控制数据并 the Centralized Logging Service 配置设置和创建和使用集中日志记录服务控制器 (CLSController) 的单个计算机的集中日志记录服务代理 （发送命令的参数Clsagent 的通信）。</span><span class="sxs-lookup"><span data-stu-id="86eb8-105">The Centralized Logging Service is controlled and configured by settings and parameters that are created and used by the Centralized Logging Service Controller (CLSController) to send commands to the individual computer's Centralized Logging Service Agent (CLSAgent).</span></span> <span data-ttu-id="86eb8-106">该代理处理发送给它的命令，并（如果是启动命令）根据提供的配置信息使用方案、提供程序、跟踪持续时间和标志的配置开始收集跟踪日志。</span><span class="sxs-lookup"><span data-stu-id="86eb8-106">The agent processes the commands that are sent to it and (in the case of a Start command) uses the configuration of the scenarios, providers, trace duration, and flags to begin collecting trace logs according to the configuration information provided.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="86eb8-107">并非所有列出 the Centralized Logging Service 的 Windows PowerShell cmdlet 用于与 Skype 适用的业务服务器 2015年在本地部署。</span><span class="sxs-lookup"><span data-stu-id="86eb8-107">Not all Windows PowerShell cmdlets listed for the Centralized Logging Service are intended for use with Skype for Business Server 2015 on-premises deployments.</span></span> <span data-ttu-id="86eb8-108">尽管它们不会工作，但以下 cmdlet 不旨在业务服务器 2015年在本地部署的 Skype 起作用：</span><span class="sxs-lookup"><span data-stu-id="86eb8-108">Although they may appear to work, the following cmdlets are not designed to function with Skype for Business Server 2015 on-premises deployments:</span></span>

-  <span data-ttu-id="86eb8-109">**CsClsRegion cmdlet:**[Get-csclsregion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) 、[Set-csclsregion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps)、 [New-csclsregion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps)和[Remove-csclsregion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="86eb8-109">**CsClsRegion cmdlets:** [Get-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps), [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps), and [Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps).</span></span> 
-  <span data-ttu-id="86eb8-110">**CsClsSearchTerm cmdlet:**[Get-csclssearchterm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps)和[Set-csclssearchterm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="86eb8-110">**CsClsSearchTerm cmdlets:** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) and [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).</span></span>  
-  <span data-ttu-id="86eb8-111">**CsClsSecurityGroup cmdlet:**[Get-csclssecuritygroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps)、 [Set-csclssecuritygroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps)、 [New-csclssecuritygroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)和[Remove-csclssecuritygroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="86eb8-111">**CsClsSecurityGroup cmdlets:** [Get-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [Set-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps),  [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps), and [Remove-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).</span></span> 

<span data-ttu-id="86eb8-112">这些 cmdlet 中定义的设置将不会阻碍或导致任何不利的行为，但旨在与 Microsoft Office 365 一起使用，并且不会产生任何本地部署中的预期的结果。</span><span class="sxs-lookup"><span data-stu-id="86eb8-112">The settings defined in these cmdlets will not hinder or cause any adverse behavior, but they are designed for use with Microsoft Office 365 and will not yield the expected results in on-premises deployments.</span></span> <span data-ttu-id="86eb8-113">这并不是说在内部部署中没有使用这些 cmdlet，而是其使用是一个更高级的主题，在本文档中没有概述。</span><span class="sxs-lookup"><span data-stu-id="86eb8-113">This is not to say that there is no use for these cmdlets in on-premises deployments, but their use is a more advanced topic that is not covered in this documentation.</span></span>
  
<span data-ttu-id="86eb8-114">在范围内包含一台计算机或池的计算机、 站点作用域 （即，定义站点站点 Redmond 包含计算机和池部署中的集合，如），或全局作用域 （即，可以运行 the Centralized Logging Service所有计算机和池部署中的)。</span><span class="sxs-lookup"><span data-stu-id="86eb8-114">The Centralized Logging Service can be run at a scope that includes a single computer or a pool of computers, at a site scope (that is, a defined site such as the site Redmond that contains a collection of computer and pools in your deployment), or at a global scope (that is, all computers and pools in your deployment).</span></span>
  
<span data-ttu-id="86eb8-115">若要使用 Skype 业务 Server 命令行管理程序配置 Centralized Logging Service 作用域，您必须是 CsAdministrator 或 CsServerAdministrator 基于角色的访问控制 (RBAC) 的安全组中或自定义 RBAC 角色的成员的包含这两个组之一。</span><span class="sxs-lookup"><span data-stu-id="86eb8-115">To configure the Centralized Logging Service scope by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="86eb8-116">若要返回的已分配此 cmdlet 的所有 RBAC 角色的列表 （包括您自己创建任何自定义 RBAC 角色），请业务 Server 命令行管理程序或 Windows PowerShell 提示符从 Skype 运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="86eb8-116">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

<span data-ttu-id="86eb8-117">例如：</span><span class="sxs-lookup"><span data-stu-id="86eb8-117">For example:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> <span data-ttu-id="86eb8-118">有的命令行命令，您可以在 Windows PowerShell 或 CLSController 运行之间的基本区别。</span><span class="sxs-lookup"><span data-stu-id="86eb8-118">There are fundamental differences between the command-line commands that you can run in Windows PowerShell or CLSController.</span></span> <span data-ttu-id="86eb8-119">Windows PowerShell 提供的丰富的方法来配置和定义的方案，以及在您的疑难解答方案的有意义的方式中重复使用这些方案。</span><span class="sxs-lookup"><span data-stu-id="86eb8-119">Windows PowerShell provides a rich method to configure and define scenarios, and to reuse those scenarios in a meaningful way for your troubleshooting scenarios.</span></span> <span data-ttu-id="86eb8-120">尽管 CLSController 提供了快速有效的发出命令和获得结果的方法，但 CLSController 的命令集受到您从命令行获得的有限数量的命令的限制。</span><span class="sxs-lookup"><span data-stu-id="86eb8-120">While CLSController does provide a fast and efficient way to issue commands and get results, the command set for CLSController is limited by the finite commands that you have available from the command line.</span></span> <span data-ttu-id="86eb8-121">与 Windows PowerShell cmdlet，不同 CLSController 无法定义新的方案、 管理在网站或全局级别和无法动态配置有限的命令集的许多其他限制的范围。</span><span class="sxs-lookup"><span data-stu-id="86eb8-121">Unlike the Windows PowerShell cmdlets, CLSController cannot define new scenarios, manage scope at a site or global level, and many other limitations of a finite command set that cannot be dynamically configured.</span></span> <span data-ttu-id="86eb8-122">尽管 CLSController 快速执行提供一种方法，Windows PowerShell 提供了一种方法来扩展超出新增功能可能与 CLSController 集中日志记录服务功能。</span><span class="sxs-lookup"><span data-stu-id="86eb8-122">While CLSController provides a means for fast execution, Windows PowerShell provides a means to extend the Centralized Logging Service functionality beyond what is possible with CLSController.</span></span> 
  
<span data-ttu-id="86eb8-123">可以执行[Search-csclslogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps)、 [Show-csclslogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps)、 [Start-csclslogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps)， [Stop-csclslogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps)， [Sync-csclslogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps)和[Update-csclslogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps)期间定义单台计算机范围命令使用-Computers 参数。</span><span class="sxs-lookup"><span data-stu-id="86eb8-123">A single computer scope can be defined during the execution of a [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps), [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps), [Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps), [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) and [Update-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) command using the -Computers parameter.</span></span> <span data-ttu-id="86eb8-124">-计算机参数接受在目标计算机的完全限定的域名 (Fqdn) 的逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="86eb8-124">The -Computers parameter accepts a comma separated list of fully qualified domain names (FQDNs) for the target computer.</span></span>
  
> [!TIP]
> <span data-ttu-id="86eb8-125">您还可以定义-池和您想要运行日志记录命令的池的以逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="86eb8-125">You can also define -Pools and a comma separated list of pools that you want to run the logging commands on.</span></span> 
  
<span data-ttu-id="86eb8-126">网站和全局作用域中的**New-**、 **Set-** 和**Remove-** Centralized Logging Service cmdlet 定义。</span><span class="sxs-lookup"><span data-stu-id="86eb8-126">Site and Global scopes are defined in the **New-**, **Set-**, and **Remove-** Centralized Logging Service cmdlets.</span></span> <span data-ttu-id="86eb8-127">以下示例演示了如何设置站点和全局作用域。</span><span class="sxs-lookup"><span data-stu-id="86eb8-127">The following examples demonstrate how to set a site and a global scope.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="86eb8-128">显示的命令可能包含其他章节中涵盖的参数和概念。</span><span class="sxs-lookup"><span data-stu-id="86eb8-128">The commands shown may contain parameters and concepts that are covered in other sections.</span></span> <span data-ttu-id="86eb8-129">示例命令旨在演示如何使用 **-Identity**参数来定义作用域，并使用其他参数在内的完整性和指定的范围。</span><span class="sxs-lookup"><span data-stu-id="86eb8-129">The example commands are intended to demonstrate the use of the **-Identity** parameter to define scope, and the other parameters are included for completeness and to specify the scope.</span></span> <span data-ttu-id="86eb8-130">有关**Set-csclsconfiguration** cmdlet 的详细信息，请参阅操作文档中的[Set-csclsconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) 。</span><span class="sxs-lookup"><span data-stu-id="86eb8-130">For details about the **Set-CsClsConfiguration** cmdlets, see [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) in the Operations documentation.</span></span>
  
### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="86eb8-131">若要检索的当前集中日志记录服务配置</span><span class="sxs-lookup"><span data-stu-id="86eb8-131">To retrieve the current Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="86eb8-132">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="86eb8-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="86eb8-133">在命令行提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="86eb8-133">Type the following at the command-line prompt:</span></span>
    
  ```
  Get-CsClsConfiguration
  ```

<span data-ttu-id="86eb8-134">若要创建新的配置或更新现有配置，请使用**New-csclsconfiguration**和**Set-csclsconfiguration** cmdlet。当您运行**Get-csclsconfiguration**时，它会显示类似于下面的屏幕快照，其中，部署当前具有默认的全局配置，但未定义站点配置的信息：</span><span class="sxs-lookup"><span data-stu-id="86eb8-134">Use the **New-CsClsConfiguration** and **Set-CsClsConfiguration** cmdlets to create a new configuration or to update an existing configuration.When you run **Get-CsClsConfiguration**, it displays information similar to the following screen shot, where the deployment currently has the default Global configuration, but no site configurations defined:</span></span>
  
![来自 Get-CsClsConfiguration 的示例输出。](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)
  
### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a><span data-ttu-id="86eb8-136">若要从计算机本地存储检索当前的集中日志记录服务配置</span><span class="sxs-lookup"><span data-stu-id="86eb8-136">To retrieve the current Centralized Logging Service configuration from the computer local store</span></span>

1. <span data-ttu-id="86eb8-137">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="86eb8-137">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="86eb8-138">在命令行提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="86eb8-138">Type the following at the command-line prompt:</span></span>
    
  ```
  Get-CsClsConfiguration -LocalStore
  ```

<span data-ttu-id="86eb8-139">当您使用第一个示例**Get-csclsconfiguration**没有指定任何参数，命令参考中央管理存储的数据。</span><span class="sxs-lookup"><span data-stu-id="86eb8-139">When you use the first example where **Get-CsClsConfiguration** does not specify any parameters, the command references the Central Management store for the data.</span></span> <span data-ttu-id="86eb8-140">如果指定参数-LocalStore，命令将引用而不是中央管理存储的计算机 LocalStore。</span><span class="sxs-lookup"><span data-stu-id="86eb8-140">If you specify the parameter -LocalStore, the command references the computer LocalStore instead of the Central Management store.</span></span>
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a><span data-ttu-id="86eb8-141">检索当前定义的方案的列表</span><span class="sxs-lookup"><span data-stu-id="86eb8-141">To retrieve a listing of scenarios currently defined</span></span>

1. <span data-ttu-id="86eb8-142">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="86eb8-142">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="86eb8-143">在命令行提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="86eb8-143">Type the following at the command-line prompt:</span></span>
    
  ```
  Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
  ```

    <span data-ttu-id="86eb8-144">例如，检索在全局作用域定义的方案：</span><span class="sxs-lookup"><span data-stu-id="86eb8-144">For example, to retrieve the scenarios that is defined at the global scope:</span></span>
    
  ```
  Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
  ```

<span data-ttu-id="86eb8-145">Cmdlet **Get-csclsconfiguration**始终显示属于给定范围内的配置的方案。</span><span class="sxs-lookup"><span data-stu-id="86eb8-145">The cmdlet **Get-CsClsConfiguration** always displays the scenarios that are a part of a given scope's configuration.</span></span> <span data-ttu-id="86eb8-146">在大多数情况下，不会显示所有方案，而会截断它们。</span><span class="sxs-lookup"><span data-stu-id="86eb8-146">In most cases, all scenarios are not displayed, and are truncated.</span></span> <span data-ttu-id="86eb8-147">此处使用的命令列出所有方案和有关所使用的提供程序、设置和标记的部分信息。</span><span class="sxs-lookup"><span data-stu-id="86eb8-147">The command used here lists all of the scenarios and partial information about what providers, settings, and flags are used.</span></span>
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="86eb8-148">通过使用 Windows PowerShell 更新 the Centralized Logging Service 的全局作用域</span><span class="sxs-lookup"><span data-stu-id="86eb8-148">To update a global scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1. <span data-ttu-id="86eb8-149">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="86eb8-149">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="86eb8-150">在命令行提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="86eb8-150">Type the following at the command-line prompt:</span></span>
    
  ```
  Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
  ```

  <span data-ttu-id="86eb8-151">例如：</span><span class="sxs-lookup"><span data-stu-id="86eb8-151">For example:</span></span>
    
  ```
  Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
  ```

<span data-ttu-id="86eb8-p111">该命令指示部署中的每个计算机和池中的 CLSAgent 将跟踪文件上的滚动值的大小设置为 40 MB。所有站点中的计算机和池都受该命令的影响，并且会将其已配置的跟踪日志滚动值设置为 40 MB。</span><span class="sxs-lookup"><span data-stu-id="86eb8-p111">The command tells the CLSAgent on each computer and pool in the deployment to set the size of the rollover value on the tracing file to 40 megabytes. Computers and pools in all sites are affected by the command, and will set their configured trace log rollover value to 40 megabytes.</span></span>
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="86eb8-154">通过使用 Windows PowerShell 更新 the Centralized Logging Service 的站点作用域</span><span class="sxs-lookup"><span data-stu-id="86eb8-154">To update a site scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1. <span data-ttu-id="86eb8-155">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="86eb8-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="86eb8-156">在命令行提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="86eb8-156">Type the following at the command-line prompt:</span></span>
    
  ```
  Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
  ```

  <span data-ttu-id="86eb8-157">例如：</span><span class="sxs-lookup"><span data-stu-id="86eb8-157">For example:</span></span>
    
  ```
  Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40  
  ```

> [!NOTE]
> <span data-ttu-id="86eb8-p112">如示例中所示，日志文件的默认位置是 %TEMP%\Tracing。但是，由于实际上是 CLSAgent 写入该文件，而且 CLSAgent 以 Network Service 的身份运行，因此 %TEMP% 变量将展开到 %WINDIR%\ServiceProfiles\NetworkService\AppData\Local。</span><span class="sxs-lookup"><span data-stu-id="86eb8-p112">As noted in the example, the default location of the log files is %TEMP%\Tracing. However, because it is actually CLSAgent that is writing the file and CSLAgent runs as Network Service, the %TEMP% variable expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span></span> 
  
<span data-ttu-id="86eb8-p113">该命令指示 Redmond 站点中的每个计算机和池中的 CLSAgent 将跟踪文件上的滚动值的大小设置为 40 MB。其他站点中的计算机和池不会受该命令的影响，并将继续使用当前配置的跟踪日志滚动值（默认定义的 (20 MB) 或在日志记录会话开始时定义的）。</span><span class="sxs-lookup"><span data-stu-id="86eb8-p113">The command tells the CLSAgent on each computer and pool in the site Redmond to set the size of the rollover value on the tracing file to 40 megabytes. Computers and pools in other sites will not be affected by the command, and will continue to use the currently configured trace log rollover value defined either by default (20 megabytes) or during the start of the logging session.</span></span>
### <a name="to-create-a-new-centralized-logging-service-configuration"></a><span data-ttu-id="86eb8-162">若要创建新的集中日志记录服务配置</span><span class="sxs-lookup"><span data-stu-id="86eb8-162">To create a new Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="86eb8-163">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="86eb8-163">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="86eb8-164">在命令行提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="86eb8-164">Type the following at the command-line prompt:</span></span>
    
  ```
  New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
  ```

    > [!NOTE]
    > <span data-ttu-id="86eb8-165">利用 New-CsClsConfiguration，可以访问大量可选配置设置。</span><span class="sxs-lookup"><span data-stu-id="86eb8-165">New-CsClsConfiguration provides access to a large number of optional configuration settings.</span></span> <span data-ttu-id="86eb8-166">有关配置选项的详细信息，请参阅[Get-csclsconfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)和[了解集中日志记录服务配置设置](http://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx)。</span><span class="sxs-lookup"><span data-stu-id="86eb8-166">For details about the configuration options, see [Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) and [Understanding Centralized Logging Service Configuration Settings](http://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx).</span></span> 
  
<span data-ttu-id="86eb8-167">例如，要创建用于定义缓存文件的网络文件夹、日志文件的滚动时间段和日志文件的滚动大小的新配置，您将键入：</span><span class="sxs-lookup"><span data-stu-id="86eb8-167">For example, to create a new configuration that defines a network folder for cache files, rollover time period for the log files and rollover size for the log files, you would type:</span></span>
    
  ```
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

<span data-ttu-id="86eb8-168">您应仔细规划创建新的配置和为 the Centralized Logging Service 定义新属性的方式。</span><span class="sxs-lookup"><span data-stu-id="86eb8-168">You should carefully plan the creation of new configurations and how you define new properties for the Centralized Logging Service.</span></span> <span data-ttu-id="86eb8-169">您在进行更改时应格外小心，并应确保了解对您正确记录问题方案的能力的影响。</span><span class="sxs-lookup"><span data-stu-id="86eb8-169">You should be cautious about making changes and make sure you understand the impact on your ability to properly log problem scenarios.</span></span> <span data-ttu-id="86eb8-170">您应更改配置，提高管理日志大小和滚动周期（允许在问题发生时予以解决）的能力。</span><span class="sxs-lookup"><span data-stu-id="86eb8-170">You should make changes to the configuration that will enhance your ability to manage logs to a size and a rollover period that will allow problem solving when it arises.</span></span>
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a><span data-ttu-id="86eb8-171">若要删除现有的集中日志记录服务配置</span><span class="sxs-lookup"><span data-stu-id="86eb8-171">To remove an existing Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="86eb8-172">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="86eb8-172">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="86eb8-173">在命令行提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="86eb8-173">Type the following at the command-line prompt:</span></span>
    
  ```
  Remove-CsClsConfiguration -Identity <scope and name>
  ```

<span data-ttu-id="86eb8-174">例如，要删除的集中日志记录服务配置为增加的日志文件翻转时间所创建，请增加滚动更新日志文件大小，并将日志文件缓存的位置，如下所示设置到网络共享：</span><span class="sxs-lookup"><span data-stu-id="86eb8-174">For example, to remove a Centralized Logging Service configuration that you created to increase the log file rollover time, increase the rollover log file size, and set the log file cache location to a network share as follows:</span></span>
    
  ```
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> <span data-ttu-id="86eb8-175">这是"以创建新的集中日志记录服务配置。"过程中创建的新配置</span><span class="sxs-lookup"><span data-stu-id="86eb8-175">This is the new configuration that was created in the procedure "To create a new Centralized Logging Service configuration."</span></span> 
  
<span data-ttu-id="86eb8-176">如果选择删除站点级配置，站点将使用全局设置。</span><span class="sxs-lookup"><span data-stu-id="86eb8-176">If you choose to remove a site-level configuration, the site will use the global settings.</span></span>
## <a name="see-also"></a><span data-ttu-id="86eb8-177">另请参阅</span><span class="sxs-lookup"><span data-stu-id="86eb8-177">See also</span></span>

#### 

[<span data-ttu-id="86eb8-178">在 Skype for Business Server 2015 配置提供程序集中日志记录服务</span><span class="sxs-lookup"><span data-stu-id="86eb8-178">Configure providers for Centralized Logging Service in Skype for Business Server 2015</span></span>](configure-providers.md)
  
[<span data-ttu-id="86eb8-179">为业务服务器 2015 the Centralized Logging Service 中 Skype 的配置方案</span><span class="sxs-lookup"><span data-stu-id="86eb8-179">Configure scenarios for the Centralized Logging Service in Skype for Business Server 2015</span></span>](configure-scenarios.md)

[<span data-ttu-id="86eb8-180">中的业务 2015 Skype 的集中日志记录服务</span><span class="sxs-lookup"><span data-stu-id="86eb8-180">Centralized Logging Service in Skype for Business 2015</span></span>](centralized-logging-service.md)

[<span data-ttu-id="86eb8-181">Set-csclsconfiguration</span><span class="sxs-lookup"><span data-stu-id="86eb8-181">Set-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)
  
[<span data-ttu-id="86eb8-182">Get-csclsconfiguration</span><span class="sxs-lookup"><span data-stu-id="86eb8-182">Get-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)
  
[<span data-ttu-id="86eb8-183">New-csclsconfiguration</span><span class="sxs-lookup"><span data-stu-id="86eb8-183">New-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)
  
[<span data-ttu-id="86eb8-184">Remove-csclsconfiguration</span><span class="sxs-lookup"><span data-stu-id="86eb8-184">Remove-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)

