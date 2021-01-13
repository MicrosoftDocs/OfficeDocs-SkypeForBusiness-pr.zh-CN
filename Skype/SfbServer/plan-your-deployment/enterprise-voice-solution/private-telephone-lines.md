---
title: 使用 Skype for Business 规划专用电话线路
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
ms.assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
description: 规划 Skype for Business Server (中的专用) 辅助电话线路企业语音。
ms.openlocfilehash: 0ae62c4ee56a16583106c89b5ca1b190ee242e2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813592"
---
# <a name="plan-for-private-telephone-lines-with-skype-for-business"></a><span data-ttu-id="bf845-103">使用 Skype for Business 规划专用电话线路</span><span class="sxs-lookup"><span data-stu-id="bf845-103">Plan for private telephone lines with Skype for Business</span></span>
 
<span data-ttu-id="bf845-104">规划 Skype for Business Server (中的专用) 辅助电话线路企业语音。</span><span class="sxs-lookup"><span data-stu-id="bf845-104">Planning for private (secondary) telephone lines in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="bf845-105">除了用户的主要电话线路外，Skype for Business Server 还允许用户使用第二条专用电话线路。</span><span class="sxs-lookup"><span data-stu-id="bf845-105">Skype for Business Server enables you to give users a second, private telephone line in addition to their primary telephone line.</span></span> <span data-ttu-id="bf845-106">专用电话线路通常分配给需要一个未列出的电话号码以便他人直接与其取得联系的高管和其他人员。</span><span class="sxs-lookup"><span data-stu-id="bf845-106">Private telephone lines are often assigned to executives and others who want an unlisted telephone number at which they can be reached directly.</span></span>
  
<span data-ttu-id="bf845-107">专用电话线路只能使用 Skype for Business Server 命令行管理程序进行配置。</span><span class="sxs-lookup"><span data-stu-id="bf845-107">Private telephone lines can only be configured with the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="bf845-108">不能使用 Skype for Business Server 控制面板配置专用电话线路。</span><span class="sxs-lookup"><span data-stu-id="bf845-108">You cannot configure private telephone lines with the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="bf845-109">专用电话线路只能在 Skype for Business Server 的部署中配置，而不应在混合部署中配置。</span><span class="sxs-lookup"><span data-stu-id="bf845-109">Private telephone lines should be configured only in deployments of Skype for Business Server and not in mixed deployments.</span></span>
  
## <a name="characteristics-of-private-telephone-lines"></a><span data-ttu-id="bf845-110">专用电话线路的特征</span><span class="sxs-lookup"><span data-stu-id="bf845-110">Characteristics of Private Telephone Lines</span></span>

<span data-ttu-id="bf845-111">尽管第二条专用电话线路的概念基本上很简单，但了解专用电话线路的特征及其与用户的主要电话线路相似和不同的方式很重要。</span><span class="sxs-lookup"><span data-stu-id="bf845-111">Although the concept of a second, private telephone line is fundamentally simple, it is important to understand the characteristics of private lines and the ways in which they are similar to and different from users' primary telephone lines.</span></span>
  
### <a name="general-characteristics-of-private-telephone-lines"></a><span data-ttu-id="bf845-112">专用电话线路的常规特征</span><span class="sxs-lookup"><span data-stu-id="bf845-112">General Characteristics of Private Telephone Lines</span></span>

- <span data-ttu-id="bf845-113">每个用户只能有一条专用电话线路。</span><span class="sxs-lookup"><span data-stu-id="bf845-113">A user can have only one private telephone line.</span></span>
    
- <span data-ttu-id="bf845-114">具有专用电话线路的用户只有一个语音邮箱，并且只使用一个电子邮件地址接收错过的呼叫通知。</span><span class="sxs-lookup"><span data-stu-id="bf845-114">A user with a private telephone line has only one voice mailbox and receives missed call notifications at a single email address.</span></span>
    
- <span data-ttu-id="bf845-115">具有专用电话线路的用户没有第二个 SIP 地址，并且第二条专用电话线路不会在网络上为用户提供第二个状态（如第二个即时消息身份）。</span><span class="sxs-lookup"><span data-stu-id="bf845-115">A user with a private telephone line does not have a second SIP address, and a second, private telephone line does not give a user a second presence on the network (such as a second instant messaging identity).</span></span> 
    
- <span data-ttu-id="bf845-116">专用电话线路仅适用于本地部署。</span><span class="sxs-lookup"><span data-stu-id="bf845-116">Private telephone lines are available for on-premises deployments only.</span></span> <span data-ttu-id="bf845-117">它们不适用于 Skype for Business Server 的托管部署。</span><span class="sxs-lookup"><span data-stu-id="bf845-117">They are not available with hosted deployments of Skype for Business Server.</span></span>
    
### <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a><span data-ttu-id="bf845-118">专用电话线路与主要电话线路的不同之处</span><span class="sxs-lookup"><span data-stu-id="bf845-118">How Private Telephone Lines Differ from Primary Telephone Lines</span></span>

- <span data-ttu-id="bf845-119">专用电话线路的电话号码不会显示在派生自 Active Directory 域服务的电话簿或联系人列表中。</span><span class="sxs-lookup"><span data-stu-id="bf845-119">The telephone numbers for private telephone lines do not appear in the telephone directories or Contacts lists that are derived from Active Directory Domain Services.</span></span>
    
- <span data-ttu-id="bf845-120">专用电话线路没有以下功能可用：呼叫转发、团队呼叫、委派、团队响铃、组内呼叫应答和响应组应用程序。</span><span class="sxs-lookup"><span data-stu-id="bf845-120">None of the following features are available with a private telephone line: call forwarding, team call, delegation, team ring, Group Call Pickup, and Response Group application.</span></span>
    
- <span data-ttu-id="bf845-121">对专用电话线路的呼叫有特殊的响铃，呼叫的系统通知会告知用户传入呼叫位于其专用线路上。</span><span class="sxs-lookup"><span data-stu-id="bf845-121">Calls to a private telephone line have a special ring, and the system notification for the call tells the user that the incoming call is on his or her private line.</span></span>
    
- <span data-ttu-id="bf845-p104">对专用电话线路的呼叫始终会发出响铃。它们不会遵循“请勿打扰”规则。</span><span class="sxs-lookup"><span data-stu-id="bf845-p104">Calls to the private telephone line always ring through. They do not follow "do not disturb" rules.</span></span>
    
- <span data-ttu-id="bf845-124">专用电话线路仅限于入站呼叫，不能用于进行传出呼叫。</span><span class="sxs-lookup"><span data-stu-id="bf845-124">Private telephone lines are inbound only and cannot be used to make outgoing calls.</span></span> <span data-ttu-id="bf845-125">当具有专用电话线路的用户发起呼叫时，该呼叫源自该用户的主要电话线路，并且不会向被叫人员隐藏该用户的姓名或用户的主要电话号码。</span><span class="sxs-lookup"><span data-stu-id="bf845-125">When a user with a private telephone line makes a call, the call originates from the user's primary telephone line and does not hide the user's name or the user's primary telephone number from the person called.</span></span>
    
### <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a><span data-ttu-id="bf845-126">专用电话线路与主要电话线路的相似之处</span><span class="sxs-lookup"><span data-stu-id="bf845-126">How Private Telephone Lines Are Similar to Primary Telephone Lines</span></span>

- <span data-ttu-id="bf845-127">专用电话线路上的未接听呼叫将路由到与主要电话线路相同的语音邮件收件箱（如果已启用语音邮件）。</span><span class="sxs-lookup"><span data-stu-id="bf845-127">Unanswered calls to a private telephone line are routed to the same voice mail inbox as for the primary telephone line (if voice mail is enabled).</span></span>
    
- <span data-ttu-id="bf845-128">呼叫接听和呼叫接听使用专用电话线路的方式与使用用户的主要电话线路的方式完全相同。</span><span class="sxs-lookup"><span data-stu-id="bf845-128">Call park and call pickup work with private telephone lines in exactly the same manner as they do with the user's primary telephone line.</span></span>
    
- <span data-ttu-id="bf845-129">在用户的主要电话线路上启用同时响铃时，也会在专用电话线路上启用此功能。</span><span class="sxs-lookup"><span data-stu-id="bf845-129">When simultaneous ringing is enabled on a user's primary telephone line, it is also enabled on the private telephone line.</span></span>
    
- <span data-ttu-id="bf845-130">专用电话线路的电话号码在呼叫详细信息记录中记录的方式与用户的主要电话线路的电话号码相同，但指示它是专用电话号码。</span><span class="sxs-lookup"><span data-stu-id="bf845-130">The telephone number for a private telephone line is recorded in the call detail record in the same manner as the telephone number for a user's primary telephone line, but with an indication that it is a private telephone number.</span></span>
    
- <span data-ttu-id="bf845-131">在用户应答专用电话线路上的呼叫后，该呼叫将被视为与该用户的主要电话线路上的呼叫相同。</span><span class="sxs-lookup"><span data-stu-id="bf845-131">After a user answers a call on a private telephone line, the call is treated the same as a call on the user's primary telephone line.</span></span> <span data-ttu-id="bf845-132">例如，如果在专用电话线路上收到呼叫的用户转发该呼叫或邀请其他人加入电话会议，该用户的名称将显示在 Skype for Business 中，并且该用户的主要电话线路的电话号码将显示在呼叫者 ID 中。</span><span class="sxs-lookup"><span data-stu-id="bf845-132">For example, if a user who receives a call on a private telephone line forwards the call or invites others to a conference call, the user's name appears in Skype for Business, and the telephone number for the user's primary telephone line appears in caller ID.</span></span>
    
- <span data-ttu-id="bf845-133">用户可以转接来自于专用电话线路的呼叫（应答前，将呼叫重定向到其他目标，如移动电话或家庭电话），方式与主要电话线路相同。</span><span class="sxs-lookup"><span data-stu-id="bf845-133">A user can deflect a call (redirect the call to another destination, such as a mobile phone or home phone, before answering) from the private telephone line in the same manner as with a primary telephone line.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="bf845-134">专用线路的呼叫路由到备用电话号码后，专用电话线路的电话号码将提供给备用电话号码，并可以显示在该号码的日志中。</span><span class="sxs-lookup"><span data-stu-id="bf845-134">When a call to a private line is routed to an alternate telephone number, the telephone number for the private telephone line is made available to the alternate telephone number and can be displayed in the logs for that number.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="bf845-135">从会议到专用电话线路的呼叫在传入系统通知中将不会有专线指示。</span><span class="sxs-lookup"><span data-stu-id="bf845-135">Calls from a conference to the private telephone line will not have a  *private-line*  indication in the incoming system notification.</span></span>
  
## <a name="administering-private-telephone-lines"></a><span data-ttu-id="bf845-136">管理专用电话线路</span><span class="sxs-lookup"><span data-stu-id="bf845-136">Administering Private Telephone Lines</span></span>

<span data-ttu-id="bf845-p107">除创建和管理专用电话线路的技术方面外，还需要为其建立管理过程。这包括确定组织中谁可以使用专线的策略，创建和维护人员及其电话号码的列表，还可能要为高管创建专用电话簿，安排用户培训和相关任务。</span><span class="sxs-lookup"><span data-stu-id="bf845-p107">In addition to the technical aspects of creating and managing private telephone lines, you will need to establish administrative procedures for them. This includes determining policies for who in the organization is eligible for a private line, creating and maintaining lists of people and their telephone lines, possibly creating a private telephone directory for executives, arranging for user training, and related tasks.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bf845-p108">专用电话线路将在 Active Directory 中作为用户对象的 msRTCSIP-PrivateLine 属性存储。默认情况下，Authenticated Users 组的任何成员对此属性具有读取访问权限。</span><span class="sxs-lookup"><span data-stu-id="bf845-p108">The private telephone line is stored in Active Directory as an msRTCSIP-PrivateLine attribute on the user object. By default any member of the Authenticated Users group has read access to this attribute.</span></span> 
  
### <a name="assigning-telephone-numbers"></a><span data-ttu-id="bf845-141">分配电话号码</span><span class="sxs-lookup"><span data-stu-id="bf845-141">Assigning Telephone Numbers</span></span>

 <span data-ttu-id="bf845-142">需要专用电话线路的新用户的帐户创建方式与没有专用电话线路的帐户相同，即使用 Skype for Business Server 控制面板或 Skype for Business Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="bf845-142">Accounts for new users who need private telephone lines are created in the same manner as accounts without private telephone lines, using Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="bf845-143">使用 Skype for Business Server 命令行管理程序 中的 **Set-CsUser** cmdlet 将电话号码分配给用户的专用电话线路，例如 **，Set-CsUser -Identity "sip:joe@contoso.com" -PrivateLine "Tel：+14255551212"**。</span><span class="sxs-lookup"><span data-stu-id="bf845-143">Use the **Set-CsUser** cmdlet in the Skype for Business Server Management Shell to assign a telephone number to a private telephone line for a user, for example, **Set-CsUser -Identity "sip:joe@contoso.com" -PrivateLine "Tel:+14255551212"**.</span></span>
  
<span data-ttu-id="bf845-144">专用电话线路的电话号码长度可以介于 3 到 15 之间，并且必须以"TEL："前缀开头。</span><span class="sxs-lookup"><span data-stu-id="bf845-144">Telephone numbers for private telephone lines can be between 3 and 15 numbers in length and must be preceded with the "TEL:" prefix.</span></span> <span data-ttu-id="bf845-145">这些号码可以具有任何区号和国家/地区代码，前提是您的组织有该区号和国家/地区代码的外线直拨分机。</span><span class="sxs-lookup"><span data-stu-id="bf845-145">They can have any area code and any country/region code as long as your organization has direct inward dialing for that area code and country/region code.</span></span> 
  
<span data-ttu-id="bf845-146">有关 cmdlet 和 Skype for Business Server 命令行管理程序 的详细信息，请参阅 Skype for Business Server 命令行管理程序 文档。</span><span class="sxs-lookup"><span data-stu-id="bf845-146">For details about cmdlets and Skype for Business Server Management Shell, see the Skype for Business Server Management Shell documentation.</span></span>
  
### <a name="private-telephone-lines-in-mixed-deployments"></a><span data-ttu-id="bf845-147">混合部署中的专用电话线路</span><span class="sxs-lookup"><span data-stu-id="bf845-147">Private Telephone Lines in Mixed Deployments</span></span>

<span data-ttu-id="bf845-148">专用电话线路应仅配置为部署 Skype for Business Server 或 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="bf845-148">Private telephone lines should be configured only for deployments of Skype for Business Server or Lync Server 2013.</span></span> <span data-ttu-id="bf845-149">在运行 Lync Server 早期版本的服务器部署中，当早期版本上的用户尝试呼叫专用电话线路时，呼叫路由失败，因为服务器无法在专用电话线路上执行反向号码查找。</span><span class="sxs-lookup"><span data-stu-id="bf845-149">In a deployment in which there are servers running earlier versions of Lync Server, when a user on earlier version attempts to call a private telephone line, routing of the call fails because the server cannot perform a reverse number lookup on a private telephone line.</span></span>
  

