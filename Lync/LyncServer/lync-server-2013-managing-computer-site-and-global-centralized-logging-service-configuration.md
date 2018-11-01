---
title: 管理计算机、站点和全局中心日志记录服务配置
TOCTitle: 管理计算机、站点和全局中心日志记录服务配置
ms:assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688138(v=OCS.15)
ms:contentKeyID: 49888518
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 管理计算机、站点和全局中心日志记录服务配置

 

_**上一次修改主题：** 2014-02-04_

集中日志记录服务可在包括单台计算机和计算机池的作用域、站点作用域（即，已定义的站定，如将计算机集合和池包含在部署中的站点 Redmond）或全局作用域（即，部署中的所有计算机和池）运行。

要使用 Lync Server 命令行管理程序配置集中日志记录服务作用域，您必须是基于 CsAdministrator 或 CsServerAdministrator 角色的访问控制 (RBAC) 安全组的成员，或是包含这两个组中的任何一个的自定义 RBAC 角色。要返回分配了此 cmdlet 的所有 RBAC 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Lync Server 命令行管理程序或 Windows PowerShell 提示符处运行以下命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Lync Server 2013 cmdlet>"}

例如：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

> [!NOTE]  
> Windows PowerShell 为您提供了无法使用 CLSController.exe 提供的更多选项和其他配置选项。CLSController 提供了快速、简洁地运行命令的方法，但限于对 CLSController 可用的命令集。Windows PowerShell 不是仅限于对 CLSController 的命令处理器可用的命令集，并提供了更广泛的命令集和更丰富的选项集。例如，CLSController.exe 为您提供了针对 –Computers 和 –pools 的作用域选项。利用 Windows PowerShell，您可以在大多数命令中指示计算机或池，当定义新方案（CLSController 具有有限数量的用户不可修改的方案）时，您可以定义站点或全局作用域。Windows PowerShell 的此强大功能支持您为方案定义站点或全局作用域，但限制到计算机或池的实际登录。<br />
可在 Windows PowerShell 或 CLSController 中运行的命令行命令之间存在根本差异。Windows PowerShell 提供了大量配置和定义方案的方法，并提供了大量以一种有意义的方式对故障排除方案重复使用这些方案的方法。尽管 CLSController 提供了快速有效的发出命令和获得结果的方法，但 CLSController 的命令集受到您从命令行获得的有限数量的命令的限制。与 Windows PowerShell cmdlet 不同，CLSController 无法定义新方案，无法管理站点或全局级别的作用域，还具有无法动态配置的有限命令集的很多其他限制。CLSController 提供了一种快速执行方法，而 Windows PowerShell 提供了一种将集中日志记录服务功能扩展到超出 CLSController 能提供的功能的范围的方法。



可以使用 –Computers 参数在 [Search-CsClsLogging](https://docs.microsoft.com/en-us/powershell/module/skype/Search-CsClsLogging)、[Show-CsClsLogging](https://docs.microsoft.com/en-us/powershell/module/skype/Show-CsClsLogging)、[Start-CsClsLogging](https://docs.microsoft.com/en-us/powershell/module/skype/Start-CsClsLogging)、[Stop-CsClsLogging](https://docs.microsoft.com/en-us/powershell/module/skype/Stop-CsClsLogging)、[Sync-CsClsLogging](https://docs.microsoft.com/en-us/powershell/module/skype/Sync-CsClsLogging) 和 [Update-CsClsLogging](https://docs.microsoft.com/en-us/powershell/module/skype/Update-CsClsLogging) 命令执行期间定义单个计算机的作用域。–Computers 参数接受目标计算机的以逗号分隔的完全限定域名 (FQDN) 的列表。

> [!TIP]
> 还可以定义–Pools 和您要对其运行日志记录命令的以逗号分隔的池的列表。


站点和全局作用域在 **New-**、**Set-** 和 **Remove-**集中日志记录服务 cmdlet 中定义。以下示例演示了如何设置站点和全局作用域。

> [!IMPORTANT]
> 显示的命令可能包含其他章节中涵盖的参数和概念。示例命令旨在演示如何使用 <strong>–Identity</strong> 参数定义作用域，还包含了其他参数来保证完整性和指定作用域。有关 <strong>Set-CsClsConfiguration</strong> cmdlet 的详细信息，请参阅操作文档中的 <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClsConfiguration">Set-CsClsConfiguration</a>。


## 检索当前集中日志记录服务配置

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  在命令行提示符处键入以下内容：
    
        Get-CsClsConfiguration

使用 **New-CsClsConfiguration** 和 **Set-CsClsConfiguration** cmdlet 创建新配置或更新现有配置。

当运行 **Get-CsClsConfiguration** 时，它将显示类似于下面的屏幕快照的信息，其中，部署当前具有默认的全局配置，但未定义站点配置：

![来自 Get-CsClsConfiguration 的示例输出。](images/JJ688138.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "来自 Get-CsClsConfiguration 的示例输出。")

## 从计算机本地存储检索当前集中日志记录服务配置

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  在命令行提示符处键入以下内容：
    
        Get-CsClsConfiguration -LocalStore

当使用第一个示例（其中的 **Get-CsClsConfiguration** 未指定任何参数），命令将引用数据的中央管理存储。如果指定了参数 –LocalStore，命令将引用计算机 LocalStore 而不是中央管理存储。

## 检索当前定义的方案的列表

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  在命令行提示符处键入以下内容：
    
        Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
    
    例如，检索在全局作用域定义的方案：
    
        Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios

cmdlet **Get-CsClsConfiguration** 始终显示作为给定作用域的配置的一部分的方案。在大多数情况下，不会显示所有方案，而会截断它们。此处使用的命令列出所有方案和有关所使用的提供程序、设置和标记的部分信息。

## 使用 Windows PowerShell 更新集中日志记录服务的全局作用域

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  在命令行提示符处键入以下内容：
    
        Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
    
    例如：
    
        Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40

该命令指示部署中的每个计算机和池中的 CLSAgent 将跟踪文件上的滚动值的大小设置为 40 MB。所有站点中的计算机和池都受该命令的影响，并且会将其已配置的跟踪日志滚动值设置为 40 MB。

## 使用 Windows PowerShell 更新集中日志记录服务的站点作用域

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  在命令行提示符处键入以下内容：
    
        Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes> -EtlFileFolder <default location %TEMP%\Tracing>
    
    例如：
    
        Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40 -EtlFileFolder "C:\LogFiles\Tracing" 
    
    > [!NOTE]  
    > 如示例中所示，日志文件的默认位置是 %TEMP%\Tracing。但是，由于实际上是 CLSAgent 写入该文件，而且 CLSAgent 以 Network Service 的身份运行，因此 %TEMP% 变量将展开到 %WINDIR%\ServiceProfiles\NetworkService\AppData\Local。
    


该命令指示 Redmond 站点中的每个计算机和池中的 CLSAgent 将跟踪文件上的滚动值的大小设置为 40 MB。其他站点中的计算机和池不会受该命令的影响，并将继续使用当前配置的跟踪日志滚动值（默认定义的 (20 MB) 或在日志记录会话开始时定义的）。

## 创建新的集中日志记录服务配置

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  在命令行提示符处键入以下内容：
    
        New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
    
    > [!NOTE]  
    > 利用 New-CsClsConfiguration，可以访问大量可选配置设置。有关配置选项的详细信息，请参阅 <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClsConfiguration">Get-CsClsConfiguration</a> 和<a href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">了解日志记录服务配置设置</a>。
    
    
    例如，要创建用于定义缓存文件的网络文件夹、日志文件的滚动时间段和日志文件的滚动大小的新配置，您将键入：
    
        New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40

您应仔细规划新配置的创建和定义集中日志记录服务的新属性的方式。您在进行更改时应格外小心，并应确保了解对您正确记录问题方案的能力的影响。您应更改配置，提高管理日志大小和滚动周期（允许在问题发生时予以解决）的能力。

## 删除现有集中日志记录服务配置。

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  在命令行提示符处键入以下内容：
    
        Remove-CsClsConfiguration -Identity <scope and name>
    
    例如，要删除您创建的集中日志记录服务配置以增加日志文件滚动时间，请增大滚动日志文件大小，并将日志文件缓存位置设置为网络共享，如下所示：
    
        Remove-CsClsConfiguration -Identity "site:Redmond"
    
    > [!NOTE]  
    > 这是在过程“创建新的集中日志记录服务配置”中创建的新配置。
    


如果选择删除站点级配置，站点将使用全局设置。

## 另请参阅

#### 概念

[集中日志记录服务的概述](lync-server-2013-overview-of-the-centralized-logging-service.md)  

#### 其他资源

[使用 PowerShell 管理集中日志记录服务配置设置](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)  
[Set-CsClsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClsConfiguration)  
[Get-CsClsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClsConfiguration)  
[New-CsClsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClsConfiguration)  
[Remove-CsClsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsClsConfiguration)

