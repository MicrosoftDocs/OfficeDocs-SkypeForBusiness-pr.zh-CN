---
title: 'Lync Server 2013: 集中式日志记录服务概述'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of the Centralized Logging Service
ms:assetid: 975718a0-f3e3-404d-9453-6224e73bfdd0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688145(v=OCS.15)
ms:contentKeyID: 49733746
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 647e6b1e5797b3936dc1fef6023c85ce4baf68b7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825441"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-centralized-logging-service-in-lync-server-2013"></a>Lync Server 2013 中的集中式日志记录服务概述

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-22_

集中式日志记录服务旨在为数据的受控制集合提供一种方法, 范围较广, 范围较窄。 你可以同时从部署中的所有服务器收集数据, 定义要跟踪的特定元素, 设置跟踪标记并从单个计算机或所有服务器的所有数据的聚合中返回搜索结果。 集中式日志记录服务在部署中的所有服务器上运行。 集中式日志记录服务的体系结构由以下代理和服务组成:

  - *集中式日志记录服务代理*   ClsAgent 是与控制器通信并接收由管理员发出的命令的服务可执行文件。 代理以服务的形式在每台 Lync 服务器计算机上运行。 当代理收到命令时, 它执行命令、将消息发送到已定义的跟踪组件, 并将跟踪日志写入磁盘。 它还会读取其计算机的跟踪日志, 并在请求时将跟踪数据发送回控制器。 ClsAgent 侦听以下端口上的命令: **tcp 50001**、 **Tcp 50002**和**tcp 50003**。

  - *集中式日志记录服务控制器*   ClsControllerLib 是 Lync Server Management Shell 和 ClsController 的命令执行引擎。 CLSControllerLib 将启动、停止、刷新和搜索命令发送到 ClsAgent。 发送搜索命令时, 生成的日志将返回到 ClsControllerLib 并进行聚合。 控制器负责向代理发送命令, 接收这些命令的状态, 并管理从搜索范围内任何计算机上的所有代理返回的搜索日志文件数据, 并将日志数据聚合到有意义的排序中输出设置。 以下主题中的信息重点介绍如何使用 Lync Server 命令行管理程序。 ClsController 仅限于 Lync Server Management Shell 中可用的功能和功能的子集。 在命令行中, 通过在 "默认`ClsController`目录 C:\\程序文件\\" 中键入 "Microsoft Lync Server 2013\\\\ClsAgent" 常用文件, 可在命令行中使用 ClsController 帮助。

**ClsController 与 ClsAgent 的通信**

![CLSController 和 CLSAgent 之间的关系。](images/JJ688145.68c90811-5cf9-4a84-95b7-ea9ffc61eac4(OCS.15).jpg "CLSController 和 CLSAgent 之间的关系。")

使用 Windows Server 命令行界面发出命令, 或使用 Lync Server Management Shell 发出命令。 这些命令将在您登录的计算机上执行，并将本地发送到 ClsAgent 或发送到部署中的其他计算机和池。

ClsAgent 维护其在本地计算机上具有的所有 .CACHE 文件的索引文件。 ClsAgent 将分配这些文件，使其均匀分布在由选项 CacheFileLocalFolders 定义的卷上，并且绝不会占用每个卷的 80% 以上的容量（即，可使用 **Set-CsClsConfiguration** cmdlet 配置本地缓存位置和百分比）。 ClsAgent 还负责从本地计算机中清除旧的缓存事件跟踪日志 (.etl) 文件。 两周之后（即，可使用 **Set-CsClsConfiguration** cmdlet 配置时间范围时），会将这些文件复制到一个文件共享中并从本地计算机中删除它们。 有关详细信息，请参阅 [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClsConfiguration)。 在收到一个搜索请求时，搜索条件将用于选择一组缓存的 .etl 文件以便根据代理所维护的索引中的值来执行搜索。

<div>


> [!NOTE]  
> 从本地计算机移至文件共享中的文件可通过 ClsAgent 进行搜索。一旦 ClsAgent 将这些文件移至文件共享中，ClsAgent 将不会维护文件的清楚和删除。您应定义一个管理任务来监控文件共享中的文件大小，并删除这些文件或对其进行存档。



</div>

可使用多种工具读取和分析生成的日志文件，其中包括 **Snooper.exe** 以及任何可读取文本文件的工具（例如 **Notepad.exe**）。 Snooper 是 Lync Server 2013 调试工具的一部分, 可从[http://go.microsoft.com/fwlink/?LinkId=285257](http://go.microsoft.com/fwlink/?linkid=285257)下载 Web。

与 OCSLogger 一样, 集中式日志记录服务有多个要跟踪的组件, 并提供选择标志的选项,\_如 tf 组件\_和 tf 诊断。 集中式日志记录服务还保留 OCSLogger 的日志记录级别选项。

在命令行 ClsController 上使用 Lync Server 管理外壳的最重要的好处是, 你可以使用针对问题空间、自定义标记和日志记录级别的选定提供程序配置和定义新方案。 对 ClsController 可用的方案仅为针对可执行文件定义的方案。

在早期版本中，提供了 OCSLogger.exe 以使管理员和支持人员能够从部署中的计算机中收集跟踪文件。尽管 OCSLogger 具有的优点不少，但它也有一个缺点。在给定时间内，您只能在一台计算机上收集日志。虽然可通过使用 OCSLogger 的独立副本来登录多台计算机，但最终将获得多个日志且无法轻松聚合结果。

当用户请求一个日志搜索时，ClsController 将确定将请求发送到哪些计算机（即，基于选定方案）。它还确定是否需要将搜索发送到已保存的 .etl 文件所在的文件共享。当搜索结果返回到 ClsController 时，控制器会将结果合并到一个呈现给用户的按时间排序的结果集中。用户可以将搜索结果保存到其本地计算机中以供进一步分析。

在启动日志记录会话时，您指定与您尝试解决的问题相关的方案。可以随时运行两个方案，其中一个方案应为 AlwaysOn 方案。顾名思义，此方案应始终在部署中运行，并收集有关所有计算机、池和组件的信息。

<div>


> [!IMPORTANT]  
> 默认情况下，AlwaysOn 方案在部署中不会运行。 您必须显式启动此方案。 一旦启动此方案，它就将继续运行直到被显式停止，并且在重新启动计算机的过程中持续保持运行状态。 有关启动和停止方案的详细信息, 请参阅<A href="lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md">使用集中日志记录服务捕获 Lync server 2013 中的日志</A>和<A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">在 lync Server 2013 中使用集中式日志记录服务的停止</A>。



</div>

在出现问题时，启动与所报告的问题相关的另一个方案。重现该问题并停止针对该方案的日志记录。开始与所报告的问题相关的日志搜索。日志的聚合收集会生成一个日志文件，其中包含站点或全局范围部署中的所有计算机中的跟踪消息。如果搜索返回的数据多于可进行可行性分析的数据（通常称为信噪比，其中噪音过高），则可使用范围更小的参数运行另一个搜索。此时，您可以关注显示的模式并可帮助您准确了解问题。最后，在执行一组优化搜索后，您可以找到与该问题相关的数据并指出根本原因。

<div>


> [!TIP]  
> 如果在 Lync Server 中出现问题方案, 请首先询问自己 "我已了解有关该问题的哪些信息？" 如果你量化问题的边界, 则可以在 Lync Server 中消除大部分运营实体的一部分。<BR>考虑以下示例方案：您知道用户在查找联系人时未获得当前结果。 在媒体组件、企业语音、会议和许多其他组件中, 不存在任何问题。 您不知道出现问题的实际位置：是客户端上还是服务器端？ 联系人通过通讯簿服务器 (ABServer) 通过用户复制程序从 Active Directory 收集并传递到客户端。 ABServer 从 RTC 数据库获取其更新（用户复制程序将更新写入该数据库），并将其收集到一个通讯簿文件中（默认情况下为 1:30 AM）。 Lync 服务器客户按随机计划检索新的通讯簿。 由于你知道进程的工作方式, 因此你可以将搜索范围减少为与用户复制程序从 Active Directory 收集的数据相关的问题, ABServer 不会检索和创建通讯簿文件, 或者客户不下载通讯簿文件。



</div>

</div>

<span> </span>

</div>

</div>

</div>

