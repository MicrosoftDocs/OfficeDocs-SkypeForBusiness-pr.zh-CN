---
title: 在 Skype for Business 2015 中规划组内呼叫应答
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
description: 该业务服务器企业语音，规划组在 Skype 呼叫的装货，使用户能够应答呼叫原本应用于其他人。
ms.openlocfilehash: ff23b08ca575f7296cbb3706ccdb351b89352804
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-group-call-pickup-in-skype-for-business-2015"></a><span data-ttu-id="5ac6e-103">在 Skype for Business 2015 中规划组内呼叫应答</span><span class="sxs-lookup"><span data-stu-id="5ac6e-103">Plan for Group Call Pickup in Skype for Business 2015</span></span>
 
<span data-ttu-id="5ac6e-104">该业务服务器企业语音，规划组在 Skype 呼叫的装货，使用户能够应答呼叫原本应用于其他人。</span><span class="sxs-lookup"><span data-stu-id="5ac6e-104">Planning for Group Call Pickup in Skype for Business Server Enterprise Voice, which enables users to answer calls originally intended for others.</span></span>
  
<span data-ttu-id="5ac6e-105">组调用拾取使用户能够应答传入呼叫向其同事，从他们自己的电话。</span><span class="sxs-lookup"><span data-stu-id="5ac6e-105">Group Call Pickup enables users to answer incoming calls to their colleagues from their own phones.</span></span> <span data-ttu-id="5ac6e-106">这允许其他用户通过拨打某个呼叫应答组号码来接听传入呼叫，从而提高了用户线路的可用性。</span><span class="sxs-lookup"><span data-stu-id="5ac6e-106">This increases the availability of a user's line by enabling other users to answer an incoming call by dialing a call pickup group number.</span></span> <span data-ttu-id="5ac6e-107">当部署组调用装货时，传入的呼叫路由到语音邮件的数目就会大大降低，这是特别有用的电话来自组织外部的客户。</span><span class="sxs-lookup"><span data-stu-id="5ac6e-107">When Group Call Pickup is deployed, the number of incoming calls that are routed to voice mail can be significantly reduced, which is particularly useful for calls from customers who are external to your organization.</span></span>
  
<span data-ttu-id="5ac6e-108">组调用拾取功能尤其适用于开放的办公环境中的业务单位。</span><span class="sxs-lookup"><span data-stu-id="5ac6e-108">The Group Call Pickup feature is designed in particular for business units in open office environments.</span></span> <span data-ttu-id="5ac6e-109">传入呼叫不是破坏性的，因为这些呼叫只会在指定目标响铃。</span><span class="sxs-lookup"><span data-stu-id="5ac6e-109">Incoming calls are not disruptive because they ring only at the intended destination.</span></span> <span data-ttu-id="5ac6e-110">但是，听到该响铃的其他用户仍可以通过拨打组号码来接听该呼叫。</span><span class="sxs-lookup"><span data-stu-id="5ac6e-110">Other users who hear the ring, however, can still pick up the call simply by dialing the group number.</span></span> 
  
<span data-ttu-id="5ac6e-111">在用户的位置不在打开的办公室布局，或地理位置分布共享公共职责的用户环境中，团队调用提供最适合的解决方案。</span><span class="sxs-lookup"><span data-stu-id="5ac6e-111">In environments where users are not located in an open office layout, or where users who share a common responsibility are geographically distributed, team call presents the most suitable solution.</span></span> <span data-ttu-id="5ac6e-112">组调用装货和团队之间的主要区别是与组调用装货，拨入呼叫响铃只能在其设定的目标，但任何人仍然可以选择回答这个问题拨打组号码。</span><span class="sxs-lookup"><span data-stu-id="5ac6e-112">The primary difference between Group Call Pickup and team call is that, with Group Call Pickup, an incoming call rings only at the intended destination, but anyone can still choose to answer it by dialing a group number.</span></span> <span data-ttu-id="5ac6e-113">与团队呼叫，呼叫响铃在所有团队成员的电话，和团队中的任何用户可以拿起电话来应答呼叫。</span><span class="sxs-lookup"><span data-stu-id="5ac6e-113">With team call, the call rings at all the team members' phones, and any user in the team can pick up the phone to answer the call.</span></span> <span data-ttu-id="5ac6e-114">组调用挑选和团队调用其他区别是组调用装货由管理员管理，通过 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="5ac6e-114">An additional difference between Group Call Pickup and team call is that Group Call Pickup is managed by an administrator, through Skype for Business Server.</span></span> <span data-ttu-id="5ac6e-115">与团队调用时，最终用户通过 Skype 业务客户端管理功能。</span><span class="sxs-lookup"><span data-stu-id="5ac6e-115">With team call, end users manage the feature by using the Skype for Business client.</span></span> <span data-ttu-id="5ac6e-116">与组调用装货，因此，这一方面的呼叫管理可以是集中式。</span><span class="sxs-lookup"><span data-stu-id="5ac6e-116">With Group Call Pickup, therefore, this aspect of call management can be centralized.</span></span>
  
<span data-ttu-id="5ac6e-117">在调用公园应用程序建立了组调用装货。</span><span class="sxs-lookup"><span data-stu-id="5ac6e-117">Group Call Pickup is built on the Call Park application.</span></span> <span data-ttu-id="5ac6e-118">部署组调用装货时，您将配置调用公园轨道表不同区域的指定为呼叫分拣组电话号码的分机号码。</span><span class="sxs-lookup"><span data-stu-id="5ac6e-118">When you deploy Group Call Pickup, you configure the call park orbit table with separate ranges of extension numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="5ac6e-119">如同呼叫寄存通道号码，呼叫应答组号码必须是未向其分配用户或电话的虚拟分机。</span><span class="sxs-lookup"><span data-stu-id="5ac6e-119">Like call park orbit numbers, call pickup group numbers must be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="5ac6e-120">在哪里部署组调用拾取每个前端池可以有一个或多个调用分拣组号范围。</span><span class="sxs-lookup"><span data-stu-id="5ac6e-120">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="5ac6e-121">对于业务服务器部署 Skype 组数字范围必须全局唯一。</span><span class="sxs-lookup"><span data-stu-id="5ac6e-121">The group number ranges must be globally unique across the Skype for Business Server deployment.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="5ac6e-122">指定为组调用拾取无法管理或通过 Skype 业务服务器控件面板查看调用公园轨道表中的数字的数字范围。</span><span class="sxs-lookup"><span data-stu-id="5ac6e-122">Number ranges that are designated as Group Call Pickup numbers in the call park orbit table cannot be managed or viewed by using the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="5ac6e-123">请参见调用公园轨道表中的所有数字范围的唯一办法是使用 Skype 业务服务器管理程序。</span><span class="sxs-lookup"><span data-stu-id="5ac6e-123">The only way to see all the number ranges in the call park orbit table is to use Skype for Business Server Management Shell.</span></span> <span data-ttu-id="5ac6e-124">与此类似，唯一的方法，若要添加，修改，或删除组调用装货的数字是对业务服务器管理外壳使用 Skype。</span><span class="sxs-lookup"><span data-stu-id="5ac6e-124">Similarly, the only way to add, modify, or remove Group Call Pickup numbers is to use Skype for Business Server Management Shell.</span></span> 
  
<span data-ttu-id="5ac6e-p106">在配置好呼叫应答组号码后，您将用户分配给呼叫应答组。分配到呼叫应答组的用户可以让他们的呼叫由其他用户接听。当某个呼叫进入到分配给呼叫应答组的用户时，注意到该呼叫的任何其他用户均可以通过手动拨打呼叫应答组号码来接听该呼叫。接听该呼叫的用户不需要是该组的成员。当呼叫由另一位用户接听时，系统会向原始被叫号码发送一条通知。</span><span class="sxs-lookup"><span data-stu-id="5ac6e-p106">After you configure the call pickup group numbers, you assign users to a call pickup group. Any user who is assigned to a call pickup group can have their calls answered by other users. When a call comes in to a user who is assigned to a call pickup group, any other user who notices the call can answer it by manually dialing the call pickup group number. The user who picks up the call does not need to be a member of the group. When a call is picked up by another user, a notification is sent to the number originally called.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5ac6e-130">用户可能只是一个呼叫应答组的成员。</span><span class="sxs-lookup"><span data-stu-id="5ac6e-130">A user can be a member of only one call pickup group.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="5ac6e-131">虽然 Skype 业务服务器部署中的任何用户可以调用分拣组成员到呼叫应答，应答呼叫的人必须知道要拨打正确的调用分拣组号码。</span><span class="sxs-lookup"><span data-stu-id="5ac6e-131">Although any user in the Skype for Business Server deployment can answer a call to a call pickup group member, the person answering the call must know the correct call pickup group number to dial.</span></span> 
  
<span data-ttu-id="5ac6e-132">如果用户在组内多部电话响铃时拨打呼叫应答组号码来接听呼叫，则用户将接听响铃时间最长的呼叫。</span><span class="sxs-lookup"><span data-stu-id="5ac6e-132">If a user dials a call pickup group number to answer a call when multiple phones in the group are ringing, the user answers the call that has been ringing the longest.</span></span>
  
<span data-ttu-id="5ac6e-133">同时响铃设置将对具有组内呼叫应答功能的用户生效。</span><span class="sxs-lookup"><span data-stu-id="5ac6e-133">Simultaneous ringing settings will work for users who have group call pickup.</span></span> <span data-ttu-id="5ac6e-134">也就是说，对于所有已配置的目标，对具有组调用装货的用户所做的调用将自动震铃和另一用户可以呼叫应答。</span><span class="sxs-lookup"><span data-stu-id="5ac6e-134">That is, a call made to a user who has Group Call Pickup will ring for all the configured destinations, and another user can answer the call.</span></span> <span data-ttu-id="5ac6e-135">例外的情况是用户配置同时响铃以呼叫所有团队成员。</span><span class="sxs-lookup"><span data-stu-id="5ac6e-135">The exception to this rule is when the user configures simultaneous ringing to call all the team members.</span></span>
  
<span data-ttu-id="5ac6e-136">不能使用组调用拾取回答以下类型的调用：</span><span class="sxs-lookup"><span data-stu-id="5ac6e-136">Group Call Pickup cannot be used to answer the following types of calls:</span></span>
  
- <span data-ttu-id="5ac6e-137">专用线路的呼叫</span><span class="sxs-lookup"><span data-stu-id="5ac6e-137">Calls to a private line</span></span>
    
- <span data-ttu-id="5ac6e-138">来自已分配有“朋友和家人”私人关系的联系人的呼叫</span><span class="sxs-lookup"><span data-stu-id="5ac6e-138">Calls from a contact who has been assigned the Friends and Family privacy relationship</span></span>
    
    > [!TIP]
    > <span data-ttu-id="5ac6e-139">调用分拣组成员的用户可以阻止某些调用被检索组调用拾取通过将该联系人标记为 Skype 业务客户端中的个人联系人。</span><span class="sxs-lookup"><span data-stu-id="5ac6e-139">A user who is a member of a call pickup group can prevent certain calls from being retrieved through Group Call Pickup by marking the contact as a personal contact in the Skype for Business client.</span></span> <span data-ttu-id="5ac6e-140">若要将联系人标记为个人联系人，请将该联系人的“私人关系”设置为“朋友和家人”。</span><span class="sxs-lookup"><span data-stu-id="5ac6e-140">To mark a contact as a personal contact, set the Privacy Relationship for the contact to Friends and Family.</span></span> <span data-ttu-id="5ac6e-141">任何来电者隐私关系的联系人设置为朋友和家人不能检索使用组调用装货。</span><span class="sxs-lookup"><span data-stu-id="5ac6e-141">Any incoming call from contacts with the Privacy Relationship set to Friends and Family cannot be retrieved by using Group Call Pickup.</span></span> 
  
- <span data-ttu-id="5ac6e-142">音频/视频呼叫的视频部分</span><span class="sxs-lookup"><span data-stu-id="5ac6e-142">Video portion of audio/video calls</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="5ac6e-p109">如果用户接听某个音频/视频呼叫，则该用户只能收到音频。呼叫方或接听方可以升级该呼叫以添加视频。</span><span class="sxs-lookup"><span data-stu-id="5ac6e-p109">If a user answers an audio/video call, the user receives only the audio. Either the person calling or the person answering the call can escalate the call to add video.</span></span> 
  
- <span data-ttu-id="5ac6e-145">路由到团队呼叫成员的同时响铃呼叫</span><span class="sxs-lookup"><span data-stu-id="5ac6e-145">Simultaneous ringing calls that are routed to team call members</span></span>
    
- <span data-ttu-id="5ac6e-146">路由到代理人的呼叫</span><span class="sxs-lookup"><span data-stu-id="5ac6e-146">Calls routed to a delegate</span></span>
    
- <span data-ttu-id="5ac6e-147">路由到响应组的呼叫</span><span class="sxs-lookup"><span data-stu-id="5ac6e-147">Calls routed to a response group</span></span>
    
<span data-ttu-id="5ac6e-148">下列类型的用户不能参与组调用装货。</span><span class="sxs-lookup"><span data-stu-id="5ac6e-148">The following types of users cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="5ac6e-149">即，它们不应包括在一组调用拾取组，和他们无法拿起呼叫的用户已启用的组调用装货。</span><span class="sxs-lookup"><span data-stu-id="5ac6e-149">That is, they should not be included in a Group Call Pickup group, and they cannot pick up calls for users who have Group Call Pickup enabled.</span></span>
  
- <span data-ttu-id="5ac6e-150">在混合部署中驻留在联机部署的用户</span><span class="sxs-lookup"><span data-stu-id="5ac6e-150">Users who are homed online in a hybrid deployment</span></span>
    
- <span data-ttu-id="5ac6e-151">用户没有驻留在任一 Skype 业务服务器 2015年池或累积更新 Lync Server 2013 的 Lync Server 2013 池： 在内部部署的 2 月 2013年</span><span class="sxs-lookup"><span data-stu-id="5ac6e-151">Users who are not homed on either a Skype for Business Server 2015 pool or a Lync Server 2013 pool with Cumulative Updates for Lync Server 2013: February 2013 in an on-premises deployment</span></span>
    
<span data-ttu-id="5ac6e-p111">如果没有人接听打给呼叫应答组成员的呼叫，则该呼叫将按照客户端设置中的指定方式进行路由。即根据客户端设置中指定方式，该呼叫转至语音邮件或转发到不同的目标。</span><span class="sxs-lookup"><span data-stu-id="5ac6e-p111">If no one answers a call to a member of a call pickup group, the call is routed as specified in the client settings. That is, the call goes to voicemail or is forwarded to a different destination, as specified in the client settings.</span></span>
  
## <a name="deployment-and-requirements"></a><span data-ttu-id="5ac6e-154">部署和要求</span><span class="sxs-lookup"><span data-stu-id="5ac6e-154">Deployment and requirements</span></span>

<span data-ttu-id="5ac6e-155">企业语音和调用公园应用程序部署时，系统会自动部署组调用装货。</span><span class="sxs-lookup"><span data-stu-id="5ac6e-155">Group Call Pickup is automatically deployed when you deploy Enterprise Voice and the Call Park application.</span></span> <span data-ttu-id="5ac6e-156">然后通过指派用户可以呼叫分拣组和组调用装货启用用户配置不同区域的数字指定为呼叫分拣组电话号码，呼叫公园轨道表启用组调用装货。</span><span class="sxs-lookup"><span data-stu-id="5ac6e-156">You enable Group Call Pickup by configuring the Call Park orbit table with separate ranges of numbers designated as call pickup group numbers, and then by assigning users to call pickup groups and enabling the users for Group Call Pickup.</span></span>
  
## <a name="clients-supported-for-group-call-pickup"></a><span data-ttu-id="5ac6e-157">客户端支持的组调用装货</span><span class="sxs-lookup"><span data-stu-id="5ac6e-157">Clients supported for Group Call Pickup</span></span>

<span data-ttu-id="5ac6e-158">下列客户端的任何可用于应答呼叫的组调用提货成员：</span><span class="sxs-lookup"><span data-stu-id="5ac6e-158">Any of the following clients can be used to answer calls to Group Call Pickup members:</span></span>
  
- <span data-ttu-id="5ac6e-159">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="5ac6e-159">Skype for Business</span></span>
    
- <span data-ttu-id="5ac6e-160">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="5ac6e-160">Lync 2013</span></span>
    
- <span data-ttu-id="5ac6e-161">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="5ac6e-161">Lync 2010</span></span>
    
- <span data-ttu-id="5ac6e-162">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="5ac6e-162">Lync Phone Edition</span></span>
    
> [!NOTE]
> <span data-ttu-id="5ac6e-163">用户可以使用任何这些客户端的应答呼叫的组调用提货成员，但用户必须驻留在与累积更新 Lync Server 2013 Skype 业务服务器池或 Lync Server 2013 池： 2 月 2013年。</span><span class="sxs-lookup"><span data-stu-id="5ac6e-163">Users can use any of these clients to answer calls to Group Call Pickup members, but the users must be homed on a Skype for Business Server pool or a Lync Server 2013 pool with Cumulative Updates for Lync Server 2013: February 2013.</span></span> 
  
<span data-ttu-id="5ac6e-164">用于选取对组调用拾取成员的调用不支持以下客户机和设备：</span><span class="sxs-lookup"><span data-stu-id="5ac6e-164">The following clients and devices are not supported for picking up calls to Group Call Pickup members:</span></span>
  
- <span data-ttu-id="5ac6e-165">Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="5ac6e-165">Lync Mobile</span></span>
    
- <span data-ttu-id="5ac6e-166">适用于 Windows 8 和 Windows RT 的 Lync 应用程序</span><span class="sxs-lookup"><span data-stu-id="5ac6e-166">Lync app for Windows 8 and Windows RT</span></span>
    
- <span data-ttu-id="5ac6e-167">Lync for iPad</span><span class="sxs-lookup"><span data-stu-id="5ac6e-167">Lync for iPad</span></span>
    
- <span data-ttu-id="5ac6e-168">模拟电话</span><span class="sxs-lookup"><span data-stu-id="5ac6e-168">Analog phones</span></span>
    
- <span data-ttu-id="5ac6e-169">具有公用电话交换网 (PSTN) 号码的电话</span><span class="sxs-lookup"><span data-stu-id="5ac6e-169">Phones with public switched telephone network (PSTN) numbers</span></span>
    
## <a name="capacity-planning"></a><span data-ttu-id="5ac6e-170">容量规划</span><span class="sxs-lookup"><span data-stu-id="5ac6e-170">Capacity planning</span></span>

<span data-ttu-id="5ac6e-171">下表描述了可用作容量规划需求基础的组调用拾取用户模型。</span><span class="sxs-lookup"><span data-stu-id="5ac6e-171">The following table describes the Group Call Pickup user model that you can use as the basis for capacity planning requirements.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5ac6e-172">调用公园应用基于组调用装货。</span><span class="sxs-lookup"><span data-stu-id="5ac6e-172">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="5ac6e-173">请记住，对于灾难恢复容量规划，成对池中每个池应能够处理的调用公园服务，包括在两个池的组调用装货，工作量。</span><span class="sxs-lookup"><span data-stu-id="5ac6e-173">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services, including Group Call Pickup, in both pools.</span></span> 
  
<span data-ttu-id="5ac6e-174">**组调用拾取的用户模型**</span><span class="sxs-lookup"><span data-stu-id="5ac6e-174">**Group Call Pickup User Model**</span></span>

|<span data-ttu-id="5ac6e-175">**跃点计数**</span><span class="sxs-lookup"><span data-stu-id="5ac6e-175">**Metric**</span></span>|<span data-ttu-id="5ac6e-176">**每个前端池<br/>（带有 8 前端服务器）**</span><span class="sxs-lookup"><span data-stu-id="5ac6e-176">**Per Front End pool  <br/>  (with 8 Front End Servers)**</span></span>|<span data-ttu-id="5ac6e-177">**每个标准版服务器**</span><span class="sxs-lookup"><span data-stu-id="5ac6e-177">**Per Standard Edition server**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5ac6e-178">建议的每组用户数</span><span class="sxs-lookup"><span data-stu-id="5ac6e-178">Recommended number of users per group</span></span>  <br/> |<span data-ttu-id="5ac6e-179">50</span><span class="sxs-lookup"><span data-stu-id="5ac6e-179">50</span></span>  <br/> |<span data-ttu-id="5ac6e-180">50</span><span class="sxs-lookup"><span data-stu-id="5ac6e-180">50</span></span>  <br/> |
|<span data-ttu-id="5ac6e-181">建议的组数</span><span class="sxs-lookup"><span data-stu-id="5ac6e-181">Recommended number of groups</span></span>  <br/> |<span data-ttu-id="5ac6e-182">500</span><span class="sxs-lookup"><span data-stu-id="5ac6e-182">500</span></span>  <br/> |<span data-ttu-id="5ac6e-183">60</span><span class="sxs-lookup"><span data-stu-id="5ac6e-183">60</span></span>  <br/> |
|<span data-ttu-id="5ac6e-184">针对组内呼叫应答启用的每个池的最大用户数</span><span class="sxs-lookup"><span data-stu-id="5ac6e-184">Maximum number of users per pool enabled for Group Call Pickup</span></span>  <br/> |<span data-ttu-id="5ac6e-185">25000</span><span class="sxs-lookup"><span data-stu-id="5ac6e-185">25,000</span></span>  <br/> |<span data-ttu-id="5ac6e-186">3000</span><span class="sxs-lookup"><span data-stu-id="5ac6e-186">3,000</span></span>  <br/> |
|<span data-ttu-id="5ac6e-187">每个池每分钟针对组内呼叫应答启用的所有用户的最大传入呼叫速率</span><span class="sxs-lookup"><span data-stu-id="5ac6e-187">Maximum rate of incoming calls to total users enabled for Group Call Pickup per pool per minute</span></span>  <br/> |<span data-ttu-id="5ac6e-188">500</span><span class="sxs-lookup"><span data-stu-id="5ac6e-188">500</span></span>  <br/> |<span data-ttu-id="5ac6e-189">60</span><span class="sxs-lookup"><span data-stu-id="5ac6e-189">60</span></span>  <br/> |
|<span data-ttu-id="5ac6e-190">每个池每分钟用户使用组内呼叫应答检索的最大呼叫速率</span><span class="sxs-lookup"><span data-stu-id="5ac6e-190">Maximum rate of calls retrieved by users with Group Call Pickup per pool per minute</span></span>  <br/> |<span data-ttu-id="5ac6e-191">200</span><span class="sxs-lookup"><span data-stu-id="5ac6e-191">200</span></span>  <br/> |<span data-ttu-id="5ac6e-192">25</span><span class="sxs-lookup"><span data-stu-id="5ac6e-192">25</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="5ac6e-193">对于具有少于八个前端服务器的前端池，线性计算度量值。</span><span class="sxs-lookup"><span data-stu-id="5ac6e-193">For Front End pools that have fewer than eight Front End Servers, calculate the metrics linearly.</span></span> <span data-ttu-id="5ac6e-194">例如，如果前端池中有一个前端服务器，来计算最大负载为表中所示的值的 1/8。</span><span class="sxs-lookup"><span data-stu-id="5ac6e-194">For example, if your Front End pool has one Front End Server, calculate the maximum load as 1/8 of the values shown in the table.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="5ac6e-195">只要不超过每个池的最大用户数，您就可以增加或减少建议的组数以及每组用户数。</span><span class="sxs-lookup"><span data-stu-id="5ac6e-195">You can increase or decrease the recommended number of users per group and number of groups as long as you do not exceed the maximum number of users per pool.</span></span> <span data-ttu-id="5ac6e-196">例如，标准版服务器可以有 120 组，每组 25 个用户使用，因为启用组调用装货的用户数仍在用户模型最大值 （即，25 个用户为 3000 个用户启用组调用装货的 120 组倍）。</span><span class="sxs-lookup"><span data-stu-id="5ac6e-196">For example, your Standard Edition server can have 120 groups with 25 users per group because the number of users enabled for Group Call Pickup is still within the user model maximum (that is, 120 groups times 25 users is 3,000 users enabled for Group Call Pickup).</span></span> 
  

