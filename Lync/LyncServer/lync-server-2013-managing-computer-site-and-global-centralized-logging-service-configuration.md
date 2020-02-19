---
title: 管理计算机、站点和全局集中日志记录服务配置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing computer, site and global Centralized Logging Service configuration
ms:assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688138(v=OCS.15)
ms:contentKeyID: 49733738
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2d33a67b0b7e8c7e2771fbdc1055d003717dbb1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136169"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-computer-site-and-global-centralized-logging-service-configuration-in-lync-server-2013"></a>在 Lync Server 2013 中管理计算机、站点和全局集中日志记录服务配置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-02-04_

集中日志记录服务可在包含单个计算机（计算机池）的范围内运行，在站点范围（即，在部署中包含计算机和池集合的网站 Redmond）中，或全局范围内运行。、部署中的所有计算机和池）。

若要使用 Lync Server 命令行管理程序配置集中日志记录服务作用域，您必须是 CsAdministrator 或 CsServerAdministrator 基于角色的访问控制（RBAC）安全组的成员，或者是包含以下项的自定义 RBAC 角色：这两个组中的任何一个。 若要返回此 cmdlet 已分配到的所有 RBAC 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Lync Server 命令行管理程序或 Windows PowerShell 提示符处运行以下命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Lync Server 2013 cmdlet>"}

例如：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>


> [!NOTE]
> Windows PowerShell 为你提供了使用 CLSController 不可用的更多选项和其他配置选项。 CLSController 提供了一种简单、简洁的方法来运行命令，但仅限于可用于 CLSController 的一组命令。 Windows PowerShell 并不局限于仅可用于 CLSController 的命令处理器的命令，并提供了更多的命令集和更丰富的选项集。 例如，CLSController 将为您提供–计算机和–池的范围选项。 在 Windows PowerShell 中，可以在大多数命令中指示计算机或池，并在定义新方案（CLSController 具有有限数量的用户不可更改的方案）时，可以定义站点或全局作用域。 Windows PowerShell 的这一强大功能使您能够定义网站或全局作用域的方案，但将实际日志记录限制为计算机或池。<BR>可以在 Windows PowerShell 或 CLSController 中运行的命令行命令之间存在根本区别。 Windows PowerShell 提供了一种丰富的方法来配置和定义方案，并以一种有意义的方式在故障排除方案中重用这些方案。 虽然 CLSController 提供了一种快速有效的方式来发出命令和获取结果，但 CLSController 的命令集受您在命令行中可用的有限命令的限制。 与 Windows PowerShell cmdlet 不同，CLSController 无法定义新方案、网站或全局级别的管理作用域，以及无法动态配置的有限命令集的许多其他限制。 虽然 CLSController 提供了快速执行的一种方法，但 Windows PowerShell 提供了一种方法来扩展集中日志记录服务的功能，而不是使用 CLSController 可能的功能。



</div>

使用– computer 参数，可以在[search-csclslogging](https://technet.microsoft.com/library/JJ619189(v=OCS.15))、 [Show-search-csclslogging](https://technet.microsoft.com/library/JJ619173(v=OCS.15))、 [Start-search-csclslogging](https://technet.microsoft.com/library/JJ619190(v=OCS.15))、 [Stop-search-csclslogging](https://technet.microsoft.com/library/JJ619180(v=OCS.15))、 [Sync-search-csclslogging](https://technet.microsoft.com/library/JJ619169(v=OCS.15))和[search-csclslogging](https://technet.microsoft.com/library/JJ619170(v=OCS.15))命令的执行过程中定义单个计算机作用域。 – Computer 参数接受目标计算机的完全限定域名（Fqdn）的逗号分隔列表。

<div>


> [!TIP]
> 您还可以定义池以及要在其上运行日志记录命令的池的逗号分隔列表。



</div>

站点和全局作用域是在**新**的、**集**的和**删除**集中的日志记录服务 cmdlet 中定义的。 下面的示例演示如何设置站点和全局作用域。

<div>


> [!IMPORTANT]
> 所显示的命令可能包含其他部分中所涉及的参数和概念。 示例命令旨在演示如何使用<STRONG>– Identity</STRONG>参数定义作用域，并包含其他参数以实现完整性并指定作用域。 有关<STRONG>new-csclsconfiguration</STRONG> cmdlet 的详细信息，请参阅操作文档中的<A href="https://technet.microsoft.com/library/JJ619182(v=OCS.15)">new-csclsconfiguration</A> 。



</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>检索当前的集中日志记录服务配置

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  在命令行提示符处键入以下内容：
    
        Get-CsClsConfiguration

使用**new-csclsconfiguration**和**new-csclsconfiguration** cmdlet 创建新配置或更新现有配置。

运行**new-csclsconfiguration**时，它会显示类似于以下屏幕截图的信息，其中部署当前具有默认全局配置，但未定义网站配置：

![New-csclsconfiguration 中的示例输出。](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "New-csclsconfiguration 中的示例输出。")

</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>从计算机本地存储中检索当前的集中日志记录服务配置

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  在命令行提示符处键入以下内容：
    
        Get-CsClsConfiguration -LocalStore

如果使用的第一个示例中的**new-csclsconfiguration**未指定任何参数，则该命令将引用数据的中央管理存储。 如果指定参数– LocalStore，该命令将引用计算机 LocalStore 而不是中央管理存储。

</div>

<div>

## <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>检索当前定义的方案列表

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  在命令行提示符处键入以下内容：
    
        Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
    
    例如，若要检索在全局范围内定义的方案，请执行以下操作：
    
        Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios

Cmdlet **new-csclsconfiguration**始终显示属于给定作用域的配置的方案。 在大多数情况下，不会显示所有方案，并且会被截断。 此处使用的命令列出了有关使用哪些提供程序、设置和标志的所有方案和部分信息。

</div>

<div>

## <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>使用 Windows PowerShell 为集中日志记录服务更新全局作用域

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  在命令行提示符处键入以下内容：
    
        Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
    
    例如：
    
        Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40

该命令将告知部署中每台计算机和池中的 CLSAgent，以将跟踪文件上的滚动值的大小设置为 40 mb。 所有站点中的计算机和池受命令影响，并将其配置的跟踪日志滚动更新值设置为 40 mb。

</div>

<div>

## <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>使用 Windows PowerShell 为集中日志记录服务更新站点范围

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  在命令行提示符处键入以下内容：
    
        Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes> -EtlFileFolder <default location %TEMP%\Tracing>
    
    例如：
    
        Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40 -EtlFileFolder "C:\LogFiles\Tracing" 
    
    <div>
    

    > [!NOTE]
    > 如示例中所述，日志文件的默认位置是%TEMP%\Tracing。 但是，由于实际上是 CLSAgent 正在写入文件，而 Clsagent 作为网络服务运行，因此% TEMP% 变量扩展为%Windir%\serviceprofiles\networkservice\appdata\local。

    
    </div>

该命令将告知网站 Redmond 中的每台计算机和池中的 CLSAgent，以将跟踪文件上的滚动值的大小设置为 40 mb。 该命令不会影响其他站点中的计算机和池，并且将继续使用当前配置的跟踪日志滚动更新值（默认为 20 mb）或在日志记录会话的启动过程中定义。

</div>

<div>

## <a name="to-create-a-new-centralized-logging-service-configuration"></a>创建新的集中日志记录服务配置

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  在命令行提示符处键入以下内容：
    
        New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
    
    <div>
    

    > [!NOTE]
    > New-csclsconfiguration 提供对大量可选配置设置的访问权限。 有关配置选项的详细信息，请参阅<A href="https://technet.microsoft.com/library/JJ619179(v=OCS.15)">new-csclsconfiguration</A> ，<A href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">了解 Lync Server 2013 中的集中日志记录服务配置设置</A>。

    
    </div>
    
    例如，若要创建为缓存文件定义网络文件夹的新配置、滚动日志文件的时间段以及日志文件的滚动时间大小，请键入：
    
        New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40

您应仔细规划新配置的创建以及如何为集中日志记录服务定义新属性。 在进行更改时应谨慎，并确保了解对您正确记录问题方案的能力的影响。 您应对配置进行更改，以增强您管理日志的大小和滚动期，以便在出现问题时能够解决问题。

</div>

<div>

## <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>删除现有的集中日志记录服务配置

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  在命令行提示符处键入以下内容：
    
        Remove-CsClsConfiguration -Identity <scope and name>
    
    例如，若要删除您创建的集中日志记录服务配置以增加日志文件滚动时间，请增加滚动更新日志文件大小，并将日志文件缓存位置设置为网络共享，如下所示：
    
        Remove-CsClsConfiguration -Identity "site:Redmond"
    
    <div>
    

    > [!NOTE]
    > 这是在 "创建新的集中日志记录服务配置" 过程中创建的新配置。

    
    </div>

如果选择删除网站级别的配置，则网站将使用全局设置。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的集中日志记录服务概述](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[在 Lync Server 2013 中管理集中日志记录服务配置设置](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)  
[New-csclsconfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))  
[New-csclsconfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))  
[新 New-csclsconfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))  
[New-csclsconfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

