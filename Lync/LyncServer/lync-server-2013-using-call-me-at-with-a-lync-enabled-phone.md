---
title: Lync Server 2013：在启用 Lync 的电话上使用呼叫我
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Call Me At with a Lync-enabled phone
ms:assetid: 975a1df8-a159-4aa4-a991-5972a535998e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383570(v=OCS.15)
ms:contentKeyID: 56470326
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 157ce646e606f6327e6d7a5fd1957da1480797e1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212858"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-call-me-at-with-a-lync-enabled-phone-and-lync-server-2013"></a><span data-ttu-id="5b595-102">将 "呼叫我" 与启用 Lync 的手机和 Lync Server 2013 一起使用</span><span class="sxs-lookup"><span data-stu-id="5b595-102">Using Call Me At with a Lync-enabled phone and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b595-103">_**上次修改的主题：** 2013-08-09_</span><span class="sxs-lookup"><span data-stu-id="5b595-103">_**Topic Last Modified:** 2013-08-09_</span></span>

<span data-ttu-id="5b595-104">Lync 中的 "呼叫我" 功能为用户提供了一种通过手机、"土地线" 或连接到公用电话交换网（PSTN）的其他设备加入会议的音频部分的方法。</span><span class="sxs-lookup"><span data-stu-id="5b595-104">The Call Me At feature in Lync provides a way for users to join the audio portion of a conference by using a cell phone, “land line,” or other device connected to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="5b595-105">当您尝试使用 Lync 加入会议时，通常会显示 "**加入会议音频**" 对话框：</span><span class="sxs-lookup"><span data-stu-id="5b595-105">When you attempt to join a meeting by using Lync, you will typically be presented with the **Join Meeting Audio** dialog box:</span></span>

<span data-ttu-id="5b595-106">![使用 Lync 加入会议音频窗口屏幕截图](images/Dn383570.e28f17f0-9f17-44ef-b893-f4ef132f47ac(OCS.15).png "使用 Lync 加入会议音频窗口屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="5b595-106">![Use Lync to join meeting audio window screenshot](images/Dn383570.e28f17f0-9f17-44ef-b893-f4ef132f47ac(OCS.15).png "Use Lync to join meeting audio window screenshot")</span></span>

<span data-ttu-id="5b595-107">如果选择 "**呼叫我**"，则可以从下拉列表中选取一个电话号码。</span><span class="sxs-lookup"><span data-stu-id="5b595-107">If you select **Call me at**, you can then pick a phone number from the dropdown list.</span></span> <span data-ttu-id="5b595-108">Lync Server 2013 将向所选号码发出电话呼叫，然后你可以使用该电话参与会议的音频部分。</span><span class="sxs-lookup"><span data-stu-id="5b595-108">Lync Server 2013 will place a phone call to the selected number, and you can then use that phone to participate in the audio portion of the conference.</span></span>

<span data-ttu-id="5b595-109">下拉列表由您在 " **Lync –选项**" 对话框中的 "**电话**" 选项卡上输入的电话号码（对于移动电话、家庭电话或其他电话）填充：</span><span class="sxs-lookup"><span data-stu-id="5b595-109">The dropdown list is populated by the phone numbers (for mobile phone, home phone, or other phone) that you have entered on the **Phones** tab in the **Lync – Options** dialog box:</span></span>

<span data-ttu-id="5b595-110">![Lync 电话设置选项屏幕截图](images/Dn383570.03d2f25d-49e2-47b4-b1e9-b1614fc0c11c(OCS.15).png "Lync 电话设置选项屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="5b595-110">![Lync Phones set up options screenshot](images/Dn383570.03d2f25d-49e2-47b4-b1e9-b1614fc0c11c(OCS.15).png "Lync Phones set up options screenshot")</span></span>

<span data-ttu-id="5b595-111">如果未在 "**电话**" 选项卡上输入任何电话号码，则下拉框中将不提供任何号码。</span><span class="sxs-lookup"><span data-stu-id="5b595-111">If you have not entered any phone numbers on the **Phones** tab then you will not have any numbers available in the dropdown box.</span></span> <span data-ttu-id="5b595-112">但是，您始终可以单击 "**新号码**"，让 Lync Server 拨出到您想要的任何电话号码：</span><span class="sxs-lookup"><span data-stu-id="5b595-112">However, you can always click **New Number** and have Lync Server dial out to any phone number you wish:</span></span>

<span data-ttu-id="5b595-113">![Lync 加入会议音频呼叫我窗口屏幕截图](images/Dn383570.27f2ac7a-cc1c-465c-b145-202ad03af4f2(OCS.15).png "Lync 加入会议音频呼叫我窗口屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="5b595-113">![Lync join meeting audio call me window screenshot](images/Dn383570.27f2ac7a-cc1c-465c-b145-202ad03af4f2(OCS.15).png "Lync join meeting audio call me window screenshot")</span></span>

<span data-ttu-id="5b595-114">如果你按预期方式使用此功能，则 "呼叫我" 功能会非常好地发挥作用：通过让 Lync Server 呼叫 PSTN 电话号码。</span><span class="sxs-lookup"><span data-stu-id="5b595-114">The Call Me At feature works extremely well provided that you use it in the way it was intended: by having Lync Server call a PSTN phone number.</span></span> <span data-ttu-id="5b595-115">但是，如果要求 Lync Server 在启用 Lync 的终结点（例如，会议室中的电话）呼叫你，则可以运行到不到最佳的体验中。</span><span class="sxs-lookup"><span data-stu-id="5b595-115">However, you can run into a less-than-optimal experience if you ask Lync Server to call you at a Lync-enabled endpoint (for example, a phone in a conference room).</span></span> <span data-ttu-id="5b595-116">下面是您可能遇到的问题，以及解决问题的两种方法。</span><span class="sxs-lookup"><span data-stu-id="5b595-116">Following is the issue you might run into, as well as two ways to work around the problem.</span></span>

<span data-ttu-id="5b595-117">若要开始，请在向支持 Lync 的电话号码提供电话号码时提供 "呼叫我" 功能。</span><span class="sxs-lookup"><span data-stu-id="5b595-117">To begin, here’s what happens when you provide the Call Me At feature with the phone number of a Lync-enabled phone.</span></span> <span data-ttu-id="5b595-118">假设 Ken Myer 尝试通过让 Lync Server 呼叫他（即启用 Lync Server 的电话号码）在1-206-555-1219 加入会议。</span><span class="sxs-lookup"><span data-stu-id="5b595-118">Suppose Ken Myer tries to join a meeting by having Lync Server call him at 1-206-555-1219, a Lync Server-enabled phone number.</span></span> <span data-ttu-id="5b595-119">Ken 最初将连接到会议，但在几秒钟后，Lync 将显示消息**呼叫未完成或已结束**，并且 Ken 将显示为已从会议中删除：</span><span class="sxs-lookup"><span data-stu-id="5b595-119">Ken will initially be connected to the meeting, but after a few seconds Lync will display the message **Call was not completed or has ended**, and Ken will appear to have been dropped from the meeting:</span></span>

<span data-ttu-id="5b595-120">![Lync 通话会议窗口的屏幕截图](images/Dn383570.c2a81727-8751-41b5-946a-03a1b75b9d95(OCS.15).png "Lync 通话会议窗口的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="5b595-120">![Screen shot of Lync call conferencing window](images/Dn383570.c2a81727-8751-41b5-946a-03a1b75b9d95(OCS.15).png "Screen shot of Lync call conferencing window")</span></span>

<span data-ttu-id="5b595-121">但请注意，Lync 对话窗口中存在差异。</span><span class="sxs-lookup"><span data-stu-id="5b595-121">Notice, however, that there is a discrepancy within the Lync conversation window.</span></span> <span data-ttu-id="5b595-122">Ken Myer 是在 "**参与者**" 标题下列出的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="5b595-122">Ken Myer is the only name listed under the **Participants** heading.</span></span> <span data-ttu-id="5b595-123">但是，如果您查看窗口的标题栏，将会看到会议总共包含4个参与者。</span><span class="sxs-lookup"><span data-stu-id="5b595-123">However, if you look in the title bar of the window, you’ll see that the conference contains a total of 4 participants.</span></span>

<span data-ttu-id="5b595-124">同样，如果您在 "对话" 窗口中查看任何其他会议参与者，将不会看到 "Ken Myer" 列于任何地方：</span><span class="sxs-lookup"><span data-stu-id="5b595-124">Likewise, if you look in the conversation window of any of the other conference participants you will not see Ken Myer listed anywhere:</span></span>

<span data-ttu-id="5b595-125">![Lync 参与者列表窗口屏幕截图](images/Dn383570.fa5990cf-2694-402c-ac06-946aa66b6837(OCS.15).png "Lync 参与者列表窗口屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="5b595-125">![Lync participant list window screenshot](images/Dn383570.fa5990cf-2694-402c-ac06-946aa66b6837(OCS.15).png "Lync participant list window screenshot")</span></span>

<span data-ttu-id="5b595-126">同时，Ken Myer 将能够通过使用其启用 Lync 的电话参与呼叫的音频部分参与。</span><span class="sxs-lookup"><span data-stu-id="5b595-126">And yet, at the same time, Ken Myer will be able to participate in the audio portion of the call by using his Lync-enabled phone.</span></span> <span data-ttu-id="5b595-127">呼叫我的功能实际工作正常，但用户体验不是最佳的。</span><span class="sxs-lookup"><span data-stu-id="5b595-127">The Call Me At feature has actually worked, but the user experience is less than optimal.</span></span>

<span data-ttu-id="5b595-128">至少有两种方法可以解决此问题。</span><span class="sxs-lookup"><span data-stu-id="5b595-128">There are at least two ways to work around this problem.</span></span> <span data-ttu-id="5b595-129">如果你已采用这种方式加入会议（如 Ken Myer），则通常可以通过使用不同的模态来解决此问题。</span><span class="sxs-lookup"><span data-stu-id="5b595-129">If you have already joined a conference in this fashion (like Ken Myer did), you can typically resolve the issue by engaging in a different modality.</span></span> <span data-ttu-id="5b595-130">例如，如果发送即时消息，对话窗口现在将显示所有会议参与者，包括您自己：</span><span class="sxs-lookup"><span data-stu-id="5b595-130">For example, if you send an instant message the conversation window will now show all the conference participants, including yourself:</span></span>

<span data-ttu-id="5b595-131">![Lync 对话和参与者列表屏幕截图](images/Dn383570.9b5ff6d6-9f73-467c-99a7-ef3aa8bd7e7a(OCS.15).png "Lync 对话和参与者列表屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="5b595-131">![Lync conversation and participant list screenshot](images/Dn383570.9b5ff6d6-9f73-467c-99a7-ef3aa8bd7e7a(OCS.15).png "Lync conversation and participant list screenshot")</span></span>

<span data-ttu-id="5b595-132">此时，您应能够以预期方式参与会议。</span><span class="sxs-lookup"><span data-stu-id="5b595-132">At this point you should be able to participate in the meeting in the expected fashion.</span></span>

<span data-ttu-id="5b595-133">或者，可以通过更改加入会议的方式来完全避免此问题。</span><span class="sxs-lookup"><span data-stu-id="5b595-133">Alternatively, you can avoid this issue altogether by changing the way you join the meeting.</span></span> <span data-ttu-id="5b595-134">如果需要让 Lync Server 呼叫启用 Lync Server 的电话，则应首先在不使用音频连接的情况下加入会议。</span><span class="sxs-lookup"><span data-stu-id="5b595-134">If you need to have Lync Server call a Lync Server-enabled phone, you should begin by joining the meeting without an audio connection.</span></span> <span data-ttu-id="5b595-135">若要执行此操作，请选择 "加入会议音频" 对话框显示 "不加入音频"：</span><span class="sxs-lookup"><span data-stu-id="5b595-135">To do that, select Don’t join audio when presented with the Join Meeting Audio dialog box:</span></span>

<span data-ttu-id="5b595-136">![Lync 不加入会议音频窗口屏幕截图](images/Dn383570.280a148d-cce5-4b02-87f9-9f78f17a81c1(OCS.15).png "Lync 不加入会议音频窗口屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="5b595-136">![Lync don't join meeting audio window screenshot](images/Dn383570.280a148d-cce5-4b02-87f9-9f78f17a81c1(OCS.15).png "Lync don't join meeting audio window screenshot")</span></span>

<span data-ttu-id="5b595-137">成功连接到会议后，您现在可以 "邀请" 启用 Lync Server 的电话，也加入会议。</span><span class="sxs-lookup"><span data-stu-id="5b595-137">After you have successfully connected to the meeting, you can now “invite” the Lync Server-enabled phone to join the meeting as well.</span></span> <span data-ttu-id="5b595-138">若要执行此操作，请将鼠标放在 "人员" 图标上，然后单击 "**邀请更多人**"：</span><span class="sxs-lookup"><span data-stu-id="5b595-138">To do that, place the mouse over the People icon and then click **Invite More People**:</span></span>

<span data-ttu-id="5b595-139">![Lync 邀请更多参与者窗口屏幕截图](images/Dn383570.69b81b29-d1d2-4ed3-acb6-e37dd18e3d86(OCS.15).png "Lync 邀请更多参与者窗口屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="5b595-139">![Lync invite more participants window screenshot](images/Dn383570.69b81b29-d1d2-4ed3-acb6-e37dd18e3d86(OCS.15).png "Lync invite more participants window screenshot")</span></span>

<span data-ttu-id="5b595-140">这将显示 "**发送 IM** " 对话框。</span><span class="sxs-lookup"><span data-stu-id="5b595-140">That will bring up the **Send an IM** dialog box.</span></span> <span data-ttu-id="5b595-141">忽略对话框标题（实际上并不是发送即时消息），并键入启用了 Lync 的手机的电话号码：</span><span class="sxs-lookup"><span data-stu-id="5b595-141">Ignore the dialog box title (you’re not actually sending an instant message) and type the phone number of the Lync-enabled phone:</span></span>

<span data-ttu-id="5b595-142">!["发送 IM" 对话框屏幕截图](images/Dn383570.cd67a3f0-06d8-41ba-a808-c067f64bec9f(OCS.15).png ""发送 IM" 对话框屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="5b595-142">![Send an IM dialog box screenshot](images/Dn383570.cd67a3f0-06d8-41ba-a808-c067f64bec9f(OCS.15).png "Send an IM dialog box screenshot")</span></span>

<span data-ttu-id="5b595-143">单击 **"确定"** 后，Lync Server 将调用在对话框中输入的号码。</span><span class="sxs-lookup"><span data-stu-id="5b595-143">After you click **OK**, Lync Server will call the number entered in the dialog box.</span></span> <span data-ttu-id="5b595-144">建立连接后，你将通过启用 Lync 的手机获得全音频功能，你将能够看到完整的会议名单并与之交互。</span><span class="sxs-lookup"><span data-stu-id="5b595-144">When the connection is made, you will have full audio capabilities through the Lync-enabled phone, and you will be able to see and interact with the full conference roster.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

