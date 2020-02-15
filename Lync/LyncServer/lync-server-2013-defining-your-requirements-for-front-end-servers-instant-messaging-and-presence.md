---
title: Lync Server 2013：定义前端服务器、即时消息和状态的要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for Front End Servers, instant messaging, and presence
ms:assetid: c21198bc-520c-4d17-8b84-7ff1475b9b0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412956(v=OCS.15)
ms:contentKeyID: 48185319
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82cce58ab401149871073f6bc49ed4c53f301cb7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42032088"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a><span data-ttu-id="143df-102">在 Lync Server 2013 中定义对前端服务器、即时消息和状态的要求</span><span class="sxs-lookup"><span data-stu-id="143df-102">Defining your requirements for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="143df-103">_**上次修改的主题：** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="143df-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="143df-104">规划即时消息 (IM) 和状态的主要任务是确保为用户准备足够的前端服务器。</span><span class="sxs-lookup"><span data-stu-id="143df-104">The main task of planning for instant messaging (IM) and presence is ensuring that you have enough Front End Servers for your users.</span></span>

<div>

## <a name="enabling-communication-with-external-users"></a><span data-ttu-id="143df-105">启用与外部用户的通信</span><span class="sxs-lookup"><span data-stu-id="143df-105">Enabling Communication with External Users</span></span>

<span data-ttu-id="143df-106">您可以通过使用户能够与外部用户进行通信，从而大大提高您的投资在 Lync Server 中的优势。</span><span class="sxs-lookup"><span data-stu-id="143df-106">You can greatly increase the benefits of your investment in Lync Server by enabling your users to communicate with external users.</span></span> <span data-ttu-id="143df-107">外部用户可能包括：</span><span class="sxs-lookup"><span data-stu-id="143df-107">External users can include:</span></span>

  - <span data-ttu-id="143df-108">\*\*\*\*   当您的组织的用户在防火墙外工作并使用其便携式计算机或其他 Lync Server 设备时，远程用户。</span><span class="sxs-lookup"><span data-stu-id="143df-108">**Remote users**   Your organization’s own users, when they are working outside your firewalls and are using their laptops or other Lync Server devices.</span></span>

  - <span data-ttu-id="143df-109">**联合用户**   来自公司的用户，你可以与其他人一起运行 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="143df-109">**Federated users**   Users from companies you work with who also run Lync Server.</span></span> <span data-ttu-id="143df-110">若要使您的用户能够轻松地与这些用户联系，您可以创建与这些公司的联盟关系。</span><span class="sxs-lookup"><span data-stu-id="143df-110">To enable your users to easily contact these users, you create federated relationships with these companies.</span></span>

  - <span data-ttu-id="143df-111">**公共用户**   ：公共 IM 服务的用户，例如 Internet 服务、Yahoo\!和 AOL 的 Windows Live 网络提供的 IM 服务、使用可扩展消息和服务器的提供程序和服务器（如 Google 谈话）的用户。</span><span class="sxs-lookup"><span data-stu-id="143df-111">**Public users**   Users of public IM services, such as IM services provided by the Windows Live network of Internet services, Yahoo\!, and AOL, and users of providers and servers that use Extensible Messaging and Presence Protocol (XMPP), such as Google Talk.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="143df-112">请注意，与 Windows Live、AOL 和 Yahoo! 的公共 IM 连接可能需要使用单独的许可证。</span><span class="sxs-lookup"><span data-stu-id="143df-112">Note that a separate license might be required for public IM connectivity with Windows Live, AOL, and Yahoo!</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="143df-113">从2012年9月1日起，Microsoft Lync 公共 IM 连接用户订阅许可证（"PIC USL"）不再可用于购买新的或更新的协议。</span><span class="sxs-lookup"><span data-stu-id="143df-113">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="143df-114">拥有主动许可证的客户将能够继续与 Yahoo！联合联合</span><span class="sxs-lookup"><span data-stu-id="143df-114">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="143df-115">信使，直到服务关闭日期。</span><span class="sxs-lookup"><span data-stu-id="143df-115">Messenger until the service shut down date.</span></span> <span data-ttu-id="143df-116">AOL 和 Yahoo！的生命周期结束日期为2014年6月</span><span class="sxs-lookup"><span data-stu-id="143df-116">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="143df-117">已宣布。</span><span class="sxs-lookup"><span data-stu-id="143df-117">has been announced.</span></span> <span data-ttu-id="143df-118">有关详细信息，请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的支持公用即时信使连接</A>。</span><span class="sxs-lookup"><span data-stu-id="143df-118">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="143df-119">PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo！联合所需的每个用户每月订阅许可证。</span><span class="sxs-lookup"><span data-stu-id="143df-119">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="143df-120">Messenger.</span><span class="sxs-lookup"><span data-stu-id="143df-120">Messenger.</span></span> <span data-ttu-id="143df-121">Microsoft 提供此服务的能力因 Yahoo！中的支持而受到了支持，其下凸的底层协议。</span><span class="sxs-lookup"><span data-stu-id="143df-121">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="143df-122">Lync 是前所未有的强大工具，用于跨组织和世界各地的个人进行连接。</span><span class="sxs-lookup"><span data-stu-id="143df-122">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="143df-123">与 Windows Live Messenger 的联盟不需要除 Lync Standard CAL 之外的其他用户/设备许可证。</span><span class="sxs-lookup"><span data-stu-id="143df-123">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="143df-124">Skype 联合身份验证将添加到此列表中，使 Lync 用户可以使用即时消息和语音访问成百上千人。</span><span class="sxs-lookup"><span data-stu-id="143df-124">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

    
    </div>

<span data-ttu-id="143df-125">若要启用任何或所有这些方案，需要部署边缘服务器以帮助启用 Lync Server 部署和外部用户之间的安全通信。</span><span class="sxs-lookup"><span data-stu-id="143df-125">To enable any or all of these scenarios, you need to deploy an Edge Server to help enable secure communications between your Lync Server deployment and external users.</span></span> <span data-ttu-id="143df-126">组织的远程用户和联盟组织的用户将能够查看彼此的状态并使用 IM 进行通信。</span><span class="sxs-lookup"><span data-stu-id="143df-126">Your organization’s remote users and users at federated organizations will be able to see each other’s presence and communicate using IM.</span></span> <span data-ttu-id="143df-127">有关启用与外部用户的通信的详细信息，请参阅规划文档中的在[Lync Server 2013 中规划外部用户访问](lync-server-2013-planning-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="143df-127">For details about enabling communication with external users, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="archiving-im-content"></a><span data-ttu-id="143df-128">存档 IM 内容</span><span class="sxs-lookup"><span data-stu-id="143df-128">Archiving IM Content</span></span>

<span data-ttu-id="143df-129">如果您的组织必须遵守合规性管理法规，Lync Server 提供了您可以使用的功能。</span><span class="sxs-lookup"><span data-stu-id="143df-129">Lync Server provides features you can use if your organization must follow compliance regulations.</span></span> <span data-ttu-id="143df-130">您可以使用存档为组织中的所有用户或仅为您指定的特定用户存档 IM 消息的内容。</span><span class="sxs-lookup"><span data-stu-id="143df-130">You can use Archiving to archive the content of IM messages for all users in your organization or for only certain users that you specify.</span></span> <span data-ttu-id="143df-131">有关详细信息，请参阅规划文档中的在[Lync Server 2013 中规划存档](lync-server-2013-planning-for-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="143df-131">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span>

<span data-ttu-id="143df-132">如果还部署了 Microsoft Exchange Server 2013，则可以将 Exchange 数据的存档与 Lync Server 数据的存档进行集成，并使用单个工具搜索两种类型的存档数据。</span><span class="sxs-lookup"><span data-stu-id="143df-132">If you also have Microsoft Exchange Server 2013 deployed, you can integrate the archiving of Exchange data with the archiving of Lync Server data, and use a single tool to search both types of archived data.</span></span> <span data-ttu-id="143df-133">有关详细信息，请参阅[配置 Microsoft Lync Server 2013 以使用 Microsoft Exchange Server 2013 存档](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="143df-133">For more information, see [Configuring Microsoft Lync Server 2013 to use Microsoft Exchange Server 2013 archiving](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

