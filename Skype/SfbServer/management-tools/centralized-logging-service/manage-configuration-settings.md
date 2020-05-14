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
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中管理集中日志记录服务配置设置

**摘要：** 了解如何检索、更新和创建 Skype for Business Server 2015 中的集中日志记录服务的配置设置。

集中日志记录服务由集中日志记录服务控制器（CLSController）创建和使用的设置和参数进行控制和配置，以将命令发送到单个计算机的集中日志记录服务代理（CLSAgent）。 代理会处理发送给它的命令，（在启动命令的情况下）使用方案、提供程序、跟踪持续时间和标志的配置，根据提供的配置信息开始收集跟踪日志。

> [!IMPORTANT]
>  并不是所有列出的集中日志记录服务的 Windows PowerShell cmdlet 都可用于 Skype for Business Server 2015 本地部署。 虽然看起来似乎可行，但以下 cmdlet 不是为在 Skype for business Server 2015 本地部署中运行而设计的：

-  **CsClsRegion cmdlet：** [CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) 、[Set-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps)、 [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps)和[Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps)。
-  **CsClsSearchTerm cmdlet：** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) 和 [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps)。
-  **CsClsSecurityGroup cmdlet：** [CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps)、 [Set-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps)、 [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)和[Remove-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps)。

这些 cmdlet 中定义的设置不会妨碍或导致任何不利行为，但它们设计为与 Microsoft 365 或 Office 365 配合使用，并且不会在本地部署中生成预期结果。 这并不是说在内部部署中没有使用这些 cmdlet，而是其使用是一个更高级的主题，在本文档中没有概述。

集中日志记录服务可在包含单个计算机或计算机池的范围内运行，在站点范围（即在部署中包含计算机和池集合的网站 Redmond）中，或在全局范围内（即部署中的所有计算机和池）。

若要使用 Skype for Business Server 命令行管理程序配置集中日志记录服务作用域，您必须是 CsAdministrator 或 CsServerAdministrator 基于角色的访问控制（RBAC）安全组的成员，或者是包含这两个组中任一组的自定义 RBAC 角色。 若要返回此 cmdlet 已分配到的所有 RBAC 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Skype for Business Server 命令行管理程序或 Windows PowerShell 提示符处运行以下命令：

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

例如：

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> 可以在 Windows PowerShell 或 CLSController 中运行的命令行命令之间存在根本区别。 Windows PowerShell 提供了一种丰富的方法来配置和定义方案，并以一种有意义的方式在故障排除方案中重用这些方案。 虽然 CLSController 提供了一种快速有效的方式来发出命令和获取结果，但 CLSController 的命令集受您在命令行中可用的有限命令的限制。 与 Windows PowerShell cmdlet 不同，CLSController 无法定义新方案、网站或全局级别的管理作用域，以及无法动态配置的有限命令集的许多其他限制。 虽然 CLSController 提供了快速执行的一种方法，但 Windows PowerShell 提供了一种方法来扩展集中日志记录服务的功能，而不是使用 CLSController 可能的功能。

可以使用-computer 参数在[搜索 search-csclslogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps)、 [Show-search-csclslogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps)、 [Start-search-csclslogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps)、 [Stop-search-csclslogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps)、 [Sync-search-csclslogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps)和[search-csclslogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps)命令的执行过程中定义单个计算机范围。 -Computer 参数接受目标计算机的完全限定域名（Fqdn）的逗号分隔列表。

> [!TIP]
> 您还可以定义池和要在其上运行日志记录命令的池的逗号分隔列表。

站点和全局作用域是在**新**的、**集**的和**删除**集中的日志记录服务 cmdlet 中定义的。 下面的示例演示如何设置站点和全局作用域。

> [!IMPORTANT]
> 所显示的命令可能包含其他部分中所涉及的参数和概念。 示例命令旨在演示如何使用 **-Identity**参数定义作用域，并包含其他参数以实现完整性并指定作用域。 有关**new-csclsconfiguration** cmdlet 的详细信息，请参阅操作文档中的[new-csclsconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) 。

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>检索当前的集中日志记录服务配置

1. 启动 Skype for Business Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **skype for business 2015**"，然后单击 " **skype for business Server Management Shell**"。

2. 在命令行提示符处键入以下内容：

   ```PowerShell
   Get-CsClsConfiguration
   ```

使用**new-csclsconfiguration**和**new-csclsconfiguration** cmdlet 创建新配置或更新现有配置。运行**new-csclsconfiguration**时，它会显示类似于以下屏幕截图的信息，其中部署当前具有默认全局配置，但未定义网站配置：

![New-csclsconfiguration 中的示例输出。](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>从计算机本地存储中检索当前的集中日志记录服务配置

1. 启动 Skype for Business Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **skype for business 2015**"，然后单击 " **skype for business Server Management Shell**"。

2. 在命令行提示符处键入以下内容：

   ```PowerShell
   Get-CsClsConfiguration -LocalStore
   ```

如果使用的第一个示例中的**new-csclsconfiguration**未指定任何参数，则该命令将引用数据的中央管理存储。 如果指定 LocalStore 参数，该命令将引用计算机 LocalStore 而不是中央管理存储。
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>检索当前定义的方案列表

1. 启动 Skype for Business Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **skype for business 2015**"，然后单击 " **skype for business Server Management Shell**"。

2. 在命令行提示符处键入以下内容：

   ```PowerShell
   Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
   ```

    例如，若要检索在全局范围内定义的方案，请执行以下操作：

   ```PowerShell
   Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
   ```

Cmdlet **new-csclsconfiguration**始终显示属于给定作用域的配置的方案。 在大多数情况下，不会显示所有方案，并且会被截断。 此处使用的命令列出了有关使用哪些提供程序、设置和标志的所有方案和部分信息。
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>使用 Windows PowerShell 为集中日志记录服务更新全局作用域

1. 启动 Skype for Business Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **skype for business 2015**"，然后单击 " **skype for business Server Management Shell**"。

2. 在命令行提示符处键入以下内容：

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   例如：

   ```PowerShell
   Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
   ```

该命令将告知部署中每台计算机和池中的 CLSAgent，以将跟踪文件上的滚动值的大小设置为 40 mb。 所有站点中的计算机和池受命令影响，并将其配置的跟踪日志滚动更新值设置为 40 mb。
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>使用 Windows PowerShell 为集中日志记录服务更新站点范围

1. 启动 Skype for Business Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **skype for business 2015**"，然后单击 " **skype for business Server Management Shell**"。

2. 在命令行提示符处键入以下内容：

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   例如：

   ```PowerShell
   Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40
   ```

> [!NOTE]
> 如示例中所述，日志文件的默认位置是%TEMP%\Tracing。 但是，由于实际上是 CLSAgent 正在写入文件，而 Clsagent 作为网络服务运行，因此% TEMP% 变量扩展为%Windir%\serviceprofiles\networkservice\appdata\local。

该命令将告知网站 Redmond 中的每台计算机和池中的 CLSAgent，以将跟踪文件上的滚动值的大小设置为 40 mb。 该命令不会影响其他站点中的计算机和池，并且将继续使用当前配置的跟踪日志滚动更新值（默认为 20 mb）或在日志记录会话的启动过程中定义。
### <a name="to-create-a-new-centralized-logging-service-configuration"></a>创建新的集中日志记录服务配置

1. 启动 Skype for Business Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **skype for business 2015**"，然后单击 " **skype for business Server Management Shell**"。

2. 在命令行提示符处键入以下内容：

   ```PowerShell
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > New-csclsconfiguration 提供对大量可选配置设置的访问权限。 有关配置选项的详细信息，请参阅[new-csclsconfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)和[了解集中日志记录服务配置设置](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx)。

例如，若要创建为缓存文件定义网络文件夹的新配置、滚动日志文件的时间段以及日志文件的滚动时间大小，请键入：

  ```PowerShell
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

您应仔细规划新配置的创建以及如何为集中日志记录服务定义新属性。 在进行更改时应谨慎，并确保了解对您正确记录问题方案的能力的影响。 您应对配置进行更改，以增强您管理日志的大小和滚动期，以便在出现问题时能够解决问题。
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>删除现有的集中日志记录服务配置

1. 启动 Skype for Business Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **skype for business 2015**"，然后单击 " **skype for business Server Management Shell**"。

2. 在命令行提示符处键入以下内容：

   ```PowerShell
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

例如，若要删除您创建的集中日志记录服务配置以增加日志文件滚动时间，请增加滚动更新日志文件大小，并将日志文件缓存位置设置为网络共享，如下所示：

  ```PowerShell
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> 这是在 "创建新的集中日志记录服务配置" 过程中创建的新配置。

如果选择删除网站级别的配置，则网站将使用全局设置。
## <a name="see-also"></a>另请参阅

[为 Skype for Business Server 2015 中的集中日志记录服务配置提供程序](configure-providers.md)

[在 Skype for Business Server 2015 中配置集中日志记录服务的方案](configure-scenarios.md)

[Skype for Business 2015 中的集中日志记录服务](centralized-logging-service.md)

[New-csclsconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[New-csclsconfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[新 New-csclsconfiguration](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[New-csclsconfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)
