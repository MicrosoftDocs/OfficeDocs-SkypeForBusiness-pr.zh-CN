---
title: 'Lync Server 2013: 在启用 Lync 的电话上使用呼叫我'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Call Me At with a Lync-enabled phone
ms:assetid: 975a1df8-a159-4aa4-a991-5972a535998e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383570(v=OCS.15)
ms:contentKeyID: 56470326
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc89ac5038d367a57b791546c287e515bfd3c7bf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845447"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-call-me-at-with-a-lync-enabled-phone-and-lync-server-2013"></a><span data-ttu-id="35efe-102">在启用 Lync 的电话和 Lync Server 2013 上使用 "呼叫我"</span><span class="sxs-lookup"><span data-stu-id="35efe-102">Using Call Me At with a Lync-enabled phone and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35efe-103">_**主题上次修改时间:** 2013-08-09_</span><span class="sxs-lookup"><span data-stu-id="35efe-103">_**Topic Last Modified:** 2013-08-09_</span></span>

<span data-ttu-id="35efe-104">Lync 中的 "呼叫我" 功能为用户提供了一种使用手机、"土地线" 或其他连接到公共交换电话网络 (PSTN) 的设备加入会议音频部分的方式。</span><span class="sxs-lookup"><span data-stu-id="35efe-104">The Call Me At feature in Lync provides a way for users to join the audio portion of a conference by using a cell phone, “land line,” or other device connected to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="35efe-105">当您尝试使用 Lync 加入会议时, 通常会显示 "**加入会议音频**" 对话框:</span><span class="sxs-lookup"><span data-stu-id="35efe-105">When you attempt to join a meeting by using Lync, you will typically be presented with the **Join Meeting Audio** dialog box:</span></span>

<span data-ttu-id="35efe-106">![使用 Lync 加入会议音频窗口屏幕截图](images/Dn383570.e28f17f0-9f17-44ef-b893-f4ef132f47ac(OCS.15).png "使用 Lync 加入会议音频窗口屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="35efe-106">![Use Lync to join meeting audio window screenshot](images/Dn383570.e28f17f0-9f17-44ef-b893-f4ef132f47ac(OCS.15).png "Use Lync to join meeting audio window screenshot")</span></span>

<span data-ttu-id="35efe-107">如果选择 "**呼叫我**", 则可以从下拉列表中选择电话号码。</span><span class="sxs-lookup"><span data-stu-id="35efe-107">If you select **Call me at**, you can then pick a phone number from the dropdown list.</span></span> <span data-ttu-id="35efe-108">Lync Server 2013 将拨打所选号码的电话, 然后您可以使用该电话参与会议的音频部分。</span><span class="sxs-lookup"><span data-stu-id="35efe-108">Lync Server 2013 will place a phone call to the selected number, and you can then use that phone to participate in the audio portion of the conference.</span></span>

<span data-ttu-id="35efe-109">下拉列表由您在 " **Lync-选项**" 对话框中的 "**电话**" 选项卡上输入的电话号码 (用于移动电话、家庭电话或其他电话) 填充:</span><span class="sxs-lookup"><span data-stu-id="35efe-109">The dropdown list is populated by the phone numbers (for mobile phone, home phone, or other phone) that you have entered on the **Phones** tab in the **Lync – Options** dialog box:</span></span>

<span data-ttu-id="35efe-110">![Lync 手机设置选项屏幕截图](images/Dn383570.03d2f25d-49e2-47b4-b1e9-b1614fc0c11c(OCS.15).png "Lync 手机设置选项屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="35efe-110">![Lync Phones set up options screenshot](images/Dn383570.03d2f25d-49e2-47b4-b1e9-b1614fc0c11c(OCS.15).png "Lync Phones set up options screenshot")</span></span>

<span data-ttu-id="35efe-111">如果您未在 "**电话**" 选项卡上输入任何电话号码, 则下拉框中将没有任何可用号码。</span><span class="sxs-lookup"><span data-stu-id="35efe-111">If you have not entered any phone numbers on the **Phones** tab then you will not have any numbers available in the dropdown box.</span></span> <span data-ttu-id="35efe-112">但是, 您始终可以单击 "**新号码**", 让 Lync Server 拨出到您想要的任何电话号码:</span><span class="sxs-lookup"><span data-stu-id="35efe-112">However, you can always click **New Number** and have Lync Server dial out to any phone number you wish:</span></span>

<span data-ttu-id="35efe-113">![Lync 加入会议音频呼叫我窗口屏幕截图](images/Dn383570.27f2ac7a-cc1c-465c-b145-202ad03af4f2(OCS.15).png "Lync 加入会议音频呼叫我窗口屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="35efe-113">![Lync join meeting audio call me window screenshot](images/Dn383570.27f2ac7a-cc1c-465c-b145-202ad03af4f2(OCS.15).png "Lync join meeting audio call me window screenshot")</span></span>

<span data-ttu-id="35efe-114">在功能上, "呼叫我" 功能非常有用, 因为它的使用方式如下: 让 Lync 服务器呼叫 PSTN 电话号码。</span><span class="sxs-lookup"><span data-stu-id="35efe-114">The Call Me At feature works extremely well provided that you use it in the way it was intended: by having Lync Server call a PSTN phone number.</span></span> <span data-ttu-id="35efe-115">但是, 如果你让 Lync 服务器在启用 Lync 的终结点 (例如, 会议室中的电话) 呼叫你, 则可以运行到低于最佳的体验。</span><span class="sxs-lookup"><span data-stu-id="35efe-115">However, you can run into a less-than-optimal experience if you ask Lync Server to call you at a Lync-enabled endpoint (for example, a phone in a conference room).</span></span> <span data-ttu-id="35efe-116">下面是你可能遇到的问题, 以及解决此问题的两种方法。</span><span class="sxs-lookup"><span data-stu-id="35efe-116">Following is the issue you might run into, as well as two ways to work around the problem.</span></span>

<span data-ttu-id="35efe-117">若要开始, 请在使用支持 Lync 的手机的电话号码向 "呼叫我" 提供功能时执行的操作。</span><span class="sxs-lookup"><span data-stu-id="35efe-117">To begin, here’s what happens when you provide the Call Me At feature with the phone number of a Lync-enabled phone.</span></span> <span data-ttu-id="35efe-118">假设 Ken Myer 尝试通过让 Lync Server 在 1-206-555-1219 (启用 Lync 服务器的电话号码) 上呼叫他来加入会议。</span><span class="sxs-lookup"><span data-stu-id="35efe-118">Suppose Ken Myer tries to join a meeting by having Lync Server call him at 1-206-555-1219, a Lync Server-enabled phone number.</span></span> <span data-ttu-id="35efe-119">Ken 最初将连接到会议, 但在几秒钟后, Lync 将显示消息**通话未完成或已结束**, 并且 Ken 将显示为已从会议中删除:</span><span class="sxs-lookup"><span data-stu-id="35efe-119">Ken will initially be connected to the meeting, but after a few seconds Lync will display the message **Call was not completed or has ended**, and Ken will appear to have been dropped from the meeting:</span></span>

<span data-ttu-id="35efe-120">![Lync 呼叫会议窗口的屏幕截图](images/Dn383570.c2a81727-8751-41b5-946a-03a1b75b9d95(OCS.15).png "Lync 呼叫会议窗口的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="35efe-120">![Screen shot of Lync call conferencing window](images/Dn383570.c2a81727-8751-41b5-946a-03a1b75b9d95(OCS.15).png "Screen shot of Lync call conferencing window")</span></span>

<span data-ttu-id="35efe-121">但是请注意, Lync 对话窗口中存在差异。</span><span class="sxs-lookup"><span data-stu-id="35efe-121">Notice, however, that there is a discrepancy within the Lync conversation window.</span></span> <span data-ttu-id="35efe-122">Ken Myer 是 "**参与者**" 标题下列出的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="35efe-122">Ken Myer is the only name listed under the **Participants** heading.</span></span> <span data-ttu-id="35efe-123">但是, 如果你查看窗口的标题栏, 你将看到该会议总共包含4个参与者。</span><span class="sxs-lookup"><span data-stu-id="35efe-123">However, if you look in the title bar of the window, you’ll see that the conference contains a total of 4 participants.</span></span>

<span data-ttu-id="35efe-124">同样, 如果你查看任何其他会议参与者的对话窗口, 你将看不到任何地方列出的 Ken Myer:</span><span class="sxs-lookup"><span data-stu-id="35efe-124">Likewise, if you look in the conversation window of any of the other conference participants you will not see Ken Myer listed anywhere:</span></span>

<span data-ttu-id="35efe-125">![Lync 参与者列表窗口屏幕截图](images/Dn383570.fa5990cf-2694-402c-ac06-946aa66b6837(OCS.15).png "Lync 参与者列表窗口屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="35efe-125">![Lync participant list window screenshot](images/Dn383570.fa5990cf-2694-402c-ac06-946aa66b6837(OCS.15).png "Lync participant list window screenshot")</span></span>

<span data-ttu-id="35efe-126">同时, Ken Myer 还将能够使用其支持 Lync 的手机参与呼叫的音频部分的会议。</span><span class="sxs-lookup"><span data-stu-id="35efe-126">And yet, at the same time, Ken Myer will be able to participate in the audio portion of the call by using his Lync-enabled phone.</span></span> <span data-ttu-id="35efe-127">"呼叫我" 功能实际上已起作用, 但用户体验不是最佳的。</span><span class="sxs-lookup"><span data-stu-id="35efe-127">The Call Me At feature has actually worked, but the user experience is less than optimal.</span></span>

<span data-ttu-id="35efe-128">至少有两种方法可以解决此问题。</span><span class="sxs-lookup"><span data-stu-id="35efe-128">There are at least two ways to work around this problem.</span></span> <span data-ttu-id="35efe-129">如果您已以这种方式加入会议 (如 Ken Myer), 则通常可以通过使用不同的模态来解决该问题。</span><span class="sxs-lookup"><span data-stu-id="35efe-129">If you have already joined a conference in this fashion (like Ken Myer did), you can typically resolve the issue by engaging in a different modality.</span></span> <span data-ttu-id="35efe-130">例如, 如果发送即时消息, 则对话窗口现在将显示所有会议参与者, 包括你:</span><span class="sxs-lookup"><span data-stu-id="35efe-130">For example, if you send an instant message the conversation window will now show all the conference participants, including yourself:</span></span>

<span data-ttu-id="35efe-131">![Lync 对话和参与者列表屏幕截图](images/Dn383570.9b5ff6d6-9f73-467c-99a7-ef3aa8bd7e7a(OCS.15).png "Lync 对话和参与者列表屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="35efe-131">![Lync conversation and participant list screenshot](images/Dn383570.9b5ff6d6-9f73-467c-99a7-ef3aa8bd7e7a(OCS.15).png "Lync conversation and participant list screenshot")</span></span>

<span data-ttu-id="35efe-132">此时, 你应该能够以预期的方式参与会议。</span><span class="sxs-lookup"><span data-stu-id="35efe-132">At this point you should be able to participate in the meeting in the expected fashion.</span></span>

<span data-ttu-id="35efe-133">或者, 您可以通过更改加入会议的方式来完全避免此问题。</span><span class="sxs-lookup"><span data-stu-id="35efe-133">Alternatively, you can avoid this issue altogether by changing the way you join the meeting.</span></span> <span data-ttu-id="35efe-134">如果您需要让 Lync Server 呼叫支持 Lync 服务器的手机, 则应首先在没有音频连接的情况下加入会议。</span><span class="sxs-lookup"><span data-stu-id="35efe-134">If you need to have Lync Server call a Lync Server-enabled phone, you should begin by joining the meeting without an audio connection.</span></span> <span data-ttu-id="35efe-135">若要执行此操作, 请在显示 "加入会议音频" 对话框时选择 "不加入音频":</span><span class="sxs-lookup"><span data-stu-id="35efe-135">To do that, select Don’t join audio when presented with the Join Meeting Audio dialog box:</span></span>

<span data-ttu-id="35efe-136">![Lync 不加入会议音频窗口屏幕截图](images/Dn383570.280a148d-cce5-4b02-87f9-9f78f17a81c1(OCS.15).png "Lync 不加入会议音频窗口屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="35efe-136">![Lync don't join meeting audio window screenshot](images/Dn383570.280a148d-cce5-4b02-87f9-9f78f17a81c1(OCS.15).png "Lync don't join meeting audio window screenshot")</span></span>

<span data-ttu-id="35efe-137">成功连接到会议后, 您现在可以 "邀请" Lync Server 启用的手机加入会议。</span><span class="sxs-lookup"><span data-stu-id="35efe-137">After you have successfully connected to the meeting, you can now “invite” the Lync Server-enabled phone to join the meeting as well.</span></span> <span data-ttu-id="35efe-138">若要执行此操作, 请将鼠标放在 "人员" 图标上, 然后单击 "**邀请更多人**":</span><span class="sxs-lookup"><span data-stu-id="35efe-138">To do that, place the mouse over the People icon and then click **Invite More People**:</span></span>

<span data-ttu-id="35efe-139">![Lync 邀请更多参与者窗口屏幕截图](images/Dn383570.69b81b29-d1d2-4ed3-acb6-e37dd18e3d86(OCS.15).png "Lync 邀请更多参与者窗口屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="35efe-139">![Lync invite more participants window screenshot](images/Dn383570.69b81b29-d1d2-4ed3-acb6-e37dd18e3d86(OCS.15).png "Lync invite more participants window screenshot")</span></span>

<span data-ttu-id="35efe-140">将弹出 "**发送 IM** " 对话框。</span><span class="sxs-lookup"><span data-stu-id="35efe-140">That will bring up the **Send an IM** dialog box.</span></span> <span data-ttu-id="35efe-141">忽略对话框标题 (实际上不是发送即时消息), 然后键入启用 Lync 的手机的电话号码:</span><span class="sxs-lookup"><span data-stu-id="35efe-141">Ignore the dialog box title (you’re not actually sending an instant message) and type the phone number of the Lync-enabled phone:</span></span>

<span data-ttu-id="35efe-142">!["发送 IM" 对话框屏幕截图](images/Dn383570.cd67a3f0-06d8-41ba-a808-c067f64bec9f(OCS.15).png "\"发送 IM\" 对话框屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="35efe-142">![Send an IM dialog box screenshot](images/Dn383570.cd67a3f0-06d8-41ba-a808-c067f64bec9f(OCS.15).png "Send an IM dialog box screenshot")</span></span>

<span data-ttu-id="35efe-143">单击 **"确定**" 后, Lync Server 将呼叫在对话框中输入的号码。</span><span class="sxs-lookup"><span data-stu-id="35efe-143">After you click **OK**, Lync Server will call the number entered in the dialog box.</span></span> <span data-ttu-id="35efe-144">建立连接后, 您将能够通过启用 Lync 的手机获得全音频功能, 您将能够看到完整的会议名单并与之交互。</span><span class="sxs-lookup"><span data-stu-id="35efe-144">When the connection is made, you will have full audio capabilities through the Lync-enabled phone, and you will be able to see and interact with the full conference roster.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

