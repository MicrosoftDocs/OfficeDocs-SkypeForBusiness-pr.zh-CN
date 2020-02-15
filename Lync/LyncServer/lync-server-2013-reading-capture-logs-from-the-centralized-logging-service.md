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
ms.openlocfilehash: d5abf7b2f6962dbf38f90f52ff82c54b035d9aa0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050174"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reading-capture-logs-from-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="9eb8d-102">从 Lync Server 2013 中的集中日志记录服务读取捕获日志</span><span class="sxs-lookup"><span data-stu-id="9eb8d-102">Reading capture logs from the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9eb8d-103">_**上次修改的主题：** 2016-12-28_</span><span class="sxs-lookup"><span data-stu-id="9eb8d-103">_**Topic Last Modified:** 2016-12-28_</span></span>

<span data-ttu-id="9eb8d-104">在运行搜索并拥有可用于跟踪报告的问题的文件后，可以充分利用集中日志记录服务的真正优势。</span><span class="sxs-lookup"><span data-stu-id="9eb8d-104">You realize the real benefit of the Centralized Logging Service after you run the search and you have a file that you can use to track down a reported problem.</span></span> <span data-ttu-id="9eb8d-105">读取该文件有多种方法。</span><span class="sxs-lookup"><span data-stu-id="9eb8d-105">There are a number of ways that you can read the file.</span></span> <span data-ttu-id="9eb8d-106">输出文件为标准文本格式，可以使用 Notepad.exe 或任何其他可以打开和读取文本文件的程序。</span><span class="sxs-lookup"><span data-stu-id="9eb8d-106">The output file is in a standard text format and you can use Notepad.exe or any other programs that will allow you to open and read a text file.</span></span> <span data-ttu-id="9eb8d-107">对于较大的文件和更复杂的问题，您可以使用 Snooper.exe 的工具，该工具旨在读取和分析集中日志记录服务的日志记录输出。</span><span class="sxs-lookup"><span data-stu-id="9eb8d-107">For larger files and more complex issues, you could use a tool like Snooper.exe that is designed to read and parse the logging output from the Centralized Logging Service.</span></span> <span data-ttu-id="9eb8d-108">Snooper 包含在可单独下载的 Lync Server 2013 调试工具中。</span><span class="sxs-lookup"><span data-stu-id="9eb8d-108">Snooper is included with the Lync Server 2013 Debug Tools that are available as a separate download.</span></span> <span data-ttu-id="9eb8d-109">您可以在此处下载 Lync Server 2013 调试工具： [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257)。</span><span class="sxs-lookup"><span data-stu-id="9eb8d-109">You can download the Lync Server 2013 Debug Tools here: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257).</span></span> <span data-ttu-id="9eb8d-110">当您安装 Lync Server 2013 调试工具时，不会创建短时间的剪切和菜单项。</span><span class="sxs-lookup"><span data-stu-id="9eb8d-110">When you install the Lync Server 2013 Debug Tools, short cuts and menu items are not created.</span></span> <span data-ttu-id="9eb8d-111">安装 Lync Server 2013 调试工具后，打开 Windows 资源管理器、命令行窗口或 Lync Server 命令行管理程序，然后转到目录（默认位置） C：\\Program Files\\Microsoft Lync Server 2013\\调试工具。</span><span class="sxs-lookup"><span data-stu-id="9eb8d-111">After you install the Lync Server 2013 Debug Tools, open Windows Explorer, a command-line window, or Lync Server Management Shell and go to the directory (default location) C:\\Program Files\\Microsoft Lync Server 2013\\Debugging Tools.</span></span> <span data-ttu-id="9eb8d-112">双击 "Snooper.exe" 或键入 Snooper.exe，然后按 ENTER （如果使用的是命令行或 Lync Server 命令行管理程序）。</span><span class="sxs-lookup"><span data-stu-id="9eb8d-112">Double-click Snooper.exe or type Snooper.exe, and then press ENTER if you are using the command line or Lync Server Management Shell.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9eb8d-113">本主题的目的不是详细介绍和讨论疑难解答技术。</span><span class="sxs-lookup"><span data-stu-id="9eb8d-113">The intent of this topic is not to detail and discuss troubleshooting techniques.</span></span> <span data-ttu-id="9eb8d-114">疑难解答及其相关过程是一个复杂的主题。</span><span class="sxs-lookup"><span data-stu-id="9eb8d-114">Troubleshooting and the processes around it is a complex subject.</span></span> <span data-ttu-id="9eb8d-115">有关疑难解答基础知识和特定工作负荷故障排除的详细信息，请参阅 Microsoft Lync Server 2010 <A href="http://go.microsoft.com/fwlink/p/?linkid=211003">https://go.microsoft.com/fwlink/p/?linkId=211003</A>资源工具包书籍。</span><span class="sxs-lookup"><span data-stu-id="9eb8d-115">For details about troubleshooting basics and troubleshooting specific workloads, see the Microsoft Lync Server 2010 Resource Kit book at <A href="http://go.microsoft.com/fwlink/p/?linkid=211003">https://go.microsoft.com/fwlink/p/?linkId=211003</A>.</span></span> <span data-ttu-id="9eb8d-116">这些过程和过程仍适用于 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="9eb8d-116">The processes and procedures still apply to Lync Server 2013.</span></span>



</div>

<span data-ttu-id="9eb8d-117">Lync Server 2013 引入了更新版本的 Snooper.exe，其中包含一些新功能。</span><span class="sxs-lookup"><span data-stu-id="9eb8d-117">Lync Server 2013 introduces an updated version of Snooper that includes some new features.</span></span> <span data-ttu-id="9eb8d-118">以下屏幕截图显示了 Office 通信服务器2007中的 Snooper.exe 版本。</span><span class="sxs-lookup"><span data-stu-id="9eb8d-118">The following screen shot shows the version of Snooper from Office Communications Server 2007.</span></span>

<span data-ttu-id="9eb8d-119">![Office 通信2007版本的 Snooper.exe。](images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Office 通信2007版本的 Snooper.exe。")</span><span class="sxs-lookup"><span data-stu-id="9eb8d-119">![Office Communications 2007 version of Snooper.](images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Office Communications 2007 version of Snooper.")</span></span>

<span data-ttu-id="9eb8d-120">以下屏幕截图显示了新版本的 Snooper.exe，其中包含在 Lync Server 2013 调试工具中。</span><span class="sxs-lookup"><span data-stu-id="9eb8d-120">The following screen shot shows the new version of Snooper included in the Lync Server 2013 Debug Tools.</span></span>

<span data-ttu-id="9eb8d-121">![Lync Server 2013 版本的 Snooper.exe。](images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Lync Server 2013 版本的 Snooper.exe。")</span><span class="sxs-lookup"><span data-stu-id="9eb8d-121">![Lync Server 2013 version of Snooper.](images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Lync Server 2013 version of Snooper.")</span></span>

<span data-ttu-id="9eb8d-122">以下屏幕快照显示了含有常用功能的工具栏。</span><span class="sxs-lookup"><span data-stu-id="9eb8d-122">The following screen shot shows the toolbar with frequently used functions.</span></span>

<span data-ttu-id="9eb8d-123">![Snooper.exe 2013 工具栏。](images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Snooper.exe 2013 工具栏。")</span><span class="sxs-lookup"><span data-stu-id="9eb8d-123">![Snooper 2013 toolbar.](images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Snooper 2013 toolbar.")</span></span>

<span data-ttu-id="9eb8d-p104">此外，具有附加值的最新功能是流程图（呼叫流）视图。可以在“消息”\*\*\*\* 选项卡中选择消息流，然后单击“呼叫流”\*\*\*\* 按钮。当您继续浏览消息时，呼叫流视图将用新数据更新。</span><span class="sxs-lookup"><span data-stu-id="9eb8d-p104">And, the newest feature that adds value is the Flow Chart (call flow) diagram view. You select a message flow in the **Message** tab and click the **Call Flow** button. As you proceed through the messages, the call flow diagram updates with new data.</span></span>

<span data-ttu-id="9eb8d-127">![Snooper.exe 2013 呼叫流示意图。](images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Snooper.exe 2013 呼叫流示意图。")</span><span class="sxs-lookup"><span data-stu-id="9eb8d-127">![Snooper 2013 call flow diagram.](images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Snooper 2013 call flow diagram.")</span></span>

<span data-ttu-id="9eb8d-p105">您可以悬停在视图上并获得消息的详细信息以及流、消息和服务器元素的内容。单击任意呼叫流箭头可转到“消息”视图中的相应消息。</span><span class="sxs-lookup"><span data-stu-id="9eb8d-p105">You can hover over the diagram view and get details about the messages and content of the flows and messages as well as the server elements. Click on any call flow arrow to go to the message in the Messages view.</span></span>

<span data-ttu-id="9eb8d-130">![呼叫流图表消息详细信息。](images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "呼叫流图表消息详细信息。")</span><span class="sxs-lookup"><span data-stu-id="9eb8d-130">![Call flow diagram message details.](images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "Call flow diagram message details.")</span></span>

<div>

## <a name="to-open-a-log-file-in-snooper"></a><span data-ttu-id="9eb8d-131">在 Snooper 中打开日志文件</span><span class="sxs-lookup"><span data-stu-id="9eb8d-131">To open a log file in Snooper</span></span>

1.  <span data-ttu-id="9eb8d-p106">要使用 Snooper 并打开日志文件，您需要具有日志文件的读取权限。要使用 Snooper 并访问日志文件，您必须是基于 CsAdministrator 或 CsServerAdministrator 角色的访问控制 (RBAC) 安全组的成员，或者是包含这两个组之一的自定义 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="9eb8d-p106">To use Snooper and open log files, you need read access to the log files. To use Snooper and access the log files you must be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span>

2.  <span data-ttu-id="9eb8d-134">安装 Lync Server 调试工具（LyncDebugTools）后，使用 Windows 资源管理器或从命令行将目录更改为 Snooper.exe 的位置。</span><span class="sxs-lookup"><span data-stu-id="9eb8d-134">After the installation of the Lync Server Debugging Tools (LyncDebugTools.msi), change directory to the location of Snooper.exe using Windows Explorer or from the command line.</span></span> <span data-ttu-id="9eb8d-135">默认情况下，调试工具位于 C：\\Program Files\\Microsoft Lync Server 2013\\调试工具中。</span><span class="sxs-lookup"><span data-stu-id="9eb8d-135">By default, the debugging tools are located in C:\\Program Files\\Microsoft Lync Server 2013\\Debugging Tools.</span></span> <span data-ttu-id="9eb8d-136">双击或运行 Snooper.exe。</span><span class="sxs-lookup"><span data-stu-id="9eb8d-136">Double-click or run Snooper.exe.</span></span>

3.  <span data-ttu-id="9eb8d-137">打开 Snooper 后，右键单击“文件”\*\*\*\*，单击“打开文件”\*\*\*\*，查找日志文件，在“打开”\*\*\*\* 对话框中选择文件，然后单击“打开”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9eb8d-137">After Snooper is open, right-click **File**, click **OpenFile**, find your log files, select a file in the **Open** dialog box, and then click **Open**.</span></span>

4.  <span data-ttu-id="9eb8d-138">日志文件的“跟踪”\*\*\*\* 消息显示在“跟踪”\*\*\*\* 选项卡上。单击“消息”\*\*\*\* 选项卡可查看所收集跟踪的消息内容。</span><span class="sxs-lookup"><span data-stu-id="9eb8d-138">The log file’s **Trace** messages are displayed on the **Trace** tab. Click the **Messages** tab to view the message contents of the collected traces.</span></span>

</div>

<div>

## <a name="to-display-a-call-flow-diagram"></a><span data-ttu-id="9eb8d-139">显示呼叫流程图</span><span class="sxs-lookup"><span data-stu-id="9eb8d-139">To display a call flow diagram</span></span>

1.  <span data-ttu-id="9eb8d-p108">要使用 Snooper 并打开日志文件，您需要具有日志文件的读取权限。要使用 Snooper 并访问日志文件，您需要是基于 CsAdministrator 或 CsServerAdministrator 角色的访问控制 (RBAC) 安全组的成员，或者是包含这两个组之一的自定义 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="9eb8d-p108">To use Snooper and open log files, you need read access to the log files. To use Snooper and access the log files, you need to be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span>

2.  <span data-ttu-id="9eb8d-142">打开日志文件并单击“消息”\*\*\*\* 选项卡，在消息视图中选择对话或在“跟踪”\*\*\*\* 选项卡上选择跟踪组件。</span><span class="sxs-lookup"><span data-stu-id="9eb8d-142">Open a log file and click the **Messages** tab, select a conversation in the messages view or select a trace component on the **Trace** tab.</span></span>

3.  <span data-ttu-id="9eb8d-143">单击“呼叫流”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9eb8d-143">Click **Call Flow**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9eb8d-p109">如果单击不属于呼叫流的消息或跟踪，将不会显示流程图并在 Snooper 的底部显示一条状态消息，指示“此消息不符合呼叫流”。选择另一条属于呼叫流的消息或跟踪，将显示呼叫流。</span><span class="sxs-lookup"><span data-stu-id="9eb8d-p109">If you click on a message or trace that is not part of a call flow, the diagram will not appear and a status message appears at the bottom of Snooper stating “This message is not eligible for callfow”. Choose another message or trace and the call flow will appear if the message or trace is part of a call flow.</span></span>

    
    </div>

4.  <span data-ttu-id="9eb8d-146">在消息或跟踪行间移动，并注意呼叫流程图是否更新或更改为显示新图。</span><span class="sxs-lookup"><span data-stu-id="9eb8d-146">Move through the Messages or the Trace lines and note whether the call flow diagram updates or changes to display a new diagram.</span></span>

5.  <span data-ttu-id="9eb8d-147">在元素上悬停可获得有关呼叫消息、终结点和其他组件的信息。</span><span class="sxs-lookup"><span data-stu-id="9eb8d-147">Hover over elements to get information about call messages, endpoints, and other components.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

