---
title: 'Lync Server 2013: 为集中式日志记录服务使用停止'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Stop for the Centralized Logging Service
ms:assetid: 09ac093e-8f30-4874-84b4-12548ac8c898
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687964(v=OCS.15)
ms:contentKeyID: 49733549
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 521328b688f90ca591abddb3e59e7d49ae771b15
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845411"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-stop-for-the-centralized-logging-service-in-lync-server-2013"></a>在 Lync Server 2013 中为集中式日志记录服务使用停止

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-11-01_

您可以使用 Stop-CsClsLogging cmdlet 停止当前正在运行的日志记录会话。通常，需要停止日志记录会话的情形并不多。例如，无需先停止日志记录就可以搜索日志和更改配置。如果您有两种方案（例如 AlwaysOn 和 UserReplicator）在运行，并且您需要收集与身份验证相关的信息，则您需要停止其他方案之一（在全局、站点、池或计算机范围内），然后才能开始运行身份验证方案。有关详细信息，请参阅 [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging)。

<div>


> [!NOTE]  
> 确定可在给定的部署、池或计算机上运行哪些方案时, 你需要记住, 你限制为<STRONG>每台计算机</STRONG>运行两种方案。 如果您要记录某个池上的活动，应将一个池视为单一实体。 在大多数情况下，在池中的每台计算机上运行不同方案没有意义。 了解正在收集其数据的问题以及考虑哪些方案在总体部署中的给定计算机上运行最有意义才是合理的。 例如, 如果你考虑 UserReplicator 方案, 则在边缘服务器或边缘池上运行 UserReplicator 时, 将有非常少的值。<BR>在了解了问题和影响范围后，应谨慎选择哪些方案在哪些计算机和池上运行。尽管 AlwaysOn 方案会收集各类提供商的信息，在多种应用下均意义显著，但具体方案可能只在特定计算机或池上具有应用价值。此外，在随机启动日志记录会话而不先了解给定方案的价值时务必小心。如果使用的方案错误，或者虽然使用的方案适合任务，但应用范围（全局、站点、池或计算机）错误，那么您就可能存在问题、没有使用价值的数据，最终效果与根本没有运行该方案时无异。



</div>

若要使用 Lync Server Management Shell 控制集中式日志记录服务功能, 您必须是 CsAdministrator 或 CsServerAdministrator 基于角色的访问控制 (RBAC) 安全组的成员, 或者是包含以下项的自定义 RBAC 角色这两个组中的任何一个。 若要返回此 cmdlet 已分配到的所有 RBAC 角色的列表 (包括你自己创建的任何自定义 RBAC 角色), 请从 Lync Server 命令行管理程序或 Windows PowerShell 提示中运行以下命令:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

例如：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>

## <a name="to-stop-a-currently-running-centralized-logging-service-session"></a>停止当前运行的集中式日志记录服务会话

1.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

2.  通过键入以下内容, 查询集中式日志记录服务以了解当前正在运行的方案:
    
        Show-CsClsLogging
    
    ![调用 Show-CsCl 后的 Windows PowerShell 控制台](images/JJ687964.eb190c32-529c-4277-a731-52c47d22d8fa(OCS.15).jpg "调用 Show-CsCl 后的 Windows PowerShell 控制台")
    
    Show-CsClsLogging 的结果是正在运行的方案以及它们所运行的范围的摘要。有关详细信息，请参阅 [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging)。

3.  若要使用特定方案停止当前正在运行的日志记录会话，请键入：
    
        Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
    
    例如：
    
        Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
    
    此命令将在 pool01.contoso.net 上使用 UserReplicatior 方案停止日志记录。
    
    <div>
    

    > [!NOTE]  
    > 在此日志记录会话期间使用 UserReplicator 方案创建的日志不会被删除。您仍然可以使用 Search-CsClsLogging 命令对日志记录执行搜索。有关详细信息，请参阅 <A href="https://docs.microsoft.com/powershell/module/skype/Search-CsClsLogging">Search-CsClsLogging</A>。

    
    </div>

作为 Start-CsClsLogging 的配套命令，Stop-CsClsLogging cmdlet 会结束方案定义的日志记录会话，并保留日志记录会话创建的日志。任何时候都可以在给定计算机上运行两个方案。停止一个方案而使用另一个方案收集信息的方法是一项常见的任务，您可以在大多数工作负载故障排除过程中执行该任务。

</div>

<div>

## <a name="see-also"></a>另请参阅


[使用 "开始使用集中式日志记录" 服务捕获 Lync Server 2013 中的日志](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)  


[Lync Server 2013 中的集中式日志记录服务概述](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging)  
[开始-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Start-CsClsLogging)  
[停止-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

