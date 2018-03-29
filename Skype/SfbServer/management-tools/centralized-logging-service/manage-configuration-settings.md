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
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中管理集中日志记录服务配置设置
 
**摘要：**了解如何检索、 更新和创建业务服务器 2015 Skype 在集中式日志记录服务的配置设置。
  
集中式日志记录服务是控制和配置设置和参数创建和集中式日志记录服务控制器 (CLSController) 用于将命令发送到单独的计算机集中式日志记录服务代理 （通过CLSAgent)。 该代理处理发送给它的命令，并（如果是启动命令）根据提供的配置信息使用方案、提供程序、跟踪持续时间和标志的配置开始收集跟踪日志。
  
> [!IMPORTANT]
>  针对集中式日志记录服务列出的并不是所有 Windows PowerShell cmdlet 都打算用 Skype 业务服务器 2015年内部部署。 尽管它们可能看起来有效，但以下 cmdlet 都不使用 Skype 业务服务器 2015年内部部署起作用：

-  **CsClsRegion cmdlet:**[获得 CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) 、[集 CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps)，[新 CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps)，并[删除 CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps)。 
-  **CsClsSearchTerm cmdlet:**[获得 CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps)和[一组 CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps)。  
-  **CsClsSecurityGroup cmdlet:**[获得 CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps)、[集 CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps)，[新 CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)，并[删除 CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps)。 

这些 cmdlet 中定义的设置不会阻碍或导致任何不良行为，但他们使用 Microsoft Office 365 的设计并不会产生预期的结果在内部部署中。 这并不是说在内部部署中没有使用这些 cmdlet，而是其使用是一个更高级的主题，在本文档中没有概述。
  
一个包括一台计算机池的范围、 网站范围 （即定义的站点站点包含的计算机和您的部署中的池集合的雷蒙德等），或全局作用域 （即，可以运行在集中式日志记录服务所有的计算机和您的部署中的池)。
  
若要通过 Skype 业务服务器管理外壳配置集中式日志记录服务范围，必须是 CsAdministrator 或 CsServerAdministrator 基于角色的访问控制 (RBAC) 的安全组中，或自定义的 RBAC 角色成员，包含这两个组之一。 若要返回所有已分配此 cmdlet 的 RBAC 角色的列表 （包括您自己创建的任何自定义的 RBAC 角色），请为业务服务器管理外壳程序或 Windows PowerShell 提示从 Skype 运行下面的命令：
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

例如：
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> 有根本的差别，您可以运行在 Windows PowerShell 或 CLSController 的命令行命令。 Windows PowerShell 提供丰富的方法配置和定义的情况下，以及在有意义的方式，为您的故障排除方案中重复使用这些方案。 尽管 CLSController 提供了快速有效的发出命令和获得结果的方法，但 CLSController 的命令集受到您从命令行获得的有限数量的命令的限制。 与 Windows PowerShell 的 cmdlet，CLSController 不能定义新的方案、 管理站点或全局级别和许多其他限制不能动态地配置有限的命令集的范围。 CLSController 提供了一种快速执行，虽然 Windows PowerShell 提供了一种方法来扩展超越什么是可能与 CLSController 的集中式日志记录服务功能。 
  
单台计算机范围可以定义[搜索 CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps)、[显示 CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps)、[开始 CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps)、[停止 CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps)、[同步 CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps)和[更新 CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps)的执行过程命令使用的计算机参数。 -计算机参数接受为目标计算机的完全合格的域名称 (Fqdn) 的逗号分隔列表。
  
> [!TIP]
> 您还可以定义的池和您想要运行的日志记录命令的池的逗号分隔列表。 
  
在**新建的**、**集中的**和**删除**集中式日志记录服务 cmdlet 定义站点和全局作用域。 以下示例演示了如何设置站点和全局作用域。
  
> [!IMPORTANT]
> 显示的命令可能包含其他章节中涵盖的参数和概念。 命令示例是为了说明如何使用**-标识**参数来定义作用域，并使用其他参数将包含的完整性和指定的范围。 有关**设置 CsClsConfiguration** cmdlet 的详细信息，请参阅[设置 CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)运营文档资料。
  
### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>检索当前的集中式记录服务配置

1. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
2. 在命令行提示符处键入以下内容：
    
  ```
  Get-CsClsConfiguration
  ```

若要创建新的配置或更新现有配置，请使用**New CsClsConfiguration**和**一组 CsClsConfiguration** cmdlet。在运行时**获取 CsClsConfiguration**，它会显示类似于下面的屏幕截图，其中部署当前具有默认全局配置，但没有定义的站点配置信息：
  
![来自 Get-CsClsConfiguration 的示例输出。](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)
  
### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>若要从本地计算机存储区中检索当前的集中式记录服务配置

1. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
2. 在命令行提示符处键入以下内容：
    
  ```
  Get-CsClsConfiguration -LocalStore
  ```

当使用第一个示例中未指定任何参数，命令引用**获取 CsClsConfiguration**中央管理存储的数据。 如果指定了参数-LocalStore，该命令引用而不是中央管理存储的计算机 LocalStore。
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>检索当前定义的方案的列表

1. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
2. 在命令行提示符处键入以下内容：
    
  ```
  Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
  ```

    例如，检索在全局作用域定义的方案：
    
  ```
  Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
  ```

该 cmdlet **Get CsClsConfiguration**始终显示属于指定作用域的配置方案。 在大多数情况下，不会显示所有方案，而会截断它们。 此处使用的命令列出所有方案和有关所使用的提供程序、设置和标记的部分信息。
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>若要使用 Windows PowerShell 更新全局作用域，在集中式日志记录服务

1. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
2. 在命令行提示符处键入以下内容：
    
  ```
  Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
  ```

  例如：
    
  ```
  Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
  ```

该命令指示部署中的每个计算机和池中的 CLSAgent 将跟踪文件上的滚动值的大小设置为 40 MB。所有站点中的计算机和池都受该命令的影响，并且会将其已配置的跟踪日志滚动值设置为 40 MB。
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>若要使用 Windows PowerShell 更新站点范围的集中式日志记录服务

1. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
2. 在命令行提示符处键入以下内容：
    
  ```
  Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
  ```

  例如：
    
  ```
  Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40  
  ```

> [!NOTE]
> 如示例中所示，日志文件的默认位置是 %TEMP%\Tracing。但是，由于实际上是 CLSAgent 写入该文件，而且 CLSAgent 以 Network Service 的身份运行，因此 %TEMP% 变量将展开到 %WINDIR%\ServiceProfiles\NetworkService\AppData\Local。 
  
该命令指示 Redmond 站点中的每个计算机和池中的 CLSAgent 将跟踪文件上的滚动值的大小设置为 40 MB。其他站点中的计算机和池不会受该命令的影响，并将继续使用当前配置的跟踪日志滚动值（默认定义的 (20 MB) 或在日志记录会话开始时定义的）。
### <a name="to-create-a-new-centralized-logging-service-configuration"></a>若要创建新的集中式记录服务配置

1. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
2. 在命令行提示符处键入以下内容：
    
  ```
  New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
  ```

    > [!NOTE]
    > 利用 New-CsClsConfiguration，可以访问大量可选配置设置。 有关配置选项的详细信息，请参阅[获取 CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)和[了解集中式日志记录服务配置设置](http://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx)。 
  
例如，要创建用于定义缓存文件的网络文件夹、日志文件的滚动时间段和日志文件的滚动大小的新配置，您将键入：
    
  ```
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

您应仔细规划，创建新的配置和集中式日志记录服务定义新属性的方式。 您在进行更改时应格外小心，并应确保了解对您正确记录问题方案的能力的影响。 您应更改配置，提高管理日志大小和滚动周期（允许在问题发生时予以解决）的能力。
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>若要删除现有的集中式记录服务配置

1. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
2. 在命令行提示符处键入以下内容：
    
  ```
  Remove-CsClsConfiguration -Identity <scope and name>
  ```

例如，要删除创建的用来增加日志文件翻转时间集中记录服务配置，增加翻转日志文件大小，并将日志文件缓存位置，如下所示设置为网络共享：
    
  ```
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> 这是在"创建新的配置集中式日志记录服务。"过程中创建新的配置 
  
如果选择删除站点级配置，站点将使用全局设置。
## <a name="see-also"></a>另请参阅

#### 

[在 Skype 为业务服务器 2015年配置集中式日志记录服务的提供商](configure-providers.md)
  
[集中式日志记录服务 Skype 在配置方案，为业务服务器 2015](configure-scenarios.md)
#### 

[企业 2015年的 Skype 在集中式日志记录服务](centralized-logging-service.md)
#### 

[一组 CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)
  
[获得 CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)
  
[新 CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)
  
[删除 CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)

