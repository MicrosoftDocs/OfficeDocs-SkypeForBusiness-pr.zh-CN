---
title: 通过 Skype for Business Server 中的工作计划呼叫计划
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
ms.assetid: a33ec637-9ac8-4cb7-b3b2-88d432efc078
description: 通过 Skype for business Server 中的工作计划进行呼叫计划，从而支持 Skype for Business 和 PBX 电话系统之间的集成，以便用户可以使用 Skype for business 控制其 PBX 电话。
ms.openlocfilehash: 38c61145dcad609c75e7b2e3433efee307f8dc28
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803152"
---
# <a name="plan-for-call-via-work-in-skype-for-business-server"></a><span data-ttu-id="1a539-103">通过 Skype for Business Server 中的工作计划呼叫计划</span><span class="sxs-lookup"><span data-stu-id="1a539-103">Plan for Call Via Work in Skype for Business Server</span></span>
 
<span data-ttu-id="1a539-104">通过 Skype for business Server 中的工作计划进行呼叫计划，从而支持 Skype for Business 和 PBX 电话系统之间的集成，以便用户可以使用 Skype for business 控制其 PBX 电话。</span><span class="sxs-lookup"><span data-stu-id="1a539-104">Planning for Call Via Work in Skype for Business Server, which enables integration between Skype for Business and your PBX phone system, so that users can use Skype for Business to control their PBX phones.</span></span>
  
 <span data-ttu-id="1a539-105">**通过工作进行呼叫**是 Skype For business 服务器中的一项新功能，使你能够将 Skype for business 解决方案与现有的 PBX 电话系统集成。</span><span class="sxs-lookup"><span data-stu-id="1a539-105">**Call Via Work** is a new feature in Skype for Business Server which enables you to integrate your Skype for Business solution with your existing PBX phone systems.</span></span> <span data-ttu-id="1a539-106">通过工作启用呼叫的用户可以在 Skype for Business 中单击，以在部署或外部用户中调用其他用户。</span><span class="sxs-lookup"><span data-stu-id="1a539-106">A user enabled for Call Via Work can click in Skype for Business to call another user, either within your deployment or an external user.</span></span> <span data-ttu-id="1a539-107">将使用用户的 PBX 电话完成呼叫。</span><span class="sxs-lookup"><span data-stu-id="1a539-107">The call is completed using the user's PBX phone.</span></span> <span data-ttu-id="1a539-108">这使使用 PBX 手机的用户可以在其丰富的 Skype for business 对话中包含音频。</span><span class="sxs-lookup"><span data-stu-id="1a539-108">This enables a user with a PBX phone to include audio in their rich Skype for Business conversations.</span></span> <span data-ttu-id="1a539-109">在早期版本的 Lync Server 远程呼叫控制中，支持用户使用 Lync Server 控制其 PBX 手机的功能。</span><span class="sxs-lookup"><span data-stu-id="1a539-109">In previous versions of Lync Server remote call control was a feature which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="1a539-110">在 Skype for Business 服务器中，此功能已替换为 "通过工作通话"。</span><span class="sxs-lookup"><span data-stu-id="1a539-110">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>
  
<span data-ttu-id="1a539-111">通过工作进行呼叫为 PBX 电话用户启用以下功能</span><span class="sxs-lookup"><span data-stu-id="1a539-111">Call Via Work enables the following for PBX phone users</span></span>
  
- <span data-ttu-id="1a539-112">单击呼叫，通过 PBX 电话提供音频。</span><span class="sxs-lookup"><span data-stu-id="1a539-112">Click-to-call experience, with the audio provided through the PBX phone.</span></span>
    
- <span data-ttu-id="1a539-113">状态、用户搜索和 IM 集成-例如，通过 IM 会话中的工作用户进行两次通话可将音频添加到其会话中，使用 PBX 手机提供的音频。</span><span class="sxs-lookup"><span data-stu-id="1a539-113">Presence, user search, and IM integration-- for example, two Call Via Work users in an IM session can add audio to their session, with the audio provided through the PBX phones.</span></span>
    
- <span data-ttu-id="1a539-114">通过工作呼叫向呼叫添加即时消息、应用程序共享和文件传输的功能。</span><span class="sxs-lookup"><span data-stu-id="1a539-114">The ability to add IM, application sharing, and file transfer to a Call Via Work call.</span></span>
    
- <span data-ttu-id="1a539-115">一键式会议加入功能</span><span class="sxs-lookup"><span data-stu-id="1a539-115">One-click meeting join capability</span></span>
    
## <a name="how-it-works"></a><span data-ttu-id="1a539-116">运作方式</span><span class="sxs-lookup"><span data-stu-id="1a539-116">How it works</span></span>

<span data-ttu-id="1a539-117">通过工作进行呼叫使用统一通信 Web API （UCWA）作为 PBX 系统和 Skype for Business Server 部署之间的后端到后用户代理（B2BUA），以便无需使用计算机支持的电信应用程序（CSTA）网关连接带有 PBX 系统的 Skype for business 服务器。</span><span class="sxs-lookup"><span data-stu-id="1a539-117">Call Via Work uses Unified Communications Web API (UCWA) as the back-to-back user agent (B2BUA) between the PBX system and your Skype for Business Server deployment, so that no computer-supported telecommunications application (CSTA) gateway is needed to connect Skype for Business Server with your PBX system.</span></span> <span data-ttu-id="1a539-118">UCWA 是以前版本的 Lync Server 中引入的一种服务，可与移动设备和 web 客户端建立连接，并且会在每台前端服务器上自动安装。</span><span class="sxs-lookup"><span data-stu-id="1a539-118">UCWA is a service introduced in previous versions of Lync Server to enable connectivity with mobile and web clients, and is automatically installed on every Front End Server.</span></span>
  
### <a name="call-workflow-for-a-call-via-work-call"></a><span data-ttu-id="1a539-119">通过工作呼叫进行呼叫的通话工作流</span><span class="sxs-lookup"><span data-stu-id="1a539-119">Call workflow for a Call Via Work call</span></span>

<span data-ttu-id="1a539-120">以下示例说明了通过工作启用呼叫呼叫的用户可以使用 Skype for Business 服务器进行呼叫：</span><span class="sxs-lookup"><span data-stu-id="1a539-120">The following illustrates how a user enabled for Call Via Work can use the Skype for Business Server to make a call:</span></span>
  
![显示单位电话呼叫通话期间的步骤；首先，呼叫者在 Skype for Business 客户端中单击呼叫某人；随后 UCMA 使呼叫者的电话响铃。在呼叫者拿起电话时，呼叫接收人](../../media/050e88ed-e18e-40c0-84d5-b17fe40c305a.jpg)
  
1. <span data-ttu-id="1a539-123">用户在其 Skype for Business 客户端中选择用户，然后单击 "电话" 图标以呼叫它们。</span><span class="sxs-lookup"><span data-stu-id="1a539-123">The user selects a user in their Skype for Business client, and clicks the phone icon to call them.</span></span> <span data-ttu-id="1a539-124">或者，在 IM 对话期间，用户通过单击呼叫正在与其进行会话的用户。</span><span class="sxs-lookup"><span data-stu-id="1a539-124">Or, during an IM conversation, the user clicks to call the user they are having the session with.</span></span>
    
2. <span data-ttu-id="1a539-125">发出呼叫的用户的 PBX 电话开始响铃。</span><span class="sxs-lookup"><span data-stu-id="1a539-125">The PBX phone of the user who placed the call starts to ring.</span></span> <span data-ttu-id="1a539-126">此电话的来电显示方式显示您已设置为在通过工作电话拨打电话的所有用户的来电显示中显示的全球电话号码。</span><span class="sxs-lookup"><span data-stu-id="1a539-126">The caller ID for this phone shows a global phone number which you have set up to show in the caller ID of all users placing Call Via Work calls.</span></span> <span data-ttu-id="1a539-127">此全球电话号码不是与任何一人的电话相对应的实际电话号码。</span><span class="sxs-lookup"><span data-stu-id="1a539-127">This global phone number is not an actual phone number that corresponds to any one person's phone.</span></span> <span data-ttu-id="1a539-128">相反，它是一个视觉信号，让用户知道这是其自己的传出呼叫，而不是同时发生的传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="1a539-128">Instead, it is a visual signal to let a user know that this is their own outgoing call, and not an incoming call happening at the same time.</span></span> <span data-ttu-id="1a539-129">当您通过工作部署呼叫时，您应该向这些用户讲解此全球电话号码及其含义。</span><span class="sxs-lookup"><span data-stu-id="1a539-129">When you deploy Call Via Work, you should educate those users about this global phone number and what it means.</span></span>
    
3. <span data-ttu-id="1a539-130">拨打呼叫的用户拿起他们的 PBX 电话。</span><span class="sxs-lookup"><span data-stu-id="1a539-130">The user who placed the call picks up their PBX phone.</span></span> <span data-ttu-id="1a539-131">然后，Skype for Business 将开始对被呼叫方的语音呼叫。</span><span class="sxs-lookup"><span data-stu-id="1a539-131">Skype for Business then initiates the voice call to the callee.</span></span> 
    
4. <span data-ttu-id="1a539-132">当被呼叫方接听时，语音通话开始。</span><span class="sxs-lookup"><span data-stu-id="1a539-132">When the callee answers, the voice call begins.</span></span> <span data-ttu-id="1a539-133">如果两个用户已有即时消息会话，则可以继续。</span><span class="sxs-lookup"><span data-stu-id="1a539-133">If the two users already had an IM session going, it can continue.</span></span>
    
### <a name="joining-a-conference-with-call-via-work"></a><span data-ttu-id="1a539-134">通过工作通过通话加入会议</span><span class="sxs-lookup"><span data-stu-id="1a539-134">Joining a Conference With Call Via Work</span></span>

<span data-ttu-id="1a539-135">通过单击会议 URL，通过工作用户的呼叫可加入计划会议。</span><span class="sxs-lookup"><span data-stu-id="1a539-135">A Call Via Work user can join a scheduled meeting by clicking the meeting URL.</span></span> <span data-ttu-id="1a539-136">然后，Skype for Business 将显示 "**拨出**" 消息，直到会议服务拨打用户的 PBX 电话。</span><span class="sxs-lookup"><span data-stu-id="1a539-136">Skype for Business then shows a **Dialing out to** message until the meeting service dials the user's PBX phone.</span></span> <span data-ttu-id="1a539-137">通过工作用户进行呼叫，然后领取 PBX 电话并加入会议。</span><span class="sxs-lookup"><span data-stu-id="1a539-137">The Call Via Work user then picks up the PBX phone and joins the meeting.</span></span>
  
<span data-ttu-id="1a539-138">通过工作用户进行的通话还可以使用 Skype for Business 中的 "**立即开会**" 选项创建 "立即开会" 会议。</span><span class="sxs-lookup"><span data-stu-id="1a539-138">A Call Via Work user can also use the **Meet Now** option in Skype for Business to create Meet Now meetings.</span></span> <span data-ttu-id="1a539-139">然后，用户看到 "**拨出到**" 消息和 PBX 电话响铃。</span><span class="sxs-lookup"><span data-stu-id="1a539-139">The user then sees the **Dialing out to** message, and the PBX phone rings.</span></span>
  
<span data-ttu-id="1a539-140">通过工作用户拨打的电话还可以通过从 Skype for Business 呼叫会议桥号码拨入会议。</span><span class="sxs-lookup"><span data-stu-id="1a539-140">A Call Via Work user can also dial in to a meeting by calling the Conference Bridge number from within Skype for Business.</span></span> <span data-ttu-id="1a539-141">如果需要会议 PIN，用户必须使用 PBX 电话输入 PIN 码。</span><span class="sxs-lookup"><span data-stu-id="1a539-141">If a conference PIN is required, the user must use their PBX phone to input the PIN.</span></span>
  
### <a name="incoming-calls"></a><span data-ttu-id="1a539-142">传入呼叫</span><span class="sxs-lookup"><span data-stu-id="1a539-142">Incoming Calls</span></span>

<span data-ttu-id="1a539-143">通过工作启用呼叫呼叫的用户收到 Skype for Business 呼叫时，PBX 电话和用户的 Skype for Business 客户端同时拨打所有电话（如果用户已设置同时拨打）。</span><span class="sxs-lookup"><span data-stu-id="1a539-143">When a user enabled for Call Via Work receives a Skype for Business call, the PBX phone and the user's Skype for Business clients all ring simultaneously (if the user has set up simultaneous ring).</span></span> <span data-ttu-id="1a539-144">用户可以通过使用 PBX 手机或单击 Skype for Business 通知上的 "**接受**" 来接受呼叫。</span><span class="sxs-lookup"><span data-stu-id="1a539-144">The user can accept the call either by picking up the PBX phone or clicking **Accept** on the Skype for Business notification.</span></span> <span data-ttu-id="1a539-145">如果用户使用 Skype for Business 接受呼叫，则通话的 Skype for business 窗口保持打开状态。</span><span class="sxs-lookup"><span data-stu-id="1a539-145">If the user accepts the call using Skype for Business, the Skype for Business window for the call stays open.</span></span> <span data-ttu-id="1a539-146">但是，如果用户通过 PBX 手机接受呼叫，则 Skype for business 通知窗口将关闭，并且没有 Skype for business 会话，只能通过 PBX 电话进行语音通话。</span><span class="sxs-lookup"><span data-stu-id="1a539-146">But if the user accepts the call by picking up the PBX phone, then the Skype for Business notification window closes and there is no Skype for Business session, only the voice call over the PBX phone.</span></span>
  
<span data-ttu-id="1a539-147">当启用通过工作呼叫呼叫的用户收到 PBX 呼叫时，仅使用 PBX 电话响铃。</span><span class="sxs-lookup"><span data-stu-id="1a539-147">When a user enabled for Call Via Work receives a PBX call, only the PBX phone rings.</span></span>
  
## <a name="limitations-of-call-via-work"></a><span data-ttu-id="1a539-148">通过工作的通话限制</span><span class="sxs-lookup"><span data-stu-id="1a539-148">Limitations of Call Via Work</span></span>

<span data-ttu-id="1a539-149">通过工作进行呼叫是一种需要很少硬件设置的语音解决方案，但与完全企业语音或远程通话控制中提供的功能有一定限制。</span><span class="sxs-lookup"><span data-stu-id="1a539-149">Call Via Work is a voice solution that requires little hardware setup, but has limitations compared to the features available in full Enterprise Voice or remote call control.</span></span> <span data-ttu-id="1a539-150">通过工作拨打的电话有以下限制：</span><span class="sxs-lookup"><span data-stu-id="1a539-150">Call Via Work has the following limitations:</span></span>
  
- <span data-ttu-id="1a539-151">如果通过工作用户拨打电话时，通过工作回呼号码设置呼叫转移到呼叫，而有人试图邀请用户的电话号码邀请此用户加入会议，邀请将不会到达用户。</span><span class="sxs-lookup"><span data-stu-id="1a539-151">If a Call Via Work user has set up call forwarding to the Call Via Work callback number, and someone tries to invite this user to a meeting by the user's phone number, the invitation will not reach the user.</span></span> <span data-ttu-id="1a539-152">你应通过单击名称而不是电话号码，向用户提供邀请参与者加入会议的操作。</span><span class="sxs-lookup"><span data-stu-id="1a539-152">You should educate your users to invite participants to meetings by clicking the name, not the phone number.</span></span> 
    
- <span data-ttu-id="1a539-153">通过工作电话进行呼叫时，增强的911功能和恶意呼叫跟踪不可用。</span><span class="sxs-lookup"><span data-stu-id="1a539-153">Enhanced 911 capability and malicious call tracing are not available during Call Via Work calls.</span></span>
    
- <span data-ttu-id="1a539-154">通过工作启用呼叫的用户不能使用委派、团队呼叫或响应组功能。</span><span class="sxs-lookup"><span data-stu-id="1a539-154">Users enabled for Call Via Work cannot use the delegation, team call, or response group features.</span></span>
    
- <span data-ttu-id="1a539-155">通过工作进行呼叫的用户无法使用 Skype for Business 录制会议、将呼叫设为静音或取消静音、保留或转接呼叫，或使用呼叫寄存。</span><span class="sxs-lookup"><span data-stu-id="1a539-155">Users of Call Via Work cannot use Skype for Business to record a meeting, mute or unmute the call, hold or transfer the call, or use call park.</span></span>
    
- <span data-ttu-id="1a539-156">用户无法使用呼叫通过工作来访问其 PBX 语音邮件消息。</span><span class="sxs-lookup"><span data-stu-id="1a539-156">Users cannot use Call Via Work to access their PBX voicemail messages.</span></span>
    
- <span data-ttu-id="1a539-157">通过工作进行呼叫的用户无法将作为语音呼叫启动的会话提升为包括视频、Powerpoint、白板或一个笔记等通信的协作会议。</span><span class="sxs-lookup"><span data-stu-id="1a539-157">Users of Call Via Work cannot escalate a session that started as a voice call to a collaborative meeting that includes communications such as video, Powerpoint, whiteboard, or One Note.</span></span>
    
- <span data-ttu-id="1a539-158">通过工作呼叫的用户不能将更多用户添加到两人通话。</span><span class="sxs-lookup"><span data-stu-id="1a539-158">Users of Call Via Work cannot add more users to a 2-person call.</span></span>
    
- <span data-ttu-id="1a539-159">不支持 deskphone 配对或 VDI 插件配对。</span><span class="sxs-lookup"><span data-stu-id="1a539-159">No support for deskphone pairing or VDI plugin pairing.</span></span>
    
- <span data-ttu-id="1a539-160">如果用户使用 PBX 电话（而不是使用 Skype for Business 窗口）发出或应答呼叫，则不会有通话记录。</span><span class="sxs-lookup"><span data-stu-id="1a539-160">If a user makes or answers a call using the PBX phone (and not using the Skype for Business window), there will be no log of the call.</span></span>
    
- <span data-ttu-id="1a539-161">如果你的 PBX 系统不支持 "**替换**"，将发生以下行为。</span><span class="sxs-lookup"><span data-stu-id="1a539-161">If your PBX system does not support **REFER with Replaces**, the following behavior will happen.</span></span> <span data-ttu-id="1a539-162">通过工作呼叫进行呼叫时，如果用户通过 PBX 手机传送正在进行的呼叫，则呼叫窗口不会从其 Skype for Business 窗口中消失。</span><span class="sxs-lookup"><span data-stu-id="1a539-162">While on a Call Via Work call, if the user transfers the ongoing call from the PBX Phone, the call window will not disappear from their Skype for Business window.</span></span> <span data-ttu-id="1a539-163">如果用户关闭呼叫窗口，则传送目标与 transferee 之间的通话将结束。</span><span class="sxs-lookup"><span data-stu-id="1a539-163">If the user then closes the call window, the call between the transfer target and the transferee will end.</span></span> 
    
## <a name="prerequisites-for-call-via-work"></a><span data-ttu-id="1a539-164">通过工作进行通话的先决条件</span><span class="sxs-lookup"><span data-stu-id="1a539-164">Prerequisites for Call Via Work</span></span>

<span data-ttu-id="1a539-165">若要允许任何用户通过工作进行呼叫，您必须准备好一些先决条件。</span><span class="sxs-lookup"><span data-stu-id="1a539-165">To enable any users for Call Via Work, you must have some pre-requisites in place.</span></span> <span data-ttu-id="1a539-166">有关这些先决条件的详细信息，以及如何通过工作启用用户呼叫的步骤，请参阅[通过 Skype For Business Server 2015 部署呼叫](../../deploy/deploy-call-via-work.md)。</span><span class="sxs-lookup"><span data-stu-id="1a539-166">For more information on these prerequisites, and for steps on how to enable users for Call Via Work, see [Deploy Call Via Work in Skype for Business Server 2015](../../deploy/deploy-call-via-work.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="1a539-167">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1a539-167">See also</span></span>

[<span data-ttu-id="1a539-168">在 Skype for Business 中规划远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="1a539-168">Plan for remote call control in Skype for Business</span></span>](remote-call-control.md)
  
[<span data-ttu-id="1a539-169">在 Skype for Business Server 2015 中部署单位电话呼叫</span><span class="sxs-lookup"><span data-stu-id="1a539-169">Deploy Call Via Work in Skype for Business Server 2015</span></span>](../../deploy/deploy-call-via-work.md)

