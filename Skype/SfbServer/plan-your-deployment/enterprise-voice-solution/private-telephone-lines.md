---
title: 在 Skype for Business Server 2015 中规划专用电话线路
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
description: 在 Skype 的专用 （辅助） 电话线路规划的业务服务器企业语音。
ms.openlocfilehash: ae1d992890d2faa1db9de097a519d363b9e1c228
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-private-telephone-lines-with-skype-for-business-2015"></a><span data-ttu-id="f226c-103">在 Skype for Business Server 2015 中规划专用电话线路</span><span class="sxs-lookup"><span data-stu-id="f226c-103">Plan for private telephone lines with Skype for Business 2015</span></span>
 
<span data-ttu-id="f226c-104">在 Skype 的专用 （辅助） 电话线路规划的业务服务器企业语音。</span><span class="sxs-lookup"><span data-stu-id="f226c-104">Planning for private (secondary) telephone lines in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="f226c-105">Skype 业务服务器可以为用户提供其主要电话线路以及第二个的专用电话线路。</span><span class="sxs-lookup"><span data-stu-id="f226c-105">Skype for Business Server enables you to give users a second, private telephone line in addition to their primary telephone line.</span></span> <span data-ttu-id="f226c-106">专用电话线路通常分配给需要一个未列出的电话号码以便他人直接与其取得联系的高管和其他人员。</span><span class="sxs-lookup"><span data-stu-id="f226c-106">Private telephone lines are often assigned to executives and others who want an unlisted telephone number at which they can be reached directly.</span></span>
  
<span data-ttu-id="f226c-107">私人电话线路只可以用 Skype 业务服务器管理外壳程序的配置。</span><span class="sxs-lookup"><span data-stu-id="f226c-107">Private telephone lines can only be configured with the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="f226c-108">用于业务服务器控件面板，不能用 Skype 配置专用电话线路。</span><span class="sxs-lookup"><span data-stu-id="f226c-108">You cannot configure private telephone lines with the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="f226c-109">仅在部署中的 Skype 业务服务器而不是混合部署，应配置专用电话线路。</span><span class="sxs-lookup"><span data-stu-id="f226c-109">Private telephone lines should be configured only in deployments of Skype for Business Server and not in mixed deployments.</span></span>
  
## <a name="characteristics-of-private-telephone-lines"></a><span data-ttu-id="f226c-110">专用电话线路的特征</span><span class="sxs-lookup"><span data-stu-id="f226c-110">Characteristics of Private Telephone Lines</span></span>

<span data-ttu-id="f226c-111">虽然从根本上简单概念的第二个专用的电话线，就必须了解专线和它们是类似于方法的特性和不同用户的主要电话线路。</span><span class="sxs-lookup"><span data-stu-id="f226c-111">Although the concept of a second, private telephone line is fundamentally simple, it is important to understand the characteristics of private lines and the ways in which they are similar to and different from users' primary telephone lines.</span></span>
  
### <a name="general-characteristics-of-private-telephone-lines"></a><span data-ttu-id="f226c-112">专用电话线路的常规特征</span><span class="sxs-lookup"><span data-stu-id="f226c-112">General Characteristics of Private Telephone Lines</span></span>

- <span data-ttu-id="f226c-113">每个用户只能有一条专用电话线路。</span><span class="sxs-lookup"><span data-stu-id="f226c-113">A user can have only one private telephone line.</span></span>
    
- <span data-ttu-id="f226c-114">具有专用电话线路的用户只有一个语音邮箱，并且只使用一个电子邮件地址接收错过的呼叫通知。</span><span class="sxs-lookup"><span data-stu-id="f226c-114">A user with a private telephone line has only one voice mailbox and receives missed call notifications at a single email address.</span></span>
    
- <span data-ttu-id="f226c-115">具有专用电话线路的用户没有第二个 SIP 地址，并且第二条专用电话线路不会在网络上为用户提供第二个状态（如第二个即时消息身份）。</span><span class="sxs-lookup"><span data-stu-id="f226c-115">A user with a private telephone line does not have a second SIP address, and a second, private telephone line does not give a user a second presence on the network (such as a second instant messaging identity).</span></span> 
    
- <span data-ttu-id="f226c-116">为只在内部部署提供了专用电话线路。</span><span class="sxs-lookup"><span data-stu-id="f226c-116">Private telephone lines are available for on-premises deployments only.</span></span> <span data-ttu-id="f226c-117">这些选项不可用的 Skype 业务服务器的承载部署。</span><span class="sxs-lookup"><span data-stu-id="f226c-117">They are not available with hosted deployments of Skype for Business Server.</span></span>
    
### <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a><span data-ttu-id="f226c-118">专用电话线路与主要电话线路的不同之处</span><span class="sxs-lookup"><span data-stu-id="f226c-118">How Private Telephone Lines Differ from Primary Telephone Lines</span></span>

- <span data-ttu-id="f226c-119">专用电话线路的电话号码不会显示在派生自 Active Directory 域服务的电话簿或联系人列表中。</span><span class="sxs-lookup"><span data-stu-id="f226c-119">The telephone numbers for private telephone lines do not appear in the telephone directories or Contacts lists that are derived from Active Directory Domain Services.</span></span>
    
- <span data-ttu-id="f226c-120">专用电话线路不具备以下功能：呼叫转接、团队呼叫、委派、小组电话、组内呼叫应答和响应组应用程序。</span><span class="sxs-lookup"><span data-stu-id="f226c-120">None of the following features are available with a private telephone line: call forwarding, team call, delegation, team ring, Group Call Pickup, and Response Group application.</span></span>
    
- <span data-ttu-id="f226c-121">对专用电话线路的呼叫有特殊的响铃，呼叫的系统通知会告知用户传入呼叫位于其专用线路上。</span><span class="sxs-lookup"><span data-stu-id="f226c-121">Calls to a private telephone line have a special ring, and the system notification for the call tells the user that the incoming call is on his or her private line.</span></span>
    
- <span data-ttu-id="f226c-p104">对专用电话线路的呼叫始终会发出响铃。它们不会遵循“请勿打扰”规则。</span><span class="sxs-lookup"><span data-stu-id="f226c-p104">Calls to the private telephone line always ring through. They do not follow "do not disturb" rules.</span></span>
    
- <span data-ttu-id="f226c-124">专用电话线路仅限于入站呼叫，不能用于进行传出呼叫。</span><span class="sxs-lookup"><span data-stu-id="f226c-124">Private telephone lines are inbound only and cannot be used to make outgoing calls.</span></span> <span data-ttu-id="f226c-125">当具有专用电话线路的用户的调用时，调用来自用户的主要电话线路和不会隐藏用户的名称或用户的主要电话号码的呼叫的人。</span><span class="sxs-lookup"><span data-stu-id="f226c-125">When a user with a private telephone line makes a call, the call originates from the user's primary telephone line and does not hide the user's name or the user's primary telephone number from the person called.</span></span>
    
### <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a><span data-ttu-id="f226c-126">专用电话线路与主要电话线路的相似之处</span><span class="sxs-lookup"><span data-stu-id="f226c-126">How Private Telephone Lines Are Similar to Primary Telephone Lines</span></span>

- <span data-ttu-id="f226c-127">专用电话线路上的未接听呼叫将路由到与主要电话线路相同的语音邮件收件箱（如果已启用语音邮件）。</span><span class="sxs-lookup"><span data-stu-id="f226c-127">Unanswered calls to a private telephone line are routed to the same voice mail inbox as for the primary telephone line (if voice mail is enabled).</span></span>
    
- <span data-ttu-id="f226c-128">挂断电话，并与用户的主要电话线路一样以相同的方式调用专用电话线路使用的分拣工作。</span><span class="sxs-lookup"><span data-stu-id="f226c-128">Call park and call pickup work with private telephone lines in exactly the same manner as they do with the user's primary telephone line.</span></span>
    
- <span data-ttu-id="f226c-129">当用户的主要电话线路上启用并发响铃时，它也被启用专用电话线路上。</span><span class="sxs-lookup"><span data-stu-id="f226c-129">When simultaneous ringing is enabled on a user's primary telephone line, it is also enabled on the private telephone line.</span></span>
    
- <span data-ttu-id="f226c-130">专用电话线路的电话号码呼叫详细记录中记录用户的主要电话线路，但使用表明，它是一个专用电话号码的电话号码的方式相同。</span><span class="sxs-lookup"><span data-stu-id="f226c-130">The telephone number for a private telephone line is recorded in the call detail record in the same manner as the telephone number for a user's primary telephone line, but with an indication that it is a private telephone number.</span></span>
    
- <span data-ttu-id="f226c-131">在用户回答对专用电话线路，电话是被同等对待用户的主要电话线路的电话。</span><span class="sxs-lookup"><span data-stu-id="f226c-131">After a user answers a call on a private telephone line, the call is treated the same as a call on the user's primary telephone line.</span></span> <span data-ttu-id="f226c-132">例如，如果收到专用电话线路的电话用户转发呼叫或邀请其他人到会议呼叫，用户的名称显示在 Skype 的业务，而用户的主要电话线路的电话号码出现在调用方标识。</span><span class="sxs-lookup"><span data-stu-id="f226c-132">For example, if a user who receives a call on a private telephone line forwards the call or invites others to a conference call, the user's name appears in Skype for Business, and the telephone number for the user's primary telephone line appears in caller ID.</span></span>
    
- <span data-ttu-id="f226c-133">用户可以转接来自于专用电话线路的呼叫（应答前，将呼叫重定向到其他目标，如移动电话或家庭电话），方式与主要电话线路相同。</span><span class="sxs-lookup"><span data-stu-id="f226c-133">A user can deflect a call (redirect the call to another destination, such as a mobile phone or home phone, before answering) from the private telephone line in the same manner as with a primary telephone line.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="f226c-134">专用线路的呼叫路由到备用电话号码后，专用电话线路的电话号码将提供给备用电话号码，并可以显示在该号码的日志中。</span><span class="sxs-lookup"><span data-stu-id="f226c-134">When a call to a private line is routed to an alternate telephone number, the telephone number for the private telephone line is made available to the alternate telephone number and can be displayed in the logs for that number.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="f226c-135">从会议对专用电话线路的调用将不具有*专用线路*指示中传入的系统通知。</span><span class="sxs-lookup"><span data-stu-id="f226c-135">Calls from a conference to the private telephone line will not have a  *private-line*  indication in the incoming system notification.</span></span>
  
## <a name="administering-private-telephone-lines"></a><span data-ttu-id="f226c-136">管理专用电话线路</span><span class="sxs-lookup"><span data-stu-id="f226c-136">Administering Private Telephone Lines</span></span>

<span data-ttu-id="f226c-p107">除创建和管理专用电话线路的技术方面外，还需要为其建立管理过程。这包括确定组织中谁可以使用专线的策略，创建和维护人员及其电话号码的列表，还可能要为高管创建专用电话簿，安排用户培训和相关任务。</span><span class="sxs-lookup"><span data-stu-id="f226c-p107">In addition to the technical aspects of creating and managing private telephone lines, you will need to establish administrative procedures for them. This includes determining policies for who in the organization is eligible for a private line, creating and maintaining lists of people and their telephone lines, possibly creating a private telephone directory for executives, arranging for user training, and related tasks.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f226c-p108">专用电话线路将在 Active Directory 中作为用户对象的 msRTCSIP-PrivateLine 属性存储。默认情况下，Authenticated Users 组的任何成员对此属性具有读取访问权限。</span><span class="sxs-lookup"><span data-stu-id="f226c-p108">The private telephone line is stored in Active Directory as an msRTCSIP-PrivateLine attribute on the user object. By default any member of the Authenticated Users group has read access to this attribute.</span></span> 
  
### <a name="assigning-telephone-numbers"></a><span data-ttu-id="f226c-141">分配电话号码</span><span class="sxs-lookup"><span data-stu-id="f226c-141">Assigning Telephone Numbers</span></span>

 <span data-ttu-id="f226c-142">需要专用电话线路的新用户帐户创建帐户，而无需专用电话线路，使用 Skype 业务服务器的控制面板或 Skype 业务服务器管理外壳程序的方式相同。</span><span class="sxs-lookup"><span data-stu-id="f226c-142">Accounts for new users who need private telephone lines are created in the same manner as accounts without private telephone lines, using Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="f226c-143">使用中的业务服务器管理外壳 Skype**集 CsUser** cmdlet 将电话号码分配给专用电话线路的用户，例如，**组 CsUser-标识"sip:joe@contoso.com"-PrivateLine"电话： +14255551212"**。</span><span class="sxs-lookup"><span data-stu-id="f226c-143">Use the **Set-CsUser** cmdlet in the Skype for Business Server Management Shell to assign a telephone number to a private telephone line for a user, for example, **Set-CsUser -Identity "sip:joe@contoso.com" -PrivateLine "Tel:+14255551212"**.</span></span>
  
<span data-ttu-id="f226c-144">对专用电话线路的电话号码可以是长度在 3 到 15 号之间和前面必须加上"TEL:"前缀。</span><span class="sxs-lookup"><span data-stu-id="f226c-144">Telephone numbers for private telephone lines can be between 3 and 15 numbers in length and must be preceded with the "TEL:" prefix.</span></span> <span data-ttu-id="f226c-145">这些号码可以具有任何区号和国家/地区代码，前提是您的组织有该区号和国家/地区代码的外线直拨分机。</span><span class="sxs-lookup"><span data-stu-id="f226c-145">They can have any area code and any country/region code as long as your organization has direct inward dialing for that area code and country/region code.</span></span> 
  
<span data-ttu-id="f226c-146">Cmdlet 和 Skype 业务服务器管理程序的详细信息，请参阅有关业务服务器管理外壳程序文档 Skype。</span><span class="sxs-lookup"><span data-stu-id="f226c-146">For details about cmdlets and Skype for Business Server Management Shell, see the Skype for Business Server Management Shell documentation.</span></span>
  
### <a name="private-telephone-lines-in-mixed-deployments"></a><span data-ttu-id="f226c-147">混合部署中的专用电话线路</span><span class="sxs-lookup"><span data-stu-id="f226c-147">Private Telephone Lines in Mixed Deployments</span></span>

<span data-ttu-id="f226c-148">应仅对 Skype 的业务服务器或 Lync Server 2013 的部署配置专用电话线路。</span><span class="sxs-lookup"><span data-stu-id="f226c-148">Private telephone lines should be configured only for deployments of Skype for Business Server or Lync Server 2013.</span></span> <span data-ttu-id="f226c-149">在部署中存在一些运行较早版本的 Lync Server 中，当用户在早期版本的服务器尝试调用专用电话线路中，路由调用的失败，因为服务器不能执行反向号码查询专用电话线路上。</span><span class="sxs-lookup"><span data-stu-id="f226c-149">In a deployment in which there are servers running earlier versions of Lync Server, when a user on earlier version attempts to call a private telephone line, routing of the call fails because the server cannot perform a reverse number lookup on a private telephone line.</span></span>
  

