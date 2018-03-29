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
description: 摘要： 了解如何检索、 更新和创建业务服务器 2015 Skype 在集中式日志记录服务的配置设置。
ms.openlocfilehash: 0c4d03119a61fccd062e650c38815bee069852f5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="5f7ac-103">在 Skype for Business Server 2015 中管理集中日志记录服务配置设置</span><span class="sxs-lookup"><span data-stu-id="5f7ac-103">Manage Centralized Logging Service configuration settings in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5f7ac-104">**摘要：**了解如何检索、 更新和创建业务服务器 2015 Skype 在集中式日志记录服务的配置设置。</span><span class="sxs-lookup"><span data-stu-id="5f7ac-104">**Summary:** Learn how to retrieve, update, and create configuration settings for the Centralized Logging Service in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="5f7ac-105">集中式日志记录服务是控制和配置设置和参数创建和集中式日志记录服务控制器 (CLSController) 用于将命令发送到单独的计算机集中式日志记录服务代理 （通过CLSAgent)。</span><span class="sxs-lookup"><span data-stu-id="5f7ac-105">The Centralized Logging Service is controlled and configured by settings and parameters that are created and used by the Centralized Logging Service Controller (CLSController) to send commands to the individual computer's Centralized Logging Service Agent (CLSAgent).</span></span> <span data-ttu-id="5f7ac-106">该代理处理发送给它的命令，并（如果是启动命令）根据提供的配置信息使用方案、提供程序、跟踪持续时间和标志的配置开始收集跟踪日志。</span><span class="sxs-lookup"><span data-stu-id="5f7ac-106">The agent processes the commands that are sent to it and (in the case of a Start command) uses the configuration of the scenarios, providers, trace duration, and flags to begin collecting trace logs according to the configuration information provided.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="5f7ac-107">针对集中式日志记录服务列出的并不是所有 Windows PowerShell cmdlet 都打算用 Skype 业务服务器 2015年内部部署。</span><span class="sxs-lookup"><span data-stu-id="5f7ac-107">Not all Windows PowerShell cmdlets listed for the Centralized Logging Service are intended for use with Skype for Business Server 2015 on-premises deployments.</span></span> <span data-ttu-id="5f7ac-108">尽管它们可能看起来有效，但以下 cmdlet 都不使用 Skype 业务服务器 2015年内部部署起作用：</span><span class="sxs-lookup"><span data-stu-id="5f7ac-108">Although they may appear to work, the following cmdlets are not designed to function with Skype for Business Server 2015 on-premises deployments:</span></span>

-  <span data-ttu-id="5f7ac-109">**CsClsRegion cmdlet:**[获得 CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) 、[集 CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps)，[新 CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps)，并[删除 CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="5f7ac-109">**CsClsRegion cmdlets:** [Get-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps), [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps), and [Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps).</span></span> 
-  <span data-ttu-id="5f7ac-110">**CsClsSearchTerm cmdlet:**[获得 CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps)和[一组 CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="5f7ac-110">**CsClsSearchTerm cmdlets:** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) and [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).</span></span>  
-  <span data-ttu-id="5f7ac-111">**CsClsSecurityGroup cmdlet:**[获得 CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps)、[集 CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps)，[新 CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)，并[删除 CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="5f7ac-111">**CsClsSecurityGroup cmdlets:** [Get-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [Set-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps),  [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps), and [Remove-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).</span></span> 

<span data-ttu-id="5f7ac-112">这些 cmdlet 中定义的设置不会阻碍或导致任何不良行为，但他们使用 Microsoft Office 365 的设计并不会产生预期的结果在内部部署中。</span><span class="sxs-lookup"><span data-stu-id="5f7ac-112">The settings defined in these cmdlets will not hinder or cause any adverse behavior, but they are designed for use with Microsoft Office 365 and will not yield the expected results in on-premises deployments.</span></span> <span data-ttu-id="5f7ac-113">这并不是说在内部部署中没有使用这些 cmdlet，而是其使用是一个更高级的主题，在本文档中没有概述。</span><span class="sxs-lookup"><span data-stu-id="5f7ac-113">This is not to say that there is no use for these cmdlets in on-premises deployments, but their use is a more advanced topic that is not covered in this documentation.</span></span>
  
<span data-ttu-id="5f7ac-114">一个包括一台计算机池的范围、 网站范围 （即定义的站点站点包含的计算机和您的部署中的池集合的雷蒙德等），或全局作用域 （即，可以运行在集中式日志记录服务所有的计算机和您的部署中的池)。</span><span class="sxs-lookup"><span data-stu-id="5f7ac-114">The Centralized Logging Service can be run at a scope that includes a single computer or a pool of computers, at a site scope (that is, a defined site such as the site Redmond that contains a collection of computer and pools in your deployment), or at a global scope (that is, all computers and pools in your deployment).</span></span>
  
<span data-ttu-id="5f7ac-115">若要通过 Skype 业务服务器管理外壳配置集中式日志记录服务范围，必须是 CsAdministrator 或 CsServerAdministrator 基于角色的访问控制 (RBAC) 的安全组中，或自定义的 RBAC 角色成员，包含这两个组之一。</span><span class="sxs-lookup"><span data-stu-id="5f7ac-115">To configure the Centralized Logging Service scope by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="5f7ac-116">若要返回所有已分配此 cmdlet 的 RBAC 角色的列表 （包括您自己创建的任何自定义的 RBAC 角色），请为业务服务器管理外壳程序或 Windows PowerShell 提示从 Skype 运行下面的命令：</span><span class="sxs-lookup"><span data-stu-id="5f7ac-116">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

<span data-ttu-id="5f7ac-117">例如：</span><span class="sxs-lookup"><span data-stu-id="5f7ac-117">For example:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> <span data-ttu-id="5f7ac-118">有根本的差别，您可以运行在 Windows PowerShell 或 CLSController 的命令行命令。</span><span class="sxs-lookup"><span data-stu-id="5f7ac-118">There are fundamental differences between the command-line commands that you can run in Windows PowerShell or CLSController.</span></span> <span data-ttu-id="5f7ac-119">Windows PowerShell 提供丰富的方法配置和定义的情况下，以及在有意义的方式，为您的故障排除方案中重复使用这些方案。</span><span class="sxs-lookup"><span data-stu-id="5f7ac-119">Windows PowerShell provides a rich method to configure and define scenarios, and to reuse those scenarios in a meaningful way for your troubleshooting scenarios.</span></span> <span data-ttu-id="5f7ac-120">尽管 CLSController 提供了快速有效的发出命令和获得结果的方法，但 CLSController 的命令集受到您从命令行获得的有限数量的命令的限制。</span><span class="sxs-lookup"><span data-stu-id="5f7ac-120">While CLSController does provide a fast and efficient way to issue commands and get results, the command set for CLSController is limited by the finite commands that you have available from the command line.</span></span> <span data-ttu-id="5f7ac-121">与 Windows PowerShell 的 cmdlet，CLSController 不能定义新的方案、 管理站点或全局级别和许多其他限制不能动态地配置有限的命令集的范围。</span><span class="sxs-lookup"><span data-stu-id="5f7ac-121">Unlike the Windows PowerShell cmdlets, CLSController cannot define new scenarios, manage scope at a site or global level, and many other limitations of a finite command set that cannot be dynamically configured.</span></span> <span data-ttu-id="5f7ac-122">CLSController 提供了一种快速执行，虽然 Windows PowerShell 提供了一种方法来扩展超越什么是可能与 CLSController 的集中式日志记录服务功能。</span><span class="sxs-lookup"><span data-stu-id="5f7ac-122">While CLSController provides a means for fast execution, Windows PowerShell provides a means to extend the Centralized Logging Service functionality beyond what is possible with CLSController.</span></span> 
  
<span data-ttu-id="5f7ac-123">单台计算机范围可以定义[搜索 CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps)、[显示 CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps)、[开始 CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps)、[停止 CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps)、[同步 CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps)和[更新 CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps)的执行过程命令使用的计算机参数。</span><span class="sxs-lookup"><span data-stu-id="5f7ac-123">A single computer scope can be defined during the execution of a [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps), [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps), [Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps), [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) and [Update-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) command using the -Computers parameter.</span></span> <span data-ttu-id="5f7ac-124">-计算机参数接受为目标计算机的完全合格的域名称 (Fqdn) 的逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="5f7ac-124">The -Computers parameter accepts a comma separated list of fully qualified domain names (FQDNs) for the target computer.</span></span>
  
> [!TIP]
> <span data-ttu-id="5f7ac-125">您还可以定义的池和您想要运行的日志记录命令的池的逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="5f7ac-125">You can also define -Pools and a comma separated list of pools that you want to run the logging commands on.</span></span> 
  
<span data-ttu-id="5f7ac-126">在**新建的**、**集中的**和**删除**集中式日志记录服务 cmdlet 定义站点和全局作用域。</span><span class="sxs-lookup"><span data-stu-id="5f7ac-126">Site and Global scopes are defined in the **New-**, **Set-**, and **Remove-** Centralized Logging Service cmdlets.</span></span> <span data-ttu-id="5f7ac-127">以下示例演示了如何设置站点和全局作用域。</span><span class="sxs-lookup"><span data-stu-id="5f7ac-127">The following examples demonstrate how to set a site and a global scope.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5f7ac-128">显示的命令可能包含其他章节中涵盖的参数和概念。</span><span class="sxs-lookup"><span data-stu-id="5f7ac-128">The commands shown may contain parameters and concepts that are covered in other sections.</span></span> <span data-ttu-id="5f7ac-129">命令示例是为了说明如何使用**-标识**参数来定义作用域，并使用其他参数将包含的完整性和指定的范围。</span><span class="sxs-lookup"><span data-stu-id="5f7ac-129">The example commands are intended to demonstrate the use of the **-Identity** parameter to define scope, and the other parameters are included for completeness and to specify the scope.</span></span> <span data-ttu-id="5f7ac-130">有关**设置 CsClsConfiguration** cmdlet 的详细信息，请参阅[设置 CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)运营文档资料。</span><span class="sxs-lookup"><span data-stu-id="5f7ac-130">For details about the **Set-CsClsConfiguration** cmdlets, see [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) in the Operations documentation.</span></span>
  
### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="5f7ac-131">检索当前的集中式记录服务配置</span><span class="sxs-lookup"><span data-stu-id="5f7ac-131">To retrieve the current Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="5f7ac-132">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="5f7ac-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="5f7ac-133">在命令行提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="5f7ac-133">Type the following at the command-line prompt:</span></span>
    
  ```
  Get-CsClsConfiguration
  ```

<span data-ttu-id="5f7ac-134">若要创建新的配置或更新现有配置，请使用**New CsClsConfiguration**和**一组 CsClsConfiguration** cmdlet。在运行时**获取 CsClsConfiguration**，它会显示类似于下面的屏幕截图，其中部署当前具有默认全局配置，但没有定义的站点配置信息：</span><span class="sxs-lookup"><span data-stu-id="5f7ac-134">Use the **New-CsClsConfiguration** and **Set-CsClsConfiguration** cmdlets to create a new configuration or to update an existing configuration.When you run **Get-CsClsConfiguration**, it displays information similar to the following screen shot, where the deployment currently has the default Global configuration, but no site configurations defined:</span></span>
  
![来自 Get-CsClsConfiguration 的示例输出。](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)
  
### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a><span data-ttu-id="5f7ac-136">若要从本地计算机存储区中检索当前的集中式记录服务配置</span><span class="sxs-lookup"><span data-stu-id="5f7ac-136">To retrieve the current Centralized Logging Service configuration from the computer local store</span></span>

1. <span data-ttu-id="5f7ac-137">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="5f7ac-137">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="5f7ac-138">在命令行提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="5f7ac-138">Type the following at the command-line prompt:</span></span>
    
  ```
  Get-CsClsConfiguration -LocalStore
  ```

<span data-ttu-id="5f7ac-139">当使用第一个示例中未指定任何参数，命令引用**获取 CsClsConfiguration**中央管理存储的数据。</span><span class="sxs-lookup"><span data-stu-id="5f7ac-139">When you use the first example where **Get-CsClsConfiguration** does not specify any parameters, the command references the Central Management store for the data.</span></span> <span data-ttu-id="5f7ac-140">如果指定了参数-LocalStore，该命令引用而不是中央管理存储的计算机 LocalStore。</span><span class="sxs-lookup"><span data-stu-id="5f7ac-140">If you specify the parameter -LocalStore, the command references the computer LocalStore instead of the Central Management store.</span></span>
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a><span data-ttu-id="5f7ac-141">检索当前定义的方案的列表</span><span class="sxs-lookup"><span data-stu-id="5f7ac-141">To retrieve a listing of scenarios currently defined</span></span>

1. <span data-ttu-id="5f7ac-142">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="5f7ac-142">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="5f7ac-143">在命令行提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="5f7ac-143">Type the following at the command-line prompt:</span></span>
    
  ```
  Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
  ```

    <span data-ttu-id="5f7ac-144">例如，检索在全局作用域定义的方案：</span><span class="sxs-lookup"><span data-stu-id="5f7ac-144">For example, to retrieve the scenarios that is defined at the global scope:</span></span>
    
  ```
  Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
  ```

<span data-ttu-id="5f7ac-145">该 cmdlet **Get CsClsConfiguration**始终显示属于指定作用域的配置方案。</span><span class="sxs-lookup"><span data-stu-id="5f7ac-145">The cmdlet **Get-CsClsConfiguration** always displays the scenarios that are a part of a given scope's configuration.</span></span> <span data-ttu-id="5f7ac-146">在大多数情况下，不会显示所有方案，而会截断它们。</span><span class="sxs-lookup"><span data-stu-id="5f7ac-146">In most cases, all scenarios are not displayed, and are truncated.</span></span> <span data-ttu-id="5f7ac-147">此处使用的命令列出所有方案和有关所使用的提供程序、设置和标记的部分信息。</span><span class="sxs-lookup"><span data-stu-id="5f7ac-147">The command used here lists all of the scenarios and partial information about what providers, settings, and flags are used.</span></span>
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="5f7ac-148">若要使用 Windows PowerShell 更新全局作用域，在集中式日志记录服务</span><span class="sxs-lookup"><span data-stu-id="5f7ac-148">To update a global scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1. <span data-ttu-id="5f7ac-149">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="5f7ac-149">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="5f7ac-150">在命令行提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="5f7ac-150">Type the following at the command-line prompt:</span></span>
    
  ```
  Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
  ```

  <span data-ttu-id="5f7ac-151">例如：</span><span class="sxs-lookup"><span data-stu-id="5f7ac-151">For example:</span></span>
    
  ```
  Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
  ```

<span data-ttu-id="5f7ac-p111">该命令指示部署中的每个计算机和池中的 CLSAgent 将跟踪文件上的滚动值的大小设置为 40 MB。所有站点中的计算机和池都受该命令的影响，并且会将其已配置的跟踪日志滚动值设置为 40 MB。</span><span class="sxs-lookup"><span data-stu-id="5f7ac-p111">The command tells the CLSAgent on each computer and pool in the deployment to set the size of the rollover value on the tracing file to 40 megabytes. Computers and pools in all sites are affected by the command, and will set their configured trace log rollover value to 40 megabytes.</span></span>
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="5f7ac-154">若要使用 Windows PowerShell 更新站点范围的集中式日志记录服务</span><span class="sxs-lookup"><span data-stu-id="5f7ac-154">To update a site scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1. <span data-ttu-id="5f7ac-155">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="5f7ac-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="5f7ac-156">在命令行提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="5f7ac-156">Type the following at the command-line prompt:</span></span>
    
  ```
  Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
  ```

  <span data-ttu-id="5f7ac-157">例如：</span><span class="sxs-lookup"><span data-stu-id="5f7ac-157">For example:</span></span>
    
  ```
  Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40  
  ```

> [!NOTE]
> <span data-ttu-id="5f7ac-p112">如示例中所示，日志文件的默认位置是 %TEMP%\Tracing。但是，由于实际上是 CLSAgent 写入该文件，而且 CLSAgent 以 Network Service 的身份运行，因此 %TEMP% 变量将展开到 %WINDIR%\ServiceProfiles\NetworkService\AppData\Local。</span><span class="sxs-lookup"><span data-stu-id="5f7ac-p112">As noted in the example, the default location of the log files is %TEMP%\Tracing. However, because it is actually CLSAgent that is writing the file and CSLAgent runs as Network Service, the %TEMP% variable expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span></span> 
  
<span data-ttu-id="5f7ac-p113">该命令指示 Redmond 站点中的每个计算机和池中的 CLSAgent 将跟踪文件上的滚动值的大小设置为 40 MB。其他站点中的计算机和池不会受该命令的影响，并将继续使用当前配置的跟踪日志滚动值（默认定义的 (20 MB) 或在日志记录会话开始时定义的）。</span><span class="sxs-lookup"><span data-stu-id="5f7ac-p113">The command tells the CLSAgent on each computer and pool in the site Redmond to set the size of the rollover value on the tracing file to 40 megabytes. Computers and pools in other sites will not be affected by the command, and will continue to use the currently configured trace log rollover value defined either by default (20 megabytes) or during the start of the logging session.</span></span>
### <a name="to-create-a-new-centralized-logging-service-configuration"></a><span data-ttu-id="5f7ac-162">若要创建新的集中式记录服务配置</span><span class="sxs-lookup"><span data-stu-id="5f7ac-162">To create a new Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="5f7ac-163">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="5f7ac-163">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="5f7ac-164">在命令行提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="5f7ac-164">Type the following at the command-line prompt:</span></span>
    
  ```
  New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
  ```

    > [!NOTE]
    > <span data-ttu-id="5f7ac-165">利用 New-CsClsConfiguration，可以访问大量可选配置设置。</span><span class="sxs-lookup"><span data-stu-id="5f7ac-165">New-CsClsConfiguration provides access to a large number of optional configuration settings.</span></span> <span data-ttu-id="5f7ac-166">有关配置选项的详细信息，请参阅[获取 CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)和[了解集中式日志记录服务配置设置](http://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx)。</span><span class="sxs-lookup"><span data-stu-id="5f7ac-166">For details about the configuration options, see [Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) and [Understanding Centralized Logging Service Configuration Settings](http://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx).</span></span> 
  
<span data-ttu-id="5f7ac-167">例如，要创建用于定义缓存文件的网络文件夹、日志文件的滚动时间段和日志文件的滚动大小的新配置，您将键入：</span><span class="sxs-lookup"><span data-stu-id="5f7ac-167">For example, to create a new configuration that defines a network folder for cache files, rollover time period for the log files and rollover size for the log files, you would type:</span></span>
    
  ```
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

<span data-ttu-id="5f7ac-168">您应仔细规划，创建新的配置和集中式日志记录服务定义新属性的方式。</span><span class="sxs-lookup"><span data-stu-id="5f7ac-168">You should carefully plan the creation of new configurations and how you define new properties for the Centralized Logging Service.</span></span> <span data-ttu-id="5f7ac-169">您在进行更改时应格外小心，并应确保了解对您正确记录问题方案的能力的影响。</span><span class="sxs-lookup"><span data-stu-id="5f7ac-169">You should be cautious about making changes and make sure you understand the impact on your ability to properly log problem scenarios.</span></span> <span data-ttu-id="5f7ac-170">您应更改配置，提高管理日志大小和滚动周期（允许在问题发生时予以解决）的能力。</span><span class="sxs-lookup"><span data-stu-id="5f7ac-170">You should make changes to the configuration that will enhance your ability to manage logs to a size and a rollover period that will allow problem solving when it arises.</span></span>
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a><span data-ttu-id="5f7ac-171">若要删除现有的集中式记录服务配置</span><span class="sxs-lookup"><span data-stu-id="5f7ac-171">To remove an existing Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="5f7ac-172">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="5f7ac-172">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="5f7ac-173">在命令行提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="5f7ac-173">Type the following at the command-line prompt:</span></span>
    
  ```
  Remove-CsClsConfiguration -Identity <scope and name>
  ```

<span data-ttu-id="5f7ac-174">例如，要删除创建的用来增加日志文件翻转时间集中记录服务配置，增加翻转日志文件大小，并将日志文件缓存位置，如下所示设置为网络共享：</span><span class="sxs-lookup"><span data-stu-id="5f7ac-174">For example, to remove a Centralized Logging Service configuration that you created to increase the log file rollover time, increase the rollover log file size, and set the log file cache location to a network share as follows:</span></span>
    
  ```
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> <span data-ttu-id="5f7ac-175">这是在"创建新的配置集中式日志记录服务。"过程中创建新的配置</span><span class="sxs-lookup"><span data-stu-id="5f7ac-175">This is the new configuration that was created in the procedure "To create a new Centralized Logging Service configuration."</span></span> 
  
<span data-ttu-id="5f7ac-176">如果选择删除站点级配置，站点将使用全局设置。</span><span class="sxs-lookup"><span data-stu-id="5f7ac-176">If you choose to remove a site-level configuration, the site will use the global settings.</span></span>
## <a name="see-also"></a><span data-ttu-id="5f7ac-177">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5f7ac-177">See also</span></span>

#### 

[<span data-ttu-id="5f7ac-178">在 Skype 为业务服务器 2015年配置集中式日志记录服务的提供商</span><span class="sxs-lookup"><span data-stu-id="5f7ac-178">Configure providers for Centralized Logging Service in Skype for Business Server 2015</span></span>](configure-providers.md)
  
[<span data-ttu-id="5f7ac-179">集中式日志记录服务 Skype 在配置方案，为业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="5f7ac-179">Configure scenarios for the Centralized Logging Service in Skype for Business Server 2015</span></span>](configure-scenarios.md)
#### 

[<span data-ttu-id="5f7ac-180">企业 2015年的 Skype 在集中式日志记录服务</span><span class="sxs-lookup"><span data-stu-id="5f7ac-180">Centralized Logging Service in Skype for Business 2015</span></span>](centralized-logging-service.md)
#### 

[<span data-ttu-id="5f7ac-181">一组 CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="5f7ac-181">Set-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)
  
[<span data-ttu-id="5f7ac-182">获得 CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="5f7ac-182">Get-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)
  
[<span data-ttu-id="5f7ac-183">新 CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="5f7ac-183">New-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)
  
[<span data-ttu-id="5f7ac-184">删除 CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="5f7ac-184">Remove-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)

