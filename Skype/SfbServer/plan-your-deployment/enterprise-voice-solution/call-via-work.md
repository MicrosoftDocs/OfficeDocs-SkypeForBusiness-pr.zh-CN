---
title: 规划用单位电话的 Skype 业务服务器的呼叫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a33ec637-9ac8-4cb7-b3b2-88d432efc078
description: 用于呼叫通过 Skype 中规划 Business Server，这样可使 for Business 的 Skype 和 PBX 电话系统，之间的集成，以便用户可以使用 for Business 的 Skype 控制其 PBX 电话。
ms.openlocfilehash: 248a6111d03539d23d4262762caa5c0a5b213460
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33909111"
---
# <a name="plan-for-call-via-work-in-skype-for-business-server"></a><span data-ttu-id="9e9f6-103">规划用单位电话的 Skype 业务服务器的呼叫</span><span class="sxs-lookup"><span data-stu-id="9e9f6-103">Plan for Call Via Work in Skype for Business Server</span></span>
 
<span data-ttu-id="9e9f6-104">用于呼叫通过 Skype 中规划 Business Server，这样可使 for Business 的 Skype 和 PBX 电话系统，之间的集成，以便用户可以使用 for Business 的 Skype 控制其 PBX 电话。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-104">Planning for Call Via Work in Skype for Business Server, which enables integration between Skype for Business and your PBX phone system, so that users can use Skype for Business to control their PBX phones.</span></span>
  
 <span data-ttu-id="9e9f6-105">**通过单位电话呼叫**中的业务服务器，它可以与您现有的 PBX 电话系统集成业务解决方案您 Skype Skype 的新功能。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-105">**Call Via Work** is a new feature in Skype for Business Server which enables you to integrate your Skype for Business solution with your existing PBX phone systems.</span></span> <span data-ttu-id="9e9f6-106">启用呼叫通过单位电话的用户可以单击 for Business 呼叫另一个用户，可以在部署或外部用户的 Skype 中。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-106">A user enabled for Call Via Work can click in Skype for Business to call another user, either within your deployment or an external user.</span></span> <span data-ttu-id="9e9f6-107">将使用用户的 PBX 电话完成呼叫。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-107">The call is completed using the user's PBX phone.</span></span> <span data-ttu-id="9e9f6-108">这样 PBX 电话与用户在其丰富 Skype 业务对话中包括音频。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-108">This enables a user with a PBX phone to include audio in their rich Skype for Business conversations.</span></span> <span data-ttu-id="9e9f6-109">在早期版本的 Lync Server 远程呼叫控制是一种功能，允许用户控制其 PBX 电话与 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-109">In previous versions of Lync Server remote call control was a feature which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="9e9f6-110">在业务服务器 Skype，此功能已取代与通过单位电话呼叫。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-110">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>
  
<span data-ttu-id="9e9f6-111">通过单位电话呼叫启用 PBX 电话用户的以下</span><span class="sxs-lookup"><span data-stu-id="9e9f6-111">Call Via Work enables the following for PBX phone users</span></span>
  
- <span data-ttu-id="9e9f6-112">单击呼叫，通过 PBX 电话提供音频。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-112">Click-to-call experience, with the audio provided through the PBX phone.</span></span>
    
- <span data-ttu-id="9e9f6-113">状态、 用户搜索和 IM 集成-例如，在 IM 会话中的两个呼叫通过单位电话用户可以添加音频到他们的会话，与 PBX 电话通过提供音频。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-113">Presence, user search, and IM integration-- for example, two Call Via Work users in an IM session can add audio to their session, with the audio provided through the PBX phones.</span></span>
    
- <span data-ttu-id="9e9f6-114">向呼叫通过单位电话呼叫添加即时消息、 应用程序共享和文件传输功能。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-114">The ability to add IM, application sharing, and file transfer to a Call Via Work call.</span></span>
    
- <span data-ttu-id="9e9f6-115">一键式会议加入功能</span><span class="sxs-lookup"><span data-stu-id="9e9f6-115">One-click meeting join capability</span></span>
    
## <a name="how-it-works"></a><span data-ttu-id="9e9f6-116">运作方式</span><span class="sxs-lookup"><span data-stu-id="9e9f6-116">How it works</span></span>

<span data-ttu-id="9e9f6-117">通过单位电话呼叫使用统一通信 Web API (UCWA) 作为背对背用户代理 (B2BUA) PBX 系统之间您 Skype 业务服务器部署中，以便连接所需的任何计算机支持的电信应用 (CSTA) 网关为业务 Server 与 PBX 系统的 Skype。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-117">Call Via Work uses Unified Communications Web API (UCWA) as the back-to-back user agent (B2BUA) between the PBX system and your Skype for Business Server deployment, so that no computer-supported telecommunications application (CSTA) gateway is needed to connect Skype for Business Server with your PBX system.</span></span> <span data-ttu-id="9e9f6-118">UCWA 是在早期版本的 Lync Server 启用 mobile 连接和 web 客户端中, 引入的一个服务，并且每个前端服务器上自动安装。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-118">UCWA is a service introduced in previous versions of Lync Server to enable connectivity with mobile and web clients, and is automatically installed on every Front End Server.</span></span>
  
### <a name="call-workflow-for-a-call-via-work-call"></a><span data-ttu-id="9e9f6-119">调用通过单位电话呼叫的呼叫工作流</span><span class="sxs-lookup"><span data-stu-id="9e9f6-119">Call workflow for a Call Via Work call</span></span>

<span data-ttu-id="9e9f6-120">以下说明了如何启用呼叫通过单位电话的用户可以使用业务服务器 Skype 发起呼叫：</span><span class="sxs-lookup"><span data-stu-id="9e9f6-120">The following illustrates how a user enabled for Call Via Work can use the Skype for Business Server to make a call:</span></span>
  
![显示单位电话呼叫通话期间的步骤；首先，呼叫者在 Skype for Business 客户端中单击呼叫某人；随后 UCMA 使呼叫者的电话响铃。在呼叫者拿起电话时，呼叫接收人](../../media/050e88ed-e18e-40c0-84d5-b17fe40c305a.jpg)
  
1. <span data-ttu-id="9e9f6-123">用户在其 Skype 业务客户端中选择用户，然后单击电话图标来呼叫该联系人。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-123">The user selects a user in their Skype for Business client, and clicks the phone icon to call them.</span></span> <span data-ttu-id="9e9f6-124">或者，在 IM 对话期间，用户通过单击呼叫正在与其进行会话的用户。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-124">Or, during an IM conversation, the user clicks to call the user they are having the session with.</span></span>
    
2. <span data-ttu-id="9e9f6-125">发出呼叫的用户的 PBX 电话开始振铃。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-125">The PBX phone of the user who placed the call starts to ring.</span></span> <span data-ttu-id="9e9f6-126">此电话的呼叫者 ID 显示您已设置为显示中的所有用户发起通过单位电话呼叫的呼叫的呼叫者 ID 全局电话号码。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-126">The caller ID for this phone shows a global phone number which you have set up to show in the caller ID of all users placing Call Via Work calls.</span></span> <span data-ttu-id="9e9f6-127">此全局电话号码不是对应于任何人电话实际电话号码。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-127">This global phone number is not an actual phone number that corresponds to any one person's phone.</span></span> <span data-ttu-id="9e9f6-128">相反，它是一个可视信号，以使用户可以知道这是他们自己的传出呼叫，并不传入呼叫同时发生。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-128">Instead, it is a visual signal to let a user know that this is their own outgoing call, and not an incoming call happening at the same time.</span></span> <span data-ttu-id="9e9f6-129">在部署通过单位电话呼叫时，您应告知有关此全局电话号码和含义的那些用户。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-129">When you deploy Call Via Work, you should educate those users about this global phone number and what it means.</span></span>
    
3. <span data-ttu-id="9e9f6-130">拨打呼叫的用户拿起他们的 PBX 电话。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-130">The user who placed the call picks up their PBX phone.</span></span> <span data-ttu-id="9e9f6-131">Skype for Business 然后发起语音呼叫到被叫方。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-131">Skype for Business then initiates the voice call to the callee.</span></span> 
    
4. <span data-ttu-id="9e9f6-132">被叫方应答时，将开始语音呼叫。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-132">When the callee answers, the voice call begins.</span></span> <span data-ttu-id="9e9f6-133">如果两个用户已经有转 IM 会话，它可以继续。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-133">If the two users already had an IM session going, it can continue.</span></span>
    
### <a name="joining-a-conference-with-call-via-work"></a><span data-ttu-id="9e9f6-134">加入使用单位电话呼叫会议</span><span class="sxs-lookup"><span data-stu-id="9e9f6-134">Joining a Conference With Call Via Work</span></span>

<span data-ttu-id="9e9f6-135">调用通过单位电话用户可以通过单击会议 URL 加入预定的会议。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-135">A Call Via Work user can join a scheduled meeting by clicking the meeting URL.</span></span> <span data-ttu-id="9e9f6-136">Skype for Business 之前的会议服务拨打该用户的 PBX 电话，然后显示**拨出**的邮件。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-136">Skype for Business then shows a **Dialing out to** message until the meeting service dials the user's PBX phone.</span></span> <span data-ttu-id="9e9f6-137">调用通过单位电话用户然后拿起 PBX 电话和加入会议。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-137">The Call Via Work user then picks up the PBX phone and joins the meeting.</span></span>
  
<span data-ttu-id="9e9f6-138">呼叫通过单位电话用户可以还使用**立即开会**选项中的业务的 Skype 创建立即开会会议。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-138">A Call Via Work user can also use the **Meet Now** option in Skype for Business to create Meet Now meetings.</span></span> <span data-ttu-id="9e9f6-139">然后，用户看到的**拨出**消息和 PBX 电话振铃。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-139">The user then sees the **Dialing out to** message, and the PBX phone rings.</span></span>
  
<span data-ttu-id="9e9f6-140">呼叫通过单位电话用户可以还拨入会议通过调用 for Business 内 Skype 中的会议桥号。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-140">A Call Via Work user can also dial in to a meeting by calling the Conference Bridge number from within Skype for Business.</span></span> <span data-ttu-id="9e9f6-141">如果需要会议 PIN，用户必须使用其 PBX 电话输入 PIN。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-141">If a conference PIN is required, the user must use their PBX phone to input the PIN.</span></span>
  
### <a name="incoming-calls"></a><span data-ttu-id="9e9f6-142">传入呼叫</span><span class="sxs-lookup"><span data-stu-id="9e9f6-142">Incoming Calls</span></span>

<span data-ttu-id="9e9f6-143">时启用的用户呼叫通过单位电话的所有拨打同时 （如果用户已设置同时响铃） 的业务客户端接收业务呼叫、 在 PBX 电话与用户的 Skype 的 Skype。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-143">When a user enabled for Call Via Work receives a Skype for Business call, the PBX phone and the user's Skype for Business clients all ring simultaneously (if the user has set up simultaneous ring).</span></span> <span data-ttu-id="9e9f6-144">用户可以接受通过拿起 PBX 电话，或单击上的业务通知 Skype**接受**呼叫。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-144">The user can accept the call either by picking up the PBX phone or clicking **Accept** on the Skype for Business notification.</span></span> <span data-ttu-id="9e9f6-145">如果用户接受 for Business 使用 Skype 调用，用于呼叫的业务窗口 Skype 保持打开状态。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-145">If the user accepts the call using Skype for Business, the Skype for Business window for the call stays open.</span></span> <span data-ttu-id="9e9f6-146">但是，如果用户接受拿起 PBX 电话的呼叫，然后关闭业务通知窗口 Skype 和业务会话，只能通过 PBX 电话的语音呼叫没有任何 Skype。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-146">But if the user accepts the call by picking up the PBX phone, then the Skype for Business notification window closes and there is no Skype for Business session, only the voice call over the PBX phone.</span></span>
  
<span data-ttu-id="9e9f6-147">当启用呼叫通过单位电话的用户收到 PBX 的呼叫，仅 PBX 电话响铃。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-147">When a user enabled for Call Via Work receives a PBX call, only the PBX phone rings.</span></span>
  
## <a name="limitations-of-call-via-work"></a><span data-ttu-id="9e9f6-148">用单位电话呼叫的限制</span><span class="sxs-lookup"><span data-stu-id="9e9f6-148">Limitations of Call Via Work</span></span>

<span data-ttu-id="9e9f6-149">通过单位电话呼叫是语音解决方案的要求很少硬件设置，但具有完整的企业语音还是远程呼叫控制中可用的功能与相比的限制。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-149">Call Via Work is a voice solution that requires little hardware setup, but has limitations compared to the features available in full Enterprise Voice or remote call control.</span></span> <span data-ttu-id="9e9f6-150">通过单位电话呼叫具有以下限制：</span><span class="sxs-lookup"><span data-stu-id="9e9f6-150">Call Via Work has the following limitations:</span></span>
  
- <span data-ttu-id="9e9f6-151">如果某人尝试邀请此用户加入会议的用户的电话号码的呼叫通过单位电话用户已设置为通过单位电话呼叫回拨号码的呼叫转接，邀请将不会到达用户。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-151">If a Call Via Work user has set up call forwarding to the Call Via Work callback number, and someone tries to invite this user to a meeting by the user's phone number, the invitation will not reach the user.</span></span> <span data-ttu-id="9e9f6-152">您应告知用户通过单击该名称，而非电话号码邀请参与者加入会议。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-152">You should educate your users to invite participants to meetings by clicking the name, not the phone number.</span></span> 
    
- <span data-ttu-id="9e9f6-153">增强型 911 的功能和恶意呼叫跟踪呼叫通过单位电话呼叫过程中不可用。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-153">Enhanced 911 capability and malicious call tracing are not available during Call Via Work calls.</span></span>
    
- <span data-ttu-id="9e9f6-154">启用呼叫通过单位电话的用户无法使用委派、 团队呼叫或响应组功能。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-154">Users enabled for Call Via Work cannot use the delegation, team call, or response group features.</span></span>
    
- <span data-ttu-id="9e9f6-155">呼叫通过单位电话的用户无法使用 for Business 的 Skype 录制会议，设置为静音或取消静音呼叫、 保留或转接呼叫，或使用呼叫寄存。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-155">Users of Call Via Work cannot use Skype for Business to record a meeting, mute or unmute the call, hold or transfer the call, or use call park.</span></span>
    
- <span data-ttu-id="9e9f6-156">用户不能使用呼叫通过单位电话访问其 PBX 的语音邮件。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-156">Users cannot use Call Via Work to access their PBX voicemail messages.</span></span>
    
- <span data-ttu-id="9e9f6-157">呼叫通过单位电话的用户无法升级到协作会议包含视频，Powerpoint 白板，如 communications 或一个注释语音呼叫作为启动会话。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-157">Users of Call Via Work cannot escalate a session that started as a voice call to a collaborative meeting that includes communications such as video, Powerpoint, whiteboard, or One Note.</span></span>
    
- <span data-ttu-id="9e9f6-158">呼叫通过单位电话的用户不能向 2 人呼叫中添加更多的用户。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-158">Users of Call Via Work cannot add more users to a 2-person call.</span></span>
    
- <span data-ttu-id="9e9f6-159">不是支持桌面电话配对或 VDI 插件配对。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-159">No support for deskphone pairing or VDI plugin pairing.</span></span>
    
- <span data-ttu-id="9e9f6-160">如果用户使或应答呼叫使用 PBX 电话 （和不使用 Skype 业务窗口），将呼叫无日志。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-160">If a user makes or answers a call using the PBX phone (and not using the Skype for Business window), there will be no log of the call.</span></span>
    
- <span data-ttu-id="9e9f6-161">如果 PBX 系统不支持**与替换的引用**，将发生以下行为。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-161">If your PBX system does not support **REFER with Replaces**, the following behavior will happen.</span></span> <span data-ttu-id="9e9f6-162">在呼叫通过单位电话呼叫中，如果用户从 PBX 电话转移正在进行的呼叫，呼叫窗口将不会消失从其 Skype 业务窗口。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-162">While on a Call Via Work call, if the user transfers the ongoing call from the PBX Phone, the call window will not disappear from their Skype for Business window.</span></span> <span data-ttu-id="9e9f6-163">如果用户然后关闭呼叫窗口，将结束传输目标与接受方之间的呼叫。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-163">If the user then closes the call window, the call between the transfer target and the transferee will end.</span></span> 
    
## <a name="prerequisites-for-call-via-work"></a><span data-ttu-id="9e9f6-164">用单位电话呼叫的先决条件</span><span class="sxs-lookup"><span data-stu-id="9e9f6-164">Prerequisites for Call Via Work</span></span>

<span data-ttu-id="9e9f6-165">若要启用呼叫通过单位电话的任何用户，您必须就地一些必备组件。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-165">To enable any users for Call Via Work, you must have some pre-requisites in place.</span></span> <span data-ttu-id="9e9f6-166">有关这些先决条件，以及如何为用户启用呼叫通过单位电话的步骤，请参阅[部署呼叫通过单位电话的业务服务器 2015 Skype 中](../../deploy/deploy-call-via-work.md)。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-166">For more information on these prerequisites, and for steps on how to enable users for Call Via Work, see [Deploy Call Via Work in Skype for Business Server 2015](../../deploy/deploy-call-via-work.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="9e9f6-167">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9e9f6-167">See also</span></span>

[<span data-ttu-id="9e9f6-168">Plan for Business 的 Skype 中的远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="9e9f6-168">Plan for remote call control in Skype for Business</span></span>](remote-call-control.md)
  
[<span data-ttu-id="9e9f6-169">在 Skype for Business Server 2015 中部署单位电话呼叫</span><span class="sxs-lookup"><span data-stu-id="9e9f6-169">Deploy Call Via Work in Skype for Business Server 2015</span></span>](../../deploy/deploy-call-via-work.md)

