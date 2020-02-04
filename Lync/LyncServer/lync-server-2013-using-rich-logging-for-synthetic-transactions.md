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
ms.openlocfilehash: 48efc99a49fd41678d07eef8685bc7f045397aa3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744042"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-rich-logging-for-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="8b036-102">在 Lync Server 2013 中对综合事务使用丰富日志记录</span><span class="sxs-lookup"><span data-stu-id="8b036-102">Using rich logging for synthetic transactions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b036-103">_**主题上次修改时间：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="8b036-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="8b036-104">综合事务（在 Microsoft Lync Server 2010 中引入）为管理员验证用户是否能够成功完成常见任务，如登录到系统、交换即时消息或拨打电话在公共交换电话网络（PSTN）上。</span><span class="sxs-lookup"><span data-stu-id="8b036-104">Synthetic transactions (introduced in Microsoft Lync Server 2010) provide a way for administrators to verify that users are able to successfully complete common tasks such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="8b036-105">这些测试（打包为一组 Lync Server Windows PowerShell cmdlet）可以由管理员手动执行，也可以由 System Center Operations Manager 等应用程序自动运行。</span><span class="sxs-lookup"><span data-stu-id="8b036-105">These tests (which are packaged as a set of Lync Server Windows PowerShell cmdlets) can be conducted manually by an administrator, or they can be automatically run by an application such as System Center Operations Manager.</span></span>

<span data-ttu-id="8b036-106">在 Lync Server 2010 中，合成事务在帮助管理员识别系统问题方面非常有用。</span><span class="sxs-lookup"><span data-stu-id="8b036-106">In Lync Server 2010, synthetic transactions proved extremely useful in helping administrators to identify problems with the system.</span></span> <span data-ttu-id="8b036-107">例如， **CsRegistration** cmdlet 可以向管理员发出警报，指出某些用户在注册 Lync Server 时遇到困难。</span><span class="sxs-lookup"><span data-stu-id="8b036-107">For example, the **Test-CsRegistration** cmdlet could alert administrators to the fact that some users were having difficulty registering with Lync Server.</span></span> <span data-ttu-id="8b036-108">但是，合成事务在帮助管理员确定这些用户为什么在 Lync Server 中注册很有用。</span><span class="sxs-lookup"><span data-stu-id="8b036-108">However, the synthetic transactions were somewhat less useful in helping administrators determine why these users were having difficulty registering with Lync Server.</span></span> <span data-ttu-id="8b036-109">这是因为合成事务未提供详细的日志记录信息，可帮助管理员解决 Lync 服务器的问题。</span><span class="sxs-lookup"><span data-stu-id="8b036-109">This was due to the fact that the synthetic transactions did not provide detailed logging information that could help administrators troubleshoot problems with Lync Server.</span></span> <span data-ttu-id="8b036-110">在最大程度上，综合事务中的详细输出提供了分步信息，使管理员能够以有意义的方式猜测可能出现问题的位置。</span><span class="sxs-lookup"><span data-stu-id="8b036-110">At best, the verbose output from a synthetic transaction provided step-by-step information that might enable an administrator to make an educated guess as to where a problem likely occurred.</span></span>

<span data-ttu-id="8b036-111">在 Microsoft Lync Server 2013 中，已重新设计了合成事务以提供丰富的日志记录。</span><span class="sxs-lookup"><span data-stu-id="8b036-111">In Microsoft Lync Server 2013, synthetic transactions have been re-architected to provide rich logging.</span></span> <span data-ttu-id="8b036-112">"丰富日志记录" 指对于综合事务仅负责的每个活动，将记录如下信息：</span><span class="sxs-lookup"><span data-stu-id="8b036-112">"Rich logging" means that, for each activity that a synthetic transaction undertakes, information such as this will be recorded:</span></span>

  - <span data-ttu-id="8b036-113">活动开始的时间</span><span class="sxs-lookup"><span data-stu-id="8b036-113">The time that the activity started</span></span>

  - <span data-ttu-id="8b036-114">活动完成的时间</span><span class="sxs-lookup"><span data-stu-id="8b036-114">The time that the activity finished</span></span>

  - <span data-ttu-id="8b036-115">执行的操作（例如，创建、加入或离开会议; 登录 Lync Server; 发送即时消息; 等等）</span><span class="sxs-lookup"><span data-stu-id="8b036-115">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Lync Server; sending an instant message; and so on)</span></span>

  - <span data-ttu-id="8b036-116">活动运行时生成的信息、详细、警告或错误消息</span><span class="sxs-lookup"><span data-stu-id="8b036-116">Informational, verbose, warning, or error messages generated when the activity ran</span></span>

  - <span data-ttu-id="8b036-117">SIP 注册消息</span><span class="sxs-lookup"><span data-stu-id="8b036-117">SIP registration messages</span></span>

  - <span data-ttu-id="8b036-118">在活动运行时生成的异常记录或诊断代码</span><span class="sxs-lookup"><span data-stu-id="8b036-118">Exception records or diagnostic codes generated when the activity ran</span></span>

  - <span data-ttu-id="8b036-119">活动运行的最终结果</span><span class="sxs-lookup"><span data-stu-id="8b036-119">The net result of running the activity</span></span>

<span data-ttu-id="8b036-120">每次运行合成事务时都会自动生成此信息。</span><span class="sxs-lookup"><span data-stu-id="8b036-120">This information is automatically generated each time a synthetic transaction is run.</span></span> <span data-ttu-id="8b036-121">但是，信息不会自动显示或保存到日志文件。</span><span class="sxs-lookup"><span data-stu-id="8b036-121">However, the information is not automatically displayed or saved to a log file.</span></span> <span data-ttu-id="8b036-122">相反，手动运行合成事务的管理员可以使用 OutLoggerVariable 参数指定将存储信息的 Windows PowerShell 变量。</span><span class="sxs-lookup"><span data-stu-id="8b036-122">Instead, administrators who are manually running a synthetic transaction can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored.</span></span> <span data-ttu-id="8b036-123">然后，管理员可以使用一对方法，使其能够以 XML 或 HTML 格式保存和/或查看丰富的日志。</span><span class="sxs-lookup"><span data-stu-id="8b036-123">From there, administrators can then use a pair of methods that enable them to save and/or view the rich log in either XML or HTML format.</span></span>

<span data-ttu-id="8b036-124">例如，Lync Server 2010 管理员可能使用类似如下的命令运行**CsRegistration** cmdlet：</span><span class="sxs-lookup"><span data-stu-id="8b036-124">For example, Lync Server 2010 administrators might run the **Test-CsRegistration** cmdlet by using a command similar to the following:</span></span>

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com

<span data-ttu-id="8b036-125">管理员可以选择包含 OutLoggerVariable 参数，后跟其选择的变量名称：</span><span class="sxs-lookup"><span data-stu-id="8b036-125">Administrators have the option of including the OutLoggerVariable parameter followed by a variable name of their choosing:</span></span>

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest

> [!NOTE]  
> <span data-ttu-id="8b036-126">不要在变量名前面加 $ 字符。</span><span class="sxs-lookup"><span data-stu-id="8b036-126">Do not preface the variable name with the $ character.</span></span> <span data-ttu-id="8b036-127">使用变量名称（如 RegistrationTest，而不是 $RegistrationTest。</span><span class="sxs-lookup"><span data-stu-id="8b036-127">Use a variable name like RegistrationTest and not $RegistrationTest.</span></span>

<span data-ttu-id="8b036-128">上面的命令输出类似于以下内容的内容：</span><span class="sxs-lookup"><span data-stu-id="8b036-128">The preceding command outputs content similar to the following:</span></span>

    Target Fqdn   : atl-cs-001.litwareinc.com
    Result        : Failure
    Latency       : 00:00:00
    Error Message : This machine does not have any assigned certificates.
    Diagnosis     :

<span data-ttu-id="8b036-129">但是，此故障的详细信息更详细，而不仅仅是上面显示的错误消息。</span><span class="sxs-lookup"><span data-stu-id="8b036-129">However, much more detailed information is available for this failure than just the error message shown above.</span></span> <span data-ttu-id="8b036-130">若要以 HTML 格式访问这些信息，请使用与此类似的命令，将变量 RegistrationTest 中存储的信息保存到 HTML 文件中：</span><span class="sxs-lookup"><span data-stu-id="8b036-130">To access that information in HTML format, use a command similar to this in order to save the information stored in the variable RegistrationTest to an HTML file:</span></span>

    $RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html

<span data-ttu-id="8b036-131">或者，你可以使用 ToXML （）方法将数据保存到 XML 文件：</span><span class="sxs-lookup"><span data-stu-id="8b036-131">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>

    $RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml

<span data-ttu-id="8b036-132">然后，可以使用 Internet Explorer、Visual Studio 或任何其他能够打开 HTML/XML 文件的应用程序来查看这些文件。</span><span class="sxs-lookup"><span data-stu-id="8b036-132">These files can then be viewed using Internet Explorer, Visual Studio, or any other application capable of opening HTML/XML files.</span></span>

<span data-ttu-id="8b036-133">从 System Center Operations Manager 内部运行的合成事务将自动为故障生成这些日志文件。</span><span class="sxs-lookup"><span data-stu-id="8b036-133">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="8b036-134">但是，如果在 Windows PowerShell 能够加载和运行合成事务之前执行失败，则不会生成这些日志。</span><span class="sxs-lookup"><span data-stu-id="8b036-134">However, these logs will not be generated if the execution fails before Windows PowerShell is able to load and run the synthetic transaction.</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="8b036-135">默认情况下，Lync Server 2013 将日志文件保存到未共享的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="8b036-135">By default, Lync Server 2013 saves log files to a folder that is not shared.</span></span> <span data-ttu-id="8b036-136">为了让这些日志随时易于访问，你应该共享此文件夹（例如， \\ \\atl-观察程序-litwareinc。 com\WatcherNode。</span><span class="sxs-lookup"><span data-stu-id="8b036-136">To make these logs readily accessible, you should share this folder (for example, \\\\atl-watcher-001.litwareinc.com\WatcherNode.</span></span>


</div>

</div>

</div>

</div>

