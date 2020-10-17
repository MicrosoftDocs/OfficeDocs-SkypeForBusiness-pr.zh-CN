---
title: Lync Server 2013：部署远程呼叫控制
description: Lync Server 2013：部署远程呼叫控制。
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
ms.openlocfilehash: 4cc5e79f3ee44c354baf435585d304574d6a980c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566078"
---
# <a name="deploying-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="494a0-103">在 Lync Server 2013 中部署远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="494a0-103">Deploying remote call control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="494a0-104">_**上次修改的主题：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="494a0-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="494a0-105">本节指导您完成为组织用户部署远程呼叫控制功能的过程。</span><span class="sxs-lookup"><span data-stu-id="494a0-105">This section guides you through the process of deploying remote call control functionality to users in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="494a0-106">虽然远程呼叫控制功能可用于在组织的防火墙之外的远程用户，但是有关部署外部访问方案的详细信息不在本文档的范围之内。</span><span class="sxs-lookup"><span data-stu-id="494a0-106">Although remote call control features are available to remote users while they are outside of your organization’s firewall, details about deploying external access scenarios are beyond the scope of this documentation.</span></span> <span data-ttu-id="494a0-107">有关部署外部用户访问的详细信息，请参阅部署文档中的在 <A href="lync-server-2013-deploying-external-user-access.md">Lync Server 2013 中部署外部用户访问</A> 。</span><span class="sxs-lookup"><span data-stu-id="494a0-107">For details about deploying external user access, see <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="494a0-108">本部分内容</span><span class="sxs-lookup"><span data-stu-id="494a0-108">In This Section</span></span>

  - [<span data-ttu-id="494a0-109">配置 Lync Server 2013 以路由到 SIP/CSTA 网关</span><span class="sxs-lookup"><span data-stu-id="494a0-109">Configuring Lync Server 2013 to route to a SIP/CSTA gateway</span></span>](lync-server-2013-configuring-lync-server-to-route-to-a-sip-csta-gateway.md)

  - [<span data-ttu-id="494a0-110">在 Lync Server 2013 中为远程呼叫控制配置静态路由</span><span class="sxs-lookup"><span data-stu-id="494a0-110">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)

  - [<span data-ttu-id="494a0-111">在 Lync Server 2013 中为远程呼叫控制配置受信任的应用程序条目</span><span class="sxs-lookup"><span data-stu-id="494a0-111">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)

  - <span data-ttu-id="494a0-112">仅当网关配置为使用 TCP 时，才能[在 Lync Server 2013 (中定义 SIP/CSTA 网关 IP 地址](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)) </span><span class="sxs-lookup"><span data-stu-id="494a0-112">[Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) (only if the gateway is configured to use TCP)</span></span>

  - [<span data-ttu-id="494a0-113">在 Lync Server 2013 中为 Lync 用户启用远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="494a0-113">Enable Lync users for remote call control in Lync Server 2013</span></span>](lync-server-2013-enable-lync-users-for-remote-call-control.md)

  - [<span data-ttu-id="494a0-114">Lync Server 2013 中的远程呼叫控制和电话号码规范化</span><span class="sxs-lookup"><span data-stu-id="494a0-114">Remote call control and phone number normalization in Lync Server 2013</span></span>](lync-server-2013-remote-call-control-and-phone-number-normalization.md)

  - <span data-ttu-id="494a0-115">[在 Lync Server 2013 中删除旧版授权主机 (可选) ](lync-server-2013-remove-a-legacy-authorized-host-optional.md) (仅当迁移以前为远程呼叫控制启用的用户时) </span><span class="sxs-lookup"><span data-stu-id="494a0-115">[Remove a legacy authorized host in Lync Server 2013 (optional)](lync-server-2013-remove-a-legacy-authorized-host-optional.md) (only if you are migrating users previously enabled for remote call control)</span></span>

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="494a0-116">相关部分</span><span class="sxs-lookup"><span data-stu-id="494a0-116">Related Sections</span></span>

[<span data-ttu-id="494a0-117">在 Lync Server 2013 中规划远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="494a0-117">Planning for remote call control in Lync Server 2013</span></span>](lync-server-2013-planning-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

