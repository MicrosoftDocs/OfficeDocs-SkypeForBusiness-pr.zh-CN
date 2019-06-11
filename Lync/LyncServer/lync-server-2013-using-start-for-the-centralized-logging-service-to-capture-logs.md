---
title: 使用 "开始" 进行集中日志记录服务捕获日志
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Start for the Centralized Logging Service to capture logs
ms:assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687958(v=OCS.15)
ms:contentKeyID: 49733543
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5033b4a8dfd8121e2f0b5926623a55358188935e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845417"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-start-for-the-centralized-logging-service-to-capture-logs-in-lync-server-2013"></a>使用 "开始使用集中式日志记录" 服务捕获 Lync Server 2013 中的日志

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-21_

若要使用集中式日志记录服务捕获跟踪日志, 请发出一个命令, 以便在一个或多个计算机和池上开始日志记录。 你还可以发出参数, 用于定义哪些计算机或池、要运行的方案 (例如, AlwaysOn、另一个预定义方案或你已创建的方案)、要跟踪的 Lync Server 组件 (例如, S4、SipStack)。

若要捕获正确的信息，您必须使用正确的方案收集问题相关信息。 在集中式日志记录服务中, 方案是基于服务器组件、日志记录级别和标志的集合来打开日志记录的概念, 它比必须在每个服务器基础上定义这些元素更有效, 更有用。 您只需定义一个方案并指定运行该方案，该方案即会在基础架构范围内的所有服务器和池中一致地运行。

默认方案称为 **AlwaysOn**。顾名思义，AlwaysOn 的目的就是持续不断地运行方案。AlwaysOn 方案为许多最常用的服务器组件收集信息级别信息（请注意，除“信息”消息外，“信息”日志记录级别还包括致命错误、错误和警告）。AlwaysOn 在问题发生之前、发生过程中和发生之后收集信息。这与以前的日志记录工具（如 OCSLogger）的典型行为截然不同。您在问题发生之后才运行 OCSLogger，这使得故障排除工作更加困难，因为获得的数据是被动而非主动的。如果 AlwaysOn 不包含您正在寻找的能够指出问题组件和纠正措施的信息（考虑到 AlwaysOn 中提供程序的广度和深度，不太可能会发生这种情况），它会指出一个合理的信息水平，以确定您需要执行的其他操作，例如，创建新方案，收集其他信息，运行不同搜索来收集更集中的详细信息等等。

集中式日志记录服务提供了两种发出命令的方法。 许多主题的重点完全是通过 Lync Server 命令行管理程序使用 Windows PowerShell。 使用大量复杂的配置和命令的功能有利于使用 Windows PowerShell 集中式日志记录服务。 由于 Windows PowerShell 通过 Lync Server Management Shell 几乎到处是 Lync Server 中的所有功能, 因此仅讨论 Windows PowerShell 命令。

<div>


> [!NOTE]
> 如果你决定使用命令行中提供的受限命令集, 则可以通过键入<CODE>ClsController.exe</CODE>来获取有关 CLSController 的帮助。 默认情况下, <STRONG>ClsController</STRONG>在目录 C:\Program Files\Microsoft Lync Server 2013 \ ClsAgent 中安装。



</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a>使用基本命令对 Windows PowerShell 运行开始 CsClsLogging

1.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

2.  通过键入以下内容, 通过集中式日志记录服务启动日志记录方案:
    
        Start-CsClsLogging -Scenario <name of scenario>
    
    例如，要启动 **AlwaysOn** 方案，可键入：
    
        Start-CsClsLogging -Scenario AlwaysOn
    
    <div>
    

    > [!NOTE]
    > AlwaysOn 方案没有默认持续时间。 此方案将一直运行到您通过 <STRONG>Stop-CsClsLogging</STRONG> cmdlet 明确停止它为止。 有关详细信息，请参阅 <A href="https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>。 对于所有其他方案，默认持续时间为 4 小时。

    
    </div>

3.  按 Enter 运行命令。
    
    <div>
    

    > [!NOTE]
    > 可能需要一小段时间（30 到 60 秒）命令才运行完毕，并接收从您的部署中的计算机返回的状态。

    
    </div>
    
    ![运行开始-CsClsLogging。](images/JJ687958.c5be7413-8cef-4de7-9712-944d20cc2fa4(OCS.15).jpg "运行开始-CsClsLogging。")

4.  要启动另一个方案，请使用 **Start-CsClsLogging** cmdlet 并提供要按如下方式运行的附加方案的名称（例如 **Authentication**）：
    
        Start-CsClsLogging -Scenario Authentication
    
    <div>
    

    > [!IMPORTANT]
    > 在任意时间可以在任何给定计算机上运行总共两个方案。 如果命令是全局范围的，则部署中的所有计算机将运行方案。 要启动第三个方案，必须在您要运行新方案的计算机、池、站点或全局范围上停止日志记录。 如果已启动全局范围，则可以在一个或多个计算机和池上停止一种方案或同时停止两种方案的日志记录。 有关管理正在运行的方案的详细信息, 请参阅在 Lync Server 2013 和<A href="https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A><A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">中使用集中日志记录服务的 "停止"</A> 。

    
    </div>

</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a>使用高级命令对 Windows PowerShell 运行开始 CsClsLogging

1.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

2.  也可以使用其他参数来管理日志记录命令。可以使用 –Duration 调整方案运行的时间长度。还可以定义 –Computers（逗号分隔的计算机完全限定域名 (FQDN) 的列表），或 –Pools（要对其运行日志记录的池的逗号分隔的 FQDN 列表）。
    
    您为池“pool01.contoso.net”上的 *UserReplicator* 方案启动了日志记录会话。 您还定义日志记录会话持续时间为 8 小时。 为此，请键入：
    
        Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
    
    此方案成功执行后将返回类似如下的结果：
    
    ![运行开始-CsClsLogging。](images/JJ687958.399f0c2e-c08c-40ab-b6c6-381dddc12fe9(OCS.15).jpg "运行开始-CsClsLogging。")
    
    注意，在此示例中，正在运行的方案是 AlwaysOn 和 UserReplicator。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的集中式日志记录服务概述](lync-server-2013-overview-of-the-centralized-logging-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

