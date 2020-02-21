---
title: Lync Server 2013：公共即时消息支持
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Public instant messaging support
ms:assetid: 1f45163b-52c6-4a78-b9c8-dfe3abe4e5eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204732(v=OCS.15)
ms:contentKeyID: 48183582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f996e8f15707a0c676ea77a6ffaeb5e6943ac48c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183495"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="public-instant-messaging-support-in-lync-server-2013"></a><span data-ttu-id="503f2-102">Lync Server 2013 中的公共即时消息支持</span><span class="sxs-lookup"><span data-stu-id="503f2-102">Public instant messaging support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="503f2-103">_**上次修改的主题：** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="503f2-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="503f2-104">Lync Server 2013 支持使用许可的公共即时消息（IM）连接提供程序，以及使用可扩展消息和状态协议（XMPP）来实现一种特殊类型的联合，以使 Lync Server 能够访问配置的 XMPP使用 Lync 2013 客户端的域合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="503f2-104">Lync Server 2013 supports the use of licensed public instant messaging (IM) connectivity providers, as well as the use of eXtensible Messaging and Presence Protocol (XMPP) to implement a special type of federation that enables a Lync Server to access configured XMPP domain partners by using the Lync 2013 client.</span></span>

<div>

## <a name="public-im-connectivity-provider-support"></a><span data-ttu-id="503f2-105">公共 IM 连接提供程序支持</span><span class="sxs-lookup"><span data-stu-id="503f2-105">Public IM Connectivity Provider Support</span></span>

<span data-ttu-id="503f2-106">当前支持的公共即时消息连接合作伙伴包括：</span><span class="sxs-lookup"><span data-stu-id="503f2-106">The currently supported public instant messaging connectivity partners are:</span></span>

  - <span data-ttu-id="503f2-107">America Online</span><span class="sxs-lookup"><span data-stu-id="503f2-107">America Online</span></span>

  - <span data-ttu-id="503f2-108">Windows Live</span><span class="sxs-lookup"><span data-stu-id="503f2-108">Windows Live</span></span>

  - <span data-ttu-id="503f2-109">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="503f2-109">Yahoo\!</span></span>

<span data-ttu-id="503f2-110">对于与 Windows Live 用户的通信，Lync Server 2013 支持对等 IM 和音频和视频呼叫。</span><span class="sxs-lookup"><span data-stu-id="503f2-110">For communications with Windows Live users, Lync Server 2013 supports peer-to-peer IM and audio and video calls.</span></span> <span data-ttu-id="503f2-111">对于与 AOL 和 Yahoo\!的通信，Lync Server 2013 支持对等 IM。</span><span class="sxs-lookup"><span data-stu-id="503f2-111">For communications with AOL and Yahoo\!, Lync Server 2013 supports peer-to-peer IM.</span></span> <span data-ttu-id="503f2-112">可能需要单独的许可证。</span><span class="sxs-lookup"><span data-stu-id="503f2-112">A separate license may be required.</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="503f2-113">从2012年9月1日起，Microsoft Lync 公共 IM 连接用户订阅许可证（"PIC USL"）不再可用于购买新的或更新的协议。</span><span class="sxs-lookup"><span data-stu-id="503f2-113">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="503f2-114">拥有主动许可证的客户将能够继续与 Yahoo！联合联合</span><span class="sxs-lookup"><span data-stu-id="503f2-114">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="503f2-115">信使，直到服务关闭日期。</span><span class="sxs-lookup"><span data-stu-id="503f2-115">Messenger until the service shut down date.</span></span> <span data-ttu-id="503f2-116">AOL 和 Yahoo！的生命周期结束日期为2014年6月</span><span class="sxs-lookup"><span data-stu-id="503f2-116">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="503f2-117">已宣布。</span><span class="sxs-lookup"><span data-stu-id="503f2-117">has been announced.</span></span> <span data-ttu-id="503f2-118">有关详细信息，请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的支持公用即时信使连接</A>。</span><span class="sxs-lookup"><span data-stu-id="503f2-118">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="503f2-119">PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo！联合所需的每个用户每月订阅许可证。</span><span class="sxs-lookup"><span data-stu-id="503f2-119">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="503f2-120">Messenger.</span><span class="sxs-lookup"><span data-stu-id="503f2-120">Messenger.</span></span> <span data-ttu-id="503f2-121">Microsoft 提供此服务的能力因 Yahoo！中的支持而受到了支持，其下凸的底层协议。</span><span class="sxs-lookup"><span data-stu-id="503f2-121">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="503f2-122">Lync 是前所未有的强大工具，用于跨组织和世界各地的个人进行连接。</span><span class="sxs-lookup"><span data-stu-id="503f2-122">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="503f2-123">与 Windows Live Messenger 的联盟不需要除 Lync Standard CAL 之外的其他用户/设备许可证。</span><span class="sxs-lookup"><span data-stu-id="503f2-123">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="503f2-124">Skype 联合身份验证将添加到此列表中，使 Lync 用户可以使用即时消息和语音访问成百上千人。</span><span class="sxs-lookup"><span data-stu-id="503f2-124">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

</div>

<div>

## <a name="xmpp-federation-support"></a><span data-ttu-id="503f2-125">XMPP 联盟支持</span><span class="sxs-lookup"><span data-stu-id="503f2-125">XMPP Federation Support</span></span>

<span data-ttu-id="503f2-p105">XMPP 联盟支持 Lync 用户与使用公共提供程序（如 GTalk）的已配置 XMPP 域用户进行通信。与这些用户的通信包括：</span><span class="sxs-lookup"><span data-stu-id="503f2-p105">XMPP federation supports Lync users communication with configured XMPP domain users who use a public provider, such as GTalk. Communications with these users can include the following:</span></span>

  - <span data-ttu-id="503f2-128">对等 IM 和状态</span><span class="sxs-lookup"><span data-stu-id="503f2-128">Peer-to-peer IM and presence</span></span>

  - <span data-ttu-id="503f2-129">在 Lync 客户端创建 XMPP 联盟联系人</span><span class="sxs-lookup"><span data-stu-id="503f2-129">Creation of XMPP federated contacts in the Lync client</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

