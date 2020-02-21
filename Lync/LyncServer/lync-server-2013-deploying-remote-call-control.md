---
title: Lync Server 2013：部署远程呼叫控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying remote call control
ms:assetid: 763037f7-7a2a-49ae-acc3-9781b0bff7e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558664(v=OCS.15)
ms:contentKeyID: 48184536
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5659bf3e210f1f8294789729a758d4877d3e70bb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188205"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="4e4eb-102">在 Lync Server 2013 中部署远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="4e4eb-102">Deploying remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e4eb-103">_**上次修改的主题：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="4e4eb-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="4e4eb-104">本节指导您完成为组织用户部署远程呼叫控制功能的过程。</span><span class="sxs-lookup"><span data-stu-id="4e4eb-104">This section guides you through the process of deploying remote call control functionality to users in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4e4eb-105">虽然远程呼叫控制功能可用于在组织的防火墙之外的远程用户，但是有关部署外部访问方案的详细信息不在本文档的范围之内。</span><span class="sxs-lookup"><span data-stu-id="4e4eb-105">Although remote call control features are available to remote users while they are outside of your organization’s firewall, details about deploying external access scenarios are beyond the scope of this documentation.</span></span> <span data-ttu-id="4e4eb-106">有关部署外部用户访问的详细信息，请参阅部署文档中的在<A href="lync-server-2013-deploying-external-user-access.md">Lync Server 2013 中部署外部用户访问</A>。</span><span class="sxs-lookup"><span data-stu-id="4e4eb-106">For details about deploying external user access, see <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4e4eb-107">本部分内容</span><span class="sxs-lookup"><span data-stu-id="4e4eb-107">In This Section</span></span>

  - [<span data-ttu-id="4e4eb-108">配置 Lync Server 2013 以路由到 SIP/CSTA 网关</span><span class="sxs-lookup"><span data-stu-id="4e4eb-108">Configuring Lync Server 2013 to route to a SIP/CSTA gateway</span></span>](lync-server-2013-configuring-lync-server-to-route-to-a-sip-csta-gateway.md)

  - [<span data-ttu-id="4e4eb-109">在 Lync Server 2013 中为远程呼叫控制配置静态路由</span><span class="sxs-lookup"><span data-stu-id="4e4eb-109">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)

  - [<span data-ttu-id="4e4eb-110">在 Lync Server 2013 中为远程呼叫控制配置受信任的应用程序条目</span><span class="sxs-lookup"><span data-stu-id="4e4eb-110">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)

  - <span data-ttu-id="4e4eb-111">[在 Lync Server 2013 中定义 SIP/CSTA 网关 IP 地址](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)（仅当网关配置为使用 TCP 时）</span><span class="sxs-lookup"><span data-stu-id="4e4eb-111">[Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) (only if the gateway is configured to use TCP)</span></span>

  - [<span data-ttu-id="4e4eb-112">在 Lync Server 2013 中为 Lync 用户启用远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="4e4eb-112">Enable Lync users for remote call control in Lync Server 2013</span></span>](lync-server-2013-enable-lync-users-for-remote-call-control.md)

  - [<span data-ttu-id="4e4eb-113">Lync Server 2013 中的远程呼叫控制和电话号码规范化</span><span class="sxs-lookup"><span data-stu-id="4e4eb-113">Remote call control and phone number normalization in Lync Server 2013</span></span>](lync-server-2013-remote-call-control-and-phone-number-normalization.md)

  - <span data-ttu-id="4e4eb-114">[在 Lync Server 2013 中删除旧版授权主机（可选）](lync-server-2013-remove-a-legacy-authorized-host-optional.md) （仅当迁移以前为远程呼叫控制启用的用户时）</span><span class="sxs-lookup"><span data-stu-id="4e4eb-114">[Remove a legacy authorized host in Lync Server 2013 (optional)](lync-server-2013-remove-a-legacy-authorized-host-optional.md) (only if you are migrating users previously enabled for remote call control)</span></span>

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="4e4eb-115">相关部分</span><span class="sxs-lookup"><span data-stu-id="4e4eb-115">Related Sections</span></span>

[<span data-ttu-id="4e4eb-116">在 Lync Server 2013 中规划远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="4e4eb-116">Planning for remote call control in Lync Server 2013</span></span>](lync-server-2013-planning-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

