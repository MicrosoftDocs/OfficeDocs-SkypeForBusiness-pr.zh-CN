---
title: Lync Server 2013：查看最佳实践分析工具中的报告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing reports from Best Practices Analyzer
ms:assetid: 7217a47b-36b1-4923-81ea-df754cff29bb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg607690(v=OCS.15)
ms:contentKeyID: 48184465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 842a04fbf47373060632ee4b367975c5c5df1cc6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138093"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-reports-from-best-practices-analyzer-in-lync-server-2013"></a>在 Lync Server 2013 中查看最佳实践分析工具报告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-21_

在使用最佳做法分析器扫描您的环境时，为扫描指定一个名称。最佳做法分析器在完成扫描后，会将扫描结果存储在报告中并将其保存在扫描名称的下方。完成扫描后，可以通过从“扫描已完成”**** 页中直接单击“查看该最佳实践扫描的报告”**** 来查看该扫描所生成的报告。稍后，您还可以查看来自该扫描或以前的扫描的报告。可以在已运行扫描的本地计算机中查看报告，从另一台计算机导入扫描结果或导出扫描结果以便在安装了最佳做法分析器的另一台计算机上查看报告。

扫描结果包含在以下类型的报告中：

  - 列表报告

  - 目录树报告

  - 其他报告

这些报告包括错误、警告和其他信息。 有关这些报告和问题类型的详细信息，请参阅[了解 Lync Server 2013 中的最佳实践分析工具创建的报告](lync-server-2013-understanding-reports-created-by-best-practices-analyzer.md)。

使用以下过程可查看之前由最佳做法分析器生成的扫描结果。

<div>

## <a name="to-view-reports-from-a-previous-scan"></a>查看以前扫描中的报告

1.  使用作为本地用户帐户成员的帐户登录到安装了最佳做法分析器的计算机。
    
    > [!NOTE]  
    > 虽然可使用作为本地 Administrators 组成员的帐户查看扫描结果，但除非您具有适当的用户权限，否则无法运行扫描。 有关详细信息，请参阅<A href="lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md">Lync Server 2013 中的最佳实践分析工具组成员身份和用户权限要求</A>。

2.  单击 "**开始**"，依次指向 "**所有程序**"、" **Microsoft Lync Server 2013**"，然后单击 "**最佳实践分析工具**"。

3.  在“欢迎”**** 屏幕上，单击“选择要查看的扫描结果”****。

4.  在“选择要查看的最佳实践扫描”**** 页上，执行下列操作之一：
    
      - 若要从本地存储的扫描结果列表中查看报告，请单击扫描的名称，然后单击“查看该扫描的报告”****。
        
        > [!NOTE]  
        > 最佳实践分析&lt;工具将从文件夹系统驱动器&gt;\\文档和设置\\&lt;用户&gt;\Application 中创建本地文件列表 Data\Microsoft\RtcBPA。
    
      - 若要查看存储在另一个位置的扫描结果报告，请单击“导入扫描”****，找到包含扫描结果的文件，然后单击“打开”****。
        
        > [!NOTE]  
        > 如果此计算机上的最佳做法分析器的版本与已用来收集导入文件中的数据的版本不匹配，则计算机上的工具可能会在此文件导入后再次对其进行分析。

5.  在“查看最佳实践报告”**** 页上，执行下列操作之一：
    
      - 若要以按服务器组件组织的列表的形式查看报告，请单击“列表报告”****，然后单击“所有问题”**** 选项卡或“信息项”**** 选项卡。
    
      - 若要以按结果类型组织的层次列表形式查看报告，请单击“目录树报告”****，然后单击“详细视图”**** 选项卡或“摘要视图”**** 选项卡。
    
      - 若要查看其他报告，请单击“其他报告”****。
    
    > [!NOTE]  
    > 若要详细了解最佳实践分析工具和他们确定的问题，请参阅<A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">在 lync server 2013 中查看并使用最佳实践分析工具创建的报告</A>，并<A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">分析和解决 lync server 2013 中的最佳实践分析工具识别的问题</A>。

</div>

</div>

</div>

</div>

</div>

