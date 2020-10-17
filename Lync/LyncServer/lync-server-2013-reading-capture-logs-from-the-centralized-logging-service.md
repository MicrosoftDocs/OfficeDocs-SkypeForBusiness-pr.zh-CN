---
title: Lync Server 2013：从集中日志记录服务读取捕获日志
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reading capture logs from the Centralized Logging Service
ms:assetid: c86ccf61-d86f-4ebd-b8d1-984a1b73005d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721879(v=OCS.15)
ms:contentKeyID: 49733813
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1058f48ede85067ac0aeefc3c8dab329bf042ef8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512029"
---
# <a name="reading-capture-logs-from-the-centralized-logging-service-in-lync-server-2013"></a>从 Lync Server 2013 中的集中日志记录服务读取捕获日志

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2016-12-28_

在运行搜索并拥有可用于跟踪报告的问题的文件后，可以充分利用集中日志记录服务的真正优势。 读取该文件有多种方法。 输出文件为标准文本格式，可以使用 Notepad.exe 或任何其他可以打开和读取文本文件的程序。 对于较大的文件和更复杂的问题，您可以使用 Snooper.exe 的工具，该工具旨在读取和分析集中日志记录服务中的日志记录输出。 Snooper 包含在可单独下载的 Lync Server 2013 调试工具中。 您可以在此处下载 Lync Server 2013 调试工具： [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257) 。 当您安装 Lync Server 2013 调试工具时，不会创建短时间的剪切和菜单项。 安装 Lync Server 2013 调试工具后，打开 Windows 资源管理器、命令行窗口或 Lync Server 命令行管理程序，然后转到目录 (默认位置) C： \\ Program Files \\ Microsoft Lync Server 2013 \\ 调试工具。 如果您使用的是命令行或 Lync Server 命令行管理程序，请双击 "Snooper.exe" 或 "键入 Snooper.exe"，然后按 ENTER。

<div>


> [!IMPORTANT]  
> 本主题的目的不是详细介绍和讨论疑难解答技术。 疑难解答及其相关过程是一个复杂的主题。 有关疑难解答基础知识和特定工作负荷故障排除的详细信息，请参阅 Microsoft Lync Server 2010 资源工具包书籍 <A href="https://go.microsoft.com/fwlink/p/?linkid=211003">https://go.microsoft.com/fwlink/p/?linkId=211003</A> 。 这些过程和过程仍适用于 Lync Server 2013。



</div>

Lync Server 2013 引入了更新版本的 Snooper.exe，其中包含一些新功能。 以下屏幕截图显示了 Office 通信服务器2007中的 Snooper.exe 版本。

![Office 通信2007版本的 Snooper.exe。](images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Office 通信2007版本的 Snooper.exe。")

以下屏幕截图显示了新版本的 Snooper.exe，其中包含在 Lync Server 2013 调试工具中。

![Lync Server 2013 版本的 Snooper.exe。](images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Lync Server 2013 版本的 Snooper.exe。")

以下屏幕快照显示了含有常用功能的工具栏。

![Snooper.exe 2013 工具栏。](images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Snooper.exe 2013 工具栏。")

此外，具有附加值的最新功能是流程图（呼叫流）视图。可以在“消息”**** 选项卡中选择消息流，然后单击“呼叫流”**** 按钮。当您继续浏览消息时，呼叫流视图将用新数据更新。

![Snooper.exe 2013 呼叫流示意图。](images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Snooper.exe 2013 呼叫流示意图。")

您可以悬停在视图上并获得消息的详细信息以及流、消息和服务器元素的内容。单击任意呼叫流箭头可转到“消息”视图中的相应消息。

![呼叫流图表消息详细信息。](images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "呼叫流图表消息详细信息。")

<div>

## <a name="to-open-a-log-file-in-snooper"></a>在 Snooper 中打开日志文件

1.  要使用 Snooper 并打开日志文件，您需要具有日志文件的读取权限。要使用 Snooper 并访问日志文件，您必须是基于 CsAdministrator 或 CsServerAdministrator 角色的访问控制 (RBAC) 安全组的成员，或者是包含这两个组之一的自定义 RBAC 角色。

2.  在安装了 Lync Server 调试工具 ( # A0) 后，请使用 Windows 资源管理器或命令行将目录更改为 Snooper.exe 的位置。 默认情况下，调试工具位于 C： \\ Program Files \\ Microsoft Lync Server 2013 \\ 调试工具中。 双击或运行 Snooper.exe。

3.  打开 Snooper 后，右键单击“文件”****，单击“打开文件”****，查找日志文件，在“打开”**** 对话框中选择文件，然后单击“打开”****。

4.  日志文件的“跟踪”**** 消息显示在“跟踪”**** 选项卡上。单击“消息”**** 选项卡可查看所收集跟踪的消息内容。

</div>

<div>

## <a name="to-display-a-call-flow-diagram"></a>显示呼叫流程图

1.  要使用 Snooper 并打开日志文件，您需要具有日志文件的读取权限。要使用 Snooper 并访问日志文件，您需要是基于 CsAdministrator 或 CsServerAdministrator 角色的访问控制 (RBAC) 安全组的成员，或者是包含这两个组之一的自定义 RBAC 角色。

2.  打开日志文件并单击“消息”**** 选项卡，在消息视图中选择对话或在“跟踪”**** 选项卡上选择跟踪组件。

3.  单击“呼叫流”****。
    
    <div>
    

    > [!NOTE]  
    > 如果单击不属于呼叫流的消息或跟踪，将不会显示流程图并在 Snooper 的底部显示一条状态消息，指示“此消息不符合呼叫流”。选择另一条属于呼叫流的消息或跟踪，将显示呼叫流。

    
    </div>

4.  在消息或跟踪行间移动，并注意呼叫流程图是否更新或更改为显示新图。

5.  在元素上悬停可获得有关呼叫消息、终结点和其他组件的信息。

</div>

</div>

<span> </span>

</div>

</div>

</div>

