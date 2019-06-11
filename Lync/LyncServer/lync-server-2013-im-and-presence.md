---
title: Lync Server 2013 IM 和状态
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IM and presence
ms:assetid: 6a93ae95-3b64-410b-ab72-74dea232f065
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417162(v=OCS.15)
ms:contentKeyID: 48184398
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18eb3d4a7fa5daaa59817d2eefde7af3a8e3f494
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830037"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="im-and-presence-in-lync-server-2013"></a><span data-ttu-id="abd01-102">Lync Server 2013 中的 IM 和状态</span><span class="sxs-lookup"><span data-stu-id="abd01-102">IM and presence in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="abd01-103">_**主题上次修改时间:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="abd01-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="abd01-104">即时消息 (IM) 和联机状态会自动安装在任何 Lync Server 部署中。</span><span class="sxs-lookup"><span data-stu-id="abd01-104">Instant messaging (IM) and presence are automatically installed in any Lync Server deployment.</span></span>

<span data-ttu-id="abd01-105">*联机状态*信息使用户能够使用适当的通信形式在适当的时间处理同事, 以获得更高效的工作环境。</span><span class="sxs-lookup"><span data-stu-id="abd01-105">*Presence* information enables users to approach colleagues at the right time with the right form of communication, to lead to a more productive work environment.</span></span> <span data-ttu-id="abd01-106">用户的状态是信息的集合, 其中包括可用性、通信意愿、其他笔记 (如位置和状态), 以及如何联系用户。</span><span class="sxs-lookup"><span data-stu-id="abd01-106">A user’s presence is a collection of information that includes availability, willingness to communicate, additional notes (such as location and status), and how the user can be contacted.</span></span> <span data-ttu-id="abd01-107">在 Lync Server 中, "联机状态" 已增强, 包含图片、位置信息和一组丰富的状态, 包括 "已关闭工作"、"请勿打扰" 和 "回退", 除了基本状态, 如 "可用"、"忙碌" 和 "正在开会"。</span><span class="sxs-lookup"><span data-stu-id="abd01-107">Presence is enhanced in Lync Server with pictures, location information, and a rich set of presence states that includes “Off Work,” “Do Not Disturb,” and “Be Right Back,” in addition to basic states such as “Available,” “Busy,” and “In a Conference.”</span></span> <span data-ttu-id="abd01-108">管理员还可以定义自定义的特定于组织的状态。</span><span class="sxs-lookup"><span data-stu-id="abd01-108">Administrators can also define customized, organization-specific presence states.</span></span>

<span data-ttu-id="abd01-109">联系人管理和用户访问选项使用户能够控制其他人可以查看哪些信息。</span><span class="sxs-lookup"><span data-stu-id="abd01-109">Contact management and user access options enable users to control what information others can see.</span></span> <span data-ttu-id="abd01-110">用户可以设置不同级别的联系人, 每个级别的联系人都可以查看不同级别的状态信息。</span><span class="sxs-lookup"><span data-stu-id="abd01-110">Users can set different levels of contacts, each of which can view different levels of presence information.</span></span>

<span data-ttu-id="abd01-111">只需查看联系人列表, 用户即可找到他们需要了解的所有内容。</span><span class="sxs-lookup"><span data-stu-id="abd01-111">By simply looking at a Contacts list, users can find everything they need to know at a glance.</span></span> <span data-ttu-id="abd01-112">简单的彩色图标表示其他用户的状态, 还会显示图片和位置。</span><span class="sxs-lookup"><span data-stu-id="abd01-112">Simple colored icons indicate other users’ presence status, and picture and location are also shown.</span></span>

<span data-ttu-id="abd01-113">随着 Lync 服务器和其他产品 (如 Outlook 和 SharePoint) 之间的集成, 每当出现联系人的姓名时 (例如在电子邮件中或在团队网站上), 也会显示状态和联系人信息。</span><span class="sxs-lookup"><span data-stu-id="abd01-113">With the integration between Lync Server and other products such as Outlook and SharePoint, whenever a contact’s name appears, such as in an email message or on a team website, the status and contact information is also displayed.</span></span> <span data-ttu-id="abd01-114">此外, 如果你部署 Exchange 2013, Lync Server 和 Exchange 2013 可以共享一个统一的联系人存储, 这些存储可由任意一种产品的客户端访问。</span><span class="sxs-lookup"><span data-stu-id="abd01-114">Additionally, if you deploy Exchange 2013, Lync Server and Exchange 2013 can share a unified contact store, which can be accessed by clients of either product.</span></span>

<span data-ttu-id="abd01-115">通过在 Lync Server 中发送即时消息, 用户可以通过及时的信息快速处理彼此的消息。</span><span class="sxs-lookup"><span data-stu-id="abd01-115">With instant messaging in Lync Server, users can quickly message each other with timely information.</span></span> <span data-ttu-id="abd01-116">如果您愿意, 您的用户也可以与公共 IM 网络 (如 MSN/Windows Live、Yahoo\!和 AOL) 的用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="abd01-116">If you prefer, your users can also communicate with users of public IM networks such as MSN/Windows Live, Yahoo\!, and AOL.</span></span> <span data-ttu-id="abd01-117">请注意, 对于使用 Windows Live、AOL 和 Yahoo 的公共 IM 连接, 可能需要单独的许可证\!</span><span class="sxs-lookup"><span data-stu-id="abd01-117">Note that a separate license might be required for public IM connectivity with Windows Live, AOL, and Yahoo\!</span></span> <span data-ttu-id="abd01-118">Lync 服务器还包括可扩展消息和状态协议 (XMPP) 兼容性, 以便你的用户可以与 Google 通话等 XMPP 服务用户交换 IM 消息和状态信息。</span><span class="sxs-lookup"><span data-stu-id="abd01-118">Lync Server also includes Extensible Messaging and Presence Protocol (XMPP) compatibility, so your users can exchange IM messages and presence information with users of XMPP services such as Google Talk.</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="abd01-119">从2012年9月1日起, Microsoft Lync 公共 IM 连接用户订阅许可证 ("PIC USL") 不再可用于购买新的或续订协议。</span><span class="sxs-lookup"><span data-stu-id="abd01-119">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="abd01-120">具有活动许可证的客户将能够继续与 Yahoo! 进行联盟</span><span class="sxs-lookup"><span data-stu-id="abd01-120">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="abd01-121">Messenger, 直到服务关闭日期。</span><span class="sxs-lookup"><span data-stu-id="abd01-121">Messenger until the service shut down date.</span></span> <span data-ttu-id="abd01-122">AOL 和 Yahoo! 的有效期结束日期为2014年6月</span><span class="sxs-lookup"><span data-stu-id="abd01-122">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="abd01-123">已宣布。</span><span class="sxs-lookup"><span data-stu-id="abd01-123">has been announced.</span></span> <span data-ttu-id="abd01-124">有关详细信息, 请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公共即时消息连接支持</A>。</span><span class="sxs-lookup"><span data-stu-id="abd01-124">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="abd01-125">PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo! 联合所需的每个每个用户每月订阅许可证。</span><span class="sxs-lookup"><span data-stu-id="abd01-125">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="abd01-126">Messenger.</span><span class="sxs-lookup"><span data-stu-id="abd01-126">Messenger.</span></span> <span data-ttu-id="abd01-127">Microsoft 提供此服务的能力已作为对 Yahoo! 的支持, 它的底层协议被向下缠绕。</span><span class="sxs-lookup"><span data-stu-id="abd01-127">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="abd01-128">Lync 比以往更多, 是一种强大的工具, 用于跨组织和全球各地的人员进行连接。</span><span class="sxs-lookup"><span data-stu-id="abd01-128">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="abd01-129">与 Windows Live Messenger 的联盟不需要除 Lync 标准 CAL 之外的其他用户/设备许可证。</span><span class="sxs-lookup"><span data-stu-id="abd01-129">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="abd01-130">Skype 联盟将添加到此列表, 使 Lync 用户可以通过 IM 和语音与成百上千人联系。</span><span class="sxs-lookup"><span data-stu-id="abd01-130">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="abd01-131">"对话历史记录" 使用户能够跟踪旧的 IM 对话, 并检索可能已由 IM 月前通信的信息。</span><span class="sxs-lookup"><span data-stu-id="abd01-131">Conversation history enables users to keep track of old IM conversations, and retrieve information that may have been communicated by IM months ago.</span></span>

<span data-ttu-id="abd01-132">持久聊天功能使用户能够参与在一段时间内保持的基于主题的多方聊天。</span><span class="sxs-lookup"><span data-stu-id="abd01-132">The Persistent Chat feature enables users to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="abd01-133">发布到聊天室 (讨论论坛) 的邮件可能是永久性的 (即, 随着时间的推移而推出), 因此来自不同地点和部门的人员可以参与, 即使他们不在同一时间进行联机也是如此。</span><span class="sxs-lookup"><span data-stu-id="abd01-133">Messages posted to chat rooms (discussion forums) can be persistent (that is, available over time), so that people from different locations and departments can participate, even when they are not all online at the same time.</span></span>

<span data-ttu-id="abd01-134">如果你的组织必须遵循合规性规定, 你可以部署邮件存档功能以存档你组织中的所有用户的即时消息的内容, 或仅针对你指定的特定用户存档即时消息的内容。</span><span class="sxs-lookup"><span data-stu-id="abd01-134">If your organization must follow compliance regulations, you can deploy a message archiving feature to archive the content of instant messages for all users in your organization, or for only certain users you specify.</span></span> <span data-ttu-id="abd01-135">如果你还部署 Exchange 2013, 你的 IM 存档可以与 Exchange 的就地保留功能集成, 以便为你的符合性提供单一的管理体验。</span><span class="sxs-lookup"><span data-stu-id="abd01-135">If you also deploy Exchange 2013, your IM archive can be integrated with the In-Place Hold feature of Exchange, to provide a single administration experience for your compliance.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

