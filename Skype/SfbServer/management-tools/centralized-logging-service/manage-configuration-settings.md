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
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
description: '摘要: 了解如何在 Skype for business Server 2015 中检索、更新和创建集中日志记录服务的配置设置。'
ms.openlocfilehash: e6c1f9c893d0b5e745e558ed37570429689259d9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274427"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中管理集中日志记录服务配置设置

**摘要:** 了解如何在 Skype for business Server 2015 中检索、更新和创建集中日志记录服务的配置设置。

集中式日志记录服务由由集中日志记录服务控制器 (CLSController) 创建并使用的设置和参数进行控制和配置, 以便向单个计算机的集中式日志记录服务代理发送命令 (CLSAgent). 该代理处理发送给它的命令，并（如果是启动命令）根据提供的配置信息使用方案、提供程序、跟踪持续时间和标志的配置开始收集跟踪日志。

> [!IMPORTANT]
>  并非所有针对集中式日志记录服务列出的 Windows PowerShell cmdlet 均可用于 Skype for Business Server 2015 本地部署。 虽然它们看起来很有效, 但以下 cmdlet 并非设计为与 Skype for business Server 2015 本地部署一起工作:

-  **CsClsRegion cmdlet:**[CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) 、[Set-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps)、 [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps)和[Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps)。
-  **CsClsSearchTerm cmdlet:**[CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps)和[Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps)。
-  **CsClsSecurityGroup cmdlet:**[CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps)、 [Set-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps)、 [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)和[Remove-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps)。

这些 cmdlet 中定义的设置不会妨碍或导致任何不利行为, 但它们专用于 Microsoft Office 365, 并且不会在本地部署中产生预期的结果。 这并不是说在内部部署中没有使用这些 cmdlet，而是其使用是一个更高级的主题，在本文档中没有概述。

集中式日志记录服务可以在包含单个计算机或计算机池的范围内运行, 在网站范围内 (即定义的网站 (如网站 Redmond), 其中包含你的部署中的计算机和池集合, 或者在全局范围内、部署中的所有计算机和池)。

若要使用 Skype for Business Server Management Shell 配置集中日志记录服务范围, 你必须是 CsAdministrator 或 CsServerAdministrator 角色的访问控制 (RBAC) 安全组的成员, 或者是一个自定义的 RBAC 角色,包含这两个组中的任何一个。 若要返回此 cmdlet 已分配到的所有 RBAC 角色的列表 (包括你自己创建的任何自定义 RBAC 角色), 请从 Skype for Business Server Management Shell 或 Windows PowerShell 提示中运行以下命令:

```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

例如：

```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> 可以在 Windows PowerShell 或 CLSController 中运行的命令行命令之间存在基本差异。 Windows PowerShell 提供了一种丰富的方法来配置和定义方案, 并以一种有意义的方式重复使用这些方案来解决你的故障排除方案。 尽管 CLSController 提供了快速有效的发出命令和获得结果的方法，但 CLSController 的命令集受到您从命令行获得的有限数量的命令的限制。 与 Windows PowerShell cmdlet 不同, CLSController 无法定义新方案、网站或全局级别的管理范围, 以及无法动态配置的有限命令集的许多其他限制。 虽然 CLSController 提供快速执行的方法, 但 Windows PowerShell 提供了一种方法来扩展集中式日志记录服务功能, 而不是 CLSController 的可能性。

可以在执行[搜索 CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps)、[显示 CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps)、[开始 CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps)、[停止 CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps)、[同步 CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps)和[更新-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps)期间定义单个计算机范围使用-计算机参数的命令。 -计算机参数接受目标计算机的完全限定的域名 (Fqdn) 的逗号分隔列表。

> [!TIP]
> 你还可以定义池和要对其运行日志记录命令的池的逗号分隔列表。

站点和全局范围在**新**的、**集的**和**删除**集中的日志记录服务 cmdlet 中定义。 以下示例演示了如何设置站点和全局作用域。

> [!IMPORTANT]
> 显示的命令可能包含其他章节中涵盖的参数和概念。 示例命令旨在演示如何使用 **-Identity**参数来定义作用域, 并包含其他参数以实现完整性和指定范围。 有关 **Set-CsClsConfiguration** cmdlet 的详细信息，请参阅操作文档中的 [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)。

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>检索当前集中式日志记录服务配置

1. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。

2. 在命令行提示符处键入以下内容：

   ```
   Get-CsClsConfiguration
   ```

使用**CsClsConfiguration**和**CsClsConfiguration** cmdlet 创建新配置或更新现有配置。当你运行**CsClsConfiguration**时, 它将显示类似于以下屏幕截图的信息, 其中部署当前具有默认全局配置, 但未定义网站配置:

![来自 Get-CsClsConfiguration 的示例输出。](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>从计算机本地应用商店检索当前集中式日志记录服务配置

1. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。

2. 在命令行提示符处键入以下内容：

   ```
   Get-CsClsConfiguration -LocalStore
   ```

使用**CsClsConfiguration**未指定任何参数的第一个示例时, 该命令将引用数据的中央管理存储。 如果你指定参数 LocalStore, 该命令将引用计算机 LocalStore, 而不是中央管理存储。
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

Cmdlet **CsClsConfiguration**始终显示属于给定范围的配置的方案。 在大多数情况下，不会显示所有方案，而会截断它们。 此处使用的命令列出所有方案和有关所使用的提供程序、设置和标记的部分信息。
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>使用 Windows PowerShell 更新集中日志记录服务的全局范围

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
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>使用 Windows PowerShell 更新集中日志记录服务的网站范围

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
### <a name="to-create-a-new-centralized-logging-service-configuration"></a>创建新的集中式日志记录服务配置

1. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。

2. 在命令行提示符处键入以下内容：

   ```
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > 利用 New-CsClsConfiguration，可以访问大量可选配置设置。 有关配置选项的详细信息, 请参阅[CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)和[了解集中日志记录服务配置设置](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx)。

例如，要创建用于定义缓存文件的网络文件夹、日志文件的滚动时间段和日志文件的滚动大小的新配置，您将键入：

  ```
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

你应该仔细规划新配置的创建以及如何为集中式日志记录服务定义新属性。 您在进行更改时应格外小心，并应确保了解对您正确记录问题方案的能力的影响。 您应更改配置，提高管理日志大小和滚动周期（允许在问题发生时予以解决）的能力。
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>删除现有的集中日志记录服务配置

1. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。

2. 在命令行提示符处键入以下内容：

   ```
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

例如, 若要删除你创建的集中日志记录服务配置以增加日志文件滚动更新时间, 请增加滚动更新日志文件大小, 并将日志文件缓存位置设置为网络共享, 如下所示:

  ```
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> 这是在 "创建新的集中日志记录服务配置" 过程中创建的新配置。

如果选择删除站点级配置，站点将使用全局设置。
## <a name="see-also"></a>另请参阅

[配置 Skype for Business Server 2015 中的集中日志记录服务的提供程序](configure-providers.md)

[配置 Skype for Business Server 2015 中的集中日志记录服务的方案](configure-scenarios.md)

[Centralized Logging Service in Skype for Business 2015](centralized-logging-service.md)

[Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[New-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[Remove-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)
