---
title: 'Lync Server 2013: 规划私人电话线'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for private telephone lines
ms:assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412728(v=OCS.15)
ms:contentKeyID: 48184909
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4287e4b80b146e26fe5e548c07e5df189b1960e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824566"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-private-telephone-lines-with-lync-server-2013"></a><span data-ttu-id="7ef02-102">在 Lync Server 2013 中规划私人电话线路</span><span class="sxs-lookup"><span data-stu-id="7ef02-102">Planning for private telephone lines with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ef02-103">_**主题上次修改时间:** 2013-02-11_</span><span class="sxs-lookup"><span data-stu-id="7ef02-103">_**Topic Last Modified:** 2013-02-11_</span></span>

<span data-ttu-id="7ef02-104">Lync Server 2013 引入了一种除了主要电话线之外为用户提供第二条专用电话线的功能。</span><span class="sxs-lookup"><span data-stu-id="7ef02-104">Lync Server 2013 introduces the ability to give users a second, private telephone line in addition to their primary telephone line.</span></span> <span data-ttu-id="7ef02-105">专用电话线路通常分配给需要一个未列出的电话号码以便他人直接与其取得联系的高管和其他人员。</span><span class="sxs-lookup"><span data-stu-id="7ef02-105">Private telephone lines are often assigned to executives and others who want an unlisted telephone number at which they can be reached directly.</span></span>

<span data-ttu-id="7ef02-106">专用电话线只能通过 Lync Server 命令行管理程序进行配置。</span><span class="sxs-lookup"><span data-stu-id="7ef02-106">Private telephone lines can only be configured with the Lync Server Management Shell.</span></span> <span data-ttu-id="7ef02-107">您不能通过 Lync Server 控制面板配置私人电话线。</span><span class="sxs-lookup"><span data-stu-id="7ef02-107">You cannot configure private telephone lines with the Lync Server Control Panel.</span></span> <span data-ttu-id="7ef02-108">专用电话线应仅在 Lync Server 的部署中而不是在混合部署中配置。</span><span class="sxs-lookup"><span data-stu-id="7ef02-108">Private telephone lines should be configured only in deployments of Lync Server and not in mixed deployments.</span></span>

<div>

## <a name="characteristics-of-private-telephone-lines"></a><span data-ttu-id="7ef02-109">专用电话线路的特征</span><span class="sxs-lookup"><span data-stu-id="7ef02-109">Characteristics of Private Telephone Lines</span></span>

<span data-ttu-id="7ef02-110">虽然第二条专用电话线路的概念从根本上讲很简单，但是，理解专用线路的特征及其与用户主要电话线路的异同很重要。</span><span class="sxs-lookup"><span data-stu-id="7ef02-110">Although the concept of a second, private telephone line is fundamentally simple, it is important to understand the characteristics of private lines and the ways in which they are similar to and different from users’ primary telephone lines.</span></span>

<div>

## <a name="general-characteristics-of-private-telephone-lines"></a><span data-ttu-id="7ef02-111">专用电话线路的常规特征</span><span class="sxs-lookup"><span data-stu-id="7ef02-111">General Characteristics of Private Telephone Lines</span></span>

  - <span data-ttu-id="7ef02-112">每个用户只能有一条专用电话线路。</span><span class="sxs-lookup"><span data-stu-id="7ef02-112">A user can have only one private telephone line.</span></span>

  - <span data-ttu-id="7ef02-113">具有专用电话线路的用户只有一个语音邮箱，并且只使用一个电子邮件地址接收错过的呼叫通知。</span><span class="sxs-lookup"><span data-stu-id="7ef02-113">A user with a private telephone line has only one voice mailbox and receives missed call notifications at a single email address.</span></span>

  - <span data-ttu-id="7ef02-114">具有专用电话线路的用户没有第二个 SIP 地址，并且第二条专用电话线路不会在网络上为用户提供第二个状态（如第二个即时消息身份）。</span><span class="sxs-lookup"><span data-stu-id="7ef02-114">A user with a private telephone line does not have a second SIP address, and a second, private telephone line does not give a user a second presence on the network (such as a second instant messaging identity).</span></span>

  - <span data-ttu-id="7ef02-115">专用电话线路仅适用于本地部署。</span><span class="sxs-lookup"><span data-stu-id="7ef02-115">Private telephone lines are available for on-premises deployments only.</span></span> <span data-ttu-id="7ef02-116">它们不适用于 Lync Server 的托管部署。</span><span class="sxs-lookup"><span data-stu-id="7ef02-116">They are not available with hosted deployments of Lync Server.</span></span>

</div>

<div>

## <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a><span data-ttu-id="7ef02-117">专用电话线路与主要电话线路的不同之处</span><span class="sxs-lookup"><span data-stu-id="7ef02-117">How Private Telephone Lines Differ from Primary Telephone Lines</span></span>

  - <span data-ttu-id="7ef02-118">专用电话线路的电话号码不会显示在派生自 Active Directory 域服务的电话簿或联系人列表中。</span><span class="sxs-lookup"><span data-stu-id="7ef02-118">The telephone numbers for private telephone lines do not appear in the telephone directories or Contacts lists that are derived from Active Directory Domain Services.</span></span>

  - <span data-ttu-id="7ef02-119">专用电话线路不具备以下功能：呼叫转接、团队呼叫、委派、小组电话、组内呼叫应答和响应组应用程序。</span><span class="sxs-lookup"><span data-stu-id="7ef02-119">None of the following features are available with a private telephone line: call forwarding, team call, delegation, team ring, Group Call Pickup, and Response Group application.</span></span>

  - <span data-ttu-id="7ef02-120">对专用电话线路的呼叫有特殊的响铃，呼叫的系统通知会告知用户传入呼叫位于其专用线路上。</span><span class="sxs-lookup"><span data-stu-id="7ef02-120">Calls to a private telephone line have a special ring, and the system notification for the call tells the user that the incoming call is on his or her private line.</span></span>

  - <span data-ttu-id="7ef02-p104">对专用电话线路的呼叫始终会发出响铃。它们不会遵循“请勿打扰”规则。</span><span class="sxs-lookup"><span data-stu-id="7ef02-p104">Calls to the private telephone line always ring through. They do not follow "do not disturb" rules.</span></span>

  - <span data-ttu-id="7ef02-p105">专用电话线路仅限于入站呼叫，不能用于进行传出呼叫。具有专用电话线路的用户发出呼叫时，该呼叫来自于该用户的主要电话线路，并且不会向被叫方隐藏该用户的名称或该用户的主要电话号码。</span><span class="sxs-lookup"><span data-stu-id="7ef02-p105">Private telephone lines are inbound only and cannot be used to make outgoing calls. When a user with a private telephone line makes a call, the call originates from the user’s primary telephone line and does not hide the user’s name or the user’s primary telephone number from the person called.</span></span>

</div>

<div>

## <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a><span data-ttu-id="7ef02-125">专用电话线路与主要电话线路的相似之处</span><span class="sxs-lookup"><span data-stu-id="7ef02-125">How Private Telephone Lines Are Similar to Primary Telephone Lines</span></span>

  - <span data-ttu-id="7ef02-126">专用电话线路上的未接听呼叫将路由到与主要电话线路相同的语音邮件收件箱（如果已启用语音邮件）。</span><span class="sxs-lookup"><span data-stu-id="7ef02-126">Unanswered calls to a private telephone line are routed to the same voice mail inbox as for the primary telephone line (if voice mail is enabled).</span></span>

  - <span data-ttu-id="7ef02-127">呼叫寄存和呼叫应答与专用电话线路协同工作的方式和其与用户主要电话线路协同工作的方式完全相同。</span><span class="sxs-lookup"><span data-stu-id="7ef02-127">Call park and call pickup work with private telephone lines in exactly the same manner as they do with the user’s primary telephone line.</span></span>

  - <span data-ttu-id="7ef02-128">在用户的主要电话线路上启用同时响铃后，也会在专用电话线路上启用该功能。</span><span class="sxs-lookup"><span data-stu-id="7ef02-128">When simultaneous ringing is enabled on a user’s primary telephone line, it is also enabled on the private telephone line.</span></span>

  - <span data-ttu-id="7ef02-129">专用电话线路的电话号码记录在呼叫详细信息记录中，方式与用户主要电话线路的电话号码相同，但会指明这是专用电话号码。</span><span class="sxs-lookup"><span data-stu-id="7ef02-129">The telephone number for a private telephone line is recorded in the call detail record in the same manner as the telephone number for a user’s primary telephone line, but with an indication that it is a private telephone number.</span></span>

  - <span data-ttu-id="7ef02-130">用户应答专用电话线路上的呼叫后，该呼叫的处理方式与该用户的主要电话线路上的呼叫相同。</span><span class="sxs-lookup"><span data-stu-id="7ef02-130">After a user answers a call on a private telephone line, the call is treated the same as a call on the user’s primary telephone line.</span></span> <span data-ttu-id="7ef02-131">例如, 如果通过专用电话线接收呼叫的用户转发呼叫或邀请其他人加入电话会议, 则用户的名称将显示在 Lync 2013 中, 并且用户的主电话线的电话号码将显示在 "来电显示" 中。</span><span class="sxs-lookup"><span data-stu-id="7ef02-131">For example, if a user who receives a call on a private telephone line forwards the call or invites others to a conference call, the user’s name appears in Lync 2013, and the telephone number for the user’s primary telephone line appears in caller ID.</span></span>

  - <span data-ttu-id="7ef02-132">用户可以转接来自于专用电话线路的呼叫（应答前，将呼叫重定向到其他目标，如移动电话或家庭电话），方式与主要电话线路相同。</span><span class="sxs-lookup"><span data-stu-id="7ef02-132">A user can deflect a call (redirect the call to another destination, such as a mobile phone or home phone, before answering) from the private telephone line in the same manner as with a primary telephone line.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7ef02-133">专用线路的呼叫路由到备用电话号码后，专用电话线路的电话号码将提供给备用电话号码，并可以显示在该号码的日志中。</span><span class="sxs-lookup"><span data-stu-id="7ef02-133">When a call to a private line is routed to an alternate telephone number, the telephone number for the private telephone line is made available to the alternate telephone number and can be displayed in the logs for that number.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7ef02-134">对于从会议向专用电话线路发出的呼叫，传入系统通知中不会指示“<EM>专线</EM>”。</span><span class="sxs-lookup"><span data-stu-id="7ef02-134">Calls from a conference to the private telephone line will not have a <EM>private-line</EM> indication in the incoming system notification.</span></span>

    
    </div>

</div>

</div>

<div>

## <a name="administering-private-telephone-lines"></a><span data-ttu-id="7ef02-135">管理专用电话线路</span><span class="sxs-lookup"><span data-stu-id="7ef02-135">Administering Private Telephone Lines</span></span>

<span data-ttu-id="7ef02-p107">除创建和管理专用电话线路的技术方面外，还需要为其建立管理过程。这包括确定组织中谁可以使用专线的策略，创建和维护人员及其电话号码的列表，还可能要为高管创建专用电话簿，安排用户培训和相关任务。</span><span class="sxs-lookup"><span data-stu-id="7ef02-p107">In addition to the technical aspects of creating and managing private telephone lines, you will need to establish administrative procedures for them. This includes determining policies for who in the organization is eligible for a private line, creating and maintaining lists of people and their telephone lines, possibly creating a private telephone directory for executives, arranging for user training, and related tasks.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7ef02-p108">专用电话线路将在 Active Directory 中作为用户对象的 msRTCSIP-PrivateLine 属性存储。默认情况下，Authenticated Users 组的任何成员对此属性具有读取访问权限。</span><span class="sxs-lookup"><span data-stu-id="7ef02-p108">The private telephone line is stored in Active Directory as an msRTCSIP-PrivateLine attribute on the user object. By default any member of the Authenticated Users group has read access to this attribute.</span></span>



</div>

<div>

## <a name="assigning-telephone-numbers"></a><span data-ttu-id="7ef02-140">分配电话号码</span><span class="sxs-lookup"><span data-stu-id="7ef02-140">Assigning Telephone Numbers</span></span>

<span data-ttu-id="7ef02-141">对于需要私人电话线的新用户, 其帐户的创建方式与没有私人电话线的帐户相同, 使用 Lync Server 控制面板或 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="7ef02-141">Accounts for new users who need private telephone lines are created in the same manner as accounts without private telephone lines, using Lync Server Control Panel or Lync Server Management Shell.</span></span>

<span data-ttu-id="7ef02-142">使用 Lync Server Management Shell 中的**move-csuser** cmdlet 为用户将电话号码分配给专用电话线, 例如, **move-csuser-Identity "Sip:joe@contoso.com"-PrivateLine "电话: + 14255551212"**。</span><span class="sxs-lookup"><span data-stu-id="7ef02-142">Use the **Set-CsUser** cmdlet in the Lync Server Management Shell to assign a telephone number to a private telephone line for a user, for example, **Set-CsUser -Identity "sip:joe@contoso.com" -PrivateLine "Tel:+14255551212"**.</span></span>

<span data-ttu-id="7ef02-143">专用电话线的电话号码长度可以介于3到15个号码之间, 并且前面必须带有 "电话:" 前缀。</span><span class="sxs-lookup"><span data-stu-id="7ef02-143">Telephone numbers for private telephone lines can be between 3 and 15 numbers in length and must be preceded with the "TEL:" prefix.</span></span> <span data-ttu-id="7ef02-144">这些号码可以具有任何区号和国家/地区代码，前提是您的组织有该区号和国家/地区代码的外线直拨分机。</span><span class="sxs-lookup"><span data-stu-id="7ef02-144">They can have any area code and any country/region code as long as your organization has direct inward dialing for that area code and country/region code.</span></span>

<span data-ttu-id="7ef02-145">有关 cmdlet 和 Lync Server 命令行管理程序的详细信息, 请参阅[Lync server 2013 管理外壳](lync-server-2013-lync-server-management-shell.md)文档。</span><span class="sxs-lookup"><span data-stu-id="7ef02-145">For details about cmdlets and Lync Server Management Shell, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

<div>

## <a name="private-telephone-lines-in-mixed-deployments"></a><span data-ttu-id="7ef02-146">混合部署中的专用电话线路</span><span class="sxs-lookup"><span data-stu-id="7ef02-146">Private Telephone Lines in Mixed Deployments</span></span>

<span data-ttu-id="7ef02-147">专用电话线应仅针对 Lync Server 的部署进行配置。</span><span class="sxs-lookup"><span data-stu-id="7ef02-147">Private telephone lines should be configured only for deployments of Lync Server.</span></span> <span data-ttu-id="7ef02-148">在具有 Lync Server 和 Office 通信服务器2007或 Office 通信服务器 2007 R2 服务器的部署中, 如果早期版本的用户尝试呼叫专用电话线, 则呼叫路由失败的原因是服务器无法在专用电话线路上执行反向号码查找。</span><span class="sxs-lookup"><span data-stu-id="7ef02-148">In a deployment in which there are both Lync Server and Office Communications Server 2007 or Office Communications Server 2007 R2 servers, when a user on earlier version attempts to call a private telephone line, routing of the call fails because the server cannot perform a reverse number lookup on a private telephone line.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

