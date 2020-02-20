---
title: Lync Server 2013：系统使用情况报告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: System usage reports
ms:assetid: 187d316d-2456-417e-b636-05527a18ef06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558618(v=OCS.15)
ms:contentKeyID: 48183529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1b020217863dd4adf04a8e91041dcae8fa078ea
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142228"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="system-usage-reports-in-lync-server-2013"></a><span data-ttu-id="b4d85-102">Lync Server 2013 中的系统使用情况报告</span><span class="sxs-lookup"><span data-stu-id="b4d85-102">System usage reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4d85-103">_**上次修改的主题：** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="b4d85-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="b4d85-104">系统使用情况报告根据 Lync Server 收集的呼叫详细信息记录（CDR）数据提供系统使用情况信息。</span><span class="sxs-lookup"><span data-stu-id="b4d85-104">The System Usage Reports provide system usage information based on call detail recording (CDR) data collected by the Lync Server.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b4d85-105">本部分内容</span><span class="sxs-lookup"><span data-stu-id="b4d85-105">In This Section</span></span>

  - [<span data-ttu-id="b4d85-106">Lync Server 2013 中的用户注册报告</span><span class="sxs-lookup"><span data-stu-id="b4d85-106">User Registration Report in Lync Server 2013</span></span>](lync-server-2013-user-registration-report.md)
    
    <span data-ttu-id="b4d85-107">提供基于注册事件（如用户登录）的 Lync Server 2013 部署的用户连接摘要。</span><span class="sxs-lookup"><span data-stu-id="b4d85-107">Provides a summary of user connectivity to the Lync Server 2013 deployment based on registration events such as user logons.</span></span> <span data-ttu-id="b4d85-108">报告提供了一种查看内部和外部登录的方法，并将登录到 Lync Server 2013 的用户数与在登录时实际使用该服务的用户数进行比较。</span><span class="sxs-lookup"><span data-stu-id="b4d85-108">The report provides a way to view both internal and external logons, and to compare the number of users who logged on to Lync Server 2013 with the number of users who actually used the service while they were logged on.</span></span>

  - [<span data-ttu-id="b4d85-109">Lync Server 2013 中的对等活动摘要报告</span><span class="sxs-lookup"><span data-stu-id="b4d85-109">Peer-to-Peer Activity Summary Report in Lync Server 2013</span></span>](lync-server-2013-peer-to-peer-activity-summary-report.md)
    
    <span data-ttu-id="b4d85-p102">提供点对点即时消息 (IM)、音频、视频、文件传输和应用程序共享会话摘要。点对点会话是仅涉及两个用户的会话。</span><span class="sxs-lookup"><span data-stu-id="b4d85-p102">Provides a summary of peer-to-peer instant messaging (IM), audio, video, file transfer, and application sharing sessions. Peer-to-peer sessions are sessions involving just two users.</span></span>

  - [<span data-ttu-id="b4d85-112">Lync Server 2013 中的会议摘要报告</span><span class="sxs-lookup"><span data-stu-id="b4d85-112">Conference Summary Report in Lync Server 2013</span></span>](lync-server-2013-conference-summary-report.md)
    
    <span data-ttu-id="b4d85-113">提供所有会议活动摘要。</span><span class="sxs-lookup"><span data-stu-id="b4d85-113">Provides a summary of all conference activities.</span></span> <span data-ttu-id="b4d85-114">会议是涉及三个或更多人的会话。</span><span class="sxs-lookup"><span data-stu-id="b4d85-114">Conferences are sessions involving three or more people.</span></span>

  - [<span data-ttu-id="b4d85-115">Lync Server 2013 中的 PSTN 会议摘要报告</span><span class="sxs-lookup"><span data-stu-id="b4d85-115">PSTN Conference Summary Report in Lync Server 2013</span></span>](lync-server-2013-pstn-conference-summary-report.md)
    
    <span data-ttu-id="b4d85-p104">提供所有 PSTN 会议摘要。这些会议是至少一个用户使用公用电话交换网 (PSTN) 拨入的会议，该会议又称为*电话拨入式会议*。</span><span class="sxs-lookup"><span data-stu-id="b4d85-p104">Provides a summary of all PSTN conferences. These are conferences where at least one user dials in using the public switched telephone network (PSTN), which is also referred to as *dial-in conferencing*.</span></span>

  - [<span data-ttu-id="b4d85-118">Lync Server 2013 中的响应组使用情况报告</span><span class="sxs-lookup"><span data-stu-id="b4d85-118">Response Group Usage Report in Lync Server 2013</span></span>](lync-server-2013-response-group-usage-report.md)
    
    <span data-ttu-id="b4d85-119">提供响应组使用情况的摘要。</span><span class="sxs-lookup"><span data-stu-id="b4d85-119">Provides a summary of Response Group usage.</span></span> <span data-ttu-id="b4d85-120">响应组应用程序为您提供了一种将电话呼叫自动路由到诸如帮助台或客户支持行等实体的方法。</span><span class="sxs-lookup"><span data-stu-id="b4d85-120">The Response Group application provides a way for you to automatically route phone calls to entities such as a help desk or customer support line.</span></span>

  - [<span data-ttu-id="b4d85-121">Lync Server 2013 中的 IP 电话清单报告</span><span class="sxs-lookup"><span data-stu-id="b4d85-121">IP Phone Inventory Report in Lync Server 2013</span></span>](lync-server-2013-ip-phone-inventory-report.md)
    
    <span data-ttu-id="b4d85-122">提供有关组织中当前正在使用的 IP 电话的信息。</span><span class="sxs-lookup"><span data-stu-id="b4d85-122">Provides information about the IP phones currently in use in the organization.</span></span> <span data-ttu-id="b4d85-123">该报告基于电话注册和登录。</span><span class="sxs-lookup"><span data-stu-id="b4d85-123">The report is based on phone registrations and logons.</span></span> <span data-ttu-id="b4d85-124">不应将其视为完整的清单。</span><span class="sxs-lookup"><span data-stu-id="b4d85-124">It should not be considered a complete inventory.</span></span> <span data-ttu-id="b4d85-125">例如，您可能已删除仍在报告中列出的手机，因为他们至少登录一次。</span><span class="sxs-lookup"><span data-stu-id="b4d85-125">For example, you might have removed phones that are still listed in the report because they logged on at least once.</span></span> <span data-ttu-id="b4d85-126">同样，您还可能有新的手机不会显示在报告中，只是因为用户尚未登录 Lync Server 及其新手机。</span><span class="sxs-lookup"><span data-stu-id="b4d85-126">Likewise, you might also have new phones that do not show up in the report simply because users have not logged on to Lync Server with their new phones yet.</span></span>

  - [<span data-ttu-id="b4d85-127">Lync Server 2013 中的呼叫允许控制报告</span><span class="sxs-lookup"><span data-stu-id="b4d85-127">Call Admission Control Report in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-report.md)
    
    <span data-ttu-id="b4d85-p107">提供使用呼叫允许控制的点对点活动和会议活动的列表。呼叫允许控制 (CAC) 是一种确定是否应根据带宽限制允许建立实时通信会话（如语音呼叫或视频呼叫）的方法。</span><span class="sxs-lookup"><span data-stu-id="b4d85-p107">Provides a list of peer-to-peer and conference activities that use call admission control. Call admission control (CAC) is a way of determining whether you should allow real-time communications sessions, such as voice or video calls, based on bandwidth constraints.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

