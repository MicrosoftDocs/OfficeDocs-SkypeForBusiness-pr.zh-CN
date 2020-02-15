---
title: Lync Server 2013：对综合事务使用丰富日志记录
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using rich logging for synthetic transactions
ms:assetid: 32714a71-9f42-4d5b-a508-e176d8f08bbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204798(v=OCS.15)
ms:contentKeyID: 48183812
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 421b691bd282b858eca64c9756e92dd24aac8b7b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007571"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-rich-logging-for-synthetic-transactions-in-lync-server-2013"></a>在 Lync Server 2013 中对综合事务使用丰富日志记录

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-22_

综合事务（在 Microsoft Lync Server 2010 中引入）为管理员提供了一种验证用户能否成功完成常见任务（如登录系统、交换即时消息或呼叫电话）的方法。在公共交换电话网络（PSTN）上。 这些测试（打包为一组 Lync Server Windows PowerShell cmdlet）可由管理员手动执行，也可以由 System Center Operations Manager 等应用程序自动运行。

在 Lync Server 2010 中，在帮助管理员识别系统问题时，综合事务证明非常有用。 例如， **CsRegistration** cmdlet 可以提醒管理员一些用户在注册 Lync Server 时遇到困难。 但是，在帮助管理员确定这些用户在使用 Lync Server 注册时遇到困难的原因方面，综合事务有些不太有用。 这是因为综合事务不提供详细的日志记录信息，从而帮助管理员解决 Lync Server 的问题。 综合事务的详细输出最多提供了分步信息，它们可能使管理员能够有根据的推测可能哪里出现了问题。

在 Microsoft Lync Server 2013 中，已重新设计了综合事务以提供丰富的日志记录。 “丰富的日志记录”意味着，对于综合事务开展的每项活动，将记录如下信息：

  - 活动的开始时间

  - 活动的完成时间

  - 执行的操作（例如，创建、加入或离开会议; 登录到 Lync Server; 发送即时消息; 等等）

  - 在活动运行时生成的参考消息、详细消息、警告消息或错误消息

  - SIP 注册消息

  - 在活动运行时生成的异常记录或诊断代码

  - 运行活动的最终结果

每次运行综合事务时都会自动生成此类信息。 不过，这些信息不会自动显示或保存到日志文件中。 相反，手动运行综合事务的管理员可以使用 OutLoggerVariable 参数指定将在其中存储信息的 Windows PowerShell 变量。 之后，管理员可以使用允许他们以 XML 或 HTML 格式保存和/或查看丰富日志的成对方法。

例如，Lync Server 2010 管理员可以使用类似如下的命令运行**CsRegistration** cmdlet：

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com

管理员可以选择包括 OutLoggerVariable 参数，后跟所选的变量名称：

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest

> [!NOTE]  
> 变量名称不要以 $ 字符开头。可使用 RegistrationTest 之类的变量名称而非 $RegistrationTest。

上述命令输出如下内容：

    Target Fqdn   : atl-cs-001.litwareinc.com
    Result        : Failure
    Latency       : 00:00:00
    Error Message : This machine does not have any assigned certificates.
    Diagnosis     :

不过，针对此问题提供了比上面显示的仅错误消息更详细的信息。若要以 HTML 格式访问该信息，请使用类似于以下命令的命令将变量 RegistrationTest 中存储的信息保存到 HTML 文件：

    $RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html

您也可以使用 ToXML() 方法将数据保存到 XML 文件：

    $RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml

然后，可以使用 Internet Explorer、Visual Studio 或任何其他能够打开 HTML/XML 文件的应用程序来查看这些文件。

从 System Center Operations Manager 内部运行的综合事务将自动为故障生成这些日志文件。 但是，如果在 Windows PowerShell 能够加载和运行综合事务之前执行失败，则不会生成这些日志。

> [!IMPORTANT]  
> 默认情况下，Lync Server 2013 将日志文件保存到不共享的文件夹中。 若要方便地访问这些日志，应共享此文件夹（例如\\ \\atl-观察程序-litwareinc。 com\WatcherNode。


</div>

</div>

</div>

</div>

