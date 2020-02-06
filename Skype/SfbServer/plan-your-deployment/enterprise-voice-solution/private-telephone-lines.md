---
title: 通过 Skype for Business 规划私人电话线
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
description: 在 Skype for Business Server Enterprise Voice 中规划专用（辅助）电话线路。
ms.openlocfilehash: 001a83e4bd81f0f47546f51f1d4993c6b1cec4bf
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802562"
---
# <a name="plan-for-private-telephone-lines-with-skype-for-business"></a><span data-ttu-id="0ca24-103">通过 Skype for Business 规划私人电话线</span><span class="sxs-lookup"><span data-stu-id="0ca24-103">Plan for private telephone lines with Skype for Business</span></span>
 
<span data-ttu-id="0ca24-104">在 Skype for Business Server Enterprise Voice 中规划专用（辅助）电话线路。</span><span class="sxs-lookup"><span data-stu-id="0ca24-104">Planning for private (secondary) telephone lines in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="0ca24-105">Skype for business 服务器使您可以除主要电话线之外为用户提供第二条专用电话线路。</span><span class="sxs-lookup"><span data-stu-id="0ca24-105">Skype for Business Server enables you to give users a second, private telephone line in addition to their primary telephone line.</span></span> <span data-ttu-id="0ca24-106">专用电话线路通常分配给需要一个未列出的电话号码以便他人直接与其取得联系的高管和其他人员。</span><span class="sxs-lookup"><span data-stu-id="0ca24-106">Private telephone lines are often assigned to executives and others who want an unlisted telephone number at which they can be reached directly.</span></span>
  
<span data-ttu-id="0ca24-107">专用电话线只能通过 Skype for Business 服务器命令行管理程序来配置。</span><span class="sxs-lookup"><span data-stu-id="0ca24-107">Private telephone lines can only be configured with the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="0ca24-108">您不能通过 Skype for business 服务器控制面板配置私人电话线。</span><span class="sxs-lookup"><span data-stu-id="0ca24-108">You cannot configure private telephone lines with the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="0ca24-109">专用电话线应仅在部署 Skype for Business 服务器而不是在混合部署中配置。</span><span class="sxs-lookup"><span data-stu-id="0ca24-109">Private telephone lines should be configured only in deployments of Skype for Business Server and not in mixed deployments.</span></span>
  
## <a name="characteristics-of-private-telephone-lines"></a><span data-ttu-id="0ca24-110">专用电话线路的特征</span><span class="sxs-lookup"><span data-stu-id="0ca24-110">Characteristics of Private Telephone Lines</span></span>

<span data-ttu-id="0ca24-111">虽然第二条专用电话线的概念基本很简单，但重要的是了解专用线路的特性以及它们与用户的主要电话线有类似的方式和不同之处。</span><span class="sxs-lookup"><span data-stu-id="0ca24-111">Although the concept of a second, private telephone line is fundamentally simple, it is important to understand the characteristics of private lines and the ways in which they are similar to and different from users' primary telephone lines.</span></span>
  
### <a name="general-characteristics-of-private-telephone-lines"></a><span data-ttu-id="0ca24-112">专用电话线路的常规特征</span><span class="sxs-lookup"><span data-stu-id="0ca24-112">General Characteristics of Private Telephone Lines</span></span>

- <span data-ttu-id="0ca24-113">每个用户只能有一条专用电话线路。</span><span class="sxs-lookup"><span data-stu-id="0ca24-113">A user can have only one private telephone line.</span></span>
    
- <span data-ttu-id="0ca24-114">具有专用电话线路的用户只有一个语音邮箱，并且只使用一个电子邮件地址接收错过的呼叫通知。</span><span class="sxs-lookup"><span data-stu-id="0ca24-114">A user with a private telephone line has only one voice mailbox and receives missed call notifications at a single email address.</span></span>
    
- <span data-ttu-id="0ca24-115">具有专用电话线路的用户没有第二个 SIP 地址，并且第二条专用电话线路不会在网络上为用户提供第二个状态（如第二个即时消息身份）。</span><span class="sxs-lookup"><span data-stu-id="0ca24-115">A user with a private telephone line does not have a second SIP address, and a second, private telephone line does not give a user a second presence on the network (such as a second instant messaging identity).</span></span> 
    
- <span data-ttu-id="0ca24-116">专用电话线路仅适用于本地部署。</span><span class="sxs-lookup"><span data-stu-id="0ca24-116">Private telephone lines are available for on-premises deployments only.</span></span> <span data-ttu-id="0ca24-117">它们不适用于 Skype for Business Server 的托管部署。</span><span class="sxs-lookup"><span data-stu-id="0ca24-117">They are not available with hosted deployments of Skype for Business Server.</span></span>
    
### <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a><span data-ttu-id="0ca24-118">专用电话线路与主要电话线路的不同之处</span><span class="sxs-lookup"><span data-stu-id="0ca24-118">How Private Telephone Lines Differ from Primary Telephone Lines</span></span>

- <span data-ttu-id="0ca24-119">专用电话线路的电话号码不会显示在派生自 Active Directory 域服务的电话簿或联系人列表中。</span><span class="sxs-lookup"><span data-stu-id="0ca24-119">The telephone numbers for private telephone lines do not appear in the telephone directories or Contacts lists that are derived from Active Directory Domain Services.</span></span>
    
- <span data-ttu-id="0ca24-120">专用电话线路不具备以下功能：呼叫转接、团队呼叫、委派、小组电话、组内呼叫应答和响应组应用程序。</span><span class="sxs-lookup"><span data-stu-id="0ca24-120">None of the following features are available with a private telephone line: call forwarding, team call, delegation, team ring, Group Call Pickup, and Response Group application.</span></span>
    
- <span data-ttu-id="0ca24-121">对专用电话线路的呼叫有特殊的响铃，呼叫的系统通知会告知用户传入呼叫位于其专用线路上。</span><span class="sxs-lookup"><span data-stu-id="0ca24-121">Calls to a private telephone line have a special ring, and the system notification for the call tells the user that the incoming call is on his or her private line.</span></span>
    
- <span data-ttu-id="0ca24-p104">对专用电话线路的呼叫始终会发出响铃。它们不会遵循“请勿打扰”规则。</span><span class="sxs-lookup"><span data-stu-id="0ca24-p104">Calls to the private telephone line always ring through. They do not follow "do not disturb" rules.</span></span>
    
- <span data-ttu-id="0ca24-124">专用电话线路仅限于入站呼叫，不能用于进行传出呼叫。</span><span class="sxs-lookup"><span data-stu-id="0ca24-124">Private telephone lines are inbound only and cannot be used to make outgoing calls.</span></span> <span data-ttu-id="0ca24-125">当具有专用电话线的用户进行呼叫时，该呼叫来自用户的主电话线，并且不会隐藏用户的姓名或用户的主要电话号码（来自呼叫者）。</span><span class="sxs-lookup"><span data-stu-id="0ca24-125">When a user with a private telephone line makes a call, the call originates from the user's primary telephone line and does not hide the user's name or the user's primary telephone number from the person called.</span></span>
    
### <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a><span data-ttu-id="0ca24-126">专用电话线路与主要电话线路的相似之处</span><span class="sxs-lookup"><span data-stu-id="0ca24-126">How Private Telephone Lines Are Similar to Primary Telephone Lines</span></span>

- <span data-ttu-id="0ca24-127">专用电话线路上的未接听呼叫将路由到与主要电话线路相同的语音邮件收件箱（如果已启用语音邮件）。</span><span class="sxs-lookup"><span data-stu-id="0ca24-127">Unanswered calls to a private telephone line are routed to the same voice mail inbox as for the primary telephone line (if voice mail is enabled).</span></span>
    
- <span data-ttu-id="0ca24-128">呼叫寄存和呼叫装货使用专用电话线的方式与使用用户的主要电话线完全相同。</span><span class="sxs-lookup"><span data-stu-id="0ca24-128">Call park and call pickup work with private telephone lines in exactly the same manner as they do with the user's primary telephone line.</span></span>
    
- <span data-ttu-id="0ca24-129">在用户的主电话线上启用同时拨打时，它也会在专用电话线上启用。</span><span class="sxs-lookup"><span data-stu-id="0ca24-129">When simultaneous ringing is enabled on a user's primary telephone line, it is also enabled on the private telephone line.</span></span>
    
- <span data-ttu-id="0ca24-130">专用电话线的电话号码以与用户的主要电话线的电话号码相同的方式记录在呼叫详细记录中，但表明它是专用电话号码。</span><span class="sxs-lookup"><span data-stu-id="0ca24-130">The telephone number for a private telephone line is recorded in the call detail record in the same manner as the telephone number for a user's primary telephone line, but with an indication that it is a private telephone number.</span></span>
    
- <span data-ttu-id="0ca24-131">用户使用专用电话线应答呼叫后，呼叫将被视为用户的主电话线上的呼叫。</span><span class="sxs-lookup"><span data-stu-id="0ca24-131">After a user answers a call on a private telephone line, the call is treated the same as a call on the user's primary telephone line.</span></span> <span data-ttu-id="0ca24-132">例如，如果通过专用电话线接收呼叫的用户转发呼叫或邀请其他人加入电话会议，则用户名将显示在 Skype for Business 中，用户的主电话线的电话号码将显示在 "来电显示" 中。</span><span class="sxs-lookup"><span data-stu-id="0ca24-132">For example, if a user who receives a call on a private telephone line forwards the call or invites others to a conference call, the user's name appears in Skype for Business, and the telephone number for the user's primary telephone line appears in caller ID.</span></span>
    
- <span data-ttu-id="0ca24-133">用户可以转接来自于专用电话线路的呼叫（应答前，将呼叫重定向到其他目标，如移动电话或家庭电话），方式与主要电话线路相同。</span><span class="sxs-lookup"><span data-stu-id="0ca24-133">A user can deflect a call (redirect the call to another destination, such as a mobile phone or home phone, before answering) from the private telephone line in the same manner as with a primary telephone line.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="0ca24-134">专用线路的呼叫路由到备用电话号码后，专用电话线路的电话号码将提供给备用电话号码，并可以显示在该号码的日志中。</span><span class="sxs-lookup"><span data-stu-id="0ca24-134">When a call to a private line is routed to an alternate telephone number, the telephone number for the private telephone line is made available to the alternate telephone number and can be displayed in the logs for that number.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="0ca24-135">从电话会议到专用电话线的通话在传入系统通知中不会有*私钥*指示。</span><span class="sxs-lookup"><span data-stu-id="0ca24-135">Calls from a conference to the private telephone line will not have a  *private-line*  indication in the incoming system notification.</span></span>
  
## <a name="administering-private-telephone-lines"></a><span data-ttu-id="0ca24-136">管理专用电话线路</span><span class="sxs-lookup"><span data-stu-id="0ca24-136">Administering Private Telephone Lines</span></span>

<span data-ttu-id="0ca24-p107">除创建和管理专用电话线路的技术方面外，还需要为其建立管理过程。这包括确定组织中谁可以使用专线的策略，创建和维护人员及其电话号码的列表，还可能要为高管创建专用电话簿，安排用户培训和相关任务。</span><span class="sxs-lookup"><span data-stu-id="0ca24-p107">In addition to the technical aspects of creating and managing private telephone lines, you will need to establish administrative procedures for them. This includes determining policies for who in the organization is eligible for a private line, creating and maintaining lists of people and their telephone lines, possibly creating a private telephone directory for executives, arranging for user training, and related tasks.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0ca24-p108">专用电话线路将在 Active Directory 中作为用户对象的 msRTCSIP-PrivateLine 属性存储。默认情况下，Authenticated Users 组的任何成员对此属性具有读取访问权限。</span><span class="sxs-lookup"><span data-stu-id="0ca24-p108">The private telephone line is stored in Active Directory as an msRTCSIP-PrivateLine attribute on the user object. By default any member of the Authenticated Users group has read access to this attribute.</span></span> 
  
### <a name="assigning-telephone-numbers"></a><span data-ttu-id="0ca24-141">分配电话号码</span><span class="sxs-lookup"><span data-stu-id="0ca24-141">Assigning Telephone Numbers</span></span>

 <span data-ttu-id="0ca24-142">对于需要私人电话线的新用户，其帐户的创建方式与没有私人电话线的帐户相同，使用 Skype for Business 服务器控制面板或 Skype for business Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="0ca24-142">Accounts for new users who need private telephone lines are created in the same manner as accounts without private telephone lines, using Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="0ca24-143">使用 Skype for Business Server Management Shell 中的**move-csuser** cmdlet 为用户将电话号码分配给专用电话线，例如， **move-csuser-Identity "Sip:joe@contoso.com"-PrivateLine "电话： + 14255551212"**。</span><span class="sxs-lookup"><span data-stu-id="0ca24-143">Use the **Set-CsUser** cmdlet in the Skype for Business Server Management Shell to assign a telephone number to a private telephone line for a user, for example, **Set-CsUser -Identity "sip:joe@contoso.com" -PrivateLine "Tel:+14255551212"**.</span></span>
  
<span data-ttu-id="0ca24-144">专用电话线的电话号码长度可以介于3到15个号码之间，并且前面必须带有 "电话：" 前缀。</span><span class="sxs-lookup"><span data-stu-id="0ca24-144">Telephone numbers for private telephone lines can be between 3 and 15 numbers in length and must be preceded with the "TEL:" prefix.</span></span> <span data-ttu-id="0ca24-145">这些号码可以具有任何区号和国家/地区代码，前提是您的组织有该区号和国家/地区代码的外线直拨分机。</span><span class="sxs-lookup"><span data-stu-id="0ca24-145">They can have any area code and any country/region code as long as your organization has direct inward dialing for that area code and country/region code.</span></span> 
  
<span data-ttu-id="0ca24-146">有关 cmdlet 和 Skype for business Server 命令行管理程序的详细信息，请参阅 Skype for Business 服务器管理外壳文档。</span><span class="sxs-lookup"><span data-stu-id="0ca24-146">For details about cmdlets and Skype for Business Server Management Shell, see the Skype for Business Server Management Shell documentation.</span></span>
  
### <a name="private-telephone-lines-in-mixed-deployments"></a><span data-ttu-id="0ca24-147">混合部署中的专用电话线路</span><span class="sxs-lookup"><span data-stu-id="0ca24-147">Private Telephone Lines in Mixed Deployments</span></span>

<span data-ttu-id="0ca24-148">专用电话线应仅针对 Skype for business Server 或 Lync Server 2013 的部署进行配置。</span><span class="sxs-lookup"><span data-stu-id="0ca24-148">Private telephone lines should be configured only for deployments of Skype for Business Server or Lync Server 2013.</span></span> <span data-ttu-id="0ca24-149">在其中有运行早期版本的 Lync Server 的服务器的部署中，当较早版本的用户尝试呼叫专用电话线时，呼叫路由失败的原因是服务器无法在专用电话线上执行反向号码查找。</span><span class="sxs-lookup"><span data-stu-id="0ca24-149">In a deployment in which there are servers running earlier versions of Lync Server, when a user on earlier version attempts to call a private telephone line, routing of the call fails because the server cannot perform a reverse number lookup on a private telephone line.</span></span>
  

