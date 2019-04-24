---
title: 在 Skype for Business Server 2015 中管理集中日志记录服务配置设置
ms.reviewer: ''
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
ms.openlocfilehash: 1aab363f88b7639e2eb61f9101864bac20cc0aa0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32217509"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中管理集中日志记录服务配置设置

**摘要：** 了解如何检索、 更新和为业务服务器 2015 Skype 创建 the Centralized Logging Service 配置设置。

控制数据并 the Centralized Logging Service 配置设置和创建和使用集中日志记录服务控制器 (CLSController) 的单个计算机的集中日志记录服务代理 （发送命令的参数Clsagent 的通信）。 该代理处理发送给它的命令，并（如果是启动命令）根据提供的配置信息使用方案、提供程序、跟踪持续时间和标志的配置开始收集跟踪日志。

> [!IMPORTANT]
>  并非所有列出 the Centralized Logging Service 的 Windows PowerShell cmdlet 用于与 Skype 适用的业务服务器 2015年在本地部署。 尽管它们不会工作，但以下 cmdlet 不旨在业务服务器 2015年在本地部署的 Skype 起作用：

-  **CsClsRegion cmdlet:**[Get-csclsregion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) 、[Set-csclsregion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps)、 [New-csclsregion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps)和[Remove-csclsregion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps)。
-  **CsClsSearchTerm cmdlet:**[Get-csclssearchterm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps)和[Set-csclssearchterm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps)。
-  **CsClsSecurityGroup cmdlet:**[Get-csclssecuritygroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps)、 [Set-csclssecuritygroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps)、 [New-csclssecuritygroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)和[Remove-csclssecuritygroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps)。

这些 cmdlet 中定义的设置将不会阻碍或导致任何不利的行为，但旨在与 Microsoft Office 365 一起使用，并且不会产生任何本地部署中的预期的结果。 这并不是说在内部部署中没有使用这些 cmdlet，而是其使用是一个更高级的主题，在本文档中没有概述。

在范围内包含一台计算机或池的计算机、 站点作用域 （即，定义站点站点 Redmond 包含计算机和池部署中的集合，如），或全局作用域 （即，可以运行 the Centralized Logging Service所有计算机和池部署中的)。

若要使用 Skype 业务 Server 命令行管理程序配置 Centralized Logging Service 作用域，您必须是 CsAdministrator 或 CsServerAdministrator 基于角色的访问控制 (RBAC) 的安全组中或自定义 RBAC 角色的成员的包含这两个组之一。 若要返回的已分配此 cmdlet 的所有 RBAC 角色的列表 （包括您自己创建任何自定义 RBAC 角色），请业务 Server 命令行管理程序或 Windows PowerShell 提示符从 Skype 运行以下命令：

```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

例如：

```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> 有的命令行命令，您可以在 Windows PowerShell 或 CLSController 运行之间的基本区别。 Windows PowerShell 提供的丰富的方法来配置和定义的方案，以及在您的疑难解答方案的有意义的方式中重复使用这些方案。 尽管 CLSController 提供了快速有效的发出命令和获得结果的方法，但 CLSController 的命令集受到您从命令行获得的有限数量的命令的限制。 与 Windows PowerShell cmdlet，不同 CLSController 无法定义新的方案、 管理在网站或全局级别和无法动态配置有限的命令集的许多其他限制的范围。 尽管 CLSController 快速执行提供一种方法，Windows PowerShell 提供了一种方法来扩展超出新增功能可能与 CLSController 集中日志记录服务功能。

可以执行[Search-csclslogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps)、 [Show-csclslogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps)、 [Start-csclslogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps)， [Stop-csclslogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps)， [Sync-csclslogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps)和[Update-csclslogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps)期间定义单台计算机范围命令使用-Computers 参数。 -计算机参数接受在目标计算机的完全限定的域名 (Fqdn) 的逗号分隔列表。

> [!TIP]
> 您还可以定义-池和您想要运行日志记录命令的池的以逗号分隔列表。

网站和全局作用域中的**New-**、 **Set-** 和**Remove-** Centralized Logging Service cmdlet 定义。 以下示例演示了如何设置站点和全局作用域。

> [!IMPORTANT]
> 显示的命令可能包含其他章节中涵盖的参数和概念。 示例命令旨在演示如何使用 **-Identity**参数来定义作用域，并使用其他参数在内的完整性和指定的范围。 有关 **Set-CsClsConfiguration** cmdlet 的详细信息，请参阅操作文档中的 [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)。

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>若要检索的当前集中日志记录服务配置

1. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。

2. 在命令行提示符处键入以下内容：

   ```
   Get-CsClsConfiguration
   ```

若要创建新的配置或更新现有配置，请使用**New-csclsconfiguration**和**Set-csclsconfiguration** cmdlet。当您运行**Get-csclsconfiguration**时，它会显示类似于下面的屏幕快照，其中，部署当前具有默认的全局配置，但未定义站点配置的信息：

![来自 Get-CsClsConfiguration 的示例输出。](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>若要从计算机本地存储检索当前的集中日志记录服务配置

1. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。

2. 在命令行提示符处键入以下内容：

   ```
   Get-CsClsConfiguration -LocalStore
   ```

当您使用第一个示例**Get-csclsconfiguration**没有指定任何参数，命令参考中央管理存储的数据。 如果指定参数-LocalStore，命令将引用而不是中央管理存储的计算机 LocalStore。
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>检索当前定义的方案的列表

1. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。

2. 在命令行提示符处键入以下内容：

   ```
   Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
   ```

    例如，检索在全局作用域定义的方案：

   ```
   Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
   ```

Cmdlet **Get-csclsconfiguration**始终显示属于给定范围内的配置的方案。 在大多数情况下，不会显示所有方案，而会截断它们。 此处使用的命令列出所有方案和有关所使用的提供程序、设置和标记的部分信息。
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>通过使用 Windows PowerShell 更新 the Centralized Logging Service 的全局作用域

1. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。

2. 在命令行提示符处键入以下内容：

   ```
   Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   例如：

   ```
   Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
   ```

该命令指示部署中的每个计算机和池中的 CLSAgent 将跟踪文件上的滚动值的大小设置为 40 MB。所有站点中的计算机和池都受该命令的影响，并且会将其已配置的跟踪日志滚动值设置为 40 MB。
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>通过使用 Windows PowerShell 更新 the Centralized Logging Service 的站点作用域

1. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。

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
### <a name="to-create-a-new-centralized-logging-service-configuration"></a>若要创建新的集中日志记录服务配置

1. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。

2. 在命令行提示符处键入以下内容：

   ```
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > 利用 New-CsClsConfiguration，可以访问大量可选配置设置。 有关配置选项的详细信息，请参阅[Get-csclsconfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)和[了解集中日志记录服务配置设置](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx)。

例如，要创建用于定义缓存文件的网络文件夹、日志文件的滚动时间段和日志文件的滚动大小的新配置，您将键入：

  ```
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

您应仔细规划创建新的配置和为 the Centralized Logging Service 定义新属性的方式。 您在进行更改时应格外小心，并应确保了解对您正确记录问题方案的能力的影响。 您应更改配置，提高管理日志大小和滚动周期（允许在问题发生时予以解决）的能力。
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>若要删除现有的集中日志记录服务配置

1. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。

2. 在命令行提示符处键入以下内容：

   ```
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

例如，要删除的集中日志记录服务配置为增加的日志文件翻转时间所创建，请增加滚动更新日志文件大小，并将日志文件缓存的位置，如下所示设置到网络共享：

  ```
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> 这是"以创建新的集中日志记录服务配置。"过程中创建的新配置

如果选择删除站点级配置，站点将使用全局设置。
## <a name="see-also"></a>另请参阅

[配置 Skype for Business Server 2015 中的集中日志记录服务的提供程序](configure-providers.md)

[配置 Skype for Business Server 2015 中的集中日志记录服务的方案](configure-scenarios.md)

[Centralized Logging Service in Skype for Business 2015](centralized-logging-service.md)

[Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[New-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[Remove-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)
