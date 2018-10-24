---
title: 集中日志记录服务的概述
TOCTitle: 集中日志记录服务的概述
ms:assetid: 975718a0-f3e3-404d-9453-6224e73bfdd0
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688145(v=OCS.15)
ms:contentKeyID: 49888523
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 集中日志记录服务的概述

 

_**上一次修改主题：** 2016-12-08_

集中日志记录服务专为在广泛的范围或有限的范围控制数据收集而设计。您可以同时从部署中的所有服务器收集数据、定义要跟踪的特定元素、设置跟踪标志并返回单台计算机中的搜索结果或返回所有服务器中的所有数据的聚合。集中日志记录服务在部署中的所有服务器上运行。集中日志记录服务包含下列代理和服务：

  - *集中日志记录服务代理*   ClsAgent.exe 是一个服务可执行文件，它与控制器进行通信并接收由管理员发出的命令。此代理在每台 Lync Server 计算机上作为一项服务运行。当此代理收到一条命令时，它将执行此命令，将消息发送给定义的组件以进行跟踪，然后将跟踪日志写入到磁盘中。在收到相应的请求时，此代理还将读取其计算机的跟踪日志并将跟踪数据发送回控制器。ClsAgent 在下列端口上侦听命令：**TCP 50001**、**TCP 50002** 和 **TCP 50003**。

  - *集中日志记录服务控制器*   ClsControllerLib.dll 是适用于 Lync Server 命令行管理程序和 ClsController.exe 的命令执行引擎。CLSControllerLib.dll 向 ClsAgent 发送 Start、Stop、Flush 和 Search 命令。在发送搜索命令时，生成的日志将返回到 ClsControllerLib.dll 并进行聚合。控制器负责将命令发送给代理、接收这些命令的状态并在搜索日志文件数据从搜索范围中任何计算机上的所有代理返回时管理该数据以及将日志数据并入一个有用的已排序输出集。下列主题中的信息重点说明如何使用 Lync Server 命令行管理程序。ClsController.exe 仅对 Lync Server 命令行管理程序中提供的部分功能有效。可通过在默认目录 C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\ClsAgent 中键入 `ClsController` 在命令行中显示有关 ClsController.exe 的帮助

**ClsController 与 ClsAgent 的通信**

![CLSController 和 CLSAgent 之间的关系。](images/JJ688145.68c90811-5cf9-4a84-95b7-ea9ffc61eac4(OCS.15).jpg "CLSController 和 CLSAgent 之间的关系。")

可使用 Windows Server 命令行接口或使用 Lync Server 命令行管理程序发出命令。这些命令将在您登录的计算机上执行，并将本地发送到 ClsAgent 或发送到部署中的其他计算机和池。

ClsAgent 维护其在本地计算机上具有的所有 .CACHE 文件的索引文件。ClsAgent 将分配这些文件，使其均匀分布在由选项 CacheFileLocalFolders 定义的卷上，并且绝不会占用每个卷的 80% 以上的容量（即，可使用 **Set-CsClsConfiguration** cmdlet 配置本地缓存位置和百分比）。ClsAgent 还负责从本地计算机中清除旧的缓存事件跟踪日志 (.etl) 文件。两周之后（即，可使用 **Set-CsClsConfiguration** cmdlet 配置时间范围时），会将这些文件复制到一个文件共享中并从本地计算机中删除它们。有关详细信息，请参阅 [Set-CsClsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClsConfiguration)。在收到一个搜索请求时，搜索条件将用于选择一组缓存的 .etl 文件以便根据代理所维护的索引中的值来执行搜索。

> [!NOTE]  
> 从本地计算机移至文件共享中的文件可通过 ClsAgent 进行搜索。一旦 ClsAgent 将这些文件移至文件共享中，ClsAgent 将不会维护文件的清楚和删除。您应定义一个管理任务来监控文件共享中的文件大小，并删除这些文件或对其进行存档。



可使用多种工具读取和分析生成的日志文件，其中包括 **Snooper.exe** 以及任何可读取文本文件的工具（例如 **Notepad.exe**）。Snooper.exe 是 Lync Server 2013 Debug Tools 的一部分并作为 Web 下载提供。

与 OCSLogger 类似，集中日志记录服务具有多个要跟踪的组件，并提供了用于选择标志（例如，TF\_COMPONENT 和 TF\_DIAG）的选项。集中日志记录服务还保留了 OCSLogger 的日志记录级别选项。

对命令行形式的 ClsController 使用 Windows PowerShell 的最大好处是，可使用面向问题区域、自定义标志和日志记录级别的选定提供程序配置和定义新方案。对 ClsController 可用的方案仅为针对可执行文件定义的方案。

在早期版本中，提供了 OCSLogger.exe 以使管理员和支持人员能够从部署中的计算机中收集跟踪文件。尽管 OCSLogger 具有的优点不少，但它也有一个缺点。在给定时间内，您只能在一台计算机上收集日志。虽然可通过使用 OCSLogger 的独立副本来登录多台计算机，但最终将获得多个日志且无法轻松聚合结果。

当用户请求一个日志搜索时，ClsController 将确定将请求发送到哪些计算机（即，基于选定方案）。它还确定是否需要将搜索发送到已保存的 .etl 文件所在的文件共享。当搜索结果返回到 ClsController 时，控制器会将结果合并到一个呈现给用户的按时间排序的结果集中。用户可以将搜索结果保存到其本地计算机中以供进一步分析。

在启动日志记录会话时，您指定与您尝试解决的问题相关的方案。可以随时运行两个方案，其中一个方案应为 AlwaysOn 方案。顾名思义，此方案应始终在部署中运行，并收集有关所有计算机、池和组件的信息。

> [!IMPORTANT]
> 默认情况下，AlwaysOn 方案在部署中不会运行。您必须显式启动此方案。一旦启动此方案，它就将继续运行直到被显式停止，并且在重新启动计算机的过程中持续保持运行状态。有关启动和停止方案的详细信息，请参阅<a href="lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md">使用启动集中日志服务以捕获日志</a>和<a href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">对集中日志记录服务使用 Stop 命令</a>。


在出现问题时，启动与所报告的问题相关的另一个方案。重现该问题并停止针对该方案的日志记录。开始与所报告的问题相关的日志搜索。日志的聚合收集会生成一个日志文件，其中包含站点或全局范围部署中的所有计算机中的跟踪消息。如果搜索返回的数据多于可进行可行性分析的数据（通常称为信噪比，其中噪音过高），则可使用范围更小的参数运行另一个搜索。此时，您可以关注显示的模式并可帮助您准确了解问题。最后，在执行一组优化搜索后，您可以找到与该问题相关的数据并指出根本原因。

> [!TIP]  
> 在面对 Lync Server 中的问题方案时，您首先问自己“我已了解与该问题相关的哪些信息？”如果量化问题边界，则可以消除 Lync Server 中的大部分操作实体。<br />
考虑以下示例方案：您知道用户在查找联系人时未获得当前结果。在媒体组件、企业语音、会议和许多其他组件中查找问题是毫无意义的。您不知道出现问题的实际位置：是客户端上还是服务器端？联系人通过用户复制程序从 Active Directory 中收集，并通过通讯簿服务器 (ABServer) 传送到客户端。ABServer 从 RTC 数据库获取其更新（用户复制程序将更新写入该数据库），并将其收集到一个通讯簿文件中（默认情况下为 1:30 AM）。Lync Server 客户端根据随机计划检索新的通讯簿。由于您知道此过程的工作方式，因此您可以减少对与由用户复制程序从 Active Directory 中收集的数据相关的问题的可能原因的搜索，ABServer 不检索和创建通讯簿文件或客户端不下载通讯簿文件。
