---
title: 在 Skype for Business Server 2015 中规划单位电话呼叫
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 10/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: a33ec637-9ac8-4cb7-b3b2-88d432efc078
description: 用于调用通过 Skype 在规划业务服务器，以便用户可以使用 Skype 业务来控制其 PBX 电话使业务的 Skype 和 PBX 电话系统之间的集成。
ms.openlocfilehash: d70ffb7cd46f5d2ffd7efe4db860f3a84ca34ef5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-call-via-work-in-skype-for-business-server-2015"></a><span data-ttu-id="f53ce-103">在 Skype for Business Server 2015 中规划单位电话呼叫</span><span class="sxs-lookup"><span data-stu-id="f53ce-103">Plan for Call Via Work in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f53ce-104">用于调用通过 Skype 在规划业务服务器，以便用户可以使用 Skype 业务来控制其 PBX 电话使业务的 Skype 和 PBX 电话系统之间的集成。</span><span class="sxs-lookup"><span data-stu-id="f53ce-104">Planning for Call Via Work in Skype for Business Server, which enables integration between Skype for Business and your PBX phone system, so that users can use Skype for Business to control their PBX phones.</span></span>
  
 <span data-ttu-id="f53ce-105">**调用通过工作**是 Skype，这使您可以与您现有的 PBX 电话系统集成业务解决方案您 Skype 业务服务器中的新功能。</span><span class="sxs-lookup"><span data-stu-id="f53ce-105">**Call Via Work** is a new feature in Skype for Business Server which enables you to integrate your Skype for Business solution with your existing PBX phone systems.</span></span> <span data-ttu-id="f53ce-106">启用呼叫通过工作的用户可以单击中业务调用另一个用户，或者在您的部署或外部用户的 Skype。</span><span class="sxs-lookup"><span data-stu-id="f53ce-106">A user enabled for Call Via Work can click in Skype for Business to call another user, either within your deployment or an external user.</span></span> <span data-ttu-id="f53ce-107">呼叫使用用户的 PBX 电话完成。</span><span class="sxs-lookup"><span data-stu-id="f53ce-107">The call is completed using the user's PBX phone.</span></span> <span data-ttu-id="f53ce-108">这使得具有 PBX 电话的用户在其丰富的业务对话 Skype 包含音频。</span><span class="sxs-lookup"><span data-stu-id="f53ce-108">This enables a user with a PBX phone to include audio in their rich Skype for Business conversations.</span></span> <span data-ttu-id="f53ce-109">在以前版本的 Lync 服务器远程调用控制是一种功能，使用户能够控制手机 PBX Lync Server。</span><span class="sxs-lookup"><span data-stu-id="f53ce-109">In previous versions of Lync Server remote call control was a feature which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="f53ce-110">在 Skype 业务服务器，此功能已被调用通过工作。</span><span class="sxs-lookup"><span data-stu-id="f53ce-110">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>
  
<span data-ttu-id="f53ce-111">调用通过工作使下面的 PBX 电话用户</span><span class="sxs-lookup"><span data-stu-id="f53ce-111">Call Via Work enables the following for PBX phone users</span></span>
  
- <span data-ttu-id="f53ce-112">单击呼叫，通过 PBX 电话提供音频。</span><span class="sxs-lookup"><span data-stu-id="f53ce-112">Click-to-call experience, with the audio provided through the PBX phone.</span></span>
    
- <span data-ttu-id="f53ce-113">状态、 用户搜索和 IM 集成--例如，两个调用通过工作用户 IM 会话中的可以添加音频到他们的会话，通过 PBX 电话提供音频。</span><span class="sxs-lookup"><span data-stu-id="f53ce-113">Presence, user search, and IM integration-- for example, two Call Via Work users in an IM session can add audio to their session, with the audio provided through the PBX phones.</span></span>
    
- <span data-ttu-id="f53ce-114">通过工作调用调用添加即时消息、 应用程序共享和文件传输的能力。</span><span class="sxs-lookup"><span data-stu-id="f53ce-114">The ability to add IM, application sharing, and file transfer to a Call Via Work call.</span></span>
    
- <span data-ttu-id="f53ce-115">一键式会议加入功能</span><span class="sxs-lookup"><span data-stu-id="f53ce-115">One-click meeting join capability</span></span>
    
## <a name="how-it-works"></a><span data-ttu-id="f53ce-116">运作方式</span><span class="sxs-lookup"><span data-stu-id="f53ce-116">How it works</span></span>

<span data-ttu-id="f53ce-117">调用通过工作使用统一通信 Web API (UCWA) 作为 PBX 系统和您 Skype 之间的背对背的用户代理 (B2BUA) 业务服务器部署中，因此连接所需的任何计算机支持的电信应用程序 (CSTA) 网关PBX 系统具有的业务服务器的 Skype。</span><span class="sxs-lookup"><span data-stu-id="f53ce-117">Call Via Work uses Unified Communications Web API (UCWA) as the back-to-back user agent (B2BUA) between the PBX system and your Skype for Business Server deployment, so that no computer-supported telecommunications application (CSTA) gateway is needed to connect Skype for Business Server with your PBX system.</span></span> <span data-ttu-id="f53ce-118">UCWA 是 Lync 服务器以启用移动与连接性和 web 客户端的前一版本中引入的服务，将自动安装在每个前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="f53ce-118">UCWA is a service introduced in previous versions of Lync Server to enable connectivity with mobile and web clients, and is automatically installed on every Front End Server.</span></span>
  
### <a name="call-workflow-for-a-call-via-work-call"></a><span data-ttu-id="f53ce-119">通过工作中调用调用工作流</span><span class="sxs-lookup"><span data-stu-id="f53ce-119">Call workflow for a Call Via Work call</span></span>

<span data-ttu-id="f53ce-120">以下说明了启用调用通过工作的用户如何使用 Skype 业务服务器进行调用：</span><span class="sxs-lookup"><span data-stu-id="f53ce-120">The following illustrates how a user enabled for Call Via Work can use the Skype for Business Server to make a call:</span></span>
  
![显示单位电话呼叫通话期间的步骤；首先，呼叫者在 Skype for Business 客户端中单击呼叫某人；随后 UCMA 使呼叫者的电话响铃。在呼叫者拿起电话时，呼叫接收人](../../media/050e88ed-e18e-40c0-84d5-b17fe40c305a.jpg)
  
1. <span data-ttu-id="f53ce-123">用户在其 Skype 业务客户端，选择用户并单击电话图标，可以给他们打电话。</span><span class="sxs-lookup"><span data-stu-id="f53ce-123">The user selects a user in their Skype for Business client, and clicks the phone icon to call them.</span></span> <span data-ttu-id="f53ce-124">或者，在 IM 对话期间，用户通过单击呼叫正在与其进行会话的用户。</span><span class="sxs-lookup"><span data-stu-id="f53ce-124">Or, during an IM conversation, the user clicks to call the user they are having the session with.</span></span>
    
2. <span data-ttu-id="f53ce-125">用户发出调用的 PBX 电话开始响。</span><span class="sxs-lookup"><span data-stu-id="f53ce-125">The PBX phone of the user who placed the call starts to ring.</span></span> <span data-ttu-id="f53ce-126">此电话的来电显示您已设置在呼叫调用通过工作的所有用户的来电显示全局的电话号码。</span><span class="sxs-lookup"><span data-stu-id="f53ce-126">The caller ID for this phone shows a global phone number which you have set up to show in the caller ID of all users placing Call Via Work calls.</span></span> <span data-ttu-id="f53ce-127">此全局电话号码不是一个实际的电话号码对应于任何一个人的电话。</span><span class="sxs-lookup"><span data-stu-id="f53ce-127">This global phone number is not an actual phone number that corresponds to any one person's phone.</span></span> <span data-ttu-id="f53ce-128">相反，它是视觉信号，让用户知道这是他们自己传出的呼叫，并不在同一时间发生的传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="f53ce-128">Instead, it is a visual signal to let a user know that this is their own outgoing call, and not an incoming call happening at the same time.</span></span> <span data-ttu-id="f53ce-129">调用通过工作部署时，应提醒这些用户了解此全局电话号码以及它意味着什么。</span><span class="sxs-lookup"><span data-stu-id="f53ce-129">When you deploy Call Via Work, you should educate those users about this global phone number and what it means.</span></span>
    
3. <span data-ttu-id="f53ce-130">拨打呼叫的用户拿起他们的 PBX 电话。</span><span class="sxs-lookup"><span data-stu-id="f53ce-130">The user who placed the call picks up their PBX phone.</span></span> <span data-ttu-id="f53ce-131">接着，Skype 业务启动语音呼叫到被调用方。</span><span class="sxs-lookup"><span data-stu-id="f53ce-131">Skype for Business then initiates the voice call to the callee.</span></span> 
    
4. <span data-ttu-id="f53ce-p107">被叫方接听时，将开始语音呼叫。如果两位用户已经在进行 IM 会话，则会话将继续。</span><span class="sxs-lookup"><span data-stu-id="f53ce-p107">When the callee answers, the voice call begins. If the two users already had an IM session going, it can continue.</span></span>
    
### <a name="joining-a-conference-with-call-via-work"></a><span data-ttu-id="f53ce-134">使用通过工号拨号加入会议</span><span class="sxs-lookup"><span data-stu-id="f53ce-134">Joining a Conference With Call Via Work</span></span>

<span data-ttu-id="f53ce-135">通过工作中调用用户可以通过单击会议 URL 加入计划的会议。</span><span class="sxs-lookup"><span data-stu-id="f53ce-135">A Call Via Work user can join a scheduled meeting by clicking the meeting URL.</span></span> <span data-ttu-id="f53ce-136">Skype 业务直到会议服务拨打用户的 PBX 电话然后将显示**为拨出**的消息。</span><span class="sxs-lookup"><span data-stu-id="f53ce-136">Skype for Business then shows a **Dialing out to** message until the meeting service dials the user's PBX phone.</span></span> <span data-ttu-id="f53ce-137">通过工作中调用用户然后选取 PBX 电话并加入会议。</span><span class="sxs-lookup"><span data-stu-id="f53ce-137">The Call Via Work user then picks up the PBX phone and joins the meeting.</span></span>
  
<span data-ttu-id="f53ce-138">通过工作中调用用户可以使用**立即开会**选项在 Skype 业务创建立即开会的会议</span><span class="sxs-lookup"><span data-stu-id="f53ce-138">A Call Via Work user can also use the **Meet Now** option in Skype for Business to create Meet Now meetings.</span></span> <span data-ttu-id="f53ce-139">然后用户会看到“**正在外拨**”消息，PBX 电话开始响铃。</span><span class="sxs-lookup"><span data-stu-id="f53ce-139">The user then sees the **Dialing out to** message, and the PBX phone rings.</span></span>
  
<span data-ttu-id="f53ce-140">通过工作中调用用户可以还拨入会议通过调用业务会议桥接器号码 Skype。</span><span class="sxs-lookup"><span data-stu-id="f53ce-140">A Call Via Work user can also dial in to a meeting by calling the Conference Bridge number from within Skype for Business.</span></span> <span data-ttu-id="f53ce-141">如果需要会议 PIN，用户必须使用他们的 PBX 电话输入 PIN。</span><span class="sxs-lookup"><span data-stu-id="f53ce-141">If a conference PIN is required, the user must use their PBX phone to input the PIN.</span></span>
  
### <a name="incoming-calls"></a><span data-ttu-id="f53ce-142">传入呼叫</span><span class="sxs-lookup"><span data-stu-id="f53ce-142">Incoming Calls</span></span>

<span data-ttu-id="f53ce-143">当启用用户调用通过工作将接收所有环同时 （如果用户设置同时振铃） 的业务客户端业务呼叫、 PBX 电话和 Skype 用户的 Skype。</span><span class="sxs-lookup"><span data-stu-id="f53ce-143">When a user enabled for Call Via Work receives a Skype for Business call, the PBX phone and the user's Skype for Business clients all ring simultaneously (if the user has set up simultaneous ring).</span></span> <span data-ttu-id="f53ce-144">用户可以接受通过拨打电话 PBX 或单击**接受**业务通知 Skype 上的调用。</span><span class="sxs-lookup"><span data-stu-id="f53ce-144">The user can accept the call either by picking up the PBX phone or clicking **Accept** on the Skype for Business notification.</span></span> <span data-ttu-id="f53ce-145">如果用户接受的业务使用 Skype 呼叫，Skype 呼叫业务窗口保持打开状态。</span><span class="sxs-lookup"><span data-stu-id="f53ce-145">If the user accepts the call using Skype for Business, the Skype for Business window for the call stays open.</span></span> <span data-ttu-id="f53ce-146">但如果用户接受的拿起 PBX 电话呼叫，Skype 业务通知窗口将关闭，并没有任何 Skype 业务会话，只通过 PBX 电话语音呼叫。</span><span class="sxs-lookup"><span data-stu-id="f53ce-146">But if the user accepts the call by picking up the PBX phone, then the Skype for Business notification window closes and there is no Skype for Business session, only the voice call over the PBX phone.</span></span>
  
<span data-ttu-id="f53ce-147">当用户调用通过工作为启用接收 PBX 电话，PBX 电话响铃。</span><span class="sxs-lookup"><span data-stu-id="f53ce-147">When a user enabled for Call Via Work receives a PBX call, only the PBX phone rings.</span></span>
  
## <a name="limitations-of-call-via-work"></a><span data-ttu-id="f53ce-148">工作通过呼叫限制</span><span class="sxs-lookup"><span data-stu-id="f53ce-148">Limitations of Call Via Work</span></span>

<span data-ttu-id="f53ce-149">调用通过工作是一种语音解决方案，需要进行很少的硬件设置，但是有比较完整的企业语音或远程呼叫控制中可用的功能的限制。</span><span class="sxs-lookup"><span data-stu-id="f53ce-149">Call Via Work is a voice solution that requires little hardware setup, but has limitations compared to the features available in full Enterprise Voice or remote call control.</span></span> <span data-ttu-id="f53ce-150">调用通过工作有以下限制：</span><span class="sxs-lookup"><span data-stu-id="f53ce-150">Call Via Work has the following limitations:</span></span>
  
- <span data-ttu-id="f53ce-151">如果调用通过工作用户设置呼叫转移到调用通过工作回拨号码，并且有人试图邀请此用户访问该用户的电话号码通过会议，邀请将不会到达用户。</span><span class="sxs-lookup"><span data-stu-id="f53ce-151">If a Call Via Work user has set up call forwarding to the Call Via Work callback number, and someone tries to invite this user to a meeting by the user's phone number, the invitation will not reach the user.</span></span> <span data-ttu-id="f53ce-152">你应指导你的用户通过单击姓名（而非电话号码）邀请参与者加入会议。</span><span class="sxs-lookup"><span data-stu-id="f53ce-152">You should educate your users to invite participants to meetings by clicking the name, not the phone number.</span></span> 
    
- <span data-ttu-id="f53ce-153">911 的增强的能力和恶意调用跟踪的工作通过调用调用期间不可用。</span><span class="sxs-lookup"><span data-stu-id="f53ce-153">Enhanced 911 capability and malicious call tracing are not available during Call Via Work calls.</span></span>
    
- <span data-ttu-id="f53ce-154">启用的工作通过调用用户不能使用委派、 团队调用或响应功能进行分组。</span><span class="sxs-lookup"><span data-stu-id="f53ce-154">Users enabled for Call Via Work cannot use the delegation, team call, or response group features.</span></span>
    
- <span data-ttu-id="f53ce-155">调用通过工作的用户无法使用 Skype 业务要录制会议，静音或取消静音通话、 存放或转接呼叫，或者使用调用公园。</span><span class="sxs-lookup"><span data-stu-id="f53ce-155">Users of Call Via Work cannot use Skype for Business to record a meeting, mute or unmute the call, hold or transfer the call, or use call park.</span></span>
    
- <span data-ttu-id="f53ce-156">用户不能使用调用通过工作来访问他们 PBX 的语音邮件消息。</span><span class="sxs-lookup"><span data-stu-id="f53ce-156">Users cannot use Call Via Work to access their PBX voicemail messages.</span></span>
    
- <span data-ttu-id="f53ce-157">用户调用通过工作的不能升级作为协作会议，其中包括通信，如视频，Powerpoint，白板或一个注意语音呼叫启动一个会话。</span><span class="sxs-lookup"><span data-stu-id="f53ce-157">Users of Call Via Work cannot escalate a session that started as a voice call to a collaborative meeting that includes communications such as video, Powerpoint, whiteboard, or One Note.</span></span>
    
- <span data-ttu-id="f53ce-158">调用通过工作的用户不能添加更多用户，对 2 人联络。</span><span class="sxs-lookup"><span data-stu-id="f53ce-158">Users of Call Via Work cannot add more users to a 2-person call.</span></span>
    
- <span data-ttu-id="f53ce-159">不支持桌面电话配对或 VDI 插件配对。</span><span class="sxs-lookup"><span data-stu-id="f53ce-159">No support for deskphone pairing or VDI plugin pairing.</span></span>
    
- <span data-ttu-id="f53ce-160">如果用户使或应答呼叫使用 PBX 电话 （而非使用 Skype 业务窗口） 时，将调用的任何日志。</span><span class="sxs-lookup"><span data-stu-id="f53ce-160">If a user makes or answers a call using the PBX phone (and not using the Skype for Business window), there will be no log of the call.</span></span>
    
- <span data-ttu-id="f53ce-161">如果你的 PBX 系统不支持 **REFER with Replaces**，将发生以下行为。</span><span class="sxs-lookup"><span data-stu-id="f53ce-161">If your PBX system does not support **REFER with Replaces**, the following behavior will happen.</span></span> <span data-ttu-id="f53ce-162">在调用通过工作调用中，如果用户从 PBX 电话转移正在进行呼叫，呼叫窗口将不会消失从其 Skype 业务窗口。</span><span class="sxs-lookup"><span data-stu-id="f53ce-162">While on a Call Via Work call, if the user transfers the ongoing call from the PBX Phone, the call window will not disappear from their Skype for Business window.</span></span> <span data-ttu-id="f53ce-163">如果用户随后关闭呼叫窗口，转接目标和受让方之间的呼叫将终结。</span><span class="sxs-lookup"><span data-stu-id="f53ce-163">If the user then closes the call window, the call between the transfer target and the transferee will end.</span></span> 
    
## <a name="prerequisites-for-call-via-work"></a><span data-ttu-id="f53ce-164">通过工作的呼叫的先决条件</span><span class="sxs-lookup"><span data-stu-id="f53ce-164">Prerequisites for Call Via Work</span></span>

<span data-ttu-id="f53ce-165">要启用所有用户的调用通过工作，必须在地方一些必备。</span><span class="sxs-lookup"><span data-stu-id="f53ce-165">To enable any users for Call Via Work, you must have some pre-requisites in place.</span></span> <span data-ttu-id="f53ce-166">了解更多有关这些系统必备组件，以及如何启用用户调用通过工作的步骤，请参阅[部署调用通过工作中的业务服务器 2015 Skype](../../deploy/deploy-call-via-work.md)。</span><span class="sxs-lookup"><span data-stu-id="f53ce-166">For more information on these prerequisites, and for steps on how to enable users for Call Via Work, see [Deploy Call Via Work in Skype for Business Server 2015](../../deploy/deploy-call-via-work.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f53ce-167">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f53ce-167">See also</span></span>

#### 

[<span data-ttu-id="f53ce-168">远程呼叫控制下的企业 2015年的 Skype 的计划</span><span class="sxs-lookup"><span data-stu-id="f53ce-168">Plan for remote call control in Skype for Business 2015</span></span>](remote-call-control.md)
  
[<span data-ttu-id="f53ce-169">部署工作在 Skype 业务服务器 2015年通过调用</span><span class="sxs-lookup"><span data-stu-id="f53ce-169">Deploy Call Via Work in Skype for Business Server 2015</span></span>](../../deploy/deploy-call-via-work.md)

