---
title: 'Lync Server 2013: 对综合事务使用丰富日志记录'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using rich logging for synthetic transactions
ms:assetid: 32714a71-9f42-4d5b-a508-e176d8f08bbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204798(v=OCS.15)
ms:contentKeyID: 48183812
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 455d7bcdc14dd4d701d749407759cead0834906f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845422"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-rich-logging-for-synthetic-transactions-in-lync-server-2013"></a>在 Lync Server 2013 中对综合事务使用丰富日志记录

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-22_

综合事务 (在 Microsoft Lync Server 2010 中引入) 为管理员验证用户是否能够成功完成常见任务, 如登录到系统、交换即时消息或拨打电话在公共交换电话网络 (PSTN) 上。 这些测试 (打包为一组 Lync Server Windows PowerShell cmdlet) 可以由管理员手动执行, 也可以由 System Center Operations Manager 等应用程序自动运行。

在 Lync Server 2010 中, 合成事务在帮助管理员识别系统问题方面非常有用。 例如, **CsRegistration** cmdlet 可以向管理员发出警报, 指出某些用户在注册 Lync Server 时遇到困难。 但是, 合成事务在帮助管理员确定这些用户为什么在 Lync Server 中注册很有用。 这是因为合成事务未提供详细的日志记录信息, 可帮助管理员解决 Lync 服务器的问题。 在最大程度上, 综合事务中的详细输出提供了分步信息, 使管理员能够以有意义的方式猜测可能出现问题的位置。

在 Microsoft Lync Server 2013 中, 已重新设计了合成事务以提供丰富的日志记录。 "丰富日志记录" 指对于综合事务仅负责的每个活动, 将记录如下信息:

  - 活动开始的时间

  - 活动完成的时间

  - 执行的操作 (例如, 创建、加入或离开会议; 登录 Lync Server; 发送即时消息; 等等)

  - 活动运行时生成的信息、详细、警告或错误消息

  - SIP 注册消息

  - 在活动运行时生成的异常记录或诊断代码

  - 活动运行的最终结果

每次运行合成事务时都会自动生成此信息。 但是, 信息不会自动显示或保存到日志文件。 相反, 手动运行合成事务的管理员可以使用 OutLoggerVariable 参数指定将存储信息的 Windows PowerShell 变量。 然后, 管理员可以使用一对方法, 使其能够以 XML 或 HTML 格式保存和/或查看丰富的日志。

例如, Lync Server 2010 管理员可能使用类似如下的命令运行**CsRegistration** cmdlet:

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com

管理员可以选择包含 OutLoggerVariable 参数, 后跟其选择的变量名称:

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest

> [!NOTE]  
> 不要在变量名前面加 $ 字符。 使用变量名称 (如 RegistrationTest, 而不是 $RegistrationTest。

上面的命令输出类似于以下内容的内容:

    Target Fqdn   : atl-cs-001.litwareinc.com
    Result        : Failure
    Latency       : 00:00:00
    Error Message : This machine does not have any assigned certificates.
    Diagnosis     :

但是, 此故障的详细信息更详细, 而不仅仅是上面显示的错误消息。 若要以 HTML 格式访问这些信息, 请使用与此类似的命令, 将变量 RegistrationTest 中存储的信息保存到 HTML 文件中:

    $RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html

或者, 你可以使用 ToXML () 方法将数据保存到 XML 文件:

    $RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml

然后, 可以使用 Internet Explorer、Visual Studio 或任何其他能够打开 HTML/XML 文件的应用程序来查看这些文件。

从 System Center Operations Manager 内部运行的合成事务将自动为故障生成这些日志文件。 但是, 如果在 Windows PowerShell 能够加载和运行合成事务之前执行失败, 则不会生成这些日志。

> [!IMPORTANT]  
> 默认情况下, Lync Server 2013 将日志文件保存到未共享的文件夹中。 为了让这些日志随时易于访问, 你应该共享此文件夹 (例如, \\ \\atl-观察程序-litwareinc。 com\WatcherNode。


</div>

</div>

</div>

</div>

