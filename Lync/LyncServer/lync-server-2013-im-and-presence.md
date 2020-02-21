---
title: Lync Server 2013 IM 和状态
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IM and presence
ms:assetid: 6a93ae95-3b64-410b-ab72-74dea232f065
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417162(v=OCS.15)
ms:contentKeyID: 48184398
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 25fceca5dfb3b308d7f9d545268c258c3e32609c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199735"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="im-and-presence-in-lync-server-2013"></a><span data-ttu-id="194cd-102">Lync Server 2013 中的 IM 和状态</span><span class="sxs-lookup"><span data-stu-id="194cd-102">IM and presence in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="194cd-103">_**上次修改的主题：** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="194cd-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="194cd-104">即时消息（IM）和状态自动安装在任何 Lync Server 部署中。</span><span class="sxs-lookup"><span data-stu-id="194cd-104">Instant messaging (IM) and presence are automatically installed in any Lync Server deployment.</span></span>

<span data-ttu-id="194cd-105">通过*状态* 信息，用户可以在适当的时间使用适当的交流方式与同事沟通，从而形成更高效的工作环境。</span><span class="sxs-lookup"><span data-stu-id="194cd-105">*Presence* information enables users to approach colleagues at the right time with the right form of communication, to lead to a more productive work environment.</span></span> <span data-ttu-id="194cd-106">用户的状态是包含忙闲状态、通信意愿、其他注释（如位置和状态）和用户联系方式在内的信息集合。</span><span class="sxs-lookup"><span data-stu-id="194cd-106">A user’s presence is a collection of information that includes availability, willingness to communicate, additional notes (such as location and status), and how the user can be contacted.</span></span> <span data-ttu-id="194cd-107">在 Lync Server 中，状态为增强，其中包含图片、位置信息和丰富的状态集状态，包括 "已关闭工作"、"请勿打扰" 和 "回退" 等基本状态（如 "可用"、"忙" 和 "在会议中"）。</span><span class="sxs-lookup"><span data-stu-id="194cd-107">Presence is enhanced in Lync Server with pictures, location information, and a rich set of presence states that includes “Off Work,” “Do Not Disturb,” and “Be Right Back,” in addition to basic states such as “Available,” “Busy,” and “In a Conference.”</span></span> <span data-ttu-id="194cd-108">管理员还可以定义自定义的特定于组织的状态。</span><span class="sxs-lookup"><span data-stu-id="194cd-108">Administrators can also define customized, organization-specific presence states.</span></span>

<span data-ttu-id="194cd-p102">联系人管理和用户访问选项使用户能够控制其他人可以查看的信息。用户可以设置各种联系人级别，每个联系人级别可以查看不同级别的状态信息。</span><span class="sxs-lookup"><span data-stu-id="194cd-p102">Contact management and user access options enable users to control what information others can see. Users can set different levels of contacts, each of which can view different levels of presence information.</span></span>

<span data-ttu-id="194cd-p103">只需查看联系人列表，用户就可以快速找到需要了解的所有内容。简单的带颜色图标可指示其他用户的状态，还会显示图片和位置。</span><span class="sxs-lookup"><span data-stu-id="194cd-p103">By simply looking at a Contacts list, users can find everything they need to know at a glance. Simple colored icons indicate other users’ presence status, and picture and location are also shown.</span></span>

<span data-ttu-id="194cd-113">随着 Lync Server 和其他产品（如 Outlook 和 SharePoint）之间的集成，只要出现联系人的名称（如电子邮件或团队网站），也会显示状态和联系人信息。</span><span class="sxs-lookup"><span data-stu-id="194cd-113">With the integration between Lync Server and other products such as Outlook and SharePoint, whenever a contact’s name appears, such as in an email message or on a team website, the status and contact information is also displayed.</span></span> <span data-ttu-id="194cd-114">此外，如果部署 Exchange 2013，Lync Server 和 Exchange 2013 可以共享统一的联系人存储库，这两个产品的客户端都可以访问它。</span><span class="sxs-lookup"><span data-stu-id="194cd-114">Additionally, if you deploy Exchange 2013, Lync Server and Exchange 2013 can share a unified contact store, which can be accessed by clients of either product.</span></span>

<span data-ttu-id="194cd-115">在 Lync Server 中使用即时消息，用户可以使用及时的信息快速消息。</span><span class="sxs-lookup"><span data-stu-id="194cd-115">With instant messaging in Lync Server, users can quickly message each other with timely information.</span></span> <span data-ttu-id="194cd-116">如果你愿意，你的用户也可以与公共 IM 网络（如 MSN/Windows Live、Yahoo\!和 AOL）的用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="194cd-116">If you prefer, your users can also communicate with users of public IM networks such as MSN/Windows Live, Yahoo\!, and AOL.</span></span> <span data-ttu-id="194cd-117">请注意，与 Windows Live、AOL 和 Yahoo 的公共 IM 连接可能需要单独的许可证\!</span><span class="sxs-lookup"><span data-stu-id="194cd-117">Note that a separate license might be required for public IM connectivity with Windows Live, AOL, and Yahoo\!</span></span> <span data-ttu-id="194cd-118">Lync Server 还包括可扩展消息和状态协议（XMPP）兼容性，因此您的用户可以与 Google 谈话等 XMPP 服务用户交换 IM 消息和状态信息。</span><span class="sxs-lookup"><span data-stu-id="194cd-118">Lync Server also includes Extensible Messaging and Presence Protocol (XMPP) compatibility, so your users can exchange IM messages and presence information with users of XMPP services such as Google Talk.</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="194cd-119">从2012年9月1日起，Microsoft Lync 公共 IM 连接用户订阅许可证（"PIC USL"）不再可用于购买新的或更新的协议。</span><span class="sxs-lookup"><span data-stu-id="194cd-119">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="194cd-120">拥有主动许可证的客户将能够继续与 Yahoo！联合联合</span><span class="sxs-lookup"><span data-stu-id="194cd-120">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="194cd-121">信使，直到服务关闭日期。</span><span class="sxs-lookup"><span data-stu-id="194cd-121">Messenger until the service shut down date.</span></span> <span data-ttu-id="194cd-122">AOL 和 Yahoo！的生命周期结束日期为2014年6月</span><span class="sxs-lookup"><span data-stu-id="194cd-122">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="194cd-123">已宣布。</span><span class="sxs-lookup"><span data-stu-id="194cd-123">has been announced.</span></span> <span data-ttu-id="194cd-124">有关详细信息，请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的支持公用即时信使连接</A>。</span><span class="sxs-lookup"><span data-stu-id="194cd-124">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="194cd-125">PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo！联合所需的每个用户每月订阅许可证。</span><span class="sxs-lookup"><span data-stu-id="194cd-125">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="194cd-126">Messenger.</span><span class="sxs-lookup"><span data-stu-id="194cd-126">Messenger.</span></span> <span data-ttu-id="194cd-127">Microsoft 提供此服务的能力因 Yahoo！中的支持而受到了支持，其下凸的底层协议。</span><span class="sxs-lookup"><span data-stu-id="194cd-127">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="194cd-128">Lync 是前所未有的强大工具，用于跨组织和世界各地的个人进行连接。</span><span class="sxs-lookup"><span data-stu-id="194cd-128">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="194cd-129">与 Windows Live Messenger 的联盟不需要除 Lync Standard CAL 之外的其他用户/设备许可证。</span><span class="sxs-lookup"><span data-stu-id="194cd-129">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="194cd-130">Skype 联合身份验证将添加到此列表中，使 Lync 用户可以使用即时消息和语音访问成百上千人。</span><span class="sxs-lookup"><span data-stu-id="194cd-130">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="194cd-131">用户可以使用对话历史记录跟踪以前的 IM 对话，并检索可能在几个月前通过 IM 进行的通信信息。</span><span class="sxs-lookup"><span data-stu-id="194cd-131">Conversation history enables users to keep track of old IM conversations, and retrieve information that may have been communicated by IM months ago.</span></span>

<span data-ttu-id="194cd-132">持久聊天功能使用户能够参与在一段时间内保持的基于主题的多个会话。</span><span class="sxs-lookup"><span data-stu-id="194cd-132">The Persistent Chat feature enables users to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="194cd-133">张贴到聊天室（论坛）的消息可以持久保存（即长时间可供访问），以使来自不同地点和部门的人员即使在并不全部同时在线的情况下也能加入聊天室。</span><span class="sxs-lookup"><span data-stu-id="194cd-133">Messages posted to chat rooms (discussion forums) can be persistent (that is, available over time), so that people from different locations and departments can participate, even when they are not all online at the same time.</span></span>

<span data-ttu-id="194cd-134">如果组织必须遵守合规性要求，则可以部署消息存档功能以存档组织中所有用户或仅某些指定用户的即时消息内容。</span><span class="sxs-lookup"><span data-stu-id="194cd-134">If your organization must follow compliance regulations, you can deploy a message archiving feature to archive the content of instant messages for all users in your organization, or for only certain users you specify.</span></span> <span data-ttu-id="194cd-135">如果还部署 Exchange 2013，您的 IM 存档可以与 Exchange 的就地保留功能集成，以便为您的符合性提供单一的管理体验。</span><span class="sxs-lookup"><span data-stu-id="194cd-135">If you also deploy Exchange 2013, your IM archive can be integrated with the In-Place Hold feature of Exchange, to provide a single administration experience for your compliance.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

