---
title: Lync Server 2013：部署外部用户访问
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying external user access
ms:assetid: d40c9574-c16b-4fe6-b848-21ae0b7e4f0e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398918(v=OCS.15)
ms:contentKeyID: 48185495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b2168e679b16ddca3a201fe375b1189642ef671
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137541"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-external-user-access-in-lync-server-2013"></a><span data-ttu-id="a0e65-102">在 Lync Server 2013 中部署外部用户访问</span><span class="sxs-lookup"><span data-stu-id="a0e65-102">Deploying external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0e65-103">_**上次修改的主题：** 2013-09-23_</span><span class="sxs-lookup"><span data-stu-id="a0e65-103">_**Topic Last Modified:** 2013-09-23_</span></span>

<span data-ttu-id="a0e65-104">为 Microsoft Lync Server 2013 部署边缘组件使未登录到组织内部网络的外部用户（包括经过身份验证和匿名的远程用户、联盟伙伴（包括 XMPP 合作伙伴））可以使用 Lync Server 与组织中的其他用户通信的移动客户端和公共即时消息（IM）服务的用户。</span><span class="sxs-lookup"><span data-stu-id="a0e65-104">Deploying edge components for Microsoft Lync Server 2013 makes it possible for external users who are not logged into your organization’s internal network, including authenticated and anonymous remote users, federated partners (including XMPP partners), mobile clients and users of public instant messaging (IM) services, to communicate with other users in your organization using Lync Server.</span></span> <span data-ttu-id="a0e65-105">Lync Server 2013 的部署和配置过程与 Lync Server 2010 没有显著不同。</span><span class="sxs-lookup"><span data-stu-id="a0e65-105">The deployment and configuration processes for Lync Server 2013 are not significantly different from Lync Server 2010.</span></span> <span data-ttu-id="a0e65-106">安装和管理工具与 Lync Server 2010 中的工具非常相似。</span><span class="sxs-lookup"><span data-stu-id="a0e65-106">The tools for installation and administration are much the same as in Lync Server 2010.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a0e65-107">Microsoft Lync Server 2013&nbsp;边缘服务器安装和配置可能是一个复杂的过程，需要与内部团队进行大量的规划和协调，包括但不限于安全性、网络、防火墙、域名系统（DNS）、负载平衡器和公钥基础结构（PKI）的注意事项。</span><span class="sxs-lookup"><span data-stu-id="a0e65-107">Microsoft Lync Server 2013&nbsp;Edge Server installation and configuration can be a complex process requiring a potentially significant amount of planning and coordination with your internal teams, including – but not limited to – security, networking, firewall, domain name system (DNS), load balancer, and public key infrastructure (PKI) considerations.</span></span> <span data-ttu-id="a0e65-108">强烈建议您先查看并使用提供的规划过程和文档，然后再部署外部访问组件。</span><span class="sxs-lookup"><span data-stu-id="a0e65-108">It is strongly recommended that you review and use the planning process and documentation provided before deploying your external access components.</span></span> <span data-ttu-id="a0e65-109">这将有助于在您执行部署过程时限制意外更改和问题的数量和频率。</span><span class="sxs-lookup"><span data-stu-id="a0e65-109">This will assist in limiting the number and frequency of undesired changes and problems as you proceed through the deployment process.</span></span> <span data-ttu-id="a0e65-110">有关规划外部用户访问的信息，请参阅<A href="lync-server-2013-planning-for-external-user-access.md">在 Lync Server 2013 中规划外部用户访问</A>。</span><span class="sxs-lookup"><span data-stu-id="a0e65-110">For information on planning you external user access, see <A href="lync-server-2013-planning-for-external-user-access.md">Planning for external user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a0e65-111">本部分内容</span><span class="sxs-lookup"><span data-stu-id="a0e65-111">In This Section</span></span>

  - [<span data-ttu-id="a0e65-112">Lync Server 2013 中的外部用户访问的部署清单</span><span class="sxs-lookup"><span data-stu-id="a0e65-112">Deployment checklist for external user access in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-external-user-access.md)

  - [<span data-ttu-id="a0e65-113">Lync Server 2013 的外部用户访问组件的系统要求</span><span class="sxs-lookup"><span data-stu-id="a0e65-113">System requirements for external user access components for Lync Server 2013</span></span>](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [<span data-ttu-id="a0e65-114">准备在外围网络中为 Lync Server 2013 安装服务器</span><span class="sxs-lookup"><span data-stu-id="a0e65-114">Preparing for installation of servers in the perimeter network for Lync Server 2013</span></span>](lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md)

  - [<span data-ttu-id="a0e65-115">在 Lync Server 2013 中构建边缘和控制器拓扑</span><span class="sxs-lookup"><span data-stu-id="a0e65-115">Building an edge and Director topology in Lync Server 2013</span></span>](lync-server-2013-building-an-edge-and-director-topology.md)

  - <span data-ttu-id="a0e65-116">[在 Lync Server 2013 中设置控制器](lync-server-2013-setting-up-the-director.md)（可选）</span><span class="sxs-lookup"><span data-stu-id="a0e65-116">[Setting up the Director in Lync Server 2013](lync-server-2013-setting-up-the-director.md) (optional)</span></span>

  - [<span data-ttu-id="a0e65-117">在 Lync Server 2013 中设置边缘服务器</span><span class="sxs-lookup"><span data-stu-id="a0e65-117">Setting up Edge Servers in Lync Server 2013</span></span>](lync-server-2013-setting-up-edge-servers.md)

  - [<span data-ttu-id="a0e65-118">为 Lync Server 2013 设置反向代理服务器</span><span class="sxs-lookup"><span data-stu-id="a0e65-118">Setting up reverse proxy servers for Lync Server 2013</span></span>](lync-server-2013-setting-up-reverse-proxy-servers.md)

  - [<span data-ttu-id="a0e65-119">在 Lync Server 2013 中配置对外部用户访问的支持</span><span class="sxs-lookup"><span data-stu-id="a0e65-119">Configuring support for external user access in Lync Server 2013</span></span>](lync-server-2013-configuring-support-for-external-user-access.md)

  - [<span data-ttu-id="a0e65-120">Lync Server 2013 中的 Lync-Skype 连接的预配指南</span><span class="sxs-lookup"><span data-stu-id="a0e65-120">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

  - [<span data-ttu-id="a0e65-121">在 Lync Server 2013 中配置 SIP 联盟、XMPP 联盟和公共即时消息</span><span class="sxs-lookup"><span data-stu-id="a0e65-121">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md)

  - [<span data-ttu-id="a0e65-122">在 Lync Server 2013 中部署移动功能</span><span class="sxs-lookup"><span data-stu-id="a0e65-122">Deploying mobility in Lync Server 2013</span></span>](lync-server-2013-deploying-mobility.md)

  - [<span data-ttu-id="a0e65-123">在 Lync Server 2013 中验证边缘部署</span><span class="sxs-lookup"><span data-stu-id="a0e65-123">Verifying your edge deployment in Lync Server 2013</span></span>](lync-server-2013-verifying-your-edge-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

