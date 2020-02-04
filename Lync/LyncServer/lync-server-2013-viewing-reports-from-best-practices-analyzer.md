---
title: Lync Server 2013：查看最佳实践分析程序中的报表
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
ms.openlocfilehash: e79732661152ba0929b62ae64f46b0cbfdb95217
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757236"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-reports-from-best-practices-analyzer-in-lync-server-2013"></a>在 Lync Server 2013 中查看最佳做法分析器中的报告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-21_

使用最佳做法分析程序扫描环境时，请指定扫描的名称。 在最佳做法分析器完成扫描后，它会将扫描结果存储在报告中，并将其保存在扫描的名称下方。 扫描完成后，您可以通过单击 "**查看此最佳做法的报告**"，直接从 "**扫描已完成**" 页面查看为该扫描生成的报告。 您也可以稍后查看该扫描或以前的扫描中的报告。 你可以在运行扫描的本地计算机上查看报表、从另一台计算机导入扫描结果或导出扫描结果以在安装了最佳做法分析器的另一台计算机上查看报告。

扫描结果显示在以下类型的报表中：

  - 列表报表

  - 树报表

  - 其他报表

这些报表包括错误、警告和其他信息。 有关这些报告和问题的详细信息，请参阅[在 Lync Server 2013 中了解由最佳做法分析器创建的报告](lync-server-2013-understanding-reports-created-by-best-practices-analyzer.md)。

使用以下过程可查看以前由最佳做法分析器生成的扫描结果。

<div>

## <a name="to-view-reports-from-a-previous-scan"></a>查看以前的扫描中的报表

1.  使用本地用户帐户的成员帐户登录到安装了最佳做法分析器的计算机。
    
    > [!NOTE]  
    > 你可以使用本地管理员组的成员帐户查看扫描结果，但除非你拥有相应的用户权利和权限，否则不能运行扫描。 有关详细信息，请参阅<A href="lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md">Lync Server 2013 中的最佳做法分析器的组成员身份和用户权限要求</A>。

2.  单击 "**开始**"，指向 "**所有程序**"，单击 " **Microsoft Lync Server 2013**"，然后单击 "**最佳做法分析器**"。

3.  在 "**欢迎**" 屏幕上，单击 **"选择要查看的扫描结果"**。

4.  在 "**选择最佳做法扫描到视图**" 页面上，执行下列操作之一：
    
      - 若要从本地存储的扫描结果列表中查看报告，请单击扫描的名称，然后单击 "**查看此扫描的报告**"。
        
        > [!NOTE]  
        > &lt;最佳做法分析器从文件夹 systemDrive&gt;\\"文档和设置\\&lt;" 用户&gt;\Application 中创建本地文件的列表 Data\Microsoft\RtcBPA。
    
      - 若要查看存储在其他位置的扫描结果的报告，请单击 "**导入扫描**"，找到包含扫描结果的文件，然后单击 "**打开**"。
        
        > [!NOTE]  
        > 如果此计算机上最佳做法分析器的版本与用于收集导入文件中的数据的版本不匹配，则计算机上的工具可能会在导入后再次分析该文件。

5.  在 "**查看最佳做法报告**" 页面上，执行下列操作之一：
    
      - 若要查看按服务器组件组织的列表中的报告，请单击 "**列表报告**"，然后单击 "**所有问题**" 选项卡或 "**信息性项目**" 选项卡。
    
      - 若要将报表作为按结果类型组织的分层列表进行查看，请单击 "**树报表**"，然后单击 "**详细视图**" 选项卡或 "**摘要视图**" 选项卡。
    
      - 若要查看其他报表，请单击 "**其他报表**"。
    
    > [!NOTE]  
    > 有关最佳做法分析器报告及其标识问题的详细信息，请参阅<A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">在 lync server 2013 中查看和使用由最佳做法分析器创建的报表</A>，并<A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">分析和解决由 lync server 2013 中的最佳做法分析器识别的问题</A>。

</div>

</div>

</div>

</div>

</div>

