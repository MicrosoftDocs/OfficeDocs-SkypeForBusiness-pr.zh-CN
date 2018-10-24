---
title: 使用启动集中日志服务以捕获日志
TOCTitle: 使用启动集中日志服务以捕获日志
ms:assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ687958(v=OCS.15)
ms:contentKeyID: 49888287
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 使用启动集中日志服务以捕获日志

 

_**上一次修改主题：** 2013-02-21_

若要使用集中日志记录服务捕获跟踪日志，您需要发出一条命令以开始在一个或多个计算机和池上进行日志记录。您还需要发出参数来定义在哪些计算机或池上捕获、运行哪些方案（例如 AlwaysOn、另一个预定义方案或已创建的方案）、跟踪哪些 Lync Server 组件（例如 S4、SipStack）。

若要捕获正确的信息，您需要确保使用正确的方案收集与问题相关的信息。在集中日志记录服务中，方案是指基于服务器组件集合、日志记录级别和标志来打开日志记录，这比基于每台服务器定义这些元素更加高效和有用。您只需定义一个方案并指定运行该方案，该方案即会在基础架构范围内的所有服务器和池中一致地运行。

默认方案称为 **AlwaysOn**。顾名思义，AlwaysOn 的目的就是持续不断地运行方案。AlwaysOn 方案为许多最常用的服务器组件收集信息级别信息（请注意，除“信息”消息外，“信息”日志记录级别还包括致命错误、错误和警告）。AlwaysOn 在问题发生之前、发生过程中和发生之后收集信息。这与以前的日志记录工具（如 OCSLogger）的典型行为截然不同。您在问题发生之后才运行 OCSLogger，这使得故障排除工作更加困难，因为获得的数据是被动而非主动的。如果 AlwaysOn 不包含您正在寻找的能够指出问题组件和纠正措施的信息（考虑到 AlwaysOn 中提供程序的广度和深度，不太可能会发生这种情况），它会指出一个合理的信息水平，以确定您需要执行的其他操作，例如，创建新方案，收集其他信息，运行不同搜索来收集更集中的详细信息等等。

集中日志记录服务提供两种发出命令的方式。有许多主题专门讨论了如何通过 Lync Server 命令行管理程序使用 Windows PowerShell。能够使用一些复杂配置和命令的能力有利于 Windows PowerShell 使用集中日志记录服务。因为通过 Lync Server 命令行管理程序使用 Windows PowerShell 对于 Lync Server 中的所有函数而言极为普遍，所以我们只讨论 Windows PowerShell 命令。

> [!NOTE]  
> 如果您决定使用命令行提供的一组有限命令，可以通过键入 <code>ClsController.exe</code> 使用 CLSController.exe 获得帮助。默认情况下，<strong>ClsController.exe</strong> 安装在目录 C:\Program Files\Microsoft Lync Server 2013\ClsAgent中。


## 使用基本命令通过 Windows PowerShell 运行 Start-CsClsLogging

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  键入以下命令通过集中日志记录服务启动日志记录方案：
    
        Start-CsClsLogging -Scenario <name of scenario>
    
    例如，要启动 **AlwaysOn** 方案，可键入：
    
        Start-CsClsLogging -Scenario AlwaysOn
    
    > [!NOTE]
    > AlwaysOn 方案没有默认持续时间。此方案将一直运行到您通过 <strong>Stop-CsClsLogging</strong> cmdlet 明确停止它为止。有关详细信息，请参阅 <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Stop-CsClsLogging">Stop-CsClsLogging</a>。对于所有其他方案，默认持续时间为 4 小时。


3.  按 Enter 运行命令。
    
    > [!NOTE]
    > 可能需要一小段时间（30 到 60 秒）命令才运行完毕，并接收从您的部署中的计算机返回的状态。
    
    ![运行 Start-CsClsLogging。](images/JJ687958.c5be7413-8cef-4de7-9712-944d20cc2fa4(OCS.15).jpg "运行 Start-CsClsLogging。")

4.  要启动另一个方案，请使用 **Start-CsClsLogging** cmdlet 并提供要按如下方式运行的附加方案的名称（例如 **Authentication**）：
    
        Start-CsClsLogging -Scenario Authentication
    
    > [!IMPORTANT]
    > 在任意时间可以在任何给定计算机上运行总共两个方案。如果命令是全局范围的，则部署中的所有计算机将运行方案。要启动第三个方案，必须在您要运行新方案的计算机、池、站点或全局范围上停止日志记录。如果已启动全局范围，则可以在一个或多个计算机和池上停止一种方案或同时停止两种方案的日志记录。有关管理哪些方案正在运行的详细信息，请参阅<a href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">对集中日志记录服务使用 Stop 命令</a>和 <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Stop-CsClsLogging">Stop-CsClsLogging</a>。


## 使用高级命令通过 Windows PowerShell 运行 Start-CsClsLogging

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  也可以使用其他参数来管理日志记录命令。可以使用 –Duration 调整方案运行的时间长度。还可以定义 –Computers（逗号分隔的计算机完全限定域名 (FQDN) 的列表），或 –Pools（要对其运行日志记录的池的逗号分隔的 FQDN 列表）。
    
    您为池“pool01.contoso.net”上的 *UserReplicator* 方案启动了日志记录会话。您还定义日志记录会话持续时间为 8 小时。为此，请键入：
    
        Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
    
    此方案成功执行后将返回类似如下的结果：
    
    ![运行 Start-CsClsLogging。](images/JJ687958.399f0c2e-c08c-40ab-b6c6-381dddc12fe9(OCS.15).jpg "运行 Start-CsClsLogging。")
    
    注意，在此示例中，正在运行的方案是 AlwaysOn 和 UserReplicator。

## 另请参阅

#### 概念

[集中日志记录服务的概述](lync-server-2013-overview-of-the-centralized-logging-service.md)

