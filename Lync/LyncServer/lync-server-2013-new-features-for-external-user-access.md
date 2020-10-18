---
title: Lync Server 2013：用于外部用户访问的新功能
description: Lync Server 2013：用于外部用户访问的新功能。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New features for external user access
ms:assetid: 99da6bd5-ec14-4ad9-8f7d-37fbddf567dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398794(v=OCS.15)
ms:contentKeyID: 48184884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9d960a469334a836c453e8ae3bbf51f1b66bb93
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578838"
---
# <a name="new-features-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="1d1e5-103">Lync Server 2013 中用于外部用户访问的新功能</span><span class="sxs-lookup"><span data-stu-id="1d1e5-103">New features for external user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d1e5-104">_**上次修改的主题：** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="1d1e5-104">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="1d1e5-105">Lync Server 2013 引入了新功能，用于扩展用户的功能和通信方法。</span><span class="sxs-lookup"><span data-stu-id="1d1e5-105">Lync Server 2013 introduces new features that extend the features and communications methods for your users.</span></span> <span data-ttu-id="1d1e5-106">另外，Lync Server 2013 引入了对现有服务所做的更改，以便更好地集成和扩展可供您的组织使用的服务。</span><span class="sxs-lookup"><span data-stu-id="1d1e5-106">Also, Lync Server 2013 introduces changes to existing services to better integrate and extend the services that are available to your organization.</span></span> <span data-ttu-id="1d1e5-107">以下是可能影响您规划和部署 Lync Server 2013 Edge Server 服务的更改的摘要。</span><span class="sxs-lookup"><span data-stu-id="1d1e5-107">Following is a summary of changes that may affect your planning and deployment of Lync Server 2013 Edge Server services.</span></span>

  - <span data-ttu-id="1d1e5-108">**对 IPv6 寻址**     的支持Lync Server 2013 支持所有边缘服务器服务的 IPv6 寻址。</span><span class="sxs-lookup"><span data-stu-id="1d1e5-108">**Support for IPv6 addressing**   Lync Server 2013 supports IPv6 addressing for all Edge Server services.</span></span> <span data-ttu-id="1d1e5-109">如果已通过 Windows Server 中的配置为接口提供了 IPv6 地址，则可以通过拓扑生成器中的 IP 地址配置来使用边缘服务器配置中的 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="1d1e5-109">If you have provided IPv6 addresses for the interfaces through configuration in Windows Server, you can use IPv6 addresses in your Edge Server configuration through the IP address configuration in Topology Builder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1d1e5-110">在 Lync Server 2013 中使用 IPv6 地址取决于您的组织部署的路由器和防火墙中的 IPv6 支持，以及通过 Internet 服务提供商的支持。</span><span class="sxs-lookup"><span data-stu-id="1d1e5-110">Use of IPv6 addresses in Lync Server 2013 depends on support of IPv6 in routers and firewalls that your organization deploys, as well as support through your Internet service provider.</span></span>

    
    </div>

  - <span data-ttu-id="1d1e5-111">\*\*可扩展消息传递和状态协议 (XMPP) \*\*    Lync Server 2013 引入了一个完全集成的 XMPP 代理 (部署在边缘服务器上) 和部署在前端服务器上的 XMPP 网关。</span><span class="sxs-lookup"><span data-stu-id="1d1e5-111">**Extensible Messaging and Presence Protocol (XMPP)**   Lync Server 2013 introduces a fully integrated XMPP proxy (deployed on the Edge Servers) and an XMPP gateway deployed on your Front End Servers.</span></span> <span data-ttu-id="1d1e5-112">可将 XMPP 联盟作为可选组件来部署。</span><span class="sxs-lookup"><span data-stu-id="1d1e5-112">You can deploy XMPP federation as an optional component.</span></span> <span data-ttu-id="1d1e5-113">添加和配置 XMPP 代理和 XMPP 网关将允许您的 Microsoft Lync 2013 用户添加来自基于 XMPP 的合作伙伴的联系人，以实现即时消息 (IM) 和状态。</span><span class="sxs-lookup"><span data-stu-id="1d1e5-113">Adding and configuring the XMPP proxy and XMPP gateway will allow your Microsoft Lync 2013 users to add contacts from XMPP-based partners for instant messaging (IM) and presence.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1d1e5-114">目前，Lync Server 2013 中的 XMPP 服务仅在 Lync 客户端和基于 XMPP 的联系人之间提供即时消息和状态。</span><span class="sxs-lookup"><span data-stu-id="1d1e5-114">Currently, the XMPP services in Lync Server 2013 only provide instant messaging and presence between Lync clients and XMPP-based contacts.</span></span>

    
    </div>

  - <span data-ttu-id="1d1e5-115">**移动客户端**     的移动服务在 Lync Server 2010 的客户更新中引入，Lync Server 2013 中的移动服务允许使用受支持的 Apple iOS、Android、Windows Phone 或 Nokia 移动设备的移动电话和平板电脑上的 Microsoft Lync 移动客户端执行诸如发送和接收即时消息、查看联系人和查看状态等活动。</span><span class="sxs-lookup"><span data-stu-id="1d1e5-115">**Mobility services for Mobile clients**   Introduced in a customer update for Lync Server 2010, Mobility services in Lync Server 2013 allow Microsoft Lync Mobile clients on mobile phones and tablet devices using supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform such activities as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="1d1e5-116">此外，移动设备支持某些企业语音功能，例如，通过单击加入会议、通过工作、单号码到达、语音邮件和未接来电通知进行呼叫。</span><span class="sxs-lookup"><span data-stu-id="1d1e5-116">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed call notification.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1d1e5-117">Mobility Service 使用反向代理和在前端服务器上部署的已发布服务。</span><span class="sxs-lookup"><span data-stu-id="1d1e5-117">The mobility services use the reverse proxy and published services that are deployed on your Front End Servers.</span></span> <span data-ttu-id="1d1e5-118">无需对边缘服务器进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="1d1e5-118">No changes are required to Edge Servers.</span></span>

    
    </div>

  - <span data-ttu-id="1d1e5-119">**控制器是一个可选角色**    Lync Server 2013 拓扑中的控制器服务器角色未发生更改。</span><span class="sxs-lookup"><span data-stu-id="1d1e5-119">**Directors are an optional role**   The role of the Director server in the Lync Server 2013 topology has not changed.</span></span> <span data-ttu-id="1d1e5-120">它仍承载 web 服务，对传入的用户请求进行预身份验证，并将外部用户定向到其主池。</span><span class="sxs-lookup"><span data-stu-id="1d1e5-120">It still hosts web services, pre-authenticates incoming user requests, and directs external users to their home pool.</span></span> <span data-ttu-id="1d1e5-121">将 Director 从推荐角色更改为可选角色不会降低 Director 的价值，但强调服务器数量和其他硬件要求 (例如，控制器) 要求的硬件负载平衡器，而不会影响特性和功能。</span><span class="sxs-lookup"><span data-stu-id="1d1e5-121">Changing the Director from a recommended role to an optional role does not diminish the value of the Director, but emphasizes reducing server count and other hardware requirements (for example, hardware load balancers for the Director) requirements without compromising features and functionality.</span></span> <span data-ttu-id="1d1e5-122">由于前端服务器可以执行与提供的服务不受影响的控制器相同的作业，因此，如果选择，则可以选择部署控制器。</span><span class="sxs-lookup"><span data-stu-id="1d1e5-122">Because the Front End Servers can do the same job as the Director with no impact to services provided, you can optionally deploy Directors if you choose to.</span></span> <span data-ttu-id="1d1e5-123">你可以放心地排除 Director，前端服务器将在其位置提供相同的服务。</span><span class="sxs-lookup"><span data-stu-id="1d1e5-123">You can safely exclude the Director with confidence that the Front End Servers will provide the same services in their place.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="1d1e5-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1d1e5-124">See Also</span></span>


[<span data-ttu-id="1d1e5-125">在 Lync Server 2013 中规划和配置 IPv6</span><span class="sxs-lookup"><span data-stu-id="1d1e5-125">Planning for and configuring IPv6 in Lync Server 2013</span></span>](lync-server-2013-planning-for-and-configuring-ipv6.md)  


[<span data-ttu-id="1d1e5-126">在 Lync Server 2013 中规划外部用户访问</span><span class="sxs-lookup"><span data-stu-id="1d1e5-126">Planning for external user access in Lync Server 2013</span></span>](lync-server-2013-planning-for-external-user-access.md)  
[<span data-ttu-id="1d1e5-127">在 Lync Server 2013 中规划可扩展消息和状态协议 (XMPP) 联盟</span><span class="sxs-lookup"><span data-stu-id="1d1e5-127">Planning for extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

