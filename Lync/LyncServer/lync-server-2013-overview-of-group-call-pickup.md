---
title: 'Lync Server 2013: 组呼叫装货概述'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of Group Call Pickup
ms:assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945623(v=OCS.15)
ms:contentKeyID: 51541466
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 132d987b7d8007873a27cd74aacfc11e0c882c39
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825476"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="49436-102">Lync Server 2013 中的组呼叫装货概述</span><span class="sxs-lookup"><span data-stu-id="49436-102">Overview of Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49436-103">_**主题上次修改时间:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="49436-103">_**Topic Last Modified:** 2013-02-12_</span></span>

<span data-ttu-id="49436-104">组呼叫分拣, Lync Server 2013 的累积更新中的新功能: 2 月 2013, 允许用户通过其自己的电话应答传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="49436-104">Group Call Pickup, a new feature in Cumulative Updates for Lync Server 2013: February 2013, lets users answer incoming calls to their colleagues from their own phones.</span></span> <span data-ttu-id="49436-105">此新功能通过拨打呼叫装货组号码使其他用户能够接听传入呼叫, 从而提高用户线路的可用性。</span><span class="sxs-lookup"><span data-stu-id="49436-105">This new feature increases the availability of a user's line by enabling other users to answer an incoming call by dialing a call pickup group number.</span></span> <span data-ttu-id="49436-106">当部署组呼叫时, 路由到语音邮件的传入呼叫数可能会显著减少, 这对于来自组织外部的客户的呼叫尤其有用。</span><span class="sxs-lookup"><span data-stu-id="49436-106">When Group Call Pickup is deployed, the number of incoming calls that are routed to voice mail can be significantly reduced, which is particularly useful for calls from customers who are external to your organization.</span></span>

<span data-ttu-id="49436-107">组呼叫功能专为打开的 office 环境中的业务单位而设计。</span><span class="sxs-lookup"><span data-stu-id="49436-107">The Group Call Pickup feature is designed in particular for business units in open office environments.</span></span> <span data-ttu-id="49436-108">传入呼叫不是破坏性的，因为这些呼叫只会在指定目标响铃。</span><span class="sxs-lookup"><span data-stu-id="49436-108">Incoming calls are not disruptive because they ring only at the intended destination.</span></span> <span data-ttu-id="49436-109">但是，听到该响铃的其他用户仍可以通过拨打组号码来接听该呼叫。</span><span class="sxs-lookup"><span data-stu-id="49436-109">Other users who hear the ring, however, can still pick up the call simply by dialing the group number.</span></span>

<span data-ttu-id="49436-110">在用户不在开放的 office 布局中的环境中, 或者在地理上分布有共同责任的用户的情况下, 工作组通话将提供最合适的解决方案。</span><span class="sxs-lookup"><span data-stu-id="49436-110">In environments where users are not located in an open office layout, or where users who share a common responsibility are geographically distributed, team call presents the most suitable solution.</span></span> <span data-ttu-id="49436-111">组呼叫挑选和团队呼叫之间的主要区别是, 使用组呼叫装货, 传入呼叫仅在预期目标位置响铃, 但任何人仍可通过拨组号码选择来应答。</span><span class="sxs-lookup"><span data-stu-id="49436-111">The primary difference between Group Call Pickup and team call is that, with Group Call Pickup, an incoming call rings only at the intended destination, but anyone can still choose to answer it by dialing a group number.</span></span> <span data-ttu-id="49436-112">通过团队通话, 呼叫将在所有团队成员的电话上响铃, 团队中的任何用户都可以接听电话来接听呼叫。</span><span class="sxs-lookup"><span data-stu-id="49436-112">With team call, the call rings at all the team members' phones, and any user in the team can pick up the phone to answer the call.</span></span> <span data-ttu-id="49436-113">组呼叫和团队通话之间的其他区别在于组呼叫由管理员通过 Lync Server 管理。</span><span class="sxs-lookup"><span data-stu-id="49436-113">An additional difference between Group Call Pickup and team call is that Group Call Pickup is managed by an administrator, through Lync Server.</span></span> <span data-ttu-id="49436-114">使用团队呼叫, 最终用户通过使用 Lync 客户端来管理功能。</span><span class="sxs-lookup"><span data-stu-id="49436-114">With team call, end users manage the feature by using the Lync client.</span></span> <span data-ttu-id="49436-115">因此, 通过群组呼叫, 可以集中管理通话管理的这一方面。</span><span class="sxs-lookup"><span data-stu-id="49436-115">With Group Call Pickup, therefore, this aspect of call management can be centralized.</span></span>

<span data-ttu-id="49436-116">组呼叫装货是在呼叫寄存应用程序上构建的。</span><span class="sxs-lookup"><span data-stu-id="49436-116">Group Call Pickup is built on the Call Park application.</span></span> <span data-ttu-id="49436-117">当您部署组呼叫时, 您可以配置 "呼叫驻留" 轨道表, 其中包含指定为 "呼叫装货" 组编号的单独的分机号码范围。</span><span class="sxs-lookup"><span data-stu-id="49436-117">When you deploy Group Call Pickup, you configure the call park orbit table with separate ranges of extension numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="49436-118">如同呼叫寄存通道号码，呼叫应答组号码必须是未向其分配用户或电话的虚拟分机。</span><span class="sxs-lookup"><span data-stu-id="49436-118">Like call park orbit numbers, call pickup group numbers must be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="49436-119">你在其中部署组呼叫装货的每个前端池都可以具有一个或多个呼叫装货组编号范围。</span><span class="sxs-lookup"><span data-stu-id="49436-119">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="49436-120">组编号范围在 Lync Server 部署中必须是全局唯一的。</span><span class="sxs-lookup"><span data-stu-id="49436-120">The group number ranges must be globally unique across the Lync Server deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="49436-121">指定为 "呼叫寄存轨道" 表中的组呼叫的号码范围无法使用 Lync Server "控制面板" 进行管理或查看。</span><span class="sxs-lookup"><span data-stu-id="49436-121">Number ranges that are designated as Group Call Pickup numbers in the call park orbit table cannot be managed or viewed by using the Lync Server Control Panel.</span></span> <span data-ttu-id="49436-122">查看 "呼叫驻留" 轨道表中的所有数字范围的唯一方式是使用 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="49436-122">The only way to see all the number ranges in the call park orbit table is to use Lync Server Management Shell.</span></span> <span data-ttu-id="49436-123">同样, 添加、修改或删除组呼叫号码的唯一方法是使用 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="49436-123">Similarly, the only way to add, modify, or remove Group Call Pickup numbers is to use Lync Server Management Shell.</span></span>



</div>

<span data-ttu-id="49436-p106">在配置好呼叫应答组号码后，您将用户分配给呼叫应答组。分配到呼叫应答组的用户可以让他们的呼叫由其他用户接听。当某个呼叫进入到分配给呼叫应答组的用户时，注意到该呼叫的任何其他用户均可以通过手动拨打呼叫应答组号码来接听该呼叫。接听该呼叫的用户不需要是该组的成员。当呼叫由另一位用户接听时，系统会向原始被叫号码发送一条通知。</span><span class="sxs-lookup"><span data-stu-id="49436-p106">After you configure the call pickup group numbers, you assign users to a call pickup group. Any user who is assigned to a call pickup group can have their calls answered by other users. When a call comes in to a user who is assigned to a call pickup group, any other user who notices the call can answer it by manually dialing the call pickup group number. The user who picks up the call does not need to be a member of the group. When a call is picked up by another user, a notification is sent to the number originally called.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="49436-129">用户可能只是一个呼叫应答组的成员。</span><span class="sxs-lookup"><span data-stu-id="49436-129">A user can be a member of only one call pickup group.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="49436-130">尽管 Lync Server 部署中的任何用户都可以接听呼叫装货组成员的呼叫, 但接听呼叫的人员必须知道正确的呼叫装货组号码才能进行拨号。</span><span class="sxs-lookup"><span data-stu-id="49436-130">Although any user in the Lync Server deployment can answer a call to a call pickup group member, the person answering the call must know the correct call pickup group number to dial.</span></span>



</div>

<span data-ttu-id="49436-131">如果用户在组内多部电话响铃时拨打呼叫应答组号码来接听呼叫，则用户将接听响铃时间最长的呼叫。</span><span class="sxs-lookup"><span data-stu-id="49436-131">If a user dials a call pickup group number to answer a call when multiple phones in the group are ringing, the user answers the call that has been ringing the longest.</span></span>

<span data-ttu-id="49436-132">同时响铃设置将对具有组内呼叫应答功能的用户生效。</span><span class="sxs-lookup"><span data-stu-id="49436-132">Simultaneous ringing settings will work for users who have group call pickup.</span></span> <span data-ttu-id="49436-133">也就是说, 对具有组呼叫装货的用户进行的呼叫将会拨打所有已配置的目的地, 另一个用户可以接听呼叫。</span><span class="sxs-lookup"><span data-stu-id="49436-133">That is, a call made to a user who has Group Call Pickup will ring for all the configured destinations, and another user can answer the call.</span></span> <span data-ttu-id="49436-134">例外的情况是用户配置同时响铃以呼叫所有团队成员。</span><span class="sxs-lookup"><span data-stu-id="49436-134">The exception to this rule is when the user configures simultaneous ringing to call all the team members.</span></span>

<span data-ttu-id="49436-135">无法使用组呼叫装货来回答以下类型的呼叫:</span><span class="sxs-lookup"><span data-stu-id="49436-135">Group Call Pickup cannot be used to answer the following types of calls:</span></span>

  - <span data-ttu-id="49436-136">专用线路的呼叫</span><span class="sxs-lookup"><span data-stu-id="49436-136">Calls to a private line</span></span>

  - <span data-ttu-id="49436-137">来自已分配有“朋友和家人”私人关系的联系人的呼叫</span><span class="sxs-lookup"><span data-stu-id="49436-137">Calls from a contact who has been assigned the Friends and Family privacy relationship</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="49436-138">作为呼叫装货组成员的用户可以通过将联系人标记为 Lync 客户端中的个人联系人来防止通过组呼叫检索某些呼叫。</span><span class="sxs-lookup"><span data-stu-id="49436-138">A user who is a member of a call pickup group can prevent certain calls from being retrieved through Group Call Pickup by marking the contact as a personal contact in the Lync client.</span></span> <span data-ttu-id="49436-139">若要将联系人标记为个人联系人，请将该联系人的“私人关系”设置为“朋友和家人”。</span><span class="sxs-lookup"><span data-stu-id="49436-139">To mark a contact as a personal contact, set the Privacy Relationship for the contact to Friends and Family.</span></span> <span data-ttu-id="49436-140">不能通过使用组呼叫装货来检索从设置为 "朋友和家人" 的隐私关系的联系人的任何传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="49436-140">Any incoming call from contacts with the Privacy Relationship set to Friends and Family cannot be retrieved by using Group Call Pickup.</span></span>

    
    </div>

  - <span data-ttu-id="49436-141">音频/视频呼叫的视频部分</span><span class="sxs-lookup"><span data-stu-id="49436-141">Video portion of audio/video calls</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="49436-p109">如果用户接听某个音频/视频呼叫，则该用户只能收到音频。呼叫方或接听方可以升级该呼叫以添加视频。</span><span class="sxs-lookup"><span data-stu-id="49436-p109">If a user answers an audio/video call, the user receives only the audio. Either the person calling or the person answering the call can escalate the call to add video.</span></span>

    
    </div>

  - <span data-ttu-id="49436-144">路由到团队呼叫成员的同时响铃呼叫</span><span class="sxs-lookup"><span data-stu-id="49436-144">Simultaneous ringing calls that are routed to team call members</span></span>

  - <span data-ttu-id="49436-145">路由到代理人的呼叫</span><span class="sxs-lookup"><span data-stu-id="49436-145">Calls routed to a delegate</span></span>

  - <span data-ttu-id="49436-146">路由到响应组的呼叫</span><span class="sxs-lookup"><span data-stu-id="49436-146">Calls routed to a response group</span></span>

<span data-ttu-id="49436-147">以下类型的用户不能参与组呼叫分拣。</span><span class="sxs-lookup"><span data-stu-id="49436-147">The following types of users cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="49436-148">也就是说, 不应将它们包括在组呼叫 "装货" 组中, 并且他们不能为启用了组呼叫装货的用户获取呼叫。</span><span class="sxs-lookup"><span data-stu-id="49436-148">That is, they should not be included in a Group Call Pickup group, and they cannot pick up calls for users who have Group Call Pickup enabled.</span></span>

  - <span data-ttu-id="49436-149">在混合部署中驻留在联机部署的用户</span><span class="sxs-lookup"><span data-stu-id="49436-149">Users who are homed online in a hybrid deployment</span></span>

  - <span data-ttu-id="49436-150">使用 Lync Server 2013 的累积更新的 Lync Server 2013 池上未托管的用户: 本地部署中的2月2013</span><span class="sxs-lookup"><span data-stu-id="49436-150">Users who are not homed on a Lync Server 2013 pool with Cumulative Updates for Lync Server 2013: February 2013 in an on-premises deployment</span></span>

<span data-ttu-id="49436-p111">如果没有人接听打给呼叫应答组成员的呼叫，则该呼叫将按照客户端设置中的指定方式进行路由。即根据客户端设置中指定方式，该呼叫转至语音邮件或转发到不同的目标。</span><span class="sxs-lookup"><span data-stu-id="49436-p111">If no one answers a call to a member of a call pickup group, the call is routed as specified in the client settings. That is, the call goes to voicemail or is forwarded to a different destination, as specified in the client settings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

