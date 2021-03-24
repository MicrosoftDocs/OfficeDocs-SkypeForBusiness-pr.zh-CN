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
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a>Manage Centralized Logging Service configuration settings in Skype for Business Server 2015

**摘要：** 了解如何在 Skype for Business Server 2015 中检索、更新和创建集中日志记录服务的配置设置。

集中日志记录服务由集中日志记录服务控制器 (CLSController) 创建和使用的设置和参数进行控制和配置，以将命令发送到单台计算机的集中日志记录服务代理 (CLSAgent) 。 代理处理发送给它的命令 (如果启动命令) 则使用方案、提供程序、跟踪持续时间和标志的配置开始根据提供的配置信息收集跟踪日志。

> [!IMPORTANT]
>  并非为Windows PowerShell日志记录服务列出的所有 cmdlet 都用于 Skype for Business Server 2015 本地部署。 尽管它们看起来可能正常运行，但以下 cmdlet 并非设计为与 Skype for Business Server 2015 本地部署一起运行：

-  **CsClsRegion** cmdlet：Get-CsClsRegion、Set-CsClsRegion、New-CsClsRegion 和 [Remove-CsClsRegion。](/powershell/module/skype/remove-csclsregion?view=skype-ps) [](/powershell/module/skype/get-csclsregion?view=skype-ps) [](/powershell/module/skype/set-csclsregion?view=skype-ps) [](/powershell/module/skype/new-csclsregion?view=skype-ps)
-  **CsClsSearchTerm cmdlet：** [Get-CsClsSearchTerm](/powershell/module/skype/get-csclssearchterm?view=skype-ps) 和 [Set-CsClsSearchTerm](/powershell/module/skype/set-csclssearchterm?view=skype-ps)。
-  **CsClsSecurityGroup** cmdlet：Get-CsClsSecurityGroup、Set-CsClsSecurityGroup、New-CsClsSecurityGroup 和 [Remove-CsClsSecurityGroup。](/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps) [](/powershell/module/skype/get-csclssecuritygroup?view=skype-ps) [](/powershell/module/skype/set-csclssecuritygroup?view=skype-ps) [](/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)

这些 cmdlet 中定义的设置不会阻碍或导致任何不良行为，但它们设计为与 Microsoft 365 或 Office 365 一同使用，不会在本地部署中产生预期结果。 这并不是说在内部部署中没有使用这些 cmdlet，而是其使用是一个更高级的主题，在本文档中没有概述。

集中日志记录服务可在包括单台计算机或计算机池的作用域、站点作用域 (（即，在部署) 中包含计算机和池集合的已定义站点（如站点 Redmond）或全局范围 (（即部署) 中所有计算机和池）运行。

若要使用 Skype for Business Server 命令行管理程序配置集中日志记录服务作用域，您必须是基于 CsAdministrator 或 CsServerAdministrator 角色的访问控制 (RBAC) 安全组的成员，或者是包含这两个组之一的自定义 RBAC 角色。 要返回分配了此 cmdlet 的所有 RBAC 角色的列表 (包括您自己创建的任何自定义 RBAC 角色) 请从 Skype for Business Server 命令行管理程序 或 Windows PowerShell 提示符运行以下命令：

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

例如：

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> 可以在 Windows PowerShell 或 CLSController 中运行的命令行命令之间存在基本差异。 Windows PowerShell提供了一种丰富的方法来配置和定义方案，并针对故障排除方案以有意义的方式重用这些方案。 虽然 CLSController 提供了一种快速有效的发出命令和获取结果的方法，但 CLSController 的命令集受命令行提供的有限命令限制。 与 Windows PowerShell cmdlet 不同，CLSController 无法定义新方案、在站点或全局级别管理范围，以及无法动态配置的有限命令集的许多其他限制。 CLSController 提供了一种快速执行方法，Windows PowerShell提供了一种扩展集中日志记录服务功能的方式，超出了 CLSController 的可能范围。

在执行 Search-CsClsLogging、Show-CsClsLogging、Start-CsClsLogging、Stop-CsClsLogging、Sync-CsClsLogging 和[](/powershell/module/skype/stop-csclslogging?view=skype-ps)[](/powershell/module/skype/start-csclslogging?view=skype-ps)[](/powershell/module/skype/search-csclslogging?view=skype-ps)[](/powershell/module/skype/show-csclslogging?view=skype-ps)[Update-CsClsLogging](/powershell/module/skype/update-csclslogging?view=skype-ps)命令期间，可以使用 -Computers 参数定义单个计算机作用域。 [](/powershell/module/skype/sync-csclslogging?view=skype-ps) -Computers 参数接受目标计算机的完全限定域名 (FQDN) 逗号分隔列表。

> [!TIP]
> 还可以定义 -Pools 和要运行日志记录命令的以逗号分隔的池列表。

站点和全局范围在 **New-、Set-** 和 **Remove-** Centralized Logging Service cmdlet 中定义。 以下示例演示如何设置站点和全局范围。

> [!IMPORTANT]
> 显示的命令可能包含其他部分中介绍的参数和概念。 示例命令旨在演示如何使用 **-Identity** 参数定义范围，并包括其他参数以用于完成和指定范围。 有关 **Set-CsClsConfiguration** cmdlet 的详细信息，请参阅操作文档中的 [Set-CsClsConfiguration。](/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>检索当前的集中日志记录服务配置

1. 启动 Skype for Business Server命令行管理程序：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**

2. 在命令行提示符下键入以下内容：

   ```PowerShell
   Get-CsClsConfiguration
   ```

使用 **New-CsClsConfiguration** 和 **Set-CsClsConfiguration** cmdlet 创建新配置或更新现有配置。运行 **Get-CsClsConfiguration** 时，将显示类似于以下屏幕截图的信息，其中部署当前具有默认的全局配置，但没有定义站点配置：

![Get-CsClsConfiguration 的示例输出。](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>从计算机本地存储检索当前集中日志记录服务配置

1. 启动 Skype for Business Server命令行管理程序：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**

2. 在命令行提示符下键入以下内容：

   ```PowerShell
   Get-CsClsConfiguration -LocalStore
   ```

使用第一个示例（其中 **Get-CsClsConfiguration** 未指定任何参数）时，该命令将引用数据的中央管理存储。 如果指定参数 -LocalStore，该命令将引用计算机 LocalStore，而不是中央管理存储。
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>检索当前定义的方案列表

1. 启动 Skype for Business Server命令行管理程序：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**

2. 在命令行提示符下键入以下内容：

   ```PowerShell
   Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
   ```

    例如，若要检索在全局范围定义的方案：

   ```PowerShell
   Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
   ```

cmdlet **Get-CsClsConfiguration** 始终显示属于给定范围的配置的一部分的方案。 在大多数情况下，不会显示所有方案，并且将被截断。 此处使用的命令列出了所有方案和有关使用哪些提供程序、设置和标志的部分信息。
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>使用日志记录服务更新集中日志记录服务的全局Windows PowerShell

1. 启动 Skype for Business Server命令行管理程序：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**

2. 在命令行提示符下键入以下内容：

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   例如：

   ```PowerShell
   Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
   ```

该命令指示部署中每台计算机和池上的 CLSAgent 将跟踪文件上的滚动值大小设置为 40 MB。 命令影响所有站点中的计算机和池，并且将配置跟踪日志滚动值设置为 40 MB。
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>使用集中日志记录服务更新站点Windows PowerShell

1. 启动 Skype for Business Server命令行管理程序：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**

2. 在命令行提示符下键入以下内容：

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   例如：

   ```PowerShell
   Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40
   ```

> [!NOTE]
> 如示例中所示，日志文件的默认位置为 %TEMP%\Tracing。 但是，由于编写文件实际上是 CLSAgent，并且 CSLAgent 作为网络服务运行，%TEMP% 变量将展开到 %WINDIR%\ServiceProfiles\NetworkService\AppData\Local。

该命令指示站点 Redmond 中每台计算机和池上的 CLSAgent 将跟踪文件上的滚动值大小设置为 40 MB。 其他站点中的计算机和池不会受该命令的影响，将继续使用当前配置的跟踪日志滚动值（默认为 (20 MB) 或在日志记录会话开始时定义）。
### <a name="to-create-a-new-centralized-logging-service-configuration"></a>创建新的集中日志记录服务配置

1. 启动 Skype for Business Server命令行管理程序：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**

2. 在命令行提示符下键入以下内容：

   ```PowerShell
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > New-CsClsConfiguration提供对大量可选配置设置的访问权限。 有关配置选项的详细信息，请参阅[Get-CsClsConfiguration](/powershell/module/skype/get-csclsconfiguration?view=skype-ps)和[Understanding Centralized Logging Service Configuration Settings。](/previous-versions/office/lync-server-2013/lync-server-2013-understanding-centralized-logging-service-configuration-settings)

例如，若要创建定义缓存文件网络文件夹、日志文件滚动时间段和日志文件滚动大小的新配置，应键入：

  ```PowerShell
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

您应仔细规划新配置的创建以及如何为集中日志记录服务定义新属性。 应谨慎进行更改，并确保了解对正确记录问题方案的能力的影响。 应更改配置，以增强管理日志的能力，使其适应大小和滚动周期，以便问题出现时能够解决问题。
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>删除现有的集中日志记录服务配置

1. 启动 Skype for Business Server命令行管理程序：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**

2. 在命令行提示符下键入以下内容：

   ```PowerShell
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

例如，若要删除为增加 日志文件 滚动时间而创建的集中日志记录服务配置，请增加 日志文件 滚动大小，将 日志文件 缓存位置设置为网络共享，如下所示：

  ```PowerShell
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> 这是在"创建新的集中日志记录服务配置"过程中创建的新配置。

如果选择删除站点级别的配置，则站点将使用全局设置。
## <a name="see-also"></a>另请参阅

[Configure providers for Centralized Logging Service in Skype for Business Server 2015](configure-providers.md)

[Configure scenarios for the Centralized Logging Service in Skype for Business Server 2015](configure-scenarios.md)

[Skype for Business 2015 中的集中日志记录服务](centralized-logging-service.md)

[Set-CsClsConfiguration](/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[Get-CsClsConfiguration](/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[New-CsClsConfiguration](/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[Remove-CsClsConfiguration](/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)