---
title: 对集中日志记录服务使用 Stop 命令
TOCTitle: 对集中日志记录服务使用 Stop 命令
ms:assetid: 09ac093e-8f30-4874-84b4-12548ac8c898
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ687964(v=OCS.15)
ms:contentKeyID: 49888294
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 对集中日志记录服务使用 Stop 命令

 

_**上一次修改主题：** 2012-11-01_

您可以使用 Stop-CsClsLogging cmdlet 停止当前正在运行的日志记录会话。通常，需要停止日志记录会话的情形并不多。例如，无需先停止日志记录就可以搜索日志和更改配置。如果您有两种方案（例如 AlwaysOn 和 UserReplicator）在运行，并且您需要收集与身份验证相关的信息，则您需要停止其他方案之一（在全局、站点、池或计算机范围内），然后才能开始运行身份验证方案。有关详细信息，请参阅 [Stop-CsClsLogging](https://docs.microsoft.com/en-us/powershell/module/skype/Stop-CsClsLogging)。

> [!NOTE]
> 在确定了可以在给定部署、池或计算机上运行哪些方案后，您需要记住，在<strong>每台计算机</strong>上只能运行两个方案。如果您要记录某个池上的活动，应将一个池视为单一实体。在大多数情况下，在池中的每台计算机上运行不同方案没有意义。了解正在收集其数据的问题以及考虑哪些方案在总体部署中的给定计算机上运行最有意义才是合理的。例如，如果您考虑 UserReplicator 方案，则在边缘服务器或边缘池上运行 UserReplicator 几乎无价值。<br />
> 在了解了问题和影响范围后，应谨慎选择哪些方案在哪些计算机和池上运行。AlwaysOn 方案对于广泛的应用具有意义，因为它收集各类提供商的信息，而具体方案只在特定计算机或池上具有应用价值。此外，在随机启动日志记录会话而不先了解给定方案的价值时务必小心。如果使用的方案错误，或者虽然使用的方案适合任务，但应用范围（全局、站点、池或计算机）错误，您可以获得不是很有用的可疑数据，就像您根本没有运行该方案一样。


要使用 Lync Server 命令行管理程序控制集中日志记录服务功能，您必须是基于 CsAdministrator 或 CsServerAdministrator 角色的访问控制 (RBAC) 安全组的成员，或是包含这两个组之一的自定义 RBAC 角色。若要返回所有已分配此 cmdlet 的 RBAC 角色列表（包括您自己创建的任何自定义 RBAC 角色），请从 Lync Server 命令行管理程序或 Windows PowerShell 提示符运行以下命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

例如：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

## 停止当前正在运行的集中日志记录服务会话

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  键入以下命令来查询集中日志记录服务以找出当前正在运行的方案：
    
        Show-CsClsLogging
    
    ![调用 Show-CsCl 后的 Windows PowerShell 控制台](images/JJ687964.eb190c32-529c-4277-a731-52c47d22d8fa(OCS.15).jpg "调用 Show-CsCl 后的 Windows PowerShell 控制台")
    
    Show-CsClsLogging 的结果是正在运行的方案以及它们所运行的范围的摘要。有关详细信息，请参阅 [Show-CsClsLogging](https://docs.microsoft.com/en-us/powershell/module/skype/Show-CsClsLogging)。

3.  若要使用特定方案停止当前正在运行的日志记录会话，请键入：
    
        Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
    
    例如：
    
        Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
    
    此命令将在 pool01.contoso.net 上使用 UserReplicatior 方案停止日志记录。
    
    > [!NOTE]
    > 在此日志记录会话期间使用 UserReplicator 方案创建的日志不会被删除。您仍然可以使用 Search-CsClsLogging 命令对日志记录执行搜索。有关详细信息，请参阅 <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Search-CsClsLogging">Search-CsClsLogging</a>。


作为 Start-CsClsLogging 的配套命令，Stop-CsClsLogging cmdlet 会结束方案定义的日志记录会话，并保留日志记录会话创建的日志。任何时候都可以在给定计算机上运行两个方案。停止一个方案而使用另一个方案收集信息的方法是一项常见的任务，您可以在大多数工作负荷故障排除过程中执行该任务。

## 另请参阅

#### 任务

[使用启动集中日志服务以捕获日志](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)  

#### 概念

[集中日志记录服务的概述](lync-server-2013-overview-of-the-centralized-logging-service.md)  

#### 其他资源

[Show-CsClsLogging](https://docs.microsoft.com/en-us/powershell/module/skype/Show-CsClsLogging)  
[Start-CsClsLogging](https://docs.microsoft.com/en-us/powershell/module/skype/Start-CsClsLogging)  
[Stop-CsClsLogging](https://docs.microsoft.com/en-us/powershell/module/skype/Stop-CsClsLogging)

