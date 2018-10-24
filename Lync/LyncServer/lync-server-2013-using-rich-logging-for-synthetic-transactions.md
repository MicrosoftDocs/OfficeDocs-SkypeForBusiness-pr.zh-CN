---
title: 使用综合事务的富日志记录
TOCTitle: 使用综合事务的富日志记录
ms:assetid: 32714a71-9f42-4d5b-a508-e176d8f08bbf
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204798(v=OCS.15)
ms:contentKeyID: 49312430
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 使用综合事务的富日志记录

 

_**上一次修改主题：** 2012-10-22_

综合事务（在 Microsoft Lync Server 2010 中引入）为管理员提供了一种验证用户是否能够成功完成常见任务（例如登录到系统、交换即时消息或者拨打位于公用电话交换网 (PSTN) 中的电话）的方法。这些测试（它们打包为一组 Lync ServerWindows PowerShell cmdlet）可以由管理员手动执行，也可以通过应用程序（例如 System Center Operations Manager）自动运行。

在 Lync Server 2010 中，已证实综合事务在帮助管理员识别系统问题方面极其有用。例如，**Test-CsRegistration** cmdlet 可以提醒管理员一些用户在向 Lync Server 注册时遇到了困难。不过，综合事务在帮助管理员确定为什么这些用户在向 Lync Server 注册时会遇到困难这一方面有点不太有用。这是由于综合事务没有提供可帮助管理员解决 Lync Server 问题的详细日志记录信息。综合事务的详细输出最多提供了分步信息，它们可能使管理员能够有根据的推测可能哪里出现了问题。

在 Microsoft Lync Server 2013 中，重新设计了综合事务以提供丰富的日志记录。“丰富的日志记录”意味着，对于综合事务开展的每项活动，将记录如下信息：

  - 活动的开始时间

  - 活动的完成时间

  - 执行的操作（例如，创建、加入或离开会议；登录到 Lync Server；发送即时消息等等）

  - 在活动运行时生成的参考消息、详细消息、警告消息或错误消息

  - SIP 注册消息

  - 在活动运行时生成的异常记录或诊断代码

  - 运行活动的最终结果

每次运行综合事务时都会自动生成此类信息。不过，这些信息不会自动显示或保存到日志文件中。手动运行综合事务的管理员可以使用 OutLoggerVariable 参数来指定将在其中存储信息的 Windows PowerShell 变量。之后，管理员可以使用允许他们以 XML 或 HTML 格式保存和/或查看丰富日志的成对方法。

例如，Lync Server 2010 管理员可以使用如下命令来运行 **Test-CsRegistration** cmdlet：

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

然后可以使用 Internet Explorer、Visual Studio 或任何其他能够打开 HTML/XML 文件的应用程序查看这些文件。

从 System Center Operations Manager 中运行的综合事务将自动针对问题生成这些日志文件。不过，如果执行过程在 Windows PowerShell 能够加载和运行综合事务之前失败，则不会生成这些日志。

> [!IMPORTANT]
> 默认情况下，Lync Server 2013 将日志文件保存到不共享的文件夹中。若要轻松访问这些日志，您应该共享此文件夹（例如，\\atl-watcher-001.litwareinc.com\WatcherNode）。

