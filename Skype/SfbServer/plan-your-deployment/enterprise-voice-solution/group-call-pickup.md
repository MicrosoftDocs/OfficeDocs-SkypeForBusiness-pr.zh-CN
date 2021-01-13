---
title: 在 Skype for Business 中规划组内呼叫接听
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
description: 在 Skype for Business Server 企业语音中规划组内呼叫应答，这使用户能够应答最初用于其他人的呼叫。
ms.openlocfilehash: 874b9385352a8c51d9c9a356dd0ccc2ca3070601
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825612"
---
# <a name="plan-for-group-call-pickup-in-skype-for-business"></a><span data-ttu-id="626f0-103">在 Skype for Business 中规划组内呼叫接听</span><span class="sxs-lookup"><span data-stu-id="626f0-103">Plan for Group Call Pickup in Skype for Business</span></span>
 
<span data-ttu-id="626f0-104">在 Skype for Business Server 企业语音中规划组内呼叫应答，这使用户能够应答最初用于其他人的呼叫。</span><span class="sxs-lookup"><span data-stu-id="626f0-104">Planning for Group Call Pickup in Skype for Business Server Enterprise Voice, which enables users to answer calls originally intended for others.</span></span>
  
<span data-ttu-id="626f0-105">利用组内呼叫应答，用户可以从自己的电话应答传入同事的呼叫。</span><span class="sxs-lookup"><span data-stu-id="626f0-105">Group Call Pickup enables users to answer incoming calls to their colleagues from their own phones.</span></span> <span data-ttu-id="626f0-106">这样，其他用户通过拨打呼叫应答组号码来应答传入呼叫，从而增加了用户线路的可用性。</span><span class="sxs-lookup"><span data-stu-id="626f0-106">This increases the availability of a user's line by enabling other users to answer an incoming call by dialing a call pickup group number.</span></span> <span data-ttu-id="626f0-107">部署组内呼叫分拣后，可以显著减少路由到语音邮件的传入呼叫数，这一点对于来自组织外部客户的呼叫特别有用。</span><span class="sxs-lookup"><span data-stu-id="626f0-107">When Group Call Pickup is deployed, the number of incoming calls that are routed to voice mail can be significantly reduced, which is particularly useful for calls from customers who are external to your organization.</span></span>
  
<span data-ttu-id="626f0-108">组内呼叫接听功能专为开放式办公环境中的业务单元而设计。</span><span class="sxs-lookup"><span data-stu-id="626f0-108">The Group Call Pickup feature is designed in particular for business units in open office environments.</span></span> <span data-ttu-id="626f0-109">传入呼叫不会中断，因为它们仅在预期目标处响铃。</span><span class="sxs-lookup"><span data-stu-id="626f0-109">Incoming calls are not disruptive because they ring only at the intended destination.</span></span> <span data-ttu-id="626f0-110">但是，听到响铃的其他用户仍然可以通过拨打组号码来接电话。</span><span class="sxs-lookup"><span data-stu-id="626f0-110">Other users who hear the ring, however, can still pick up the call simply by dialing the group number.</span></span> 
  
<span data-ttu-id="626f0-111">在用户不位于开放式办公室布局的环境中，或者共享共同责任的用户分布在不同地理位置的环境中，团队通话提供了最适合的解决方案。</span><span class="sxs-lookup"><span data-stu-id="626f0-111">In environments where users are not located in an open office layout, or where users who share a common responsibility are geographically distributed, team call presents the most suitable solution.</span></span> <span data-ttu-id="626f0-112">组内呼叫应答和团队呼叫之间的主要区别在于，使用组内呼叫应答时，传入呼叫仅在预期目标处响铃，但任何人都可以选择通过拨打组号码来应答呼叫。</span><span class="sxs-lookup"><span data-stu-id="626f0-112">The primary difference between Group Call Pickup and team call is that, with Group Call Pickup, an incoming call rings only at the intended destination, but anyone can still choose to answer it by dialing a group number.</span></span> <span data-ttu-id="626f0-113">通过团队呼叫，呼叫会在所有团队成员的电话中响铃，团队中的任意用户都可以接听电话来应答呼叫。</span><span class="sxs-lookup"><span data-stu-id="626f0-113">With team call, the call rings at all the team members' phones, and any user in the team can pick up the phone to answer the call.</span></span> <span data-ttu-id="626f0-114">组内呼叫接听和团队呼叫之间的另一个区别是，组内呼叫接听由管理员通过 Skype for Business Server 进行管理。</span><span class="sxs-lookup"><span data-stu-id="626f0-114">An additional difference between Group Call Pickup and team call is that Group Call Pickup is managed by an administrator, through Skype for Business Server.</span></span> <span data-ttu-id="626f0-115">通过团队呼叫，最终用户使用 Skype for Business 客户端管理该功能。</span><span class="sxs-lookup"><span data-stu-id="626f0-115">With team call, end users manage the feature by using the Skype for Business client.</span></span> <span data-ttu-id="626f0-116">因此，使用组内呼叫接听，可以集中管理呼叫的这一方面。</span><span class="sxs-lookup"><span data-stu-id="626f0-116">With Group Call Pickup, therefore, this aspect of call management can be centralized.</span></span>
  
<span data-ttu-id="626f0-117">组内呼叫分拣是在呼叫管理应用程序上构建的。</span><span class="sxs-lookup"><span data-stu-id="626f0-117">Group Call Pickup is built on the Call Park application.</span></span> <span data-ttu-id="626f0-118">部署组内呼叫分拣时，使用指定为呼叫分拣组号码的单独分机号码范围来配置呼叫安排通道表。</span><span class="sxs-lookup"><span data-stu-id="626f0-118">When you deploy Group Call Pickup, you configure the call park orbit table with separate ranges of extension numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="626f0-119">与呼叫 PARK 通道号码一样，呼叫接听组号码必须是未为其分配用户或电话的虚拟分机。</span><span class="sxs-lookup"><span data-stu-id="626f0-119">Like call park orbit numbers, call pickup group numbers must be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="626f0-120">部署组内呼叫分拣的每个前端池可以有一个或多个呼叫分拣组号码范围。</span><span class="sxs-lookup"><span data-stu-id="626f0-120">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="626f0-121">组号码范围必须在 Skype for Business Server 部署中具有全局唯一性。</span><span class="sxs-lookup"><span data-stu-id="626f0-121">The group number ranges must be globally unique across the Skype for Business Server deployment.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="626f0-122">无法使用 Skype for Business Server 控制面板管理或查看在呼叫托管通道表中指定为组内呼叫接听号码的号码范围。</span><span class="sxs-lookup"><span data-stu-id="626f0-122">Number ranges that are designated as Group Call Pickup numbers in the call park orbit table cannot be managed or viewed by using the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="626f0-123">查看呼叫等待通道表中的所有号码范围的唯一方法就是使用 Skype for Business Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="626f0-123">The only way to see all the number ranges in the call park orbit table is to use Skype for Business Server Management Shell.</span></span> <span data-ttu-id="626f0-124">同样，添加、修改或删除组内呼叫接听号码的唯一方法就是使用 Skype for Business Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="626f0-124">Similarly, the only way to add, modify, or remove Group Call Pickup numbers is to use Skype for Business Server Management Shell.</span></span> 
  
<span data-ttu-id="626f0-125">配置呼叫接听组号码后，将用户分配给呼叫接听组。</span><span class="sxs-lookup"><span data-stu-id="626f0-125">After you configure the call pickup group numbers, you assign users to a call pickup group.</span></span> <span data-ttu-id="626f0-126">分配到呼叫应答组的任何用户都可以由其他用户应答其呼叫。</span><span class="sxs-lookup"><span data-stu-id="626f0-126">Any user who is assigned to a call pickup group can have their calls answered by other users.</span></span> <span data-ttu-id="626f0-127">当呼叫进入分配到呼叫应答组的用户时，任何注意到该呼叫的其他用户都可以通过手动拨打呼叫应答组号码来应答呼叫。</span><span class="sxs-lookup"><span data-stu-id="626f0-127">When a call comes in to a user who is assigned to a call pickup group, any other user who notices the call can answer it by manually dialing the call pickup group number.</span></span> <span data-ttu-id="626f0-128">接到呼叫的用户不需要是组的成员。</span><span class="sxs-lookup"><span data-stu-id="626f0-128">The user who picks up the call does not need to be a member of the group.</span></span> <span data-ttu-id="626f0-129">当其他用户选取呼叫时，会向最初调用的号码发送通知。</span><span class="sxs-lookup"><span data-stu-id="626f0-129">When a call is picked up by another user, a notification is sent to the number originally called.</span></span>
  
> [!NOTE]
> <span data-ttu-id="626f0-130">用户只能是一个呼叫接听组的成员。</span><span class="sxs-lookup"><span data-stu-id="626f0-130">A user can be a member of only one call pickup group.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="626f0-131">尽管 Skype for Business Server 部署中的任意用户都可以应答呼叫应答组的成员的呼叫，但接听呼叫的人员必须知道要拨打的正确呼叫应答组号码。</span><span class="sxs-lookup"><span data-stu-id="626f0-131">Although any user in the Skype for Business Server deployment can answer a call to a call pickup group member, the person answering the call must know the correct call pickup group number to dial.</span></span> 
  
<span data-ttu-id="626f0-132">如果用户在组中多部电话响铃时拨打呼叫应答组号码以应答呼叫，则用户将应答响铃时间最长的呼叫。</span><span class="sxs-lookup"><span data-stu-id="626f0-132">If a user dials a call pickup group number to answer a call when multiple phones in the group are ringing, the user answers the call that has been ringing the longest.</span></span>
  
<span data-ttu-id="626f0-133">同时响铃设置适用于具有组内呼叫接听的用户。</span><span class="sxs-lookup"><span data-stu-id="626f0-133">Simultaneous ringing settings will work for users who have group call pickup.</span></span> <span data-ttu-id="626f0-134">也就是说，向具有组内呼叫应答的用户的呼叫将针对所有配置的目标响铃，其他用户可以应答该呼叫。</span><span class="sxs-lookup"><span data-stu-id="626f0-134">That is, a call made to a user who has Group Call Pickup will ring for all the configured destinations, and another user can answer the call.</span></span> <span data-ttu-id="626f0-135">此规则的例外情况是用户配置同时响铃以呼叫所有团队成员。</span><span class="sxs-lookup"><span data-stu-id="626f0-135">The exception to this rule is when the user configures simultaneous ringing to call all the team members.</span></span>
  
<span data-ttu-id="626f0-136">组内呼叫应答不能用于应答以下类型的呼叫：</span><span class="sxs-lookup"><span data-stu-id="626f0-136">Group Call Pickup cannot be used to answer the following types of calls:</span></span>
  
- <span data-ttu-id="626f0-137">拨打专线</span><span class="sxs-lookup"><span data-stu-id="626f0-137">Calls to a private line</span></span>
    
- <span data-ttu-id="626f0-138">来自已分配有"朋友和家人"私人关系的联系人的呼叫</span><span class="sxs-lookup"><span data-stu-id="626f0-138">Calls from a contact who has been assigned the Friends and Family privacy relationship</span></span>
    
    > [!TIP]
    > <span data-ttu-id="626f0-139">作为呼叫接听组的成员的用户可以通过在 Skype for Business 客户端中将联系人标记为个人联系人来阻止通过组内呼叫分拣检索某些呼叫。</span><span class="sxs-lookup"><span data-stu-id="626f0-139">A user who is a member of a call pickup group can prevent certain calls from being retrieved through Group Call Pickup by marking the contact as a personal contact in the Skype for Business client.</span></span> <span data-ttu-id="626f0-140">若要将联系人标记为个人联系人，将联系人的隐私关系设置为"家庭"。</span><span class="sxs-lookup"><span data-stu-id="626f0-140">To mark a contact as a personal contact, set the Privacy Relationship for the contact to Friends and Family.</span></span> <span data-ttu-id="626f0-141">无法使用组内呼叫分拣功能检索隐私关系设置为"朋友"和"家庭"的联系人的任何传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="626f0-141">Any incoming call from contacts with the Privacy Relationship set to Friends and Family cannot be retrieved by using Group Call Pickup.</span></span> 
  
- <span data-ttu-id="626f0-142">音频/视频呼叫的视频部分</span><span class="sxs-lookup"><span data-stu-id="626f0-142">Video portion of audio/video calls</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="626f0-143">如果用户应答音频/视频呼叫，则用户仅接收音频。</span><span class="sxs-lookup"><span data-stu-id="626f0-143">If a user answers an audio/video call, the user receives only the audio.</span></span> <span data-ttu-id="626f0-144">呼叫者或接听电话的人可以升级呼叫以添加视频。</span><span class="sxs-lookup"><span data-stu-id="626f0-144">Either the person calling or the person answering the call can escalate the call to add video.</span></span> 
  
- <span data-ttu-id="626f0-145">路由到团队呼叫成员的同时响铃呼叫</span><span class="sxs-lookup"><span data-stu-id="626f0-145">Simultaneous ringing calls that are routed to team call members</span></span>
    
- <span data-ttu-id="626f0-146">路由到代理人的呼叫</span><span class="sxs-lookup"><span data-stu-id="626f0-146">Calls routed to a delegate</span></span>
    
- <span data-ttu-id="626f0-147">路由到响应组的呼叫</span><span class="sxs-lookup"><span data-stu-id="626f0-147">Calls routed to a response group</span></span>
    
<span data-ttu-id="626f0-148">以下类型的用户不能参与组内呼叫接听。</span><span class="sxs-lookup"><span data-stu-id="626f0-148">The following types of users cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="626f0-149">也就是说，它们不应包含在组内呼叫接听组中，并且无法接听已启用组内呼叫接听的用户的呼叫。</span><span class="sxs-lookup"><span data-stu-id="626f0-149">That is, they should not be included in a Group Call Pickup group, and they cannot pick up calls for users who have Group Call Pickup enabled.</span></span>
  
- <span data-ttu-id="626f0-150">在混合部署中联机管理的用户</span><span class="sxs-lookup"><span data-stu-id="626f0-150">Users who are homed online in a hybrid deployment</span></span>
    
- <span data-ttu-id="626f0-151">未位于 Skype for Business Server 2015 池或 Lync Server 2013 池（具有 Lync Server 2013 累积更新）上的用户：2013 年 2 月本地部署</span><span class="sxs-lookup"><span data-stu-id="626f0-151">Users who are not homed on either a Skype for Business Server 2015 pool or a Lync Server 2013 pool with Cumulative Updates for Lync Server 2013: February 2013 in an on-premises deployment</span></span>
    
<span data-ttu-id="626f0-152">如果没有人应答对呼叫应答组的成员的呼叫，则按照客户端设置中指定的方式路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="626f0-152">If no one answers a call to a member of a call pickup group, the call is routed as specified in the client settings.</span></span> <span data-ttu-id="626f0-153">即，呼叫转到语音邮件或转发到其他目标，如客户端设置中指定。</span><span class="sxs-lookup"><span data-stu-id="626f0-153">That is, the call goes to voicemail or is forwarded to a different destination, as specified in the client settings.</span></span>
  
## <a name="deployment-and-requirements"></a><span data-ttu-id="626f0-154">部署和要求</span><span class="sxs-lookup"><span data-stu-id="626f0-154">Deployment and requirements</span></span>

<span data-ttu-id="626f0-155">在部署呼叫和呼叫企业语音自动部署组内呼叫接听。</span><span class="sxs-lookup"><span data-stu-id="626f0-155">Group Call Pickup is automatically deployed when you deploy Enterprise Voice and the Call Park application.</span></span> <span data-ttu-id="626f0-156">通过配置具有指定为呼叫接听组号码的单独号码范围的呼叫等待通道表，然后为用户分配呼叫接听组并启用用户进行组内呼叫分拣，可以启用组内呼叫分拣。</span><span class="sxs-lookup"><span data-stu-id="626f0-156">You enable Group Call Pickup by configuring the Call Park orbit table with separate ranges of numbers designated as call pickup group numbers, and then by assigning users to call pickup groups and enabling the users for Group Call Pickup.</span></span>
  
## <a name="clients-supported-for-group-call-pickup"></a><span data-ttu-id="626f0-157">支持组内呼叫接听的客户端</span><span class="sxs-lookup"><span data-stu-id="626f0-157">Clients supported for Group Call Pickup</span></span>

<span data-ttu-id="626f0-158">以下任何客户端都可用于应答对组内呼叫应答成员的呼叫：</span><span class="sxs-lookup"><span data-stu-id="626f0-158">Any of the following clients can be used to answer calls to Group Call Pickup members:</span></span>
  
- <span data-ttu-id="626f0-159">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="626f0-159">Skype for Business</span></span>
    
- <span data-ttu-id="626f0-160">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="626f0-160">Lync 2013</span></span>
    
- <span data-ttu-id="626f0-161">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="626f0-161">Lync 2010</span></span>
    
- <span data-ttu-id="626f0-162">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="626f0-162">Lync Phone Edition</span></span>
    
> [!NOTE]
> <span data-ttu-id="626f0-163">用户可以使用其中任一客户端应答对组内呼叫应答成员的呼叫，但用户必须位于 Skype for Business Server 池或 Lync Server 2013 池（具有 Lync Server 2013 累积更新：2013 年 2 月）上。</span><span class="sxs-lookup"><span data-stu-id="626f0-163">Users can use any of these clients to answer calls to Group Call Pickup members, but the users must be homed on a Skype for Business Server pool or a Lync Server 2013 pool with Cumulative Updates for Lync Server 2013: February 2013.</span></span> 
  
<span data-ttu-id="626f0-164">以下客户端和设备不支持接听组内呼叫分拣成员的呼叫：</span><span class="sxs-lookup"><span data-stu-id="626f0-164">The following clients and devices are not supported for picking up calls to Group Call Pickup members:</span></span>
  
- <span data-ttu-id="626f0-165">Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="626f0-165">Lync Mobile</span></span>
    
- <span data-ttu-id="626f0-166">适用于 Windows 8 和 Windows RT 的 Lync 应用</span><span class="sxs-lookup"><span data-stu-id="626f0-166">Lync app for Windows 8 and Windows RT</span></span>
    
- <span data-ttu-id="626f0-167">Lync for iPad</span><span class="sxs-lookup"><span data-stu-id="626f0-167">Lync for iPad</span></span>
    
- <span data-ttu-id="626f0-168">模拟电话</span><span class="sxs-lookup"><span data-stu-id="626f0-168">Analog phones</span></span>
    
- <span data-ttu-id="626f0-169">具有公用电话交换网的电话 (PSTN) 号码</span><span class="sxs-lookup"><span data-stu-id="626f0-169">Phones with public switched telephone network (PSTN) numbers</span></span>
    
## <a name="capacity-planning"></a><span data-ttu-id="626f0-170">容量规划</span><span class="sxs-lookup"><span data-stu-id="626f0-170">Capacity planning</span></span>

<span data-ttu-id="626f0-171">下表介绍了可以用作容量规划要求基础的组内呼叫分拣用户模型。</span><span class="sxs-lookup"><span data-stu-id="626f0-171">The following table describes the Group Call Pickup user model that you can use as the basis for capacity planning requirements.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="626f0-172">组内呼叫接听基于呼叫管理应用程序。</span><span class="sxs-lookup"><span data-stu-id="626f0-172">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="626f0-173">请记住，对于灾难恢复容量规划，配对池的每个池都应能够处理两个池中的呼叫保留服务（包括组呼叫接听）的工作负荷。</span><span class="sxs-lookup"><span data-stu-id="626f0-173">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services, including Group Call Pickup, in both pools.</span></span> 
  
<span data-ttu-id="626f0-174">**组内呼叫接听用户模型**</span><span class="sxs-lookup"><span data-stu-id="626f0-174">**Group Call Pickup User Model**</span></span>

|<span data-ttu-id="626f0-175">**跃点数**</span><span class="sxs-lookup"><span data-stu-id="626f0-175">**Metric**</span></span>|<span data-ttu-id="626f0-176">**每个前端池  <br/>  池 (8 台前端服务器)**</span><span class="sxs-lookup"><span data-stu-id="626f0-176">**Per Front End pool  <br/>  (with 8 Front End Servers)**</span></span>|<span data-ttu-id="626f0-177">**每台 Standard Edition Server**</span><span class="sxs-lookup"><span data-stu-id="626f0-177">**Per Standard Edition server**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="626f0-178">每个组的推荐用户数</span><span class="sxs-lookup"><span data-stu-id="626f0-178">Recommended number of users per group</span></span>  <br/> |<span data-ttu-id="626f0-179">50</span><span class="sxs-lookup"><span data-stu-id="626f0-179">50</span></span>  <br/> |<span data-ttu-id="626f0-180">50</span><span class="sxs-lookup"><span data-stu-id="626f0-180">50</span></span>  <br/> |
|<span data-ttu-id="626f0-181">建议的组数</span><span class="sxs-lookup"><span data-stu-id="626f0-181">Recommended number of groups</span></span>  <br/> |<span data-ttu-id="626f0-182">500</span><span class="sxs-lookup"><span data-stu-id="626f0-182">500</span></span>  <br/> |<span data-ttu-id="626f0-183">60</span><span class="sxs-lookup"><span data-stu-id="626f0-183">60</span></span>  <br/> |
|<span data-ttu-id="626f0-184">启用组内呼叫分拣的每个池的最大用户数</span><span class="sxs-lookup"><span data-stu-id="626f0-184">Maximum number of users per pool enabled for Group Call Pickup</span></span>  <br/> |<span data-ttu-id="626f0-185">25,000</span><span class="sxs-lookup"><span data-stu-id="626f0-185">25,000</span></span>  <br/> |<span data-ttu-id="626f0-186">3,000</span><span class="sxs-lookup"><span data-stu-id="626f0-186">3,000</span></span>  <br/> |
|<span data-ttu-id="626f0-187">每分钟为每个池启用组内呼叫分拣功能的用户总数的最大传入呼叫速率</span><span class="sxs-lookup"><span data-stu-id="626f0-187">Maximum rate of incoming calls to total users enabled for Group Call Pickup per pool per minute</span></span>  <br/> |<span data-ttu-id="626f0-188">500</span><span class="sxs-lookup"><span data-stu-id="626f0-188">500</span></span>  <br/> |<span data-ttu-id="626f0-189">60</span><span class="sxs-lookup"><span data-stu-id="626f0-189">60</span></span>  <br/> |
|<span data-ttu-id="626f0-190">每分钟每个池具有组内呼叫接听的用户检索的最大呼叫速率</span><span class="sxs-lookup"><span data-stu-id="626f0-190">Maximum rate of calls retrieved by users with Group Call Pickup per pool per minute</span></span>  <br/> |<span data-ttu-id="626f0-191">200</span><span class="sxs-lookup"><span data-stu-id="626f0-191">200</span></span>  <br/> |<span data-ttu-id="626f0-192">25</span><span class="sxs-lookup"><span data-stu-id="626f0-192">25</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="626f0-193">对于前端服务器数少于 8 台的前端池，线性计算指标。</span><span class="sxs-lookup"><span data-stu-id="626f0-193">For Front End pools that have fewer than eight Front End Servers, calculate the metrics linearly.</span></span> <span data-ttu-id="626f0-194">例如，如果前端池有一台前端服务器，则计算最大负载为表中所示值的 1/8。</span><span class="sxs-lookup"><span data-stu-id="626f0-194">For example, if your Front End pool has one Front End Server, calculate the maximum load as 1/8 of the values shown in the table.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="626f0-195">您可以增加或减少每个组的建议用户数和组数，只要不超过每个池的最大用户数。</span><span class="sxs-lookup"><span data-stu-id="626f0-195">You can increase or decrease the recommended number of users per group and number of groups as long as you do not exceed the maximum number of users per pool.</span></span> <span data-ttu-id="626f0-196">例如，Standard Edition Server 可以有 120 个组，每个组有 25 个用户，因为启用组内呼叫分拣的用户数仍位于用户模型最大 (即，120 个组次 25 个用户为 3，000 个用户启用了组内呼叫分拣) 。</span><span class="sxs-lookup"><span data-stu-id="626f0-196">For example, your Standard Edition server can have 120 groups with 25 users per group because the number of users enabled for Group Call Pickup is still within the user model maximum (that is, 120 groups times 25 users is 3,000 users enabled for Group Call Pickup).</span></span> 
  

