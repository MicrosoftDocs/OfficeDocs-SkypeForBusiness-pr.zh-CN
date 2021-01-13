---
title: 在 Skype for Business Server 中规划通过工位呼叫
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
ms.assetid: a33ec637-9ac8-4cb7-b3b2-88d432efc078
description: 在 Skype for Business Server 中规划通过工号呼叫，这将支持 Skype for Business 与 PBX 电话系统集成，以便用户可以使用 Skype for Business 控制其 PBX 电话。
ms.openlocfilehash: e443a5d2709f1aca69ef200e72de43251cd16047
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825872"
---
# <a name="plan-for-call-via-work-in-skype-for-business-server"></a><span data-ttu-id="11e10-103">在 Skype for Business Server 中规划通过工位呼叫</span><span class="sxs-lookup"><span data-stu-id="11e10-103">Plan for Call Via Work in Skype for Business Server</span></span>
 
<span data-ttu-id="11e10-104">在 Skype for Business Server 中规划通过工号呼叫，这将支持 Skype for Business 与 PBX 电话系统集成，以便用户可以使用 Skype for Business 控制其 PBX 电话。</span><span class="sxs-lookup"><span data-stu-id="11e10-104">Planning for Call Via Work in Skype for Business Server, which enables integration between Skype for Business and your PBX phone system, so that users can use Skype for Business to control their PBX phones.</span></span>
  
 <span data-ttu-id="11e10-105">**通过工号** 呼叫是 Skype for Business Server 中的一项新功能，使你能够将 Skype for Business 解决方案与现有 PBX 电话系统集成。</span><span class="sxs-lookup"><span data-stu-id="11e10-105">**Call Via Work** is a new feature in Skype for Business Server which enables you to integrate your Skype for Business solution with your existing PBX phone systems.</span></span> <span data-ttu-id="11e10-106">启用了通过工位呼叫的用户可以在 Skype for Business 中单击以呼叫部署中的其他用户或外部用户。</span><span class="sxs-lookup"><span data-stu-id="11e10-106">A user enabled for Call Via Work can click in Skype for Business to call another user, either within your deployment or an external user.</span></span> <span data-ttu-id="11e10-107">呼叫使用用户的 PBX 电话完成。</span><span class="sxs-lookup"><span data-stu-id="11e10-107">The call is completed using the user's PBX phone.</span></span> <span data-ttu-id="11e10-108">这使具有 PBX 电话的用户能够将音频包括在丰富的 Skype for Business 对话中。</span><span class="sxs-lookup"><span data-stu-id="11e10-108">This enables a user with a PBX phone to include audio in their rich Skype for Business conversations.</span></span> <span data-ttu-id="11e10-109">在早期版本的 Lync Server 远程呼叫控制中，该功能使用户能够使用 Lync Server 控制 PBX 电话。</span><span class="sxs-lookup"><span data-stu-id="11e10-109">In previous versions of Lync Server remote call control was a feature which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="11e10-110">在 Skype for Business Server 中，此功能已替换为通过工位电话呼叫功能。</span><span class="sxs-lookup"><span data-stu-id="11e10-110">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>
  
<span data-ttu-id="11e10-111">通过工号呼叫为 PBX 电话用户启用以下功能</span><span class="sxs-lookup"><span data-stu-id="11e10-111">Call Via Work enables the following for PBX phone users</span></span>
  
- <span data-ttu-id="11e10-112">即点即用体验，通过 PBX 电话提供的音频。</span><span class="sxs-lookup"><span data-stu-id="11e10-112">Click-to-call experience, with the audio provided through the PBX phone.</span></span>
    
- <span data-ttu-id="11e10-113">状态、用户搜索和 IM 集成-例如，IM 会话中的两个通过工位呼叫的用户可以通过 PBX 电话提供的音频将音频添加到其会话。</span><span class="sxs-lookup"><span data-stu-id="11e10-113">Presence, user search, and IM integration-- for example, two Call Via Work users in an IM session can add audio to their session, with the audio provided through the PBX phones.</span></span>
    
- <span data-ttu-id="11e10-114">能够将 IM、应用程序共享和文件传输添加到通过工位电话呼叫。</span><span class="sxs-lookup"><span data-stu-id="11e10-114">The ability to add IM, application sharing, and file transfer to a Call Via Work call.</span></span>
    
- <span data-ttu-id="11e10-115">一键式会议加入功能</span><span class="sxs-lookup"><span data-stu-id="11e10-115">One-click meeting join capability</span></span>
    
## <a name="how-it-works"></a><span data-ttu-id="11e10-116">运作方式</span><span class="sxs-lookup"><span data-stu-id="11e10-116">How it works</span></span>

<span data-ttu-id="11e10-117">通过工号呼叫使用统一通信 Web API (UCWA) 作为 PBX 系统和 Skype for Business Server 部署之间的后端用户代理 (B2BUA) ，因此无需计算机支持的电信应用程序 (CSTA) 网关将 Skype for Business Server 与 PBX 系统连接。</span><span class="sxs-lookup"><span data-stu-id="11e10-117">Call Via Work uses Unified Communications Web API (UCWA) as the back-to-back user agent (B2BUA) between the PBX system and your Skype for Business Server deployment, so that no computer-supported telecommunications application (CSTA) gateway is needed to connect Skype for Business Server with your PBX system.</span></span> <span data-ttu-id="11e10-118">UCWA 是 Lync Server 早期版本中引入的一项服务，用于启用与移动和 Web 客户端的连接，并且会自动安装在每个前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="11e10-118">UCWA is a service introduced in previous versions of Lync Server to enable connectivity with mobile and web clients, and is automatically installed on every Front End Server.</span></span>
  
### <a name="call-workflow-for-a-call-via-work-call"></a><span data-ttu-id="11e10-119">通过工位呼叫的呼叫工作流</span><span class="sxs-lookup"><span data-stu-id="11e10-119">Call workflow for a Call Via Work call</span></span>

<span data-ttu-id="11e10-120">下面说明了启用通过工位电话呼叫的用户如何使用 Skype for Business Server 进行呼叫：</span><span class="sxs-lookup"><span data-stu-id="11e10-120">The following illustrates how a user enabled for Call Via Work can use the Skype for Business Server to make a call:</span></span>
  
![显示通过工位电话呼叫期间的步骤;首先，呼叫者单击呼叫 Skype for Business 客户端中的某人;然后 UCWA 将呼叫者的电话响铃。](../../media/050e88ed-e18e-40c0-84d5-b17fe40c305a.jpg)
  
1. <span data-ttu-id="11e10-123">用户在 Skype for Business 客户端中选择一个用户，然后单击电话图标以呼叫他们。</span><span class="sxs-lookup"><span data-stu-id="11e10-123">The user selects a user in their Skype for Business client, and clicks the phone icon to call them.</span></span> <span data-ttu-id="11e10-124">或者，在 IM 对话期间，用户单击以呼叫正在与用户进行会话的用户。</span><span class="sxs-lookup"><span data-stu-id="11e10-124">Or, during an IM conversation, the user clicks to call the user they are having the session with.</span></span>
    
2. <span data-ttu-id="11e10-125">拨打呼叫的用户的 PBX 电话开始响铃。</span><span class="sxs-lookup"><span data-stu-id="11e10-125">The PBX phone of the user who placed the call starts to ring.</span></span> <span data-ttu-id="11e10-126">此电话的呼叫者 ID 显示已设置为显示在发出通过工号呼叫的所有用户的呼叫者 ID 中的全局电话号码。</span><span class="sxs-lookup"><span data-stu-id="11e10-126">The caller ID for this phone shows a global phone number which you have set up to show in the caller ID of all users placing Call Via Work calls.</span></span> <span data-ttu-id="11e10-127">此全局电话号码不是对应于任何一个人电话的实际电话号码。</span><span class="sxs-lookup"><span data-stu-id="11e10-127">This global phone number is not an actual phone number that corresponds to any one person's phone.</span></span> <span data-ttu-id="11e10-128">相反，它是一个可视信号，用于让用户知道这是他们自己的传出呼叫，而不是同时发生的传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="11e10-128">Instead, it is a visual signal to let a user know that this is their own outgoing call, and not an incoming call happening at the same time.</span></span> <span data-ttu-id="11e10-129">部署通过工号呼叫时，应该向这些用户说明此全局电话号码及其的含义。</span><span class="sxs-lookup"><span data-stu-id="11e10-129">When you deploy Call Via Work, you should educate those users about this global phone number and what it means.</span></span>
    
3. <span data-ttu-id="11e10-130">拨打呼叫的用户将接听其 PBX 电话。</span><span class="sxs-lookup"><span data-stu-id="11e10-130">The user who placed the call picks up their PBX phone.</span></span> <span data-ttu-id="11e10-131">Skype for Business 然后向被叫方发起语音呼叫。</span><span class="sxs-lookup"><span data-stu-id="11e10-131">Skype for Business then initiates the voice call to the callee.</span></span> 
    
4. <span data-ttu-id="11e10-132">当被叫方应答时，语音呼叫将开始。</span><span class="sxs-lookup"><span data-stu-id="11e10-132">When the callee answers, the voice call begins.</span></span> <span data-ttu-id="11e10-133">如果两个用户已经在进行 IM 会话，它可以继续。</span><span class="sxs-lookup"><span data-stu-id="11e10-133">If the two users already had an IM session going, it can continue.</span></span>
    
### <a name="joining-a-conference-with-call-via-work"></a><span data-ttu-id="11e10-134">通过电话呼叫加入会议</span><span class="sxs-lookup"><span data-stu-id="11e10-134">Joining a Conference With Call Via Work</span></span>

<span data-ttu-id="11e10-135">通过工位电话呼叫用户可以通过单击会议 URL 加入安排的会议。</span><span class="sxs-lookup"><span data-stu-id="11e10-135">A Call Via Work user can join a scheduled meeting by clicking the meeting URL.</span></span> <span data-ttu-id="11e10-136">Skype for Business 随后将显示" **拨出** "消息，直到会议服务拨打用户的 PBX 电话。</span><span class="sxs-lookup"><span data-stu-id="11e10-136">Skype for Business then shows a **Dialing out to** message until the meeting service dials the user's PBX phone.</span></span> <span data-ttu-id="11e10-137">然后，通过工号呼叫用户接听 PBX 电话并加入会议。</span><span class="sxs-lookup"><span data-stu-id="11e10-137">The Call Via Work user then picks up the PBX phone and joins the meeting.</span></span>
  
<span data-ttu-id="11e10-138">通过工位电话呼叫用户还可使用Skype for Business 中的"立即开会"选项创建"立即开会"会议。</span><span class="sxs-lookup"><span data-stu-id="11e10-138">A Call Via Work user can also use the **Meet Now** option in Skype for Business to create Meet Now meetings.</span></span> <span data-ttu-id="11e10-139">然后，用户会看到 **"拨出"** 消息，并且 PBX 电话响铃。</span><span class="sxs-lookup"><span data-stu-id="11e10-139">The user then sees the **Dialing out to** message, and the PBX phone rings.</span></span>
  
<span data-ttu-id="11e10-140">通过工号拨号用户还可通过从 Skype for Business 内呼叫会议网桥号码来拨入会议。</span><span class="sxs-lookup"><span data-stu-id="11e10-140">A Call Via Work user can also dial in to a meeting by calling the Conference Bridge number from within Skype for Business.</span></span> <span data-ttu-id="11e10-141">如果需要会议 PIN，用户必须使用其 PBX 电话输入 PIN。</span><span class="sxs-lookup"><span data-stu-id="11e10-141">If a conference PIN is required, the user must use their PBX phone to input the PIN.</span></span>
  
### <a name="incoming-calls"></a><span data-ttu-id="11e10-142">传入呼叫</span><span class="sxs-lookup"><span data-stu-id="11e10-142">Incoming Calls</span></span>

<span data-ttu-id="11e10-143">当启用了通过工号呼叫的用户收到 Skype for Business 呼叫时，如果用户设置了同时响铃 (则 PBX 电话和用户的 Skype for Business 客户端将同时) 。</span><span class="sxs-lookup"><span data-stu-id="11e10-143">When a user enabled for Call Via Work receives a Skype for Business call, the PBX phone and the user's Skype for Business clients all ring simultaneously (if the user has set up simultaneous ring).</span></span> <span data-ttu-id="11e10-144">用户可以通过接听 PBX 电话或单击 Skype for Business通知上的"接受"来接受呼叫。</span><span class="sxs-lookup"><span data-stu-id="11e10-144">The user can accept the call either by picking up the PBX phone or clicking **Accept** on the Skype for Business notification.</span></span> <span data-ttu-id="11e10-145">如果用户使用 Skype for Business 接受呼叫，则呼叫的 Skype for Business 窗口保持打开状态。</span><span class="sxs-lookup"><span data-stu-id="11e10-145">If the user accepts the call using Skype for Business, the Skype for Business window for the call stays open.</span></span> <span data-ttu-id="11e10-146">但是，如果用户通过接听 PBX 电话接受呼叫，则 Skype for Business 通知窗口关闭，并且没有 Skype for Business 会话，仅通过 PBX 电话进行语音呼叫。</span><span class="sxs-lookup"><span data-stu-id="11e10-146">But if the user accepts the call by picking up the PBX phone, then the Skype for Business notification window closes and there is no Skype for Business session, only the voice call over the PBX phone.</span></span>
  
<span data-ttu-id="11e10-147">启用通过工号呼叫的用户收到 PBX 呼叫时，仅 PBX 电话响铃。</span><span class="sxs-lookup"><span data-stu-id="11e10-147">When a user enabled for Call Via Work receives a PBX call, only the PBX phone rings.</span></span>
  
## <a name="limitations-of-call-via-work"></a><span data-ttu-id="11e10-148">通过工次电话呼叫的限制</span><span class="sxs-lookup"><span data-stu-id="11e10-148">Limitations of Call Via Work</span></span>

<span data-ttu-id="11e10-149">通过工位呼叫是一种语音解决方案，几乎不需要硬件设置，但与完整呼叫或远程呼叫控制企业语音功能相比，存在一些限制。</span><span class="sxs-lookup"><span data-stu-id="11e10-149">Call Via Work is a voice solution that requires little hardware setup, but has limitations compared to the features available in full Enterprise Voice or remote call control.</span></span> <span data-ttu-id="11e10-150">通过工次电话呼叫具有以下限制：</span><span class="sxs-lookup"><span data-stu-id="11e10-150">Call Via Work has the following limitations:</span></span>
  
- <span data-ttu-id="11e10-151">如果通过工号呼叫的用户设置了呼叫转发到"通过工号呼叫"回拨号码，并且有人尝试按用户的电话号码邀请该用户参加会议，则邀请将不会到达该用户。</span><span class="sxs-lookup"><span data-stu-id="11e10-151">If a Call Via Work user has set up call forwarding to the Call Via Work callback number, and someone tries to invite this user to a meeting by the user's phone number, the invitation will not reach the user.</span></span> <span data-ttu-id="11e10-152">应指导用户通过单击姓名而不是电话号码来邀请参与者参加会议。</span><span class="sxs-lookup"><span data-stu-id="11e10-152">You should educate your users to invite participants to meetings by clicking the name, not the phone number.</span></span> 
    
- <span data-ttu-id="11e10-153">增强型 911 功能以及恶意呼叫跟踪在通过工号呼叫期间不可用。</span><span class="sxs-lookup"><span data-stu-id="11e10-153">Enhanced 911 capability and malicious call tracing are not available during Call Via Work calls.</span></span>
    
- <span data-ttu-id="11e10-154">启用了通过工位呼叫的用户无法使用委派、团队呼叫或响应组功能。</span><span class="sxs-lookup"><span data-stu-id="11e10-154">Users enabled for Call Via Work cannot use the delegation, team call, or response group features.</span></span>
    
- <span data-ttu-id="11e10-155">通过工位呼叫的用户无法使用 Skype for Business 录制会议、将呼叫静音或取消静音、保留或转接呼叫或使用呼叫等待。</span><span class="sxs-lookup"><span data-stu-id="11e10-155">Users of Call Via Work cannot use Skype for Business to record a meeting, mute or unmute the call, hold or transfer the call, or use call park.</span></span>
    
- <span data-ttu-id="11e10-156">用户无法使用通过工位电话访问其 PBX 语音邮件。</span><span class="sxs-lookup"><span data-stu-id="11e10-156">Users cannot use Call Via Work to access their PBX voicemail messages.</span></span>
    
- <span data-ttu-id="11e10-157">通过工号呼叫的用户无法将作为语音呼叫启动的会话升级至包含视频、Powerpoint、白板或 One Note 等通信的协作会议。</span><span class="sxs-lookup"><span data-stu-id="11e10-157">Users of Call Via Work cannot escalate a session that started as a voice call to a collaborative meeting that includes communications such as video, Powerpoint, whiteboard, or One Note.</span></span>
    
- <span data-ttu-id="11e10-158">通过工号呼叫的用户无法向 2 人呼叫添加更多用户。</span><span class="sxs-lookup"><span data-stu-id="11e10-158">Users of Call Via Work cannot add more users to a 2-person call.</span></span>
    
- <span data-ttu-id="11e10-159">不支持桌面电话配对或 VDI 插件配对。</span><span class="sxs-lookup"><span data-stu-id="11e10-159">No support for deskphone pairing or VDI plugin pairing.</span></span>
    
- <span data-ttu-id="11e10-160">如果用户使用 PBX 电话应答或 (而未使用 Skype for Business) ，则没有呼叫日志。</span><span class="sxs-lookup"><span data-stu-id="11e10-160">If a user makes or answers a call using the PBX phone (and not using the Skype for Business window), there will be no log of the call.</span></span>
    
- <span data-ttu-id="11e10-161">如果您的 PBX 系统不支持 **REFER with Replaces，** 则会发生以下行为。</span><span class="sxs-lookup"><span data-stu-id="11e10-161">If your PBX system does not support **REFER with Replaces**, the following behavior will happen.</span></span> <span data-ttu-id="11e10-162">在通过工号呼叫时，如果用户从 PBX 电话转移正在进行的呼叫，则呼叫窗口不会从 Skype for Business 窗口消失。</span><span class="sxs-lookup"><span data-stu-id="11e10-162">While on a Call Via Work call, if the user transfers the ongoing call from the PBX Phone, the call window will not disappear from their Skype for Business window.</span></span> <span data-ttu-id="11e10-163">如果用户随后关闭呼叫窗口，则转接目标与被转接人之间的呼叫将结束。</span><span class="sxs-lookup"><span data-stu-id="11e10-163">If the user then closes the call window, the call between the transfer target and the transferee will end.</span></span> 
    
## <a name="prerequisites-for-call-via-work"></a><span data-ttu-id="11e10-164">通过工次电话呼叫的先决条件</span><span class="sxs-lookup"><span data-stu-id="11e10-164">Prerequisites for Call Via Work</span></span>

<span data-ttu-id="11e10-165">若要为任何用户启用通过工位电话呼叫，必须具备一些先决条件。</span><span class="sxs-lookup"><span data-stu-id="11e10-165">To enable any users for Call Via Work, you must have some pre-requisites in place.</span></span> <span data-ttu-id="11e10-166">有关这些先决条件以及如何为用户启用通过工号呼叫的步骤，请参阅[Deploy Call Via Work in Skype for Business Server 2015。](../../deploy/deploy-call-via-work.md)</span><span class="sxs-lookup"><span data-stu-id="11e10-166">For more information on these prerequisites, and for steps on how to enable users for Call Via Work, see [Deploy Call Via Work in Skype for Business Server 2015](../../deploy/deploy-call-via-work.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="11e10-167">另请参阅</span><span class="sxs-lookup"><span data-stu-id="11e10-167">See also</span></span>

[<span data-ttu-id="11e10-168">在 Skype for Business 中规划远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="11e10-168">Plan for remote call control in Skype for Business</span></span>](remote-call-control.md)
  
[<span data-ttu-id="11e10-169">在 Skype for Business Server 2015 中部署通过工号呼叫</span><span class="sxs-lookup"><span data-stu-id="11e10-169">Deploy Call Via Work in Skype for Business Server 2015</span></span>](../../deploy/deploy-call-via-work.md)

