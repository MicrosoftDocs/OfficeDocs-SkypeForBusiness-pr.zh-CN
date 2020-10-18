---
title: 使用 Start 获取集中日志记录服务以捕获日志
description: 使用 Start 实现集中日志记录服务以捕获日志。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Start for the Centralized Logging Service to capture logs
ms:assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687958(v=OCS.15)
ms:contentKeyID: 49733543
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6321af0b12f3650d3b741e65968849332b53af45
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580218"
---
# <a name="using-start-for-the-centralized-logging-service-to-capture-logs-in-lync-server-2013"></a>使用 Start 实现集中日志记录服务以在 Lync Server 2013 中捕获日志

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-21_

若要使用集中日志记录服务捕获跟踪日志，您需要发出命令以在一个或多个计算机和池上开始日志记录。 此外，还会发出参数，用于定义哪些计算机或池、哪些应用场景 (例如，AlwaysOn、另一个预定义方案或已创建的方案) ，什么 Lync Server 组件 (例如，S4、SipStack) 跟踪。

若要捕获正确的信息，您需要确保使用正确的方案收集与问题相关的信息。 在集中日志记录服务中，方案是基于一组服务器组件、日志记录级别和标志启用日志记录的概念，这比必须在每个服务器上定义这些元素的效率更高，更有用。 您只需定义一个方案并指定运行该方案，该方案即会在基础架构范围内的所有服务器和池中一致地运行。

默认方案称为 **AlwaysOn**。顾名思义，AlwaysOn 的目的就是持续不断地运行方案。AlwaysOn 方案为许多最常用的服务器组件收集信息级别信息（请注意，除“信息”消息外，“信息”日志记录级别还包括致命错误、错误和警告）。AlwaysOn 在问题发生之前、发生过程中和发生之后收集信息。这与以前的日志记录工具（如 OCSLogger）的典型行为截然不同。您在问题发生之后才运行 OCSLogger，这使得故障排除工作更加困难，因为获得的数据是被动而非主动的。如果 AlwaysOn 不包含您正在寻找的能够指出问题组件和纠正措施的信息（考虑到 AlwaysOn 中提供程序的广度和深度，不太可能会发生这种情况），它会指出一个合理的信息水平，以确定您需要执行的其他操作，例如，创建新方案，收集其他信息，运行不同搜索来收集更集中的详细信息等等。

集中日志记录服务提供了两种发出命令的方法。 许多主题已重点 squarely 通过 Lync Server 命令行管理程序使用 Windows PowerShell。 使用多个复杂配置和命令的能力有利于使用 Windows PowerShell 进行集中日志记录服务。 由于 lync server 命令行管理程序中的 Windows PowerShell 几乎普遍适用于 Lync Server 中的所有功能，因此仅讨论 Windows PowerShell 命令。

<div>


> [!NOTE]
> 如果您决定使用在命令行中可用的有限命令集，则可以通过键入来获取有关 CLSController.exe 的帮助 <CODE>ClsController.exe</CODE> 。 默认情况下， <STRONG>ClsController.exe</STRONG> 安装在目录 C:\Program Files\Microsoft Lync Server 2013 \ ClsAgent 中。



</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a>使用基本命令在 Windows PowerShell 中运行 Start-CsClsLogging

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  通过键入以下命令，通过集中式日志记录服务启动日志记录方案：
    
        Start-CsClsLogging -Scenario <name of scenario>
    
    例如，若要启动 **AlwaysOn** 方案，请键入：
    
        Start-CsClsLogging -Scenario AlwaysOn
    
    <div>
    

    > [!NOTE]
    > AlwaysOn 方案没有默认持续时间。 此方案将一直运行，直到您使用 <STRONG>search-csclslogging</STRONG> cmdlet 显式停止它。 有关详细信息，请参阅 <A href="https://technet.microsoft.com/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>。 对于所有其他方案，默认持续时间为4小时。

    
    </div>

3.  按 Enter 运行命令。
    
    <div>
    

    > [!NOTE]
    > 可能需要一小段时间 (30 到 60) 秒的时间，才能运行这些命令，并从部署中的计算机接收返回的状态。

    
    </div>
    
    ![运行 Search-csclslogging。](images/JJ687958.c5be7413-8cef-4de7-9712-944d20cc2fa4(OCS.15).jpg "运行 Search-csclslogging。")

4.  若要启动另一个方案，请使用 **search-csclslogging** cmdlet 和要运行的其他方案的名称，如下所示 (例如，方案 **身份验证**) ：
    
        Start-CsClsLogging -Scenario Authentication
    
    <div>
    

    > [!IMPORTANT]
    > 您可以随时在任何给定计算机上运行两个方案。 如果该命令在范围内是全局的，则部署中的所有计算机都将运行该方案或方案。 若要启动第三个方案，必须在要在其上运行新方案的计算机、池、站点或全局范围上停止日志记录。 如果已启动全局作用域，则可以在一个或多个计算机和池上停止对一个或两个方案的日志记录。 有关管理正在运行的方案的详细信息，请参阅<A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">在 Lync Server 2013 和 search-csclslogging 中使用集中日志记录服务的 "停止"</A> 。 <A href="https://technet.microsoft.com/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>

    
    </div>

</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a>使用高级命令在 Windows PowerShell 中运行 Start-CsClsLogging

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  其他参数可用于管理日志记录命令。 您可以使用– Duration 调整应用场景运行的时间长度。 您还可以定义计算机、计算机完全限定的域名列表 (Fqdn) 以逗号分隔，或者是池，即要对其运行日志记录的池的 Fqdn 的 Fqdn 列表（以逗号分隔）。
    
    为池 "pool01.contoso.net" 上的 *UserReplicator* 方案启动日志记录会话。 您还可以定义日志记录会话的持续时间为8小时。 为此，请键入：
    
        Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
    
    此方案的成功执行将返回结果，如下所示：
    
    ![运行 Search-csclslogging。](images/JJ687958.399f0c2e-c08c-40ab-b6c6-381dddc12fe9(OCS.15).jpg "运行 Search-csclslogging。")
    
    请注意，在此示例中，AlwaysOn 方案正在运行，并且 UserReplicator 方案正在运行。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的集中日志记录服务概述](lync-server-2013-overview-of-the-centralized-logging-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

