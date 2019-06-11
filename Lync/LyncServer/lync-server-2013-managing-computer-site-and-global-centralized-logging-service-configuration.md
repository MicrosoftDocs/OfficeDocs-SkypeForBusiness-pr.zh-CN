---
title: 管理计算机、站点和全局集中日志记录服务配置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing computer, site and global Centralized Logging Service configuration
ms:assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688138(v=OCS.15)
ms:contentKeyID: 49733738
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02c18e57b81daf93139493d046b8b2124e04e767
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-computer-site-and-global-centralized-logging-service-configuration-in-lync-server-2013"></a>在 Lync Server 2013 中管理计算机、站点和全局集中日志记录服务配置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2014-02-04_

集中式日志记录服务可以在包含单个计算机的范围 (即计算机池) 所在的范围内运行 (即, 定义的网站 (如网站 Redmond), 其中包含你的部署中的计算机和池的集合, 或者在全局范围内、部署中的所有计算机和池)。

若要使用 Lync Server 命令行管理器配置集中式日志记录服务范围, 你必须是 CsAdministrator 或 CsServerAdministrator 基于角色的访问控制 (RBAC) 安全组的成员, 或者是包含以下项的自定义 RBAC 角色这两个组中的任何一个。 若要返回此 cmdlet 已分配到的所有 RBAC 角色的列表 (包括你自己创建的任何自定义 RBAC 角色), 请从 Lync Server 命令行管理程序或 Windows PowerShell 提示中运行以下命令:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Lync Server 2013 cmdlet>"}

例如：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>


> [!NOTE]
> Windows PowerShell 通过使用 CLSController 提供了更多选项和其他不可用的配置选项。 CLSController 提供了一种快速、简洁的方法来运行命令, 但仅限于可用于 CLSController 的命令集。 Windows PowerShell 不仅限于 CLSController 的命令处理器可用的命令, 并提供了更多的命令集和更丰富的选项集。 例如, CLSController 将为你提供-计算机和-池的范围选项。 使用 Windows PowerShell, 你可以在大多数命令中指示计算机或池, 并且当你定义新方案时 (CLSController 具有的用户不能更改的有限数量的方案), 你可以定义一个网站或全局范围。 Windows PowerShell 的这一强大功能允许你定义网站或全局范围的方案, 但将实际日志记录限制到计算机或池。<BR>可以在 Windows PowerShell 或 CLSController 中运行的命令行命令之间存在基本差异。 Windows PowerShell 提供了一种丰富的方法来配置和定义方案, 并以一种有意义的方式重复使用这些方案来解决你的故障排除方案。 尽管 CLSController 提供了快速有效的发出命令和获得结果的方法，但 CLSController 的命令集受到您从命令行获得的有限数量的命令的限制。 与 Windows PowerShell cmdlet 不同, CLSController 无法定义新方案、网站或全局级别的管理范围, 以及无法动态配置的有限命令集的许多其他限制。 虽然 CLSController 提供快速执行的方法, 但 Windows PowerShell 提供了一种方法来扩展集中式日志记录服务功能, 而不是 CLSController 的可能性。



</div>

可以使用 –Computers 参数在 [Search-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619189(v=OCS.15))、[Show-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619173(v=OCS.15))、[Start-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619190(v=OCS.15))、[Stop-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15))、[Sync-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619169(v=OCS.15)) 和 [Update-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619170(v=OCS.15)) 命令执行期间定义单个计算机的作用域。–Computers 参数接受目标计算机的以逗号分隔的完全限定域名 (FQDN) 的列表。

<div>


> [!TIP]
> 还可以定义–Pools 和您要对其运行日志记录命令的以逗号分隔的池的列表。



</div>

站点和全局范围在**新**的、**集的**和**删除**集中的日志记录服务 cmdlet 中定义。 以下示例演示了如何设置站点和全局作用域。

<div>


> [!IMPORTANT]
> 显示的命令可能包含其他章节中涵盖的参数和概念。 示例命令旨在演示如何使用 <STRONG>–Identity</STRONG> 参数定义作用域，还包含了其他参数来保证完整性和指定作用域。 有关 <STRONG>Set-CsClsConfiguration</STRONG> cmdlet 的详细信息，请参阅操作文档中的 <A href="https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15)">Set-CsClsConfiguration</A>。



</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>检索当前集中式日志记录服务配置

1.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

2.  在命令行提示符处键入以下内容：
    
        Get-CsClsConfiguration

使用 **New-CsClsConfiguration** 和 **Set-CsClsConfiguration** cmdlet 创建新配置或更新现有配置。

当运行 **Get-CsClsConfiguration** 时，它将显示类似于下面的屏幕快照的信息，其中，部署当前具有默认的全局配置，但未定义站点配置：

![CsClsConfiguration 的示例输出。](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "CsClsConfiguration 的示例输出。")

</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>从计算机本地应用商店检索当前集中式日志记录服务配置

1.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

2.  在命令行提示符处键入以下内容：
    
        Get-CsClsConfiguration -LocalStore

使用**CsClsConfiguration**未指定任何参数的第一个示例时, 该命令将引用数据的中央管理存储。 如果你指定参数-LocalStore, 该命令将引用计算机 LocalStore, 而不是中央管理存储。

</div>

<div>

## <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>检索当前定义的方案的列表

1.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

2.  在命令行提示符处键入以下内容：
    
        Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
    
    例如，检索在全局作用域定义的方案：
    
        Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios

cmdlet **Get-CsClsConfiguration** 始终显示作为给定作用域的配置的一部分的方案。 在大多数情况下，不会显示所有方案，而会截断它们。 此处使用的命令列出所有方案和有关所使用的提供程序、设置和标记的部分信息。

</div>

<div>

## <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>使用 Windows PowerShell 更新集中日志记录服务的全局范围

1.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

2.  在命令行提示符处键入以下内容：
    
        Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
    
    例如：
    
        Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40

该命令指示部署中的每个计算机和池中的 CLSAgent 将跟踪文件上的滚动值的大小设置为 40 MB。所有站点中的计算机和池都受该命令的影响，并且会将其已配置的跟踪日志滚动值设置为 40 MB。

</div>

<div>

## <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>使用 Windows PowerShell 更新集中日志记录服务的网站范围

1.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

2.  在命令行提示符处键入以下内容：
    
        Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes> -EtlFileFolder <default location %TEMP%\Tracing>
    
    例如：
    
        Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40 -EtlFileFolder "C:\LogFiles\Tracing" 
    
    <div>
    

    > [!NOTE]
    > 如示例中所示，日志文件的默认位置是 %TEMP%\Tracing。但是，由于实际上是 CLSAgent 写入该文件，而且 CLSAgent 以 Network Service 的身份运行，因此 %TEMP% 变量将展开到 %WINDIR%\ServiceProfiles\NetworkService\AppData\Local。

    
    </div>

该命令指示 Redmond 站点中的每个计算机和池中的 CLSAgent 将跟踪文件上的滚动值的大小设置为 40 MB。其他站点中的计算机和池不会受该命令的影响，并将继续使用当前配置的跟踪日志滚动值（默认定义的 (20 MB) 或在日志记录会话开始时定义的）。

</div>

<div>

## <a name="to-create-a-new-centralized-logging-service-configuration"></a>创建新的集中式日志记录服务配置

1.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

2.  在命令行提示符处键入以下内容：
    
        New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
    
    <div>
    

    > [!NOTE]
    > 利用 New-CsClsConfiguration，可以访问大量可选配置设置。 有关配置选项的详细信息, 请参阅<A href="https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15)">CsClsConfiguration</A>和<A href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">了解 Lync Server 2013 中的集中日志记录服务配置设置</A>。

    
    </div>
    
    例如，要创建用于定义缓存文件的网络文件夹、日志文件的滚动时间段和日志文件的滚动大小的新配置，您将键入：
    
        New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40

你应该仔细规划新配置的创建以及如何为集中式日志记录服务定义新属性。 您在进行更改时应格外小心，并应确保了解对您正确记录问题方案的能力的影响。 您应更改配置，提高管理日志大小和滚动周期（允许在问题发生时予以解决）的能力。

</div>

<div>

## <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>删除现有的集中日志记录服务配置

1.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

2.  在命令行提示符处键入以下内容：
    
        Remove-CsClsConfiguration -Identity <scope and name>
    
    例如, 若要删除你创建的集中日志记录服务配置以增加日志文件滚动更新时间, 请增加滚动更新日志文件大小, 并将日志文件缓存位置设置为网络共享, 如下所示:
    
        Remove-CsClsConfiguration -Identity "site:Redmond"
    
    <div>
    

    > [!NOTE]
    > 这是在 "创建新的集中日志记录服务配置" 过程中创建的新配置。

    
    </div>

如果选择删除站点级配置，站点将使用全局设置。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的集中式日志记录服务概述](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[在 Lync Server 2013 中管理集中式日志记录服务配置设置](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)  
[Set-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15))  
[Get-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15))  
[New-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619177(v=OCS.15))  
[Remove-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619191(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

