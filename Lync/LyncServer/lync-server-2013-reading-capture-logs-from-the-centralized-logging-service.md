---
title: 从集中日志记录服务读取捕获的日志
TOCTitle: 从集中日志记录服务读取捕获的日志
ms:assetid: c86ccf61-d86f-4ebd-b8d1-984a1b73005d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721879(v=OCS.15)
ms:contentKeyID: 49888607
ms.date: 12/29/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 从集中日志记录服务读取捕获的日志

 

_**上一次修改主题：** 2016-12-28_

在运行搜索后，您会体会到集中日志记录服务的好处，您将拥有一个可用于跟踪已报告问题的文件。读取该文件有多种方法。输出文件为标准文本格式，可以使用 Notepad.exe 或任何其他可以打开和读取文本文件的程序。对于较大文件和更复杂的问题，可以使用 Snooper.exe 之类的工具，该工具可用于读取和解析集中日志记录服务的记录输出。Snooper 包含在可单独下载的 Lync Server 2013 调试工具中。Lync Server 2013 调试工具不会创建快捷方式或菜单项。安装完 Lync Server 2013 调试工具后，打开 Windows 资源管理器、命令行窗口或 Lync Server 命令行管理程序，然后转到目录（默认位置）C:\\Program Files\\Microsoft Lync Server 2013\\Debugging Tools。双击 Snooper.exe 或键入 Snooper.exe，然后按 ENTER（如果使用命令行或 Lync Server 命令行管理程序）。

> [!IMPORTANT]
> 本主题的目的不是详细介绍和讨论疑难解答技术。疑难解答及其相关过程是一个复杂的主题。有关疑难解答基础和疑难解答具体工作负荷的详细信息，请参阅 Microsoft Lync Server 2010 资源工具包丛书，网址为 <a href="http://go.microsoft.com/fwlink/?linkid=211003%26clcid=0x804" class="uri">http://go.microsoft.com/fwlink/?linkid=211003&amp;clcid=0x804</a>。过程和步骤仍适用于 Lync Server 2013。


Lync Server 2013 引入了更新版本的 Snooper，其中包括了一些新功能。以下屏幕快照显示了 Office Communications Server 2007 中的 Snooper 版本。

![Snooper 的 Office Communications 2007 版本。](images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Snooper 的 Office Communications 2007 版本。")

以下屏幕快照显示了 Lync Server 2013 调试工具中包含的新版本的 Snooper。

![Snooper 的 Lync Server 2013 版本。](images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Snooper 的 Lync Server 2013 版本。")

以下屏幕快照显示了含有常用功能的工具栏。

![Snooper 2013 工具栏。](images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Snooper 2013 工具栏。")

此外，具有附加值的最新功能是流程图（呼叫流）视图。可以在“消息”选项卡中选择消息流，然后单击“呼叫流”按钮。当您继续浏览消息时，呼叫流视图将用新数据更新。

![Snooper 2013 呼叫流程图。](images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Snooper 2013 呼叫流程图。")

您可以悬停在视图上并获得消息的详细信息以及流、消息和服务器元素的内容。单击任意呼叫流箭头可转到“消息”视图中的相应消息。

![呼叫流程图消息详细信息。](images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "呼叫流程图消息详细信息。")

## 在 Snooper 中打开日志文件

1.  要使用 Snooper 并打开日志文件，您需要具有日志文件的读取权限。要使用 Snooper 并访问日志文件，您必须是基于 CsAdministrator 或 CsServerAdministrator 角色的访问控制 (RBAC) 安全组的成员，或者是包含这两个组之一的自定义 RBAC 角色。

2.  安装 Lync Server 调试工具 (LyncDebugTools.msi) 后，使用 Windows 资源管理器或从命令行将目录切换到 Snooper.exe 的位置。默认情况下，调试工具位于 C:\\Program Files\\Microsoft Lync Server 2013\\Debugging Tools。双击或运行 Snooper.exe。

3.  打开 Snooper 后，右键单击“文件”，单击“打开文件”，查找日志文件，在“打开”对话框中选择文件，然后单击“打开”。

4.  日志文件的“跟踪”消息显示在“跟踪”选项卡上。单击“消息”选项卡可查看所收集跟踪的消息内容。

## 显示呼叫流程图

1.  要使用 Snooper 并打开日志文件，您需要具有日志文件的读取权限。要使用 Snooper 并访问日志文件，您需要是基于 CsAdministrator 或 CsServerAdministrator 角色的访问控制 (RBAC) 安全组的成员，或者是包含这两个组之一的自定义 RBAC 角色。

2.  打开日志文件并单击“消息”选项卡，在消息视图中选择对话或在“跟踪”选项卡上选择跟踪组件。

3.  单击“呼叫流”。
    
    > [!NOTE]  
	> 如果单击不属于呼叫流的消息或跟踪，将不会显示流程图并在 Snooper 的底部显示一条状态消息，指示“此消息不符合呼叫流”。选择另一条属于呼叫流的消息或跟踪，将显示呼叫流。
    


4.  在消息或跟踪行间移动，并注意呼叫流程图是否更新或更改为显示新图。

5.  在元素上悬停可获得有关呼叫消息、终结点和其他组件的信息。

