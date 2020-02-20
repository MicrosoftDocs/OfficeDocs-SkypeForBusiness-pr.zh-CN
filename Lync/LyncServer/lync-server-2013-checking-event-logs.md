---
title: Lync Server 2013：检查事件日志
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Checking event logs
ms:assetid: 5500720d-c628-4dbd-84bc-a5becc39b99c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720914(v=OCS.15)
ms:contentKeyID: 63969602
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41c49839b01b531c1cd4c9a5eb4cff5fb6a155f4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145961"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="checking-event-logs-in-lync-server-2013"></a>在 Lync Server 2013 中检查事件日志

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-08-06_

您可以使用[Windows 事件查看器](https://go.microsoft.com/fwlink/p/?linkid=314067)查看事件日志，并获取有关服务故障的信息、AD DS 中的复制错误以及有关系统资源（如虚拟内存和磁盘空间）的警告。 事件查看器包含在 Windows Server 2008 和2012中。

在 Lync Server 2013 日志记录工具中，当结束调试会话时，请单击 "**分析日志文件**" 以使用 snooper.exe 工具查看日志文件。

事件查看器维护有关计算机上的应用程序、安全性和系统事件的日志。 Lync Server 2013 和 Windows 将警告和错误条件都报告给事件日志。 因此，请每天查看事件日志。

使用事件查看器执行以下操作：

  - 查看和管理事件日志。

  - 获取有关必须解决的硬件、软件和系统问题的信息。

  - 确定需要后续操作的趋势。

在 Windows Server 操作系统上运行 Lync Server 的服务器记录以下四种类型的日志中的事件：

  - **应用**程序日志应用程序日志包含由应用程序或程序记录的事件。    开发人员确定要记录的事件。 例如，数据库程序可能会在应用程序日志中记录文件错误。 大多数 Lync Server 2013 相关事件都显示在应用程序日志中。

  - **安全**日志除了与资源使用相关的事件（如创建、打开或删除文件或其他对象）以外，安全日志还记录诸如有效和无效的登录尝试等事件。    例如，如果启用了登录审核，则登录系统的尝试将记录在安全日志中。

  - **系统日志**   系统日志包含由 Windows 系统组件记录的事件。 例如，在启动过程中要加载的驱动程序或其他系统组件的故障将记录在系统日志中。 系统组件记录的事件类型是由服务器预先确定的。

  - **Lync Server 2013**   日志记录工具记录与身份验证、连接和用户操作相关的重要事件。 启用诊断日志记录后，可以在事件查看器中查看日志条目。

<div>


> [!NOTE]  
> 我们建议您不要使用最大日志记录设置，除非您被 Microsoft 客户支持服务的要求这样做。 最大日志消耗大量资源，并且可以提供多个 "误报"，即仅在最大日志记录中记录的错误，而不是问题的原因。 此外，我们还建议您不要永久启用诊断日志记录。 仅在进行故障排除时使用它。



</div>

在每个事件查看器日志中，Lync Server 2013 记录信息、警告和错误事件。 请密切监视这些日志，以跟踪在 Lync Server 2013 服务器上正在执行的事务类型。 应定期存档日志或使用自动滚动更新以避免空间不足。 由于日志文件可能占用有限的空间量，增加日志大小（例如，到 50 MB）并将其设置为 "覆盖"，以便 Lync Server 2013 服务器可以继续写入新事件。

您还可以通过使用以下工具和技术来自动执行事件日志管理：

  - System Center Operations Manager 监视 Lync Server 2013 服务器的运行状况和使用情况。 适用于 Operations Manager 的 Lync Server 2013 管理包通过为运行 Lync Server 2013 的服务器提供专用监视扩展了 Operations Manager。

  - 适用于 Operations Manager 的 Lync Server 2013 管理包监视 Lync Server 2013 的标准版和企业版。 此版本还包含以前是单独的管理包的体验质量（QoE）管理包。

受监视的类型为 QoE 的事件日志条目、性能计数器和监控状态。 此版本的管理包仅监视 Lync Server 2013 和2010，不能用于监视 Office 通信服务器2007。

管理包提供以下功能：

  - 表明服务影响事件的警报

  - 指示配置和其他未通过服务影响的问题的警报

  - Lync Server 服务的状态监视

  - 产品知识：确定问题的原因和解决方法

有关 Lync Server 2013 管理包的详细信息，请参阅[使用 System Center Operations Manager 监视 Lync Server 2013](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)。

**事件 Comb**   事件 Comb 工具将多台计算机的事件日志中的特定事件收集到一个中心位置。 它允许仅报告事件 Id 或它指定的事件源。 有关事件 Comb 的详细信息，请参阅[帐户锁定和管理工具](https://go.microsoft.com/fwlink/?linkid=35607)网站。

****   Windows Server 2012 中的事件触发器可以在 windows 事件查看器中 "将任务附加到此事件" —管理员可以运行某个程序、发送一封电子邮件或显示屏幕上的邮件。 有关此功能的详细信息，请参阅 Windows Server 2008 R2 主题[运行任务以响应给定事件](https://technet.microsoft.com/library/cc748900.aspx)。 您还可以使用命令行工具（如 "Eventtrigger"）来创建和查询事件日志，并将程序与特定的已记录事件相关联。 通过使用 Eventtriggers，您可以创建在特定事件发生时运行程序的事件触发器。

<div>

## <a name="see-also"></a>另请参阅


[Windows 事件查看器](https://go.microsoft.com/fwlink/p/?linkid=314067)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

