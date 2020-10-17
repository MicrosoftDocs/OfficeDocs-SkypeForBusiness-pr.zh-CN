---
title: Lync Server 2013：规划公共即时消息连接
description: Lync Server 2013：规划公共即时消息连接。
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
ms.openlocfilehash: 9a020a291a39d78aea9271926c99b508a8cd9827
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549288"
---
# <a name="planning-for-public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="c916b-103">在 Lync Server 2013 中规划公共即时消息连接</span><span class="sxs-lookup"><span data-stu-id="c916b-103">Planning for public instant messaging connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c916b-104">_**上次修改的主题：** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="c916b-104">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="c916b-105">公共即时消息连接是一类联合，配置为允许您的内部和外部 Lync Server 2013 用户从以下任一项添加联系人：</span><span class="sxs-lookup"><span data-stu-id="c916b-105">Public Instant Messaging Connectivity is a class of federation, and is configured to allow your internal and external Lync Server 2013 users to add contacts from any of the following:</span></span>

  - <span data-ttu-id="c916b-106">Messenger 联系人</span><span class="sxs-lookup"><span data-stu-id="c916b-106">Messenger contacts</span></span>

  - <span data-ttu-id="c916b-107">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="c916b-107">Yahoo\!</span></span> <span data-ttu-id="c916b-108">contacts</span><span class="sxs-lookup"><span data-stu-id="c916b-108">contacts</span></span>

  - <span data-ttu-id="c916b-109">America Online (AOL) 联系人</span><span class="sxs-lookup"><span data-stu-id="c916b-109">America Online (AOL) contacts</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="c916b-110">从2012年9月1日起，Microsoft Lync 公共 IM 连接用户订阅许可证 (PIC USL) 不再可用于购买新的或更新的协议。</span><span class="sxs-lookup"><span data-stu-id="c916b-110">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="c916b-111">拥有主动许可证的客户将能够继续与 Yahoo！联合联合</span><span class="sxs-lookup"><span data-stu-id="c916b-111">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="c916b-112">信使，直到服务关闭日期。</span><span class="sxs-lookup"><span data-stu-id="c916b-112">Messenger until the service shutdown date.</span></span> <span data-ttu-id="c916b-113">AOL 和 Yahoo！的生命周期结束日期为2014年6月</span><span class="sxs-lookup"><span data-stu-id="c916b-113">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="c916b-114">已宣布。</span><span class="sxs-lookup"><span data-stu-id="c916b-114">has been announced.</span></span> <span data-ttu-id="c916b-115">有关详细信息，请参阅 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的支持公用即时信使连接</A>。</span><span class="sxs-lookup"><span data-stu-id="c916b-115">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="c916b-116">PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo！联合所需的每用户、每月订阅许可证。</span><span class="sxs-lookup"><span data-stu-id="c916b-116">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="c916b-117">Messenger.</span><span class="sxs-lookup"><span data-stu-id="c916b-117">Messenger.</span></span> <span data-ttu-id="c916b-118">Microsoft 提供此服务的能力因 Yahoo！中的支持而异，将不会续订的底层协议。</span><span class="sxs-lookup"><span data-stu-id="c916b-118">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="c916b-119">Lync 是前所未有的强大工具，用于跨组织和世界各地的个人进行连接。</span><span class="sxs-lookup"><span data-stu-id="c916b-119">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="c916b-120">与 Windows Live Messenger 的联盟不需要除 Lync Standard CAL 之外的其他用户/设备许可证。</span><span class="sxs-lookup"><span data-stu-id="c916b-120">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="c916b-121">Skype 联盟将添加到此列表中，使 Lync 用户能够通过即时消息和语音访问数百个人。</span><span class="sxs-lookup"><span data-stu-id="c916b-121">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="c916b-122">此类联盟需要规划以下注意事项：</span><span class="sxs-lookup"><span data-stu-id="c916b-122">This class of federation requires the following planning considerations:</span></span>

  - <span data-ttu-id="c916b-123">除了即时消息之外，Windows Live Messenger 用户可以与 Lync Server 2013 用户进行对等音频/视频通信。</span><span class="sxs-lookup"><span data-stu-id="c916b-123">Windows Live Messenger users can have peer-to-peer audio/visual communication with Lync Server 2013 users, in addition to instant messaging.</span></span> <span data-ttu-id="c916b-124">您的边缘服务器必须满足特定的端口和协议要求。</span><span class="sxs-lookup"><span data-stu-id="c916b-124">Your Edge Servers must meet specific port and protocol requirements.</span></span> <span data-ttu-id="c916b-125">有关详细信息，请参阅 [确定 Lync Server 2013 的外部 A/V 防火墙和端口要求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c916b-125">For details, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

  - <span data-ttu-id="c916b-126">Yahoo 即时消息没有独特的要求，而不是通常在提供联合的典型边缘服务器的规划和部署中使用的要求。</span><span class="sxs-lookup"><span data-stu-id="c916b-126">Yahoo instant messaging has no unique requirements, other than those typically used in the planning and deployment of the typical Edge Server that is providing federation.</span></span>

  - <span data-ttu-id="c916b-127">美洲在线要求分配给访问边缘服务的边缘服务器证书具有客户端增强型密钥用法 (EKU) 。</span><span class="sxs-lookup"><span data-stu-id="c916b-127">America Online requires that your Edge Server certificate assigned to the Access Edge service has a client enhanced key usage (EKU).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c916b-128">本部分内容</span><span class="sxs-lookup"><span data-stu-id="c916b-128">In This Section</span></span>

  - [<span data-ttu-id="c916b-129">证书摘要-Lync Server 2013 中的公共即时消息连接</span><span class="sxs-lookup"><span data-stu-id="c916b-129">Certificate summary - Public instant messaging connectivity in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-public-instant-messaging-connectivity.md)

  - [<span data-ttu-id="c916b-130">端口摘要-Lync Server 2013 中的公共即时消息连接</span><span class="sxs-lookup"><span data-stu-id="c916b-130">Port summary - Public instant messaging connectivity in Lync Server 2013</span></span>](lync-server-2013-port-summary-public-instant-messaging-connectivity.md)

  - <span data-ttu-id="c916b-131">[DNS 摘要-Lync Server 2013 中的公共即时消息连接](https://technet.microsoft.com/library/jj618375\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="c916b-131">[DNS summary - Public instant messaging connectivity in Lync Server 2013](https://technet.microsoft.com/library/jj618375\(v=ocs.15\))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

