---
title: Lync Server 2013：组呼叫装货概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Group Call Pickup
ms:assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945623(v=OCS.15)
ms:contentKeyID: 51541466
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9001d3e89e07943915b923ec4bfa8abf2683c78
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216258"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="f8fc9-102">Lync Server 2013 中的组内呼叫装货概述</span><span class="sxs-lookup"><span data-stu-id="f8fc9-102">Overview of Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8fc9-103">_**上次修改的主题：** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="f8fc9-103">_**Topic Last Modified:** 2013-02-12_</span></span>

<span data-ttu-id="f8fc9-104">组呼叫应答（Lync Server 2013 的累积更新中的新功能：2月2013）允许用户将传入呼叫从其自己的电话应答给其同事。</span><span class="sxs-lookup"><span data-stu-id="f8fc9-104">Group Call Pickup, a new feature in Cumulative Updates for Lync Server 2013: February 2013, lets users answer incoming calls to their colleagues from their own phones.</span></span> <span data-ttu-id="f8fc9-105">此新功能通过让其他用户可以通过拨打呼叫应答组号码来应答传入呼叫，从而提高用户线路的可用性。</span><span class="sxs-lookup"><span data-stu-id="f8fc9-105">This new feature increases the availability of a user's line by enabling other users to answer an incoming call by dialing a call pickup group number.</span></span> <span data-ttu-id="f8fc9-106">当部署组呼叫应答时，路由到语音邮件的传入呼叫的数量会大大减少，这对于来自组织外部的客户的呼叫尤其有用。</span><span class="sxs-lookup"><span data-stu-id="f8fc9-106">When Group Call Pickup is deployed, the number of incoming calls that are routed to voice mail can be significantly reduced, which is particularly useful for calls from customers who are external to your organization.</span></span>

<span data-ttu-id="f8fc9-107">组内呼叫应答功能专为在打开的 office 环境中的业务单位而设计。</span><span class="sxs-lookup"><span data-stu-id="f8fc9-107">The Group Call Pickup feature is designed in particular for business units in open office environments.</span></span> <span data-ttu-id="f8fc9-108">传入呼叫不会造成中断，因为它们仅在预期目标进行环。</span><span class="sxs-lookup"><span data-stu-id="f8fc9-108">Incoming calls are not disruptive because they ring only at the intended destination.</span></span> <span data-ttu-id="f8fc9-109">但是，其他听到此铃声的用户仍可以通过拨打组号码来直接接听呼叫。</span><span class="sxs-lookup"><span data-stu-id="f8fc9-109">Other users who hear the ring, however, can still pick up the call simply by dialing the group number.</span></span>

<span data-ttu-id="f8fc9-110">在用户不位于开放办公室布局中的环境中，或在地理上分布有共同职责的用户时，工作组呼叫将提供最合适的解决方案。</span><span class="sxs-lookup"><span data-stu-id="f8fc9-110">In environments where users are not located in an open office layout, or where users who share a common responsibility are geographically distributed, team call presents the most suitable solution.</span></span> <span data-ttu-id="f8fc9-111">组呼叫应答和团队呼叫之间的主要区别在于，使用组内呼叫应答，传入呼叫只会在预期的目的地振铃，但任何人都仍可以通过拨打组号码来选择应答。</span><span class="sxs-lookup"><span data-stu-id="f8fc9-111">The primary difference between Group Call Pickup and team call is that, with Group Call Pickup, an incoming call rings only at the intended destination, but anyone can still choose to answer it by dialing a group number.</span></span> <span data-ttu-id="f8fc9-112">使用团队呼叫时，呼叫会在所有团队成员的电话中响铃，并且团队中的任何用户都可以接听电话以应答呼叫。</span><span class="sxs-lookup"><span data-stu-id="f8fc9-112">With team call, the call rings at all the team members' phones, and any user in the team can pick up the phone to answer the call.</span></span> <span data-ttu-id="f8fc9-113">组呼叫应答和团队呼叫之间的其他区别在于组呼叫应答由管理员通过 Lync Server 进行管理。</span><span class="sxs-lookup"><span data-stu-id="f8fc9-113">An additional difference between Group Call Pickup and team call is that Group Call Pickup is managed by an administrator, through Lync Server.</span></span> <span data-ttu-id="f8fc9-114">通过团队呼叫，最终用户使用 Lync 客户端管理功能。</span><span class="sxs-lookup"><span data-stu-id="f8fc9-114">With team call, end users manage the feature by using the Lync client.</span></span> <span data-ttu-id="f8fc9-115">因此，使用组间电话取货，可以集中管理呼叫管理的这一方面。</span><span class="sxs-lookup"><span data-stu-id="f8fc9-115">With Group Call Pickup, therefore, this aspect of call management can be centralized.</span></span>

<span data-ttu-id="f8fc9-116">组内呼叫应答是在呼叫寄存应用程序上建立的。</span><span class="sxs-lookup"><span data-stu-id="f8fc9-116">Group Call Pickup is built on the Call Park application.</span></span> <span data-ttu-id="f8fc9-117">在部署组内呼叫应答时，可以使用指定为呼叫应答组号码的单独范围的分机号来配置呼叫寄存通道表。</span><span class="sxs-lookup"><span data-stu-id="f8fc9-117">When you deploy Group Call Pickup, you configure the call park orbit table with separate ranges of extension numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="f8fc9-118">与呼叫寄存通道一样，呼叫应答组号码必须是没有向其分配用户或电话的虚拟分机号码。</span><span class="sxs-lookup"><span data-stu-id="f8fc9-118">Like call park orbit numbers, call pickup group numbers must be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="f8fc9-119">您在其中部署组内呼叫应答的每个前端池都可以有一个或多个呼叫应答组号码范围。</span><span class="sxs-lookup"><span data-stu-id="f8fc9-119">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="f8fc9-120">在 Lync Server 部署中，组号范围必须是全局唯一的。</span><span class="sxs-lookup"><span data-stu-id="f8fc9-120">The group number ranges must be globally unique across the Lync Server deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f8fc9-121">在呼叫寄存通道表中指定为组呼叫应答表的号码范围不能通过使用 Lync Server 控制面板进行管理或查看。</span><span class="sxs-lookup"><span data-stu-id="f8fc9-121">Number ranges that are designated as Group Call Pickup numbers in the call park orbit table cannot be managed or viewed by using the Lync Server Control Panel.</span></span> <span data-ttu-id="f8fc9-122">查看呼叫寄存通道表中的所有号码范围的唯一方法是使用 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="f8fc9-122">The only way to see all the number ranges in the call park orbit table is to use Lync Server Management Shell.</span></span> <span data-ttu-id="f8fc9-123">同样，添加、修改或删除组呼叫应答号码的唯一方法是使用 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="f8fc9-123">Similarly, the only way to add, modify, or remove Group Call Pickup numbers is to use Lync Server Management Shell.</span></span>



</div>

<span data-ttu-id="f8fc9-124">配置呼叫应答组号码之后，将用户分配给呼叫应答组。</span><span class="sxs-lookup"><span data-stu-id="f8fc9-124">After you configure the call pickup group numbers, you assign users to a call pickup group.</span></span> <span data-ttu-id="f8fc9-125">分配给呼叫应答组的任何用户都可以通过其他用户应答其呼叫。</span><span class="sxs-lookup"><span data-stu-id="f8fc9-125">Any user who is assigned to a call pickup group can have their calls answered by other users.</span></span> <span data-ttu-id="f8fc9-126">当呼叫到达分配给呼叫应答组的用户时，任何其他通知呼叫的用户都可以通过手动拨打呼叫应答组号码来应答该呼叫。</span><span class="sxs-lookup"><span data-stu-id="f8fc9-126">When a call comes in to a user who is assigned to a call pickup group, any other user who notices the call can answer it by manually dialing the call pickup group number.</span></span> <span data-ttu-id="f8fc9-127">选取呼叫的用户不需要是组的成员。</span><span class="sxs-lookup"><span data-stu-id="f8fc9-127">The user who picks up the call does not need to be a member of the group.</span></span> <span data-ttu-id="f8fc9-128">当由另一个用户接听呼叫时，会向最初调用的号码发送一个通知。</span><span class="sxs-lookup"><span data-stu-id="f8fc9-128">When a call is picked up by another user, a notification is sent to the number originally called.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f8fc9-129">一个用户只能是一个呼叫装货组的成员。</span><span class="sxs-lookup"><span data-stu-id="f8fc9-129">A user can be a member of only one call pickup group.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="f8fc9-130">尽管 Lync Server 部署中的任何用户都可以接听呼叫应答组成员的呼叫，但应答呼叫的人必须知道正确的呼叫应答组号码才能进行拨号。</span><span class="sxs-lookup"><span data-stu-id="f8fc9-130">Although any user in the Lync Server deployment can answer a call to a call pickup group member, the person answering the call must know the correct call pickup group number to dial.</span></span>



</div>

<span data-ttu-id="f8fc9-131">当组中的多个电话响铃时，如果用户拨打呼叫应答组号码应答呼叫，则用户将应答已响铃最长的呼叫。</span><span class="sxs-lookup"><span data-stu-id="f8fc9-131">If a user dials a call pickup group number to answer a call when multiple phones in the group are ringing, the user answers the call that has been ringing the longest.</span></span>

<span data-ttu-id="f8fc9-132">同时响铃设置将适用于具有组呼叫应答的用户。</span><span class="sxs-lookup"><span data-stu-id="f8fc9-132">Simultaneous ringing settings will work for users who have group call pickup.</span></span> <span data-ttu-id="f8fc9-133">也就是说，对具有组呼叫应答的用户进行的呼叫将会响铃所有已配置的目标，而另一个用户可以应答呼叫。</span><span class="sxs-lookup"><span data-stu-id="f8fc9-133">That is, a call made to a user who has Group Call Pickup will ring for all the configured destinations, and another user can answer the call.</span></span> <span data-ttu-id="f8fc9-134">此规则的例外是当用户配置同时响铃以呼叫所有团队成员时。</span><span class="sxs-lookup"><span data-stu-id="f8fc9-134">The exception to this rule is when the user configures simultaneous ringing to call all the team members.</span></span>

<span data-ttu-id="f8fc9-135">无法使用组呼叫应答来回答以下类型的呼叫：</span><span class="sxs-lookup"><span data-stu-id="f8fc9-135">Group Call Pickup cannot be used to answer the following types of calls:</span></span>

  - <span data-ttu-id="f8fc9-136">对专用线路的呼叫</span><span class="sxs-lookup"><span data-stu-id="f8fc9-136">Calls to a private line</span></span>

  - <span data-ttu-id="f8fc9-137">来自已被分配了好友和家人隐私关系的联系人的呼叫</span><span class="sxs-lookup"><span data-stu-id="f8fc9-137">Calls from a contact who has been assigned the Friends and Family privacy relationship</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="f8fc9-138">作为呼叫应答组成员的用户可以通过将联系人标记为 Lync 客户端中的个人联系人，来防止通过组呼叫应答检索某些呼叫。</span><span class="sxs-lookup"><span data-stu-id="f8fc9-138">A user who is a member of a call pickup group can prevent certain calls from being retrieved through Group Call Pickup by marking the contact as a personal contact in the Lync client.</span></span> <span data-ttu-id="f8fc9-139">若要将联系人标记为个人联系人，请将联系人的隐私关系设置为 "好友" 和 "家人"。</span><span class="sxs-lookup"><span data-stu-id="f8fc9-139">To mark a contact as a personal contact, set the Privacy Relationship for the contact to Friends and Family.</span></span> <span data-ttu-id="f8fc9-140">无法通过使用组呼叫应答来检索从具有 "隐私关系" 设置为 "朋友和家人" 的联系人的任何传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="f8fc9-140">Any incoming call from contacts with the Privacy Relationship set to Friends and Family cannot be retrieved by using Group Call Pickup.</span></span>

    
    </div>

  - <span data-ttu-id="f8fc9-141">音频/视频呼叫的视频部分</span><span class="sxs-lookup"><span data-stu-id="f8fc9-141">Video portion of audio/video calls</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f8fc9-142">如果用户应答音频/视频呼叫，则用户只接收音频。</span><span class="sxs-lookup"><span data-stu-id="f8fc9-142">If a user answers an audio/video call, the user receives only the audio.</span></span> <span data-ttu-id="f8fc9-143">呼叫者或应答呼叫的人员可以升级呼叫以添加视频。</span><span class="sxs-lookup"><span data-stu-id="f8fc9-143">Either the person calling or the person answering the call can escalate the call to add video.</span></span>

    
    </div>

  - <span data-ttu-id="f8fc9-144">路由到团队呼叫成员的同时响铃呼叫</span><span class="sxs-lookup"><span data-stu-id="f8fc9-144">Simultaneous ringing calls that are routed to team call members</span></span>

  - <span data-ttu-id="f8fc9-145">路由到代理的呼叫</span><span class="sxs-lookup"><span data-stu-id="f8fc9-145">Calls routed to a delegate</span></span>

  - <span data-ttu-id="f8fc9-146">路由到响应组的呼叫</span><span class="sxs-lookup"><span data-stu-id="f8fc9-146">Calls routed to a response group</span></span>

<span data-ttu-id="f8fc9-147">以下类型的用户不能参与组内呼叫应答。</span><span class="sxs-lookup"><span data-stu-id="f8fc9-147">The following types of users cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="f8fc9-148">即，不应将它们包含在组内呼叫应答组中，并且不能为启用了组内呼叫应答的用户接听呼叫。</span><span class="sxs-lookup"><span data-stu-id="f8fc9-148">That is, they should not be included in a Group Call Pickup group, and they cannot pick up calls for users who have Group Call Pickup enabled.</span></span>

  - <span data-ttu-id="f8fc9-149">在混合部署中托管联机的用户</span><span class="sxs-lookup"><span data-stu-id="f8fc9-149">Users who are homed online in a hybrid deployment</span></span>

  - <span data-ttu-id="f8fc9-150">没有驻留在 lync server 2013 池中且具有对 Lync Server 2013 的累积更新的用户：本地部署中的二月2013</span><span class="sxs-lookup"><span data-stu-id="f8fc9-150">Users who are not homed on a Lync Server 2013 pool with Cumulative Updates for Lync Server 2013: February 2013 in an on-premises deployment</span></span>

<span data-ttu-id="f8fc9-151">如果没有人应答对呼叫应答组的成员的呼叫，则该呼叫将按客户端设置中指定的顺序进行路由。</span><span class="sxs-lookup"><span data-stu-id="f8fc9-151">If no one answers a call to a member of a call pickup group, the call is routed as specified in the client settings.</span></span> <span data-ttu-id="f8fc9-152">也就是说，呼叫转到语音邮件或转发到其他目标，如客户端设置中所指定。</span><span class="sxs-lookup"><span data-stu-id="f8fc9-152">That is, the call goes to voicemail or is forwarded to a different destination, as specified in the client settings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

