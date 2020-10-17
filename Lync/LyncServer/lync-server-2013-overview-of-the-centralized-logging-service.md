---
title: Lync Server 2013：集中日志记录服务概述
description: Lync Server 2013：集中日志记录服务概述。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Centralized Logging Service
ms:assetid: 975718a0-f3e3-404d-9453-6224e73bfdd0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688145(v=OCS.15)
ms:contentKeyID: 49733746
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a357063ff80611789981f5e98a69899ea5cd27a9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560908"
---
# <a name="overview-of-the-centralized-logging-service-in-lync-server-2013"></a>Lync Server 2013 中的集中日志记录服务概述

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-22_

集中日志记录服务旨在提供一种对数据的受控制集合的方法，其中包含广泛或较窄的范围。 您可以从部署中的所有服务器同时收集数据，定义要跟踪的特定元素，设置跟踪标记，并从单个计算机或从所有服务器返回的所有数据的聚合中返回搜索结果。 集中日志记录服务在部署中的所有服务器上运行。 集中日志记录服务的体系结构由以下代理和服务组成：

  - *集中日志记录服务代理*    ClsAgent.exe 是与控制器进行通信并接收由管理员发出的命令的服务可执行文件。 代理作为服务在每台 Lync Server 计算机上运行。 当代理收到命令时，它执行命令，将邮件发送到已定义的跟踪组件，并将跟踪日志写入磁盘。 它还会读取其计算机的跟踪日志，并在请求时将跟踪数据发送回控制器。 ClsAgent 侦听以下端口上的命令： **tcp 50001**、 **Tcp 50002**和 **tcp 50003**。

  - *集中日志记录服务控制器*    ClsControllerLib.dll 是 Lync Server 命令行管理程序和 ClsController.exe 的命令执行引擎。 CLSControllerLib.dll 将 Start、Stop、Flush 和 Search 命令发送到 ClsAgent。 发送搜索命令时，生成的日志将返回到 ClsControllerLib.dll 并进行聚合。 控制器负责向代理发送命令，接收这些命令的状态，并在从搜索范围内的任何计算机上的所有代理返回时管理搜索日志文件数据，并将日志数据聚合到有意义的已排序输出集。 以下主题中的信息重点介绍了如何使用 Lync Server 命令行管理程序。 ClsController.exe 仅限于 Lync Server 命令行管理程序中提供的功能和功能的子集。 在命令行中，可通过 `ClsController` 在 "默认目录 C：程序文件" 中键入 " \\ \\ \\ Microsoft Lync Server 2013 \\ ClsAgent" 来获取有关 ClsController.exe 的帮助。

**ClsController 到 ClsAgent 的通信**

![CLSController 和 CLSAgent 之间的关系。](images/JJ688145.68c90811-5cf9-4a84-95b7-ea9ffc61eac4(OCS.15).jpg "CLSController 和 CLSAgent 之间的关系。")

您可以使用 Windows Server 命令行界面或 Lync Server 命令行管理程序发出命令。 命令在您登录到的计算机上执行，并将其发送到您的部署中的 ClsAgent 本地或其他计算机和池。

ClsAgent 维护全部的索引文件。在本地计算机上缓存文件。 ClsAgent 将其分配给它们，以便在选项 CacheFileLocalFolders 定义的卷上平均分布，而不使用每个卷的 80% (也就是说，本地缓存位置和百分比可以使用 **new-csclsconfiguration** cmdlet) 进行配置。 ClsAgent 还负责老化旧的缓存事件跟踪日志 ( .etl) 本地计算机中的文件。 两周后 (也就是说，使用 **new-csclsconfiguration** cmdlet 可配置时间范围，) 将这些文件复制到文件共享中并从本地计算机中删除。 有关详细信息，请参阅 [new-csclsconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClsConfiguration)。 收到搜索请求时，搜索条件将用于选择一组缓存的 .etl 文件，以根据代理维护的索引中的值执行搜索。

<div>


> [!NOTE]  
> 从本地计算机移动到文件共享的文件可以通过 ClsAgent 进行搜索。 一旦 ClsAgent 将文件移动到文件共享，ClsAgent 将不会维护文件的老化和删除。 应定义管理任务以监视文件共享中的文件大小，并将其删除或存档。



</div>

可以使用各种工具读取和分析生成的日志文件，其中包括 **Snooper.exe** 和可读取文本文件的任何工具，如 **Notepad.exe**。 Snooper.exe 是 Lync Server 2013 调试工具的一部分，可从下载 Web [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257) 。

与 OCSLogger 一样，集中日志记录服务有多个要跟踪的组件，并提供了选择 flags 的选项，如 TF \_ COMPONENT 和 TF settings \_ 。 集中日志记录服务还保留 OCSLogger 的日志记录级别选项。

在命令行 ClsController 中使用 Lync Server 命令行管理程序的最重要的优势在于，您可以使用针对问题空间、自定义标记和日志记录级别的选定提供程序来配置和定义新方案。 可用于 ClsController 的方案仅限于为可执行文件定义的方案。

在以前的版本中，提供了 OCSLogger.exe，使管理员和支持人员能够从部署中的计算机收集跟踪文件。 OCSLogger 对于其所有优势而言都存在缺陷。 在给定时间，您只能在一台计算机上收集日志。 您可以通过使用 OCSLogger 的单独副本登录到多台计算机，但最终要使用多个日志，而不是聚合结果的简单方法。

当用户请求日志搜索时，ClsController 将根据) 选择的方案来确定将请求发送到 (的计算机。 它还确定是否需要将搜索发送到保存的 .etl 文件所在的文件共享。 当搜索结果返回到 ClsController 时，该控制器会将结果合并到一个显示给用户的单个按时间排序的结果集。 用户可以将搜索结果保存到本地计算机，以供进一步分析。

启动日志记录会话时，将指定与您尝试解决的问题相关的方案。 您可以随时运行两个方案。 这两种方案中的一种应是 AlwaysOn 方案。 顾名思义，它应始终在您的部署中运行，并收集所有计算机、池和组件的信息。

<div>


> [!IMPORTANT]  
> 默认情况下，AlwaysOn 方案未在您的部署中运行。 您必须显式启动方案。 启动后，它将继续运行，直到显式停止，并且运行状态将在计算机重新启动后保持。 有关启动和停止方案的详细信息，请参阅 <A href="lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md">使用 Start For 集中日志记录服务捕获 Lync server 2013 中的日志</A> 和 <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">在 lync Server 2013 中使用集中日志记录服务的停止</A>。



</div>

出现问题时，请启动与报告的问题相关的第二个方案。 重现该问题，并停止第二个方案的日志记录。 相对于报告的问题开始进行日志搜索。 日志的聚合集合将生成一个日志文件，其中包含来自网站中的所有计算机或部署全局范围的跟踪消息。 如果搜索返回的数据多于您可以 feasibly 分析 (通常称为噪声率的比率，在这种情况下，噪音过高) ，则可以使用较窄的参数运行另一个搜索。 此时，您可以开始注意显示的模式，并可帮助您更清楚地关注问题。 最终，在执行几个改进的搜索之后，您可以找到与该问题相关的数据，并确定根本原因。

<div>


> [!TIP]  
> 在 Lync Server 中出现问题的情况下，请首先询问自己 "我已经知道问题是什么？"。 如果您量化问题边界，则可以在 Lync Server 中消除大部分操作实体的组成部分。<BR>考虑一个您知道用户在查找联系人时没有获取当前结果的示例方案。 在媒体组件、企业语音、会议和许多其他组件中找不到问题。 您可能不知道问题实际上是什么：在客户端上，或者是服务器端问题？ 联系人由用户复制程序从 Active Directory 中收集，并通过通讯簿服务器 (ABServer) 的方式传递到客户端。 ABServer 从 RTC 数据库中获取其更新 (其中，用户复制程序将其写入) 并将其收集到通讯簿文件中，默认– 1:30 AM。 Lync Server 客户端按随机计划检索新的通讯簿。 由于您知道该过程的工作方式，因此您可以将您的搜索范围降低到用户复制程序从 Active Directory 收集的数据相关问题的潜在原因，ABServer 不检索和创建通讯簿文件，或者客户端不会下载通讯簿文件。



</div>

</div>

<span> </span>

</div>

</div>

</div>

