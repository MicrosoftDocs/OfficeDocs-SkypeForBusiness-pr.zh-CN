---
title: Lync Server 2013 电话拨入式会议概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Dial-in conferencing overview
ms:assetid: 6e581cef-960a-4730-8b22-91b2129d34e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398524(v=OCS.15)
ms:contentKeyID: 48184436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 820c880d44a1ecede139a8d3caddf3f6c40e65a1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830406"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="6e7b3-102">Lync Server 2013 中的电话拨入式会议概述</span><span class="sxs-lookup"><span data-stu-id="6e7b3-102">Overview of dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e7b3-103">_**主题上次修改时间:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="6e7b3-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="6e7b3-104">如果你的组织有用户在外出时需要出席 Lync Server 2013 本地会议或无法访问计算机, 则可以部署电话拨入式会议, 以便他们可以使用公共交换电话加入会议网络 (PSTN) 电话。</span><span class="sxs-lookup"><span data-stu-id="6e7b3-104">If your organization has users who need to attend Lync Server 2013 on-premises conferences when they are out of the office or do not have access to a computer, you can deploy dial-in conferencing so that they can join the conference by using a public switched telephone network (PSTN) phone.</span></span>

<span data-ttu-id="6e7b3-105">电话拨入式会议是一项可选功能, 您可以在部署 Lync Server 2013 会议时进行配置。</span><span class="sxs-lookup"><span data-stu-id="6e7b3-105">Dial-in conferencing is an optional feature that you can configure when you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="6e7b3-106">虽然电话拨入式会议使用企业语音使用的某些 Lync Server 2013 组件, 但即使不部署企业语音, 也可以部署拨入式会议。</span><span class="sxs-lookup"><span data-stu-id="6e7b3-106">Although dial-in conferencing uses some of the same Lync Server 2013 components that Enterprise Voice uses, you can deploy dial-in conferencing even if you do not deploy Enterprise Voice.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6e7b3-107">如果你部署电话拨入式会议, 则必须在部署 Lync Server 2013 会议的每个池中部署它。</span><span class="sxs-lookup"><span data-stu-id="6e7b3-107">If you deploy dial-in conferencing, you must deploy it in every pool where you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="6e7b3-108">无需在每个池中分配访问号码, 但必须在每个池中部署拨入功能。</span><span class="sxs-lookup"><span data-stu-id="6e7b3-108">You do not need to assign access numbers in every pool, but you must deploy the dial-in feature in every pool.</span></span> <span data-ttu-id="6e7b3-109">当用户从一个池中调用访问号码以在其他池中加入 Lync Server 2013 会议时, 此要求支持录制的名称功能。</span><span class="sxs-lookup"><span data-stu-id="6e7b3-109">This requirement supports the recorded name feature when a user calls an access number from one pool to join a Lync Server 2013 conference in a different pool.</span></span>



</div>

<span data-ttu-id="6e7b3-110">必须为会议策略中的拨入访问启用会议。</span><span class="sxs-lookup"><span data-stu-id="6e7b3-110">Conferences must be enabled for dial-in access in meeting policy.</span></span> <span data-ttu-id="6e7b3-111">默认情况下，允许拨入访问的会议会在会议邀请中包括以下信息：</span><span class="sxs-lookup"><span data-stu-id="6e7b3-111">By default, conferences that are enabled for dial-in access include the following information in the conference invitation:</span></span>

  - <span data-ttu-id="6e7b3-112">标识会议的数字会议 ID。</span><span class="sxs-lookup"><span data-stu-id="6e7b3-112">A numeric conference ID that identifies the conference.</span></span>

  - <span data-ttu-id="6e7b3-113">一个或多个 PSTN 访问号码。</span><span class="sxs-lookup"><span data-stu-id="6e7b3-113">One or more PSTN access numbers.</span></span>

  - <span data-ttu-id="6e7b3-114">指向 "电话拨入式会议设置" 页面的链接, 其中包含具有相关语言的访问号码的完整列表;用于创建、重置或取消阻止个人识别码 (Pin) 的位置;和其他信息, 如双音调多频率 (DTMF) 控件。</span><span class="sxs-lookup"><span data-stu-id="6e7b3-114">A link to a Dial-in Conferencing Settings page, which contains a complete list of access numbers with their associated languages; a place to create, reset, or unblock personal identification numbers (PINs); and other information, such as dual-tone multi-frequency (DTMF) controls.</span></span>

<span data-ttu-id="6e7b3-115">电话拨入式会议支持企业用户和匿名用户。</span><span class="sxs-lookup"><span data-stu-id="6e7b3-115">Dial-in conferencing supports both enterprise and anonymous users.</span></span> <span data-ttu-id="6e7b3-116">企业用户在其组织内具有 Active Directory 域服务凭据和 Lync Server 2013 帐户。</span><span class="sxs-lookup"><span data-stu-id="6e7b3-116">Enterprise users have Active Directory Domain Services credentials and Lync Server 2013 accounts within their organization.</span></span> <span data-ttu-id="6e7b3-117">匿名用户在组织内不具有企业凭据。</span><span class="sxs-lookup"><span data-stu-id="6e7b3-117">Anonymous users do not have enterprise credentials within your organization.</span></span> <span data-ttu-id="6e7b3-118">在电话拨入式会议环境中，联盟伙伴组织中使用 PSTN 连接至会议的用户被视为匿名用户。</span><span class="sxs-lookup"><span data-stu-id="6e7b3-118">In the dial-in conferencing context, a user in a federated partner’s organization who uses the PSTN to connect to a conference is treated like an anonymous user.</span></span> <span data-ttu-id="6e7b3-119">对于电话拨入式会议（不同于其他环境），联盟用户都未经过身份验证。</span><span class="sxs-lookup"><span data-stu-id="6e7b3-119">For dial-in conferencing, unlike other contexts, federated users are not authenticated.</span></span>

<span data-ttu-id="6e7b3-p105">参加允许拨入访问会议的企业用户或会议主持人拨打一个会议访问号码后，系统会提示他们输入会议 ID。如果主持人尚未参加会议，则用户可以输入其统一通信 (UC) 分机号（或完整电话号码）和 PIN，或者等待主持人准许其参加会议。通过只输入其 PIN，会议组织者就可以以主持人身份参加会议。前端服务器使用完整电话号码或分机号与 PIN 的组合唯一地将企业用户映射到其 Active Directory 凭据。因此，在会议中是按名称对企业用户进行身份验证和标识的。企业用户还可以担任由组织者预定义的会议角色。</span><span class="sxs-lookup"><span data-stu-id="6e7b3-p105">Enterprise users or conference leaders who join a conference that is enabled for dial-in access dial one of the conference access numbers and then are prompted to enter the conference ID. If a leader has not yet joined the meeting, users can either enter their unified communications (UC) extension (or full phone number) and PIN or wait to be admitted by a leader. The Meeting organizer can join the meeting as a leader by entering just their PIN. The Front End Server uses the combination of full phone number or extension, and PIN, to uniquely map enterprise users to their Active Directory credentials. As a result, enterprise users are authenticated and identified by name in the conference. Enterprise users can also assume a conference role predefined by the organizer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6e7b3-126">通过 office IP 手机或从 Lync Server 2013 或 Lync 2010 助理拨入的企业用户将不会收到其电话号码的提示, 因为他们已经过身份验证。</span><span class="sxs-lookup"><span data-stu-id="6e7b3-126">Enterprise users who dial in from an office IP phone or from Lync Server 2013 or Lync 2010 Attendant are not prompted for their phone number because they are already authenticated.</span></span>



</div>

<span data-ttu-id="6e7b3-p106">要参加电话拨入式会议的匿名用户拨打一个会议接入号码后，系统会提示他们输入会议 ID。还会提示未经身份验证的匿名用户记录其名称。记录的名称用于在会议中标识未经身份验证的用户。除非至少一个主持人或经过身份验证的用户已参加会议，否则不允许匿名用户参加会议，且无法向其分配预定义角色。</span><span class="sxs-lookup"><span data-stu-id="6e7b3-p106">Anonymous users who want to join a dial-in conference dial one of the conference access numbers and then they are prompted to enter the conference ID. Unauthenticated anonymous users are also prompted to record their name. The recorded name identifies unauthenticated users in the conference. Anonymous users are not admitted to the conference until at least one leader or authenticated user has joined, and they cannot be assigned a predefined role.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6e7b3-p107">选择不输入其电话号码和 PIN 的企业用户未经过身份验证。系统会提示他们记录其名称，并在会议中将他们视为匿名用户。</span><span class="sxs-lookup"><span data-stu-id="6e7b3-p107">Enterprise users who choose not to enter their phone number and PIN are not authenticated. They are prompted to record their name and are treated as anonymous users in the conference.</span></span>



</div>

<span data-ttu-id="6e7b3-133">在计划时间, 会议组织者可以通过使会议关闭或锁定来选择限制对会议的访问。</span><span class="sxs-lookup"><span data-stu-id="6e7b3-133">At schedule time, the meeting organizer can choose to restrict access to the meeting by making the meeting closed or locked.</span></span> <span data-ttu-id="6e7b3-134">这种情况下，会请求拨入用户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="6e7b3-134">In this case, dial-in users are requested to authenticate.</span></span> <span data-ttu-id="6e7b3-135">如果拨入用户失败或选择不进行身份验证, 则会将其转移到大厅。</span><span class="sxs-lookup"><span data-stu-id="6e7b3-135">If dial-in users fail or choose not to authenticate, they are transferred to the lobby.</span></span> <span data-ttu-id="6e7b3-136">他们在大厅中等待, 直到组长接受或拒绝他们, 或者他们超时且断开连接。</span><span class="sxs-lookup"><span data-stu-id="6e7b3-136">They wait in the lobby until a leader accepts or rejects them, or they time out and are disconnected.</span></span> <span data-ttu-id="6e7b3-137">拨入用户在等待会议时将听到音乐。</span><span class="sxs-lookup"><span data-stu-id="6e7b3-137">Dial-in users hear music if they are waiting to be admitted to the conference.</span></span> <span data-ttu-id="6e7b3-138">一旦被允许加入会议，电话拨入用户就可以参与会议的音频部分，并可使用电话键盘执行双音多频 (DTMF) 命令。</span><span class="sxs-lookup"><span data-stu-id="6e7b3-138">After they are admitted to a conference, dial-in users can participate in the audio portion of the conference and can exercise dual-tone multi-frequency (DTMF) commands by using the phone keypad.</span></span> <span data-ttu-id="6e7b3-139">电话拨入主持人可以使用 DTMF 命令打开或关闭参与者的取消静音功能、锁定或解锁会议、允许会议厅中的人加入会议、打开或关闭进入和退出通知。</span><span class="sxs-lookup"><span data-stu-id="6e7b3-139">Dial-in leaders can exercise DTMF commands to turn participants' ability to unmute on or off, lock or unlock the conference, admit people from the lobby, and turn entry and exit announcements on or off.</span></span> <span data-ttu-id="6e7b3-140">主持人还可以使用 DTMF 命令允许会议厅中的每个人加入会议，从而更改会议的权限以允许随后的任何人加入会议。</span><span class="sxs-lookup"><span data-stu-id="6e7b3-140">Leaders can also use a DTMF command to admit everyone from the lobby, which changes the permissions of the meeting to allow anyone who subsequently joins.</span></span> <span data-ttu-id="6e7b3-141">所有电话拨入参与者都可以使用 DTMF 命令收听帮助，收听会议名单，以及使自己静音。</span><span class="sxs-lookup"><span data-stu-id="6e7b3-141">All dial-in participants can exercise DTMF commands to hear Help, listen to the conference roster, and mute themselves.</span></span>

<span data-ttu-id="6e7b3-142">拨入式参与者 (即, 无论是从 PSTN 拨号), 在会议期间收听个人公告, 例如他们是否已被静音或已取消静音、正在录制会议还是正在会议厅中等待其他人。</span><span class="sxs-lookup"><span data-stu-id="6e7b3-142">Dial-in participants (that is, whether or not they dial from the PSTN), hear personal announcements during the conference, such as whether they have been muted or unmuted, the meeting is being recorded, or someone is waiting in the lobby.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6e7b3-143">通过单击链接（而不是电话拨入）参加会议的与会者不会听到个人通知。</span><span class="sxs-lookup"><span data-stu-id="6e7b3-143">Participants who join the conference by clicking a link instead of dialing in do not hear personal announcements.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

