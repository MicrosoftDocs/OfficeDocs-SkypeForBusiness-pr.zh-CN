---
title: Lync Server 2013：对综合事务使用丰富日志记录
description: Lync Server 2013：对综合事务使用丰富日志记录。
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
ms.openlocfilehash: 5fd984386985bced64265ebedfd57c56a84a4443
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580298"
---
# <a name="using-rich-logging-for-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="742bf-103">在 Lync Server 2013 中对综合事务使用丰富日志记录</span><span class="sxs-lookup"><span data-stu-id="742bf-103">Using rich logging for synthetic transactions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="742bf-104">_**上次修改的主题：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="742bf-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="742bf-105"> (在 Microsoft Lync Server 2010 中引入的综合事务) 为管理员提供了一种方法，用于验证用户是否能够成功完成常见任务，如登录系统、交换即时消息或呼叫位于公用电话交换网 (PSTN) 的电话。</span><span class="sxs-lookup"><span data-stu-id="742bf-105">Synthetic transactions (introduced in Microsoft Lync Server 2010) provide a way for administrators to verify that users are able to successfully complete common tasks such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="742bf-106">这些测试 (打包为一组 Lync Server Windows PowerShell cmdlet) 可由管理员手动执行，也可以由 System Center Operations Manager 等应用程序自动运行。</span><span class="sxs-lookup"><span data-stu-id="742bf-106">These tests (which are packaged as a set of Lync Server Windows PowerShell cmdlets) can be conducted manually by an administrator, or they can be automatically run by an application such as System Center Operations Manager.</span></span>

<span data-ttu-id="742bf-107">在 Lync Server 2010 中，在帮助管理员识别系统问题时，综合事务证明非常有用。</span><span class="sxs-lookup"><span data-stu-id="742bf-107">In Lync Server 2010, synthetic transactions proved extremely useful in helping administrators to identify problems with the system.</span></span> <span data-ttu-id="742bf-108">例如， **CsRegistration** cmdlet 可以提醒管理员一些用户在注册 Lync Server 时遇到困难。</span><span class="sxs-lookup"><span data-stu-id="742bf-108">For example, the **Test-CsRegistration** cmdlet could alert administrators to the fact that some users were having difficulty registering with Lync Server.</span></span> <span data-ttu-id="742bf-109">但是，在帮助管理员确定这些用户在使用 Lync Server 注册时遇到困难的原因方面，综合事务有些不太有用。</span><span class="sxs-lookup"><span data-stu-id="742bf-109">However, the synthetic transactions were somewhat less useful in helping administrators determine why these users were having difficulty registering with Lync Server.</span></span> <span data-ttu-id="742bf-110">这是因为综合事务不提供详细的日志记录信息，从而帮助管理员解决 Lync Server 的问题。</span><span class="sxs-lookup"><span data-stu-id="742bf-110">This was due to the fact that the synthetic transactions did not provide detailed logging information that could help administrators troubleshoot problems with Lync Server.</span></span> <span data-ttu-id="742bf-111">综合事务的详细输出最多提供了分步信息，它们可能使管理员能够有根据的推测可能哪里出现了问题。</span><span class="sxs-lookup"><span data-stu-id="742bf-111">At best, the verbose output from a synthetic transaction provided step-by-step information that might enable an administrator to make an educated guess as to where a problem likely occurred.</span></span>

<span data-ttu-id="742bf-112">在 Microsoft Lync Server 2013 中，已重新设计了综合事务以提供丰富的日志记录。</span><span class="sxs-lookup"><span data-stu-id="742bf-112">In Microsoft Lync Server 2013, synthetic transactions have been re-architected to provide rich logging.</span></span> <span data-ttu-id="742bf-113">“丰富的日志记录”意味着，对于综合事务开展的每项活动，将记录如下信息：</span><span class="sxs-lookup"><span data-stu-id="742bf-113">"Rich logging" means that, for each activity that a synthetic transaction undertakes, information such as this will be recorded:</span></span>

  - <span data-ttu-id="742bf-114">活动的开始时间</span><span class="sxs-lookup"><span data-stu-id="742bf-114">The time that the activity started</span></span>

  - <span data-ttu-id="742bf-115">活动的完成时间</span><span class="sxs-lookup"><span data-stu-id="742bf-115">The time that the activity finished</span></span>

  - <span data-ttu-id="742bf-116">执行的操作 (例如，创建、加入会议或离开会议;登录到 Lync Server;发送即时消息;依此类推) </span><span class="sxs-lookup"><span data-stu-id="742bf-116">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Lync Server; sending an instant message; and so on)</span></span>

  - <span data-ttu-id="742bf-117">在活动运行时生成的参考消息、详细消息、警告消息或错误消息</span><span class="sxs-lookup"><span data-stu-id="742bf-117">Informational, verbose, warning, or error messages generated when the activity ran</span></span>

  - <span data-ttu-id="742bf-118">SIP 注册消息</span><span class="sxs-lookup"><span data-stu-id="742bf-118">SIP registration messages</span></span>

  - <span data-ttu-id="742bf-119">在活动运行时生成的异常记录或诊断代码</span><span class="sxs-lookup"><span data-stu-id="742bf-119">Exception records or diagnostic codes generated when the activity ran</span></span>

  - <span data-ttu-id="742bf-120">运行活动的最终结果</span><span class="sxs-lookup"><span data-stu-id="742bf-120">The net result of running the activity</span></span>

<span data-ttu-id="742bf-121">每次运行综合事务时都会自动生成此类信息。</span><span class="sxs-lookup"><span data-stu-id="742bf-121">This information is automatically generated each time a synthetic transaction is run.</span></span> <span data-ttu-id="742bf-122">不过，这些信息不会自动显示或保存到日志文件中。</span><span class="sxs-lookup"><span data-stu-id="742bf-122">However, the information is not automatically displayed or saved to a log file.</span></span> <span data-ttu-id="742bf-123">相反，手动运行综合事务的管理员可以使用 OutLoggerVariable 参数指定将在其中存储信息的 Windows PowerShell 变量。</span><span class="sxs-lookup"><span data-stu-id="742bf-123">Instead, administrators who are manually running a synthetic transaction can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored.</span></span> <span data-ttu-id="742bf-124">之后，管理员可以使用允许他们以 XML 或 HTML 格式保存和/或查看丰富日志的成对方法。</span><span class="sxs-lookup"><span data-stu-id="742bf-124">From there, administrators can then use a pair of methods that enable them to save and/or view the rich log in either XML or HTML format.</span></span>

<span data-ttu-id="742bf-125">例如，Lync Server 2010 管理员可以使用类似如下的命令运行 **CsRegistration** cmdlet：</span><span class="sxs-lookup"><span data-stu-id="742bf-125">For example, Lync Server 2010 administrators might run the **Test-CsRegistration** cmdlet by using a command similar to the following:</span></span>

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com

<span data-ttu-id="742bf-126">管理员可以选择包括 OutLoggerVariable 参数，后跟所选的变量名称：</span><span class="sxs-lookup"><span data-stu-id="742bf-126">Administrators have the option of including the OutLoggerVariable parameter followed by a variable name of their choosing:</span></span>

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest

> [!NOTE]  
> <span data-ttu-id="742bf-p105">变量名称不要以 $ 字符开头。可使用 RegistrationTest 之类的变量名称而非 $RegistrationTest。</span><span class="sxs-lookup"><span data-stu-id="742bf-p105">Do not preface the variable name with the $ character. Use a variable name like RegistrationTest and not $RegistrationTest.</span></span>

<span data-ttu-id="742bf-129">上述命令输出如下内容：</span><span class="sxs-lookup"><span data-stu-id="742bf-129">The preceding command outputs content similar to the following:</span></span>

    Target Fqdn   : atl-cs-001.litwareinc.com
    Result        : Failure
    Latency       : 00:00:00
    Error Message : This machine does not have any assigned certificates.
    Diagnosis     :

<span data-ttu-id="742bf-p106">不过，针对此问题提供了比上面显示的仅错误消息更详细的信息。若要以 HTML 格式访问该信息，请使用类似于以下命令的命令将变量 RegistrationTest 中存储的信息保存到 HTML 文件：</span><span class="sxs-lookup"><span data-stu-id="742bf-p106">However, much more detailed information is available for this failure than just the error message shown above. To access that information in HTML format, use a command similar to this in order to save the information stored in the variable RegistrationTest to an HTML file:</span></span>

    $RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html

<span data-ttu-id="742bf-132">您也可以使用 ToXML() 方法将数据保存到 XML 文件：</span><span class="sxs-lookup"><span data-stu-id="742bf-132">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>

    $RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml

<span data-ttu-id="742bf-133">然后，可以使用 Internet Explorer、Visual Studio 或任何其他能够打开 HTML/XML 文件的应用程序来查看这些文件。</span><span class="sxs-lookup"><span data-stu-id="742bf-133">These files can then be viewed using Internet Explorer, Visual Studio, or any other application capable of opening HTML/XML files.</span></span>

<span data-ttu-id="742bf-134">从 System Center Operations Manager 内部运行的综合事务将自动为故障生成这些日志文件。</span><span class="sxs-lookup"><span data-stu-id="742bf-134">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="742bf-135">但是，如果在 Windows PowerShell 能够加载和运行综合事务之前执行失败，则不会生成这些日志。</span><span class="sxs-lookup"><span data-stu-id="742bf-135">However, these logs will not be generated if the execution fails before Windows PowerShell is able to load and run the synthetic transaction.</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="742bf-136">默认情况下，Lync Server 2013 将日志文件保存到不共享的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="742bf-136">By default, Lync Server 2013 saves log files to a folder that is not shared.</span></span> <span data-ttu-id="742bf-137">若要方便地访问这些日志，应共享此文件夹 (例如 \\ \\ atl-观察程序 litwareinc. com\WatcherNode。</span><span class="sxs-lookup"><span data-stu-id="742bf-137">To make these logs readily accessible, you should share this folder (for example, \\\\atl-watcher-001.litwareinc.com\WatcherNode.</span></span>


</div>

</div>

</div>

</div>

