---
title: Lync Server 2013：设计交互式语音响应呼叫流
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Design interactive voice response call flows
ms:assetid: f3477f0a-3ad5-4b13-a73c-046aa451db19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413020(v=OCS.15)
ms:contentKeyID: 48185826
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 649d085253610002e7623872012a400ac0a1f079
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498939"
---
# <a name="design-interactive-voice-response-call-flows-in-lync-server-2013"></a><span data-ttu-id="6da12-102">在 Lync Server 2013 中设计交互式语音响应呼叫流</span><span class="sxs-lookup"><span data-stu-id="6da12-102">Design interactive voice response call flows in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6da12-103">_**上次修改的主题：** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="6da12-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="6da12-p101">使用互动语音响应 (IVR) 可从呼叫者获取信息，并将呼叫引导到相应的队列。问题/答案对确定要使用哪个队列。根据呼叫者的响应，呼叫者或者收听后续问题，或者被路由至相应的队列。会将 IVR 问题及呼叫者的响应提供给接收呼叫的代理，同时向该代理提供宝贵的信息。</span><span class="sxs-lookup"><span data-stu-id="6da12-p101">You can use interactive voice response (IVR) to obtain information from callers and direct the call to the appropriate queue. Question-and-answer pairs determine which queue to use. Depending on the caller’s response, the caller either hears a follow-up question, or is routed to the appropriate queue. The IVR questions and the caller’s responses are provided to the responding agent who accepts the call, providing valuable information to the agent.</span></span>

<div>

## <a name="overview-of-ivr-features"></a><span data-ttu-id="6da12-108">IVR 功能概述</span><span class="sxs-lookup"><span data-stu-id="6da12-108">Overview of IVR Features</span></span>

<span data-ttu-id="6da12-109">响应组应用程序提供了采用26种语言的语音识别和文本到语音转换功能。</span><span class="sxs-lookup"><span data-stu-id="6da12-109">The Response Group application offers speech recognition and text-to-speech capabilities in 26 languages.</span></span> <span data-ttu-id="6da12-110">可以使用文本到语音转换功能或 Wave (.wav) 或 Windows Media 音频 (.wma) 文件输入 IVR 问题。</span><span class="sxs-lookup"><span data-stu-id="6da12-110">You can enter IVR questions using text-to-speech or a wave (.wav) or Windows Media audio (.wma) file.</span></span> <span data-ttu-id="6da12-111">呼叫者可以使用语音或双音多频 (DTMF) 响应进行响应。</span><span class="sxs-lookup"><span data-stu-id="6da12-111">Callers can respond by using voice or dual-tone multifrequency (DTMF) responses.</span></span>

<span data-ttu-id="6da12-p103">互动工作流最多支持两级问题，每个问题最多有四个可能的答案。IVR 向呼叫者提出问题，并根据呼叫者的响应，将其路由至某个队列或提出第二个问题。第二个问题也可以有四个可能的答案。根据呼叫者对第二级问题的回答，将呼叫者路由至相应的队列。</span><span class="sxs-lookup"><span data-stu-id="6da12-p103">Interactive workflows support up to two levels of questions, with each question having up to four possible answers. The IVR asks the caller a question, and depending on the caller’s response, routes the caller to a queue or asks a second question. The second question can also have four possible answers. Depending on the answer to the second-level question, the caller is routed to the appropriate queue.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6da12-116">当您使用 Lync Server 命令行管理程序设计呼叫流时，您可以定义任何号码级别的 IVR 问题和任意数量的应答。</span><span class="sxs-lookup"><span data-stu-id="6da12-116">When you design call flows by using Lync Server Management Shell, you can define any number levels of IVR questions and any number of answers.</span></span> <span data-ttu-id="6da12-117">但是，为了方便呼叫者使用，建议不要使用三个级别以上的问题，并且每个问题的答案不要超过五个。</span><span class="sxs-lookup"><span data-stu-id="6da12-117">However, for caller usability, we recommend that you not use more than three levels of questions, with not more than five answers each.</span></span> <span data-ttu-id="6da12-118">此外，如果设计的呼叫流中有两个以上的问题，每个级别多于四个，则无法使用 Lync Server 2013 控制面板编辑呼叫流。</span><span class="sxs-lookup"><span data-stu-id="6da12-118">In addition, if you design a call flow that has more than two levels of questions with more than four answers each, you cannot edit the call flow by using Lync Server 2013 Control Panel.</span></span>



</div>

<span data-ttu-id="6da12-119">将 IVR 问题及呼叫者的响应提供给接收呼叫的响应代理。</span><span class="sxs-lookup"><span data-stu-id="6da12-119">The IVR questions and the caller’s responses are provided to the responding agent who accepts the call.</span></span>

</div>

<div>

## <a name="working-with-speech-technologies"></a><span data-ttu-id="6da12-120">使用语音技术</span><span class="sxs-lookup"><span data-stu-id="6da12-120">Working with Speech Technologies</span></span>

<span data-ttu-id="6da12-121">语音识别和文本到语音转换等语音技术可以增强用户体验，并使用户能够更自然和更有效地获得信息。</span><span class="sxs-lookup"><span data-stu-id="6da12-121">Speech technologies, such as speech recognition and text-to-speech, can enhance customer experience and let people access information more naturally and effectively.</span></span> <span data-ttu-id="6da12-122">但是，语音引擎在有些情况下无法正确识别所指定的文本或用户语音响应。</span><span class="sxs-lookup"><span data-stu-id="6da12-122">However, there can be cases where the specified text or the user voice response is not recognized correctly by the speech engine.</span></span> <span data-ttu-id="6da12-123">例如，" \# " 符号由文本到语音引擎转换为 "数字" 一词。</span><span class="sxs-lookup"><span data-stu-id="6da12-123">For example, the "\#" symbol is translated by the text-to-speech engine as the word "number."</span></span> <span data-ttu-id="6da12-124">通过以下方式可以缓解这一问题：</span><span class="sxs-lookup"><span data-stu-id="6da12-124">This issue can be mitigated by the following:</span></span>

  - <span data-ttu-id="6da12-p106">语音引擎让呼叫者尝试回答问题五次。如果呼叫者回答问题有误（即答案不是所指定的响应之一）或根本未提供答案，则呼叫者将再获得一次回答问题的机会。呼叫者有五次机会来回答问题，然后才会被挂断。可以将 IVR 配置为呼叫者每次出错后播放自定义消息。每次都将重复该问题。</span><span class="sxs-lookup"><span data-stu-id="6da12-p106">The speech engine gives the caller five attempts to answer the question. If the caller answers the question incorrectly (that is, the answer is not one of the specified responses) or does not provide an answer at all, the caller gets another chance to answer the question. The caller has five attempts to answer the question before being disconnected. You can configure the IVR to play a customized message after each caller error. The question is repeated each time.</span></span>

  - <span data-ttu-id="6da12-p107">为了尽量避免语音引擎将环境噪声识别为响应，请使用长一点的响应。例如，响应应包含多个音节，并且不同响应之间应有明显的发音区别。</span><span class="sxs-lookup"><span data-stu-id="6da12-p107">To minimize the potential for ambient noise to be interpreted by the speech engine as a response, use longer responses. For example, responses should have more than one syllable and should sound significantly different from each other.</span></span>

  - <span data-ttu-id="6da12-p108">如果问题同时包括语音和 DTMF 响应，请将语音响应配置为表示具体概念的语句，而不是 DTMF 响应。例如，不要使用“请按或说 1”，而应使用“请按 1 或说出帐单”。</span><span class="sxs-lookup"><span data-stu-id="6da12-p108">If your questions have both speech and DTMF responses, configure the speech responses with words that represent the concept rather than the DTMF response. For example, instead of using "Press or say one" use "Press 1 or say billing."</span></span>

  - <span data-ttu-id="6da12-134">设计 IVR 之后，请呼叫工作流、收听提示、使用语音对每个提示做出响应，并确认 IVR 的声音和行为符合预期。</span><span class="sxs-lookup"><span data-stu-id="6da12-134">After you design your IVR, call the workflow, listen to the prompts, respond to each of the prompts using voice, and verify that the IVR sounds and behaves as expected.</span></span> <span data-ttu-id="6da12-135">然后，可以修改 IVR 以更正任何释读问题。</span><span class="sxs-lookup"><span data-stu-id="6da12-135">You can then modify the IVR to fix any interpretation issues.</span></span> <span data-ttu-id="6da12-136">在前面的示例中，如果需要引用 \# 键，可以重写 IVR 提示以使用项名称，而不是 \# 符号。</span><span class="sxs-lookup"><span data-stu-id="6da12-136">Following the previous example, if you need to refer to the \# key, you can rewrite your IVR prompt to use the key name, rather than the \# symbol.</span></span> <span data-ttu-id="6da12-137">例如，“要与销售人员交谈，请按井号键”。</span><span class="sxs-lookup"><span data-stu-id="6da12-137">For example, "To talk to sales, press the pound key."</span></span>

</div>

<div>

## <a name="ivr-design-examples"></a><span data-ttu-id="6da12-138">IVR 设计示例</span><span class="sxs-lookup"><span data-stu-id="6da12-138">IVR Design Examples</span></span>

<span data-ttu-id="6da12-139">以下各节包含不同 IVR 方案和问题/答案对的示例。</span><span class="sxs-lookup"><span data-stu-id="6da12-139">The following sections contain examples of different IVR scenarios and question-and-answer pairs.</span></span>

<div>

## <a name="ivr-with-one-level-of-questions"></a><span data-ttu-id="6da12-140">只有单级问题的 IVR</span><span class="sxs-lookup"><span data-stu-id="6da12-140">IVR with One Level of Questions</span></span>

<span data-ttu-id="6da12-p110">下例介绍使用单级问题的 IVR。该 IVR 使用语音识别来检测呼叫者的响应。</span><span class="sxs-lookup"><span data-stu-id="6da12-p110">The following example shows an IVR that uses one level of questions. It uses speech recognition to detect the caller’s response.</span></span>

<span data-ttu-id="6da12-p111">**问题：**“感谢您致电人力资源部。如果要与薪酬组通话，请说‘薪酬’。否则，请说‘人力资源’。”</span><span class="sxs-lookup"><span data-stu-id="6da12-p111">**Question:** "Thank you for calling Human Resources. If you would like to speak to payroll, say payroll. Otherwise, say HR."</span></span>

  - <span data-ttu-id="6da12-146">**选择选项 1：** 将呼叫者路由至薪酬组。</span><span class="sxs-lookup"><span data-stu-id="6da12-146">**Option 1 is selected:** The caller is routed to the payroll team.</span></span>

  - <span data-ttu-id="6da12-147">**选择选项 2：** 将呼叫者路由至人力资源组。</span><span class="sxs-lookup"><span data-stu-id="6da12-147">**Option 2 is selected:** The caller is routed to the human resources team.</span></span>

<span data-ttu-id="6da12-148">下图显示了相应的呼叫流。</span><span class="sxs-lookup"><span data-stu-id="6da12-148">The following figure shows the call flow.</span></span>

<span data-ttu-id="6da12-149">**单级互动呼叫流**</span><span class="sxs-lookup"><span data-stu-id="6da12-149">**One-level interactive call flow**</span></span>

<span data-ttu-id="6da12-150">![使用交互式语音响应设计呼叫流](images/Gg413020.4820a9f7-b5b0-4831-b972-baae0c015ec1(OCS.15).jpg "使用交互式语音响应设计呼叫流")</span><span class="sxs-lookup"><span data-stu-id="6da12-150">![Design Call Flows by Using Interactive Voice Respo](images/Gg413020.4820a9f7-b5b0-4831-b972-baae0c015ec1(OCS.15).jpg "Design Call Flows by Using Interactive Voice Respo")</span></span>

</div>

<div>

## <a name="ivr-with-two-levels-of-questions"></a><span data-ttu-id="6da12-151">含有两级问题的 IVR</span><span class="sxs-lookup"><span data-stu-id="6da12-151">IVR with Two Levels of Questions</span></span>

<span data-ttu-id="6da12-p112">下例介绍使用两级问题的 IVR。该 IVR 允许呼叫者使用语音或 DTMF 小键盘输入进行响应。</span><span class="sxs-lookup"><span data-stu-id="6da12-p112">The following example shows an IVR that uses two levels of questions. It allows callers to respond using either speech or DTMF keypad input.</span></span>

<span data-ttu-id="6da12-p113">**问题：**“感谢您致电 IT 技术支持。如果有网络访问问题，请按或说网络。如果有软件问题，则按或说软件。如果有硬件问题，则按或说硬件。”</span><span class="sxs-lookup"><span data-stu-id="6da12-p113">**Question:** "Thank you for calling the IT Help Desk. If you have a network access problem, press 1 or say network. If you have a software problem, press 2 or say software. If you have a hardware problem, press 3 or say hardware."</span></span>

  - <span data-ttu-id="6da12-158">**选择选项 1：** 将呼叫者路由至网络支持组。</span><span class="sxs-lookup"><span data-stu-id="6da12-158">**Option 1 is selected:** The caller is routed to the network support team.</span></span>

  - <span data-ttu-id="6da12-159">**选择选项 2：** 向呼叫者提出后续问题：</span><span class="sxs-lookup"><span data-stu-id="6da12-159">**Option 2 is selected:** The caller is asked a follow-up question:</span></span>
    
    <span data-ttu-id="6da12-p114">**问题：**“如果是操作系统的问题，请按 1 或说操作系统。如果是内部应用程序的问题，请按 2 或说内部应用程序。否则，请按 3 或说其他。”</span><span class="sxs-lookup"><span data-stu-id="6da12-p114">**Question:** "If this is an operating system problem, press 1 or say operating system. If this is a problem with an internal application, press 2 or say internal application. Otherwise, press 3 or say other."</span></span>
    
      - <span data-ttu-id="6da12-163">**选择选项 1：** 将呼叫者路由至操作系统支持组。</span><span class="sxs-lookup"><span data-stu-id="6da12-163">**Option 1 is selected:** The caller is routed to the operating systems support team.</span></span>
    
      - <span data-ttu-id="6da12-164">**选择选项 2：** 将呼叫者路由至内部应用程序支持组。</span><span class="sxs-lookup"><span data-stu-id="6da12-164">**Option 2 is selected:** The caller is routed to the internal applications support team.</span></span>
    
      - <span data-ttu-id="6da12-165">**选择选项 3：** 将呼叫者路由至软件支持组。</span><span class="sxs-lookup"><span data-stu-id="6da12-165">**Option 3 is selected:** The caller is routed to the software support team.</span></span>

  - <span data-ttu-id="6da12-166">**选择选项 3：** 向呼叫者提出后续问题：</span><span class="sxs-lookup"><span data-stu-id="6da12-166">**Option 3 is selected:** The caller is asked a follow-up question:</span></span>
    
    <span data-ttu-id="6da12-p115">**问题：**“如果是打印机问题，请按 1。否则，请按 2。”</span><span class="sxs-lookup"><span data-stu-id="6da12-p115">**Question:** "If this is a printer problem press 1. Otherwise, press 2."</span></span>
    
      - <span data-ttu-id="6da12-169">**选择选项 1：** 将呼叫者路由至打印机支持组。</span><span class="sxs-lookup"><span data-stu-id="6da12-169">**Option 1 is selected:** The caller is routed to the printer support team.</span></span>
    
      - <span data-ttu-id="6da12-170">**选择选项 2：** 将呼叫者路由至硬件支持组。</span><span class="sxs-lookup"><span data-stu-id="6da12-170">**Option 2 is selected:** The caller is routed to the hardware support team.</span></span>

<span data-ttu-id="6da12-171">下图显示了相应的呼叫流。</span><span class="sxs-lookup"><span data-stu-id="6da12-171">The following figure shows the call flow.</span></span>

<span data-ttu-id="6da12-172">**两级互动呼叫流**</span><span class="sxs-lookup"><span data-stu-id="6da12-172">**Two-level interactive call flow**</span></span>

<span data-ttu-id="6da12-173">![使用交互式语音响应设计呼叫流](images/Gg413020.a5b62083-312d-4419-898b-d1a225a5379f(OCS.15).jpg "使用交互式语音响应设计呼叫流")</span><span class="sxs-lookup"><span data-stu-id="6da12-173">![Design Call Flows by Using Interactive Voice Respo](images/Gg413020.a5b62083-312d-4419-898b-d1a225a5379f(OCS.15).jpg "Design Call Flows by Using Interactive Voice Respo")</span></span>

</div>

</div>

<div>

## <a name="best-practices"></a><span data-ttu-id="6da12-174">最佳做法</span><span class="sxs-lookup"><span data-stu-id="6da12-174">Best Practices</span></span>

<span data-ttu-id="6da12-175">下面列出了用于设计 IVR 的一些最佳做法：</span><span class="sxs-lookup"><span data-stu-id="6da12-175">The following list describes some best practices for designing your IVR:</span></span>

  - <span data-ttu-id="6da12-p116">让呼叫者快速开始任务。避免在 IVR 中提供过多信息或过长的营销消息。</span><span class="sxs-lookup"><span data-stu-id="6da12-p116">Let the caller get to the task quickly. Avoid providing too much information or lengthy marketing messages in your IVR.</span></span>

  - <span data-ttu-id="6da12-p117">如果要包含过长的消息，可以考虑将其附加到第一个问题后面，而不要附加到欢迎消息中。如果该消息作为第一个问题的一部分，呼叫者可以通过回答问题来跳过该消息，但是呼叫者无法跳过欢迎消息。</span><span class="sxs-lookup"><span data-stu-id="6da12-p117">If you want to include a lengthy message, consider appending it to the first question instead of to the welcome message. Callers can bypass the message if it is part of the first question by answering the question, but they cannot bypass the welcome message.</span></span>

  - <span data-ttu-id="6da12-p118">以呼叫者的语言讲话。避免造作的语言。自然地讲话。</span><span class="sxs-lookup"><span data-stu-id="6da12-p118">Speak in the caller’s language. Avoid stilted language. Speak naturally.</span></span>

  - <span data-ttu-id="6da12-p119">高效书写和有效提示。删除任何不必要的选项。调整信息结构，使呼叫者的预期响应出现在句尾。例如，“要与销售团队通话，请按 1”。</span><span class="sxs-lookup"><span data-stu-id="6da12-p119">Write efficient and effective prompts. Remove any unnecessary options. Structure the information so that the caller’s expected response is at the end of the sentence. For example, “To speak to the sales team, press 1."</span></span>

  - <span data-ttu-id="6da12-p120">使语音响应用户友好。例如，如果同时指定 DTMF 和语音响应，请使用与此类似的格式：“要与销售团队通话，请按 1 或说销售。”</span><span class="sxs-lookup"><span data-stu-id="6da12-p120">Make voice responses user friendly. For example, if you specify both DTMF and voice responses, use something like: "To speak to the sales team, press 1 or say sales."</span></span>

  - <span data-ttu-id="6da12-189">在组织中部署 IVR 之前，请先对一组用户测试该 IVR。</span><span class="sxs-lookup"><span data-stu-id="6da12-189">Test the IVR on a group of users before you deploy it across your organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

