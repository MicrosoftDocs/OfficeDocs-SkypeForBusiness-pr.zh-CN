---
title: Lync Server 2013：定义前端服务器、即时消息和状态的要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your requirements for Front End Servers, instant messaging, and presence
ms:assetid: c21198bc-520c-4d17-8b84-7ff1475b9b0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412956(v=OCS.15)
ms:contentKeyID: 48185319
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 176b73f6d82c03e3bcdb0f2b0066752cd68f307c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830688"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a><span data-ttu-id="37f7c-102">在 Lync Server 2013 中定义前端服务器、即时消息和状态的要求</span><span class="sxs-lookup"><span data-stu-id="37f7c-102">Defining your requirements for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37f7c-103">_**主题上次修改时间:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="37f7c-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="37f7c-104">规划即时消息 (IM) 和状态的主要任务是确保您有足够的前端服务器供用户使用。</span><span class="sxs-lookup"><span data-stu-id="37f7c-104">The main task of planning for instant messaging (IM) and presence is ensuring that you have enough Front End Servers for your users.</span></span>

<div>

## <a name="enabling-communication-with-external-users"></a><span data-ttu-id="37f7c-105">启用与外部用户的通信</span><span class="sxs-lookup"><span data-stu-id="37f7c-105">Enabling Communication with External Users</span></span>

<span data-ttu-id="37f7c-106">通过使你的用户能够与外部用户进行通信, 你可以在 Lync Server 中大大增加投资的优势。</span><span class="sxs-lookup"><span data-stu-id="37f7c-106">You can greatly increase the benefits of your investment in Lync Server by enabling your users to communicate with external users.</span></span> <span data-ttu-id="37f7c-107">外部用户可能包括：</span><span class="sxs-lookup"><span data-stu-id="37f7c-107">External users can include:</span></span>

  - <span data-ttu-id="37f7c-108">\*\*\*\*   当您的组织的用户在您的防火墙外工作且正在使用其笔记本或其他 Lync Server 设备时, 您的组织自己的用户的远程用户。</span><span class="sxs-lookup"><span data-stu-id="37f7c-108">**Remote users**   Your organization’s own users, when they are working outside your firewalls and are using their laptops or other Lync Server devices.</span></span>

  - <span data-ttu-id="37f7c-109">**联盟用户**   来自公司的用户, 您可以使用该用户同时运行 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="37f7c-109">**Federated users**   Users from companies you work with who also run Lync Server.</span></span> <span data-ttu-id="37f7c-110">要使用户轻松与这些用户联系，应与这些公司建立联盟关系。</span><span class="sxs-lookup"><span data-stu-id="37f7c-110">To enable your users to easily contact these users, you create federated relationships with these companies.</span></span>

  - <span data-ttu-id="37f7c-111">\*\*\*\*   公共 IM 服务的公共用户用户, 例如由 Internet 服务、Yahoo\!和 AOL 的 Windows Live 网络提供的 IM 服务, 以及使用可扩展消息和状态协议 (XMPP) 的提供商和服务器的用户, 如Google 通话。</span><span class="sxs-lookup"><span data-stu-id="37f7c-111">**Public users**   Users of public IM services, such as IM services provided by the Windows Live network of Internet services, Yahoo\!, and AOL, and users of providers and servers that use Extensible Messaging and Presence Protocol (XMPP), such as Google Talk.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="37f7c-112">请注意, 对于使用 Windows Live、AOL 和 Yahoo! 的公共 IM 连接, 可能需要单独的许可证</span><span class="sxs-lookup"><span data-stu-id="37f7c-112">Note that a separate license might be required for public IM connectivity with Windows Live, AOL, and Yahoo!</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="37f7c-113">从2012年9月1日起, Microsoft Lync 公共 IM 连接用户订阅许可证 ("PIC USL") 不再可用于购买新的或续订协议。</span><span class="sxs-lookup"><span data-stu-id="37f7c-113">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="37f7c-114">具有活动许可证的客户将能够继续与 Yahoo! 进行联盟</span><span class="sxs-lookup"><span data-stu-id="37f7c-114">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="37f7c-115">Messenger, 直到服务关闭日期。</span><span class="sxs-lookup"><span data-stu-id="37f7c-115">Messenger until the service shut down date.</span></span> <span data-ttu-id="37f7c-116">AOL 和 Yahoo! 的有效期结束日期为2014年6月</span><span class="sxs-lookup"><span data-stu-id="37f7c-116">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="37f7c-117">已宣布。</span><span class="sxs-lookup"><span data-stu-id="37f7c-117">has been announced.</span></span> <span data-ttu-id="37f7c-118">有关详细信息, 请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公共即时消息连接支持</A>。</span><span class="sxs-lookup"><span data-stu-id="37f7c-118">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="37f7c-119">PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo! 联合所需的每个每个用户每月订阅许可证。</span><span class="sxs-lookup"><span data-stu-id="37f7c-119">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="37f7c-120">Messenger.</span><span class="sxs-lookup"><span data-stu-id="37f7c-120">Messenger.</span></span> <span data-ttu-id="37f7c-121">Microsoft 提供此服务的能力已作为对 Yahoo! 的支持, 它的底层协议被向下缠绕。</span><span class="sxs-lookup"><span data-stu-id="37f7c-121">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="37f7c-122">Lync 比以往更多, 是一种强大的工具, 用于跨组织和全球各地的人员进行连接。</span><span class="sxs-lookup"><span data-stu-id="37f7c-122">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="37f7c-123">与 Windows Live Messenger 的联盟不需要除 Lync 标准 CAL 之外的其他用户/设备许可证。</span><span class="sxs-lookup"><span data-stu-id="37f7c-123">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="37f7c-124">Skype 联盟将添加到此列表, 使 Lync 用户可以通过 IM 和语音与成百上千人联系。</span><span class="sxs-lookup"><span data-stu-id="37f7c-124">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

    
    </div>

<span data-ttu-id="37f7c-125">若要启用任何或所有这些方案, 你需要部署边缘服务器以帮助在 Lync Server 部署和外部用户之间实现安全通信。</span><span class="sxs-lookup"><span data-stu-id="37f7c-125">To enable any or all of these scenarios, you need to deploy an Edge Server to help enable secure communications between your Lync Server deployment and external users.</span></span> <span data-ttu-id="37f7c-126">组织的远程用户和联盟组织的用户将能够查看彼此的状态并使用 IM 进行通信。</span><span class="sxs-lookup"><span data-stu-id="37f7c-126">Your organization’s remote users and users at federated organizations will be able to see each other’s presence and communicate using IM.</span></span> <span data-ttu-id="37f7c-127">有关启用与外部用户的通信的详细信息, 请参阅规划文档中的[在 Lync Server 2013 中规划外部用户访问](lync-server-2013-planning-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="37f7c-127">For details about enabling communication with external users, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="archiving-im-content"></a><span data-ttu-id="37f7c-128">将 IM 内容存档</span><span class="sxs-lookup"><span data-stu-id="37f7c-128">Archiving IM Content</span></span>

<span data-ttu-id="37f7c-129">如果您的组织必须遵守合规性规定, 则 Lync Server 提供您可以使用的功能。</span><span class="sxs-lookup"><span data-stu-id="37f7c-129">Lync Server provides features you can use if your organization must follow compliance regulations.</span></span> <span data-ttu-id="37f7c-130">你可以使用存档功能为组织中的所有用户或仅为你指定的特定用户存档 IM 消息的内容。</span><span class="sxs-lookup"><span data-stu-id="37f7c-130">You can use Archiving to archive the content of IM messages for all users in your organization or for only certain users that you specify.</span></span> <span data-ttu-id="37f7c-131">有关详细信息, 请参阅规划文档中的[在 Lync Server 2013 中规划存档](lync-server-2013-planning-for-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="37f7c-131">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span>

<span data-ttu-id="37f7c-132">如果你还部署了 Microsoft Exchange Server 2013, 你可以将 Exchange 数据的存档与 Lync Server 数据的存档进行集成, 并使用单个工具搜索两种类型的已存档数据。</span><span class="sxs-lookup"><span data-stu-id="37f7c-132">If you also have Microsoft Exchange Server 2013 deployed, you can integrate the archiving of Exchange data with the archiving of Lync Server data, and use a single tool to search both types of archived data.</span></span> <span data-ttu-id="37f7c-133">有关详细信息, 请参阅[将 Microsoft Lync server 2013 配置为使用 Microsoft Exchange Server 2013 存档](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="37f7c-133">For more information, see [Configuring Microsoft Lync Server 2013 to use Microsoft Exchange Server 2013 archiving](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

