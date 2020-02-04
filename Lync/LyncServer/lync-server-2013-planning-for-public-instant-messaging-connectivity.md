---
title: Lync Server 2013：规划公共即时消息连接
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for public instant messaging connectivity
ms:assetid: e75e8884-05c7-414a-8014-bc9aa8126fb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205349(v=OCS.15)
ms:contentKeyID: 48185698
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7885d17e708f2073006131862f06d93d9057fb3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725232"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="dd006-102">在 Lync Server 2013 中规划公共即时消息连接</span><span class="sxs-lookup"><span data-stu-id="dd006-102">Planning for public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd006-103">_**主题上次修改时间：** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="dd006-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="dd006-104">公用即时消息连接是一种联盟类，并配置为允许您的内部和外部 Lync Server 2013 用户从以下任何内容添加联系人：</span><span class="sxs-lookup"><span data-stu-id="dd006-104">Public Instant Messaging Connectivity is a class of federation, and is configured to allow your internal and external Lync Server 2013 users to add contacts from any of the following:</span></span>

  - <span data-ttu-id="dd006-105">Messenger 联系人</span><span class="sxs-lookup"><span data-stu-id="dd006-105">Messenger contacts</span></span>

  - <span data-ttu-id="dd006-106">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="dd006-106">Yahoo\!</span></span> <span data-ttu-id="dd006-107">联系人</span><span class="sxs-lookup"><span data-stu-id="dd006-107">contacts</span></span>

  - <span data-ttu-id="dd006-108">美国在线（AOL）联系人</span><span class="sxs-lookup"><span data-stu-id="dd006-108">America Online (AOL) contacts</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="dd006-109">从2012年9月1日起，Microsoft Lync 公共 IM 连接用户订购许可证（PIC USL）不再可用于购买新的或续订协议。</span><span class="sxs-lookup"><span data-stu-id="dd006-109">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="dd006-110">具有活动许可证的客户将能够继续与 Yahoo！进行联盟</span><span class="sxs-lookup"><span data-stu-id="dd006-110">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="dd006-111">Messenger，直到服务关闭日期。</span><span class="sxs-lookup"><span data-stu-id="dd006-111">Messenger until the service shutdown date.</span></span> <span data-ttu-id="dd006-112">AOL 和 Yahoo！的有效期结束日期为2014年6月</span><span class="sxs-lookup"><span data-stu-id="dd006-112">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="dd006-113">已宣布。</span><span class="sxs-lookup"><span data-stu-id="dd006-113">has been announced.</span></span> <span data-ttu-id="dd006-114">有关详细信息，请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公共即时消息连接支持</A>。</span><span class="sxs-lookup"><span data-stu-id="dd006-114">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="dd006-115">PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo！联合所需的每用户、每月订阅许可证。</span><span class="sxs-lookup"><span data-stu-id="dd006-115">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="dd006-116">Messenger.</span><span class="sxs-lookup"><span data-stu-id="dd006-116">Messenger.</span></span> <span data-ttu-id="dd006-117">Microsoft 提供此服务的能力已由 Yahoo！的支持（将不会续订的底层协议）提供。</span><span class="sxs-lookup"><span data-stu-id="dd006-117">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="dd006-118">Lync 比以往更多，是一种强大的工具，用于跨组织和全球各地的人员进行连接。</span><span class="sxs-lookup"><span data-stu-id="dd006-118">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="dd006-119">与 Windows Live Messenger 的联盟不需要除 Lync 标准 CAL 之外的其他用户/设备许可证。</span><span class="sxs-lookup"><span data-stu-id="dd006-119">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="dd006-120">Skype 联盟将添加到此列表，使 Lync 用户可以通过 IM 和语音与成百上千人联系。</span><span class="sxs-lookup"><span data-stu-id="dd006-120">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="dd006-121">此类联合需要以下规划注意事项：</span><span class="sxs-lookup"><span data-stu-id="dd006-121">This class of federation requires the following planning considerations:</span></span>

  - <span data-ttu-id="dd006-122">除了即时消息外，Windows Live Messenger 用户可以与 Lync Server 2013 用户进行对等音频/视频通信。</span><span class="sxs-lookup"><span data-stu-id="dd006-122">Windows Live Messenger users can have peer-to-peer audio/visual communication with Lync Server 2013 users, in addition to instant messaging.</span></span> <span data-ttu-id="dd006-123">边缘服务器必须满足特定的端口和协议要求。</span><span class="sxs-lookup"><span data-stu-id="dd006-123">Your Edge Servers must meet specific port and protocol requirements.</span></span> <span data-ttu-id="dd006-124">有关详细信息，请参阅[确定 Lync Server 2013 的外部 A/V 防火墙和端口要求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="dd006-124">For details, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

  - <span data-ttu-id="dd006-125">Yahoo 即时消息没有独特的要求，除了通常用于提供联合的典型边缘服务器的规划和部署中。</span><span class="sxs-lookup"><span data-stu-id="dd006-125">Yahoo instant messaging has no unique requirements, other than those typically used in the planning and deployment of the typical Edge Server that is providing federation.</span></span>

  - <span data-ttu-id="dd006-126">北美洲联机要求分配给 Access Edge 服务的 Edge 服务器证书具有客户端增强型密钥用法（EKU）。</span><span class="sxs-lookup"><span data-stu-id="dd006-126">America Online requires that your Edge Server certificate assigned to the Access Edge service has a client enhanced key usage (EKU).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="dd006-127">本节内容</span><span class="sxs-lookup"><span data-stu-id="dd006-127">In This Section</span></span>

  - [<span data-ttu-id="dd006-128">证书摘要-Lync Server 2013 中的公共即时消息连接</span><span class="sxs-lookup"><span data-stu-id="dd006-128">Certificate summary - Public instant messaging connectivity in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-public-instant-messaging-connectivity.md)

  - [<span data-ttu-id="dd006-129">端口摘要-Lync Server 2013 中的公共即时消息连接</span><span class="sxs-lookup"><span data-stu-id="dd006-129">Port summary - Public instant messaging connectivity in Lync Server 2013</span></span>](lync-server-2013-port-summary-public-instant-messaging-connectivity.md)

  - <span data-ttu-id="dd006-130">[DNS 摘要-Lync Server 2013 中的公共即时消息连接](https://technet.microsoft.com/en-us/library/jj618375\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="dd006-130">[DNS summary - Public instant messaging connectivity in Lync Server 2013](https://technet.microsoft.com/en-us/library/jj618375\(v=ocs.15\))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

