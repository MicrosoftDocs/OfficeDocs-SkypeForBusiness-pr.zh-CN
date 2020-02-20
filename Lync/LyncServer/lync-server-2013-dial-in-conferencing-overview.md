---
title: Lync Server 2013 电话拨入式会议概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing overview
ms:assetid: 6e581cef-960a-4730-8b22-91b2129d34e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398524(v=OCS.15)
ms:contentKeyID: 48184436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fdeaa7b53dfd39415dd729404b1b3a14dee29c7c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153874"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="8b627-102">Lync Server 2013 中的电话拨入式会议概述</span><span class="sxs-lookup"><span data-stu-id="8b627-102">Overview of dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b627-103">_**上次修改的主题：** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="8b627-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="8b627-104">如果贵组织的用户在外出时需要出席 Lync Server 2013 本地会议或无法访问计算机，则可以部署电话拨入式会议，以便他们可以使用公开交换电话加入会议网络（PSTN）电话。</span><span class="sxs-lookup"><span data-stu-id="8b627-104">If your organization has users who need to attend Lync Server 2013 on-premises conferences when they are out of the office or do not have access to a computer, you can deploy dial-in conferencing so that they can join the conference by using a public switched telephone network (PSTN) phone.</span></span>

<span data-ttu-id="8b627-105">电话拨入式会议是一项可选功能，可在部署 Lync Server 2013 会议时进行配置。</span><span class="sxs-lookup"><span data-stu-id="8b627-105">Dial-in conferencing is an optional feature that you can configure when you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="8b627-106">虽然电话拨入式会议使用企业语音使用的一些相同的 Lync Server 2013 组件，但即使不部署企业语音，也可以部署电话拨入式会议。</span><span class="sxs-lookup"><span data-stu-id="8b627-106">Although dial-in conferencing uses some of the same Lync Server 2013 components that Enterprise Voice uses, you can deploy dial-in conferencing even if you do not deploy Enterprise Voice.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8b627-107">如果要部署电话拨入式会议，则必须在部署 Lync Server 2013 会议的每个池中部署它。</span><span class="sxs-lookup"><span data-stu-id="8b627-107">If you deploy dial-in conferencing, you must deploy it in every pool where you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="8b627-108">无需在每个池中分配访问号码，但必须在每个池中部署拨入功能。</span><span class="sxs-lookup"><span data-stu-id="8b627-108">You do not need to assign access numbers in every pool, but you must deploy the dial-in feature in every pool.</span></span> <span data-ttu-id="8b627-109">当用户从一个池中调用访问号码以在不同的池中加入 Lync Server 2013 会议时，此要求支持所记录的名称功能。</span><span class="sxs-lookup"><span data-stu-id="8b627-109">This requirement supports the recorded name feature when a user calls an access number from one pool to join a Lync Server 2013 conference in a different pool.</span></span>



</div>

<span data-ttu-id="8b627-p103">在会议策略中，会议必须支持拨入访问。默认情况下，允许拨入访问的会议会在会议邀请中包括以下信息：</span><span class="sxs-lookup"><span data-stu-id="8b627-p103">Conferences must be enabled for dial-in access in meeting policy. By default, conferences that are enabled for dial-in access include the following information in the conference invitation:</span></span>

  - <span data-ttu-id="8b627-112">用于标识会议的数字会议 ID。</span><span class="sxs-lookup"><span data-stu-id="8b627-112">A numeric conference ID that identifies the conference.</span></span>

  - <span data-ttu-id="8b627-113">一个或多个 PSTN 接入号码。</span><span class="sxs-lookup"><span data-stu-id="8b627-113">One or more PSTN access numbers.</span></span>

  - <span data-ttu-id="8b627-114">指向 "电话拨入式会议设置" 页的链接，其中包含访问号码及其关联语言的完整列表;用于创建、重置或取消阻止个人识别码（Pin）的位置;以及其他信息，如双音多频（DTMF）控件。</span><span class="sxs-lookup"><span data-stu-id="8b627-114">A link to a Dial-in Conferencing Settings page, which contains a complete list of access numbers with their associated languages; a place to create, reset, or unblock personal identification numbers (PINs); and other information, such as dual-tone multi-frequency (DTMF) controls.</span></span>

<span data-ttu-id="8b627-115">电话拨入式会议支持企业用户和匿名用户。</span><span class="sxs-lookup"><span data-stu-id="8b627-115">Dial-in conferencing supports both enterprise and anonymous users.</span></span> <span data-ttu-id="8b627-116">企业用户在其组织中具有 Active Directory 域服务凭据和 Lync Server 2013 帐户。</span><span class="sxs-lookup"><span data-stu-id="8b627-116">Enterprise users have Active Directory Domain Services credentials and Lync Server 2013 accounts within their organization.</span></span> <span data-ttu-id="8b627-117">匿名用户在组织内不具有企业凭据。</span><span class="sxs-lookup"><span data-stu-id="8b627-117">Anonymous users do not have enterprise credentials within your organization.</span></span> <span data-ttu-id="8b627-118">在电话拨入式会议环境中，联盟伙伴组织中使用 PSTN 连接至会议的用户被视为匿名用户。</span><span class="sxs-lookup"><span data-stu-id="8b627-118">In the dial-in conferencing context, a user in a federated partner’s organization who uses the PSTN to connect to a conference is treated like an anonymous user.</span></span> <span data-ttu-id="8b627-119">对于电话拨入式会议（不同于其他环境），联盟用户都未经过身份验证。</span><span class="sxs-lookup"><span data-stu-id="8b627-119">For dial-in conferencing, unlike other contexts, federated users are not authenticated.</span></span>

<span data-ttu-id="8b627-120">参加允许拨入访问会议的企业用户或会议主持人拨打一个会议访问号码后，系统会提示他们输入会议 ID。</span><span class="sxs-lookup"><span data-stu-id="8b627-120">Enterprise users or conference leaders who join a conference that is enabled for dial-in access dial one of the conference access numbers and then are prompted to enter the conference ID.</span></span> <span data-ttu-id="8b627-121">如果主持人尚未参加会议，则用户可以输入其统一通信 (UC) 分机号（或完整电话号码）和 PIN，或者等待主持人准许其参加会议。</span><span class="sxs-lookup"><span data-stu-id="8b627-121">If a leader has not yet joined the meeting, users can either enter their unified communications (UC) extension (or full phone number) and PIN or wait to be admitted by a leader.</span></span> <span data-ttu-id="8b627-122">通过只输入其 PIN，会议组织者就可以以主持人身份参加会议。</span><span class="sxs-lookup"><span data-stu-id="8b627-122">The Meeting organizer can join the meeting as a leader by entering just their PIN.</span></span> <span data-ttu-id="8b627-123">前端服务器使用完整的电话号码或分机和 PIN 的组合，将企业用户唯一映射到其 Active Directory 凭据。</span><span class="sxs-lookup"><span data-stu-id="8b627-123">The Front End Server uses the combination of full phone number or extension, and PIN, to uniquely map enterprise users to their Active Directory credentials.</span></span> <span data-ttu-id="8b627-124">因此，在会议中是按名称对企业用户进行身份验证和标识的。</span><span class="sxs-lookup"><span data-stu-id="8b627-124">As a result, enterprise users are authenticated and identified by name in the conference.</span></span> <span data-ttu-id="8b627-125">企业用户还可以担任由组织者预定义的会议角色。</span><span class="sxs-lookup"><span data-stu-id="8b627-125">Enterprise users can also assume a conference role predefined by the organizer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8b627-126">从 office IP 手机或从 Lync Server 2013 或 Lync 2010 助理拨入的企业用户不会收到其电话号码的提示，因为它们已经过身份验证。</span><span class="sxs-lookup"><span data-stu-id="8b627-126">Enterprise users who dial in from an office IP phone or from Lync Server 2013 or Lync 2010 Attendant are not prompted for their phone number because they are already authenticated.</span></span>



</div>

<span data-ttu-id="8b627-p106">要参加电话拨入式会议的匿名用户拨打一个会议接入号码后，系统会提示他们输入会议 ID。还会提示未经身份验证的匿名用户记录其名称。记录的名称用于在会议中标识未经身份验证的用户。除非至少一个主持人或经过身份验证的用户已参加会议，否则不允许匿名用户参加会议，且无法向其分配预定义角色。</span><span class="sxs-lookup"><span data-stu-id="8b627-p106">Anonymous users who want to join a dial-in conference dial one of the conference access numbers and then they are prompted to enter the conference ID. Unauthenticated anonymous users are also prompted to record their name. The recorded name identifies unauthenticated users in the conference. Anonymous users are not admitted to the conference until at least one leader or authenticated user has joined, and they cannot be assigned a predefined role.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8b627-p107">选择不输入其电话号码和 PIN 的企业用户未经过身份验证。系统会提示他们记录其名称，并在会议中将他们视为匿名用户。</span><span class="sxs-lookup"><span data-stu-id="8b627-p107">Enterprise users who choose not to enter their phone number and PIN are not authenticated. They are prompted to record their name and are treated as anonymous users in the conference.</span></span>



</div>

<span data-ttu-id="8b627-p108">到预定时间时，会议组织者可选择通过关闭或锁定会议来限制对会议的访问。在这种情况下，系统会请求电话拨入用户进行身份验证。如果电话拨入用户身份验证失败或选择不进行身份验证，他们会被转移到会议厅中等待，直到主持人接受或拒绝他们，或者连接超时并断开连接。他们在会议厅中等待获准加入会议时，电话拨入用户将听到音乐。一旦被允许加入会议，电话拨入用户就可以参与会议的音频部分，并可使用电话键盘执行双音多频 (DTMF) 命令。电话拨入主持人可以使用 DTMF 命令打开或关闭参与者的取消静音功能、锁定或解锁会议、允许会议厅中的人加入会议、打开或关闭进入和退出通知。主持人还可以使用 DTMF 命令允许会议厅中的每个人加入会议，从而更改会议的权限以允许随后的任何人加入会议。所有电话拨入参与者都可以使用 DTMF 命令收听帮助，收听会议名单，以及使自己静音。</span><span class="sxs-lookup"><span data-stu-id="8b627-p108">At schedule time, the meeting organizer can choose to restrict access to the meeting by making the meeting closed or locked. In this case, dial-in users are requested to authenticate. If dial-in users fail or choose not to authenticate, they are transferred to the lobby. They wait in the lobby until a leader accepts or rejects them, or they time out and are disconnected. Dial-in users hear music if they are waiting to be admitted to the conference. After they are admitted to a conference, dial-in users can participate in the audio portion of the conference and can exercise dual-tone multi-frequency (DTMF) commands by using the phone keypad. Dial-in leaders can exercise DTMF commands to turn participants' ability to unmute on or off, lock or unlock the conference, admit people from the lobby, and turn entry and exit announcements on or off. Leaders can also use a DTMF command to admit everyone from the lobby, which changes the permissions of the meeting to allow anyone who subsequently joins. All dial-in participants can exercise DTMF commands to hear Help, listen to the conference roster, and mute themselves.</span></span>

<span data-ttu-id="8b627-142">电话拨入参与者（即，无论他们是否从 PSTN 拨号）在会议期间收听个人通知，例如，是否已将其静音或取消静音，是否记录会议，或者是否有人在会议厅中等待。</span><span class="sxs-lookup"><span data-stu-id="8b627-142">Dial-in participants (that is, whether or not they dial from the PSTN), hear personal announcements during the conference, such as whether they have been muted or unmuted, the meeting is being recorded, or someone is waiting in the lobby.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8b627-143">通过单击链接（而不是电话拨入）参加会议的与会者不会听到个人通知。</span><span class="sxs-lookup"><span data-stu-id="8b627-143">Participants who join the conference by clicking a link instead of dialing in do not hear personal announcements.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

