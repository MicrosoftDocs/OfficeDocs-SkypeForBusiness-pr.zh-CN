---
title: Lync Server 2013：会议的计划详细信息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scheduling details
ms:assetid: 39ca6fff-2c15-4347-9f1f-6c8687a39a49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204823(v=OCS.15)
ms:contentKeyID: 48183910
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7dd61ce47daf1898afd1fb654493ef12ebee9ff1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200969"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scheduling-details-for-meetings-in-lync-server-2013"></a><span data-ttu-id="3a160-102">Lync Server 2013 中会议的日程安排详细信息</span><span class="sxs-lookup"><span data-stu-id="3a160-102">Scheduling details for meetings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a160-103">_**上次修改的主题：** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="3a160-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="3a160-104">检查确保在请求的时间没有安排其他会议后，处理请求的大型会议支持人员将在大型会议池中安排会议。</span><span class="sxs-lookup"><span data-stu-id="3a160-104">After checking to ensure that no other meeting is scheduled at the requested time, the large meeting support staff that handles the request schedules the meeting on the large-meeting pool.</span></span> <span data-ttu-id="3a160-105">使用与 Lync Server 2013 客户端一起安装的 lync 的联机会议外接程序，以使用在专用大型会议池中启用了 Lync Server 的用户的凭据来执行此任务。</span><span class="sxs-lookup"><span data-stu-id="3a160-105">Use the Online Meeting Add-in for Lync that is installed with the Lync Server 2013 client to perform this task, using the credentials of a user enabled for Lync Server in the dedicated large-meeting pool.</span></span>

<span data-ttu-id="3a160-106">若要确保最佳用户体验，应使用适用于会议组织者的需求的合适访问级别和会议设置安排大型会议，这点很重要。</span><span class="sxs-lookup"><span data-stu-id="3a160-106">To ensure the best user experience, it is important to schedule the large meeting with the right access levels and meeting settings that are appropriate to the meeting organizer’s needs.</span></span> <span data-ttu-id="3a160-107">建议在 Lync 会议选项中配置以下计划设置：</span><span class="sxs-lookup"><span data-stu-id="3a160-107">We recommend the following scheduling settings configured in Lync Meeting options:</span></span>

  - <span data-ttu-id="3a160-108">对每个大型会议使用新的会议空间而不重用专用会议空间。</span><span class="sxs-lookup"><span data-stu-id="3a160-108">Use a new meeting space for each large meeting instead of reusing the dedicated meeting space.</span></span>

  - <span data-ttu-id="3a160-109">按以下方式指定会议访问级别：</span><span class="sxs-lookup"><span data-stu-id="3a160-109">Specify the meeting access level as follows:</span></span>
    
      - <span data-ttu-id="3a160-p103">如果至少有一个被邀请者在组织外部，则将会议访问类型设置为**任何人（无限制**）。这样，您在会议过程中便无需管理可能较大的会议厅。</span><span class="sxs-lookup"><span data-stu-id="3a160-p103">If at least one invitee is external to the organization, set the meeting access type to **Anyone (no restrictions**. This enables you to avoid having to manage a potentially large lobby when the meeting is in progress.</span></span>
    
      - <span data-ttu-id="3a160-112">如果会议是仅针对内部的会议，则将会议访问类型设置为**我的组织中的任何人**。</span><span class="sxs-lookup"><span data-stu-id="3a160-112">If the meeting is an internal-only meeting, set the meeting access type to **Anyone from my organization**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="3a160-113">避免将会议访问类型设置为<STRONG>从我的公司邀请的人员</STRONG>，因为当您使用此设置时，组织者必须将所有用户电子邮件地址添加到被邀请者列表，且您无法邀请通讯组。</span><span class="sxs-lookup"><span data-stu-id="3a160-113">Avoid setting the meeting access type to <STRONG>People I invite from my company</STRONG> because when you use this setting, organizers must add all user email addresses to the invitee list and you cannot invite a distribution group.</span></span><BR><span data-ttu-id="3a160-p104">避免将会议访问类型设置为<STRONG>只有我（会议组织者）</STRONG>，因为此设置要求在会议运行时必须将每个会议参与者（包括演示者）置于会议厅中。负责主持大型会议的人员随后必须持续监视会议厅名单并允许位于会议厅中的新用户加入会议。</span><span class="sxs-lookup"><span data-stu-id="3a160-p104">Avoid setting the meeting access type to <STRONG>Only me, the meeting organizer</STRONG> because this setting requires that every meeting participant, including presenters, must be put in the lobby at meeting run time. The person responsible for running the large meeting must then constantly monitor the lobby roster and admit new users who are in the lobby.</span></span>

        
        </div>

  - <span data-ttu-id="3a160-116">允许用电话拨入的用户通过选中“呼叫者直接参与”\*\*\*\* 设置自动进入会议。</span><span class="sxs-lookup"><span data-stu-id="3a160-116">Allow users who dial-in from phones to enter the meeting automatically by checking the **Callers get in directly** setting.</span></span>

  - <span data-ttu-id="3a160-117">显式邀请以下用户：</span><span class="sxs-lookup"><span data-stu-id="3a160-117">Explicitly invite the following users:</span></span>
    
      - <span data-ttu-id="3a160-118">会议组织者和代理人（请求者）</span><span class="sxs-lookup"><span data-stu-id="3a160-118">Meeting organizer and delegate (requester)</span></span>
    
      - <span data-ttu-id="3a160-119">会议请求者提供的演示者的列表</span><span class="sxs-lookup"><span data-stu-id="3a160-119">The list of presenters provided by a meeting requester</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3a160-120">如果会议访问类型设置为<STRONG>我选择的人员</STRONG>，则需要将大型会议的每个参与者作为会议的被邀请者显式添加。</span><span class="sxs-lookup"><span data-stu-id="3a160-120">If the meeting access type is set to <STRONG>People I choose</STRONG>, you need to explicitly add each participant of a large meeting as an invitee of the meeting.</span></span>

    
    </div>

  - <span data-ttu-id="3a160-p105">显式管理演示者，而不用将演示者选项设置为自动升级值之一。确保将以下用户作为演示者添加：</span><span class="sxs-lookup"><span data-stu-id="3a160-p105">Explicitly manage presenters, instead of setting the presenter option to one of the auto-promote values. Be sure to add the following users as presenters:</span></span>
    
      - <span data-ttu-id="3a160-123">会议组织者和代理人（请求者）</span><span class="sxs-lookup"><span data-stu-id="3a160-123">Meeting organizer and delegate (requester)</span></span>
    
      - <span data-ttu-id="3a160-124">大型会议请求者提供的演示者的列表</span><span class="sxs-lookup"><span data-stu-id="3a160-124">The list of presenters provided by large meeting requesters</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3a160-p106">通过显式管理演示者，您可以控制演示者的数量，以便将其限制为足够小的数量，从而有可能获得有效的大型会议。如果大多数会议参与者都具有与会者角色，则有助于减少人员意外获得对演示的控制权、删除 PowerPoint 演示、将演示者设为静音/取消静音以及对会议的其他中断的机会。</span><span class="sxs-lookup"><span data-stu-id="3a160-p106">By explicitly managing presenters, you can control the number of presenters, so that you can limit presenters to a small enough number to make it possible to have an effective large meeting. If the majority of meeting participants have the attendee role, it helps reduce the chance of people accidentally taking control of the presentation, deleting a PowerPoint presentation, muting/unmuting presenters, and other disruptions to the meeting.</span></span>

    
    </div>

  - <span data-ttu-id="3a160-127">选中“将所有与会者设为静音”\*\*\*\* 设置以确保只有演示者能将音频广播到会议中。</span><span class="sxs-lookup"><span data-stu-id="3a160-127">Check the **Mute all attendees** setting to make sure that only presenters can broadcast audio into the meeting.</span></span>

  - <span data-ttu-id="3a160-128">选中“阻止与会者的视频”\*\*\*\* 设置以确保只有参与者能将视频广播到会议中。</span><span class="sxs-lookup"><span data-stu-id="3a160-128">Check the **Block attendees’ video** setting to make sure only presenters can broadcast video into the meeting.</span></span>

<span data-ttu-id="3a160-129">下图显示了适用于 Lync 的联机会议外接程序的推荐设置。</span><span class="sxs-lookup"><span data-stu-id="3a160-129">The following figure shows the recommended settings for the Online Meeting Add-in for Lync.</span></span>

<span data-ttu-id="3a160-130">![54e4e70d-06b0-45cd-8d94-bab649cd5dc0](images/JJ204823.54e4e70d-06b0-45cd-8d94-bab649cd5dc0(OCS.15).jpg "54e4e70d-06b0-45cd-8d94-bab649cd5dc0")</span><span class="sxs-lookup"><span data-stu-id="3a160-130">![54e4e70d-06b0-45cd-8d94-bab649cd5dc0](images/JJ204823.54e4e70d-06b0-45cd-8d94-bab649cd5dc0(OCS.15).jpg "54e4e70d-06b0-45cd-8d94-bab649cd5dc0")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

