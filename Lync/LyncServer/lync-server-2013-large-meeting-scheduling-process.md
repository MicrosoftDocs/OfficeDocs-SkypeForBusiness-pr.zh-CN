---
title: Lync Server 2013：大型会议日程安排过程
description: Lync Server 2013：大型会议计划过程。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Large-meeting scheduling process
ms:assetid: de267458-885f-4176-a8d7-1a218e67640e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205334(v=OCS.15)
ms:contentKeyID: 48185639
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96d383b6da96fb7d36e031485feac2ff927df347
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557588"
---
# <a name="large-meeting-scheduling-process-in-lync-server-2013"></a><span data-ttu-id="16c01-103">Lync Server 2013 中的大型会议日程安排过程</span><span class="sxs-lookup"><span data-stu-id="16c01-103">Large-meeting scheduling process in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16c01-104">_**上次修改的主题：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="16c01-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="16c01-105">由于专用大型会议池一次仅支持一个大型会议，因此我们建议实施大型会议日程安排过程来帮助防止大型会议冲突。</span><span class="sxs-lookup"><span data-stu-id="16c01-105">Because only one large meeting at a time is supported on the dedicated large meeting pool, we recommend implementing a large meeting scheduling process to help prevent large meeting conflicts.</span></span> <span data-ttu-id="16c01-106">此计划过程的目的是为了便于设置大型会议。</span><span class="sxs-lookup"><span data-stu-id="16c01-106">The purpose of such the scheduling process is to facilitate setting up large meetings.</span></span> <span data-ttu-id="16c01-107">Lync Server 或 Lync Server 客户端不会直接提供此类功能。</span><span class="sxs-lookup"><span data-stu-id="16c01-107">Such capability is not provided directly by Lync Server or Lync Server clients.</span></span> <span data-ttu-id="16c01-108">实施此类过程的一种方法是使用贵组织的支持团队的票证系统（如果有）。</span><span class="sxs-lookup"><span data-stu-id="16c01-108">One way to implement such a process is to use your organization’s support team’s ticketing system, if available.</span></span>

<span data-ttu-id="16c01-109">对于大型会议的组织者，安排大型会议需要完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="16c01-109">For organizers of large meetings, scheduling a large meeting involves completing the following steps:</span></span>

1.  <span data-ttu-id="16c01-110">会议组织者或代理人决定了即将召开的会议的时间、持续时间和大小，以及演示者列表。</span><span class="sxs-lookup"><span data-stu-id="16c01-110">The meeting organizer or delegate determines the time, duration, and size of an upcoming meeting, in addition to the list of presenters.</span></span> <span data-ttu-id="16c01-111">如果预期的会议大小超过250个用户，或者为了确保会议的用户体验少于250个用户，则组织者或代理人将提交大型会议的请求。</span><span class="sxs-lookup"><span data-stu-id="16c01-111">If the anticipated meeting size exceeds 250 users or to ensure the best user experience for a meeting of fewer than 250 users, the organizer or the delegate submits a request for a large meeting.</span></span>

2.  <span data-ttu-id="16c01-112">计划员工检查以查看是否有请求的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="16c01-112">The scheduling staff checks to see whether the requested date and time is available.</span></span> <span data-ttu-id="16c01-113">由于我们一次仅支持专用池上的一个大型会议，因此计划员工需要检查大型会议日历，以确定是否为请求的日期和时间安排了另一个会议。</span><span class="sxs-lookup"><span data-stu-id="16c01-113">Since we support only a single large meeting on the dedicated pool at a time, the scheduling staff needs to check the large-meeting calendar to determine whether there is another meeting scheduled for the requested date and time.</span></span> <span data-ttu-id="16c01-114">如果请求的时间可用，员工将批准会议请求。</span><span class="sxs-lookup"><span data-stu-id="16c01-114">If the requested time is available, the staff approves the meeting request.</span></span>

3.  <span data-ttu-id="16c01-115">如果请求得到批准，则计划员工 (使用专用池上的凭据) 将 Lync 2013 的联机会议外接程序用于 Outlook，以便在专用大型会议池上设置会议。</span><span class="sxs-lookup"><span data-stu-id="16c01-115">If the request is approved, the scheduling staff (using credentials on the dedicated pool) uses Online Meeting Add-in for Lync 2013 with Outlook to set up a meeting on the dedicated large-meeting pool.</span></span> <span data-ttu-id="16c01-116">作为审批通知的一部分，将用于加入会议的 URL 提供给申请者。</span><span class="sxs-lookup"><span data-stu-id="16c01-116">The URL to be used to join the meeting is provided to the requester as part of the approval notice.</span></span>

4.  <span data-ttu-id="16c01-117">会议组织者或代理人使用 Outlook 安排即将召开的会议，并将用于加入会议的 URL 添加到会议邀请中。</span><span class="sxs-lookup"><span data-stu-id="16c01-117">The meeting organizer or delegate uses Outlook to schedule the upcoming meeting, adding the URL for joining the meeting to the meeting invitation.</span></span> <span data-ttu-id="16c01-118">会议组织者或代理人将指定被邀请的用户并发出会议邀请。</span><span class="sxs-lookup"><span data-stu-id="16c01-118">The meeting organizer or delegate then specifies the users to be invited and sends out the meeting invitation.</span></span>
    
    <span data-ttu-id="16c01-119">下图说明了用于安排大型会议的典型请求和审批工作流。</span><span class="sxs-lookup"><span data-stu-id="16c01-119">The following figure illustrates a typical request and approval workflow for scheduling large meetings.</span></span>
    
    <span data-ttu-id="16c01-120">![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")</span><span class="sxs-lookup"><span data-stu-id="16c01-120">![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")</span></span>  

</div>

<span> </span>

</div>

</div>

</div>

