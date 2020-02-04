---
title: Lync Server 2013 企业语音
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enterprise Voice
ms:assetid: c9da8099-6f4f-4346-ac67-f041bb96072c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417163(v=OCS.15)
ms:contentKeyID: 48185404
ms.date: 04/08/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e62224a7187c54222364045d0ac7b1aa70bccb9c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735412"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="39cc3-102">Lync Server 2013 中的企业语音</span><span class="sxs-lookup"><span data-stu-id="39cc3-102">Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39cc3-103">_**主题上次修改时间：** 2015-04-08_</span><span class="sxs-lookup"><span data-stu-id="39cc3-103">_**Topic Last Modified:** 2015-04-08_</span></span>

<span data-ttu-id="39cc3-104">使用企业语音，Lync 服务器提供一种独立的 Internet 协议（VoIP）产品，用于增强或更换传统专用分支 exchange （PBX）系统。</span><span class="sxs-lookup"><span data-stu-id="39cc3-104">With Enterprise Voice, Lync Server delivers a stand-alone Voice over Internet Protocol (VoIP) offering to enhance or replace traditional private branch exchange (PBX) systems.</span></span> <span data-ttu-id="39cc3-105">企业语音用户可以通过您的组织的 VoIP 网络或 PBX 呼叫同事，并且他们可以拨打您的组织外部的传统电话号码。</span><span class="sxs-lookup"><span data-stu-id="39cc3-105">Enterprise Voice users can call colleagues on your organization’s VoIP network or PBX, and they can call traditional phone numbers outside your organization.</span></span> <span data-ttu-id="39cc3-106">企业语音解决方案包括常见呼叫功能，如 "应答"、"转发"、"转移"、"保持"、"转移"、"发布和寄存" 以及 "增强9-1-1 （E9）" （E9-1-1 仅在美国可用）。）企业语音还支持一系列最新的和较旧的 IP 和 USB 设备。</span><span class="sxs-lookup"><span data-stu-id="39cc3-106">The Enterprise Voice solution includes common calling features such as answer, forward, transfer, hold, divert, release and park, and Enhanced 9-1-1 (E9-1-1) calling (E9-1-1 is available only in the United States.) Enterprise Voice also supports a broad range of current and older IP and USB devices.</span></span>

<div>

## <a name="placing-and-receiving-calls"></a><span data-ttu-id="39cc3-107">拨打和接听电话</span><span class="sxs-lookup"><span data-stu-id="39cc3-107">Placing and Receiving Calls</span></span>

<span data-ttu-id="39cc3-108">使用 Lync，用户可以通过在键盘上键入姓名或电话号码，或使用屏幕上显示的拨号盘来拨打电话。</span><span class="sxs-lookup"><span data-stu-id="39cc3-108">Using Lync, users can place calls by typing a name or phone number on their keyboard, or using a dial pad displayed on their screen.</span></span> <span data-ttu-id="39cc3-109">用户也可以直接从其联系人列表中发起呼叫。</span><span class="sxs-lookup"><span data-stu-id="39cc3-109">Users can also initiate calls directly from their Contacts list.</span></span> <span data-ttu-id="39cc3-110">您也可以部署 Lync Phone 版设备，这些设备是由 Microsoft 合作伙伴提供的独立的 IP 电话设备。</span><span class="sxs-lookup"><span data-stu-id="39cc3-110">You can also deploy Lync Phone Edition devices, which are stand-alone IP phone devices provided by Microsoft partners.</span></span>

<span data-ttu-id="39cc3-111">用户可以有多个电话设备注册到 Lync 服务器，并且可以轻松地在它们之间进行切换。</span><span class="sxs-lookup"><span data-stu-id="39cc3-111">Users can have multiple phone devices registered with Lync Server, and can switch between them easily.</span></span>

<span data-ttu-id="39cc3-112">使用 IP 电话设备上的可自定义铃声和类似于电脑上的即时消息的通知，用户同时收到对其所有设备的传入呼叫的通知。</span><span class="sxs-lookup"><span data-stu-id="39cc3-112">Users are alerted to incoming calls on all their devices simultaneously, with customizable ringtones on IP phone devices and a notification similar to an instant message on their PC.</span></span>

<span data-ttu-id="39cc3-113">用户还可以设置连接到其桌面电话、PC 和手机的单个电话号码，以便无论他们身在何处均可访问。</span><span class="sxs-lookup"><span data-stu-id="39cc3-113">Users can also set a single telephone number that connects to their desk phone, PC and mobile phone, so they can be reached no matter where they are.</span></span>

</div>

<div>

## <a name="basic-call-features"></a><span data-ttu-id="39cc3-114">基本呼叫功能</span><span class="sxs-lookup"><span data-stu-id="39cc3-114">Basic Call Features</span></span>

<span data-ttu-id="39cc3-115">通话时，用户可以接听其他传入呼叫或发起拨出的通话，并且现有的活动通话将自动置于保持状态。</span><span class="sxs-lookup"><span data-stu-id="39cc3-115">While on a call, a user can answer additional incoming calls or initiate outgoing calls, and the existing active call is automatically put on hold.</span></span> <span data-ttu-id="39cc3-116">可以直接或在第一位用户与第二位用户进行私下通话时，将呼叫从一个用户转移到另一个用户。</span><span class="sxs-lookup"><span data-stu-id="39cc3-116">Calls can be transferred from one user to another, either directly or after the first user speaks privately with the second user.</span></span> <span data-ttu-id="39cc3-117">用户还可以将呼叫转移到另一台设备;例如，他们可以将活动呼叫转移到其移动电话，因为他们将外出。</span><span class="sxs-lookup"><span data-stu-id="39cc3-117">Users can also transfer calls to another device; for example, they could transfer an active call to their mobile phone as they walk out the door of their office.</span></span>

</div>

<div>

## <a name="richer-communications"></a><span data-ttu-id="39cc3-118">更丰富的通信</span><span class="sxs-lookup"><span data-stu-id="39cc3-118">Richer Communications</span></span>

<span data-ttu-id="39cc3-119">使用 Lync 与另一个用户交谈时，用户可以轻松地向呼叫添加文本、视频或桌面共享。</span><span class="sxs-lookup"><span data-stu-id="39cc3-119">When talking to another user with Lync, users can easily add text, video, or desktop sharing to the call.</span></span> <span data-ttu-id="39cc3-120">"请勿打扰" 功能与 Lync 中的状态设置集成。</span><span class="sxs-lookup"><span data-stu-id="39cc3-120">The Do-Not-Disturb feature is integrated with the presence settings in Lync.</span></span>

<span data-ttu-id="39cc3-121">通过 Exchange 统一消息（UM），Lync 和 Lync 服务器集成到 Microsoft Exchange Server 2013 和 Microsoft Outlook 2013。</span><span class="sxs-lookup"><span data-stu-id="39cc3-121">With Exchange Unified Messaging (UM), Lync and Lync Server integrate with Microsoft Exchange Server 2013 and Microsoft Outlook 2013.</span></span> <span data-ttu-id="39cc3-122">用户可以在其 Lync 窗口和电子邮件中查看是否有新的语音邮件。</span><span class="sxs-lookup"><span data-stu-id="39cc3-122">Users can see if they have new voice mail both in their Lync window and in email.</span></span> <span data-ttu-id="39cc3-123">在电子邮件中，他们可以单击以在电子邮件中播放语音邮件音频，或查看语音邮件的记录。</span><span class="sxs-lookup"><span data-stu-id="39cc3-123">While in email they can click to play the voice mail audio in an email message, or view a transcript of the voice mail message.</span></span>

</div>

<div>

## <a name="advanced-calling-features"></a><span data-ttu-id="39cc3-124">高级通话功能</span><span class="sxs-lookup"><span data-stu-id="39cc3-124">Advanced Calling Features</span></span>

<span data-ttu-id="39cc3-125">企业语音还包括多项高级通话功能，如 Lync 呼叫委派、团队呼叫、组呼叫分拣和响应组。</span><span class="sxs-lookup"><span data-stu-id="39cc3-125">Enterprise Voice includes several advanced calling features as well, such as Lync call delegation, team calling, Group Call Pickup, and Response Groups.</span></span>

<span data-ttu-id="39cc3-126">Lync 呼叫委派使用户可以通过 "**工具** \> **选项** \> **呼叫转接设置**" 将呼叫处理委派给一个或多个助理。</span><span class="sxs-lookup"><span data-stu-id="39cc3-126">Lync call delegation enables users to delegate call handling to one or more assistants, by going to **Tools** \> **Options** \> **Call Forwarding Settings**.</span></span> <span data-ttu-id="39cc3-127">代理人可以代表用户执行多个呼叫任务，包括筛选呼叫、拨打电话和发起会议。</span><span class="sxs-lookup"><span data-stu-id="39cc3-127">The delegate can perform multiple calling tasks on behalf of the user, including screening calls, placing calls, and initiating conferences.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="39cc3-128">您可能正在寻找另一个名称类似的功能，即 Lync 日历委派。</span><span class="sxs-lookup"><span data-stu-id="39cc3-128">You may be looking for another similarly named feature, Lync calendar delegation.</span></span> <span data-ttu-id="39cc3-129">它不需要企业语音功能，并且允许用户从 Outlook 安排联机 Lync 会议。</span><span class="sxs-lookup"><span data-stu-id="39cc3-129">It doesn't require the Enterprise Voice feature and does allow users to schedule online Lync meetings from Outlook.</span></span> <span data-ttu-id="39cc3-130">如果你在此处查找此信息，我们建议签出<A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-set-csclientpolicy</A>以了解有关启用 Exchange 委派同步的信息。</span><span class="sxs-lookup"><span data-stu-id="39cc3-130">If you've come here looking for that info, we recommend checking out <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A> for information on enabling Exchange delegate sync.</span></span>



</div>

<span data-ttu-id="39cc3-131">团队通话使用户可以让传入呼叫同时拨打团队成员的电话，以便团队中的任何人都可以接听呼叫。</span><span class="sxs-lookup"><span data-stu-id="39cc3-131">Team calling enables a user to have incoming calls simultaneously ring the phones of teammates so that anyone on the team can answer the call.</span></span>

<span data-ttu-id="39cc3-132">组呼叫分拣，Lync Server 2013 的累积更新中的新功能：2月2013，允许用户通过其自己的电话应答传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="39cc3-132">Group Call Pickup, a new feature in Cumulative Updates for Lync Server 2013: February 2013, lets users answer incoming calls to their colleagues from their own phones.</span></span> <span data-ttu-id="39cc3-133">组呼叫挑选与团队通话的不同之处在于：传入呼叫仅在预期收件人的电话上响铃，但任何其他用户都可以通过拨打呼叫装货组号码选择接听电话。</span><span class="sxs-lookup"><span data-stu-id="39cc3-133">Group Call Pickup differs from team calling primarily in that an incoming call rings only at the intended recipient's phone, but any other user can choose to answer it by dialing a call pickup group number.</span></span>

<span data-ttu-id="39cc3-134">可以设置响应组，以便对指定的代理进行排队和智能地路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="39cc3-134">Response Groups can be set up for queuing and intelligently routing calls to designated agents.</span></span> <span data-ttu-id="39cc3-135">常见用途包括 IT 人员服务中心、人力资源 hotlines 和其他内部联系中心。</span><span class="sxs-lookup"><span data-stu-id="39cc3-135">Common uses include IT helpdesks, human resources hotlines, and other internal contact centers.</span></span>

</div>

<div>

## <a name="enterprise-voice-administration"></a><span data-ttu-id="39cc3-136">企业语音管理</span><span class="sxs-lookup"><span data-stu-id="39cc3-136">Enterprise Voice Administration</span></span>

<span data-ttu-id="39cc3-137">Lync 服务器使用标准和已发布接口与现有基础结构进行互操作。</span><span class="sxs-lookup"><span data-stu-id="39cc3-137">Lync Server uses standards and published interfaces to interoperate with existing infrastructure.</span></span> <span data-ttu-id="39cc3-138">它支持网关和 SIP 选项（如 SIP 中继），用于与 IP PBX 系统和 PSTN 网络的互连，以便你可以在一段时间内将用户迁移到企业语音，同时最大限度地减少中断。</span><span class="sxs-lookup"><span data-stu-id="39cc3-138">It supports both gateway and SIP options (such as SIP trunking) for interconnection to IP PBX systems and the PSTN networks, so that you can migrate users to Enterprise Voice over time, while minimizing disruption.</span></span> <span data-ttu-id="39cc3-139">Lync Server 支持传统的编解码器，如711、722和723.1，以实现与传统 VoIP 解决方案的互操作性。</span><span class="sxs-lookup"><span data-stu-id="39cc3-139">Lync Server supports traditional codecs such as G.711, G.722, and G.723.1 for interoperability with traditional VoIP solutions.</span></span>

<span data-ttu-id="39cc3-140">使用呼叫许可控制（CAC），管理员可以对受约束的网络链接上的 Lync Server 语音和视频流量进行限制，并指定当新呼叫超过限制时要执行的操作。</span><span class="sxs-lookup"><span data-stu-id="39cc3-140">With call admission control (CAC), administrators can set limits on the amount of Lync Server voice and video traffic carried on constrained network links, and specify the action to be taken if a new call would exceed the limit.</span></span> <span data-ttu-id="39cc3-141">操作可能包括通过备用路径路由，或者拒绝呼叫。</span><span class="sxs-lookup"><span data-stu-id="39cc3-141">The actions could include routing by an alternate path, or refusing the call.</span></span>

<span data-ttu-id="39cc3-142">Lync Server 与第三方 Survivable 分支装置配合使用，以便在分支机构中提供本地呼叫服务和连接到 PSTN，以防 WAN 在中心站点出现故障。</span><span class="sxs-lookup"><span data-stu-id="39cc3-142">Lync Server works with third-party Survivable Branch Appliances to provide local calling services and connection to PSTN at branch offices, in case of WAN failure at the central site.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

