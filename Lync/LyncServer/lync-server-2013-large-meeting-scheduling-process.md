---
title: 'Lync Server 2013: 大型会议日程安排过程'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Large-meeting scheduling process
ms:assetid: de267458-885f-4176-a8d7-1a218e67640e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205334(v=OCS.15)
ms:contentKeyID: 48185639
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af97cdbd07603c420780a92fbbe0a03c8a4d0520
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="large-meeting-scheduling-process-in-lync-server-2013"></a><span data-ttu-id="352e1-102">Lync Server 2013 中的大型会议日程安排流程</span><span class="sxs-lookup"><span data-stu-id="352e1-102">Large-meeting scheduling process in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="352e1-103">_**主题上次修改时间:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="352e1-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="352e1-104">由于在专用大型会议池上一次仅支持一个大型会议, 因此我们建议实施大型会议安排流程以帮助防止大型会议冲突。</span><span class="sxs-lookup"><span data-stu-id="352e1-104">Because only one large meeting at a time is supported on the dedicated large meeting pool, we recommend implementing a large meeting scheduling process to help prevent large meeting conflicts.</span></span> <span data-ttu-id="352e1-105">此计划过程的目的是帮助设置大型会议。</span><span class="sxs-lookup"><span data-stu-id="352e1-105">The purpose of such the scheduling process is to facilitate setting up large meetings.</span></span> <span data-ttu-id="352e1-106">Lync Server 或 Lync Server 客户端不直接提供此类功能。</span><span class="sxs-lookup"><span data-stu-id="352e1-106">Such capability is not provided directly by Lync Server or Lync Server clients.</span></span> <span data-ttu-id="352e1-107">实施此类过程的一个方法是使用组织支持团队的票证系统（如果有的话）。</span><span class="sxs-lookup"><span data-stu-id="352e1-107">One way to implement such a process is to use your organization’s support team’s ticketing system, if available.</span></span>

<span data-ttu-id="352e1-108">对于大型会议的组织者, 安排大型会议需要完成以下步骤:</span><span class="sxs-lookup"><span data-stu-id="352e1-108">For organizers of large meetings, scheduling a large meeting involves completing the following steps:</span></span>

1.  <span data-ttu-id="352e1-p102">会议组织者或代理人决定即将举行的会议的时间、持续时间、规模以及演示者列表。如果预期会议规模超过 250 名用户或者要确保为少于 250 名用户的会议提供最佳用户体验，组织者或代理人应提交大型会议请求。</span><span class="sxs-lookup"><span data-stu-id="352e1-p102">The meeting organizer or delegate determines the time, duration, and size of an upcoming meeting, in addition to the list of presenters. If the anticipated meeting size exceeds 250 users or to ensure the best user experience for a meeting of fewer than 250 users, the organizer or the delegate submits a request for a large meeting.</span></span>

2.  <span data-ttu-id="352e1-p103">计划人员检查申请日期和时间是否可行。由于专用池一次仅支持一个大型会议，计划人员需要检查大型会议日历，以确定申请日期和时间是否计划了其他会议。如果申请的时间可行，计划人员将批准会议请求。</span><span class="sxs-lookup"><span data-stu-id="352e1-p103">The scheduling staff checks to see whether the requested date and time is available. Since we support only a single large meeting on the dedicated pool at a time, the scheduling staff needs to check the large-meeting calendar to determine whether there is another meeting scheduled for the requested date and time. If the requested time is available, the staff approves the meeting request.</span></span>

3.  <span data-ttu-id="352e1-114">如果请求已获批准, 则计划人员 (使用专用池上的凭据) 使用适用于 Lync 2013 的联机会议加载项在专用大型会议池中设置会议。</span><span class="sxs-lookup"><span data-stu-id="352e1-114">If the request is approved, the scheduling staff (using credentials on the dedicated pool) uses Online Meeting Add-in for Lync 2013 with Outlook to set up a meeting on the dedicated large-meeting pool.</span></span> <span data-ttu-id="352e1-115">用于加入会议的 URL 将作为批准通知的一部分提供给申请者。</span><span class="sxs-lookup"><span data-stu-id="352e1-115">The URL to be used to join the meeting is provided to the requester as part of the approval notice.</span></span>

4.  <span data-ttu-id="352e1-p105">会议组织者或代理人使用 Outlook 计划即将到来的会议，将用于加入会议的 URL 添加到会议邀请中。会议组织者或代理人随后指定要邀请的用户并发出会议邀请。</span><span class="sxs-lookup"><span data-stu-id="352e1-p105">The meeting organizer or delegate uses Outlook to schedule the upcoming meeting, adding the URL for joining the meeting to the meeting invitation. The meeting organizer or delegate then specifies the users to be invited and sends out the meeting invitation.</span></span>
    
    <span data-ttu-id="352e1-118">下图显示了用于安排大型会议的典型请求和审批工作流。</span><span class="sxs-lookup"><span data-stu-id="352e1-118">The following figure illustrates a typical request and approval workflow for scheduling large meetings.</span></span>
    
    <span data-ttu-id="352e1-119">![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")</span><span class="sxs-lookup"><span data-stu-id="352e1-119">![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")</span></span>  

</div>

<span> </span>

</div>

</div>

</div>

