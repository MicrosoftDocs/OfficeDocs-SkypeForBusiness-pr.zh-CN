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
ms.openlocfilehash: 6651c9cb15322498d68fa9b6cd705b68dc601c6d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740832"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="bea9d-102">在 Lync Server 2013 中部署远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="bea9d-102">Deploying remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bea9d-103">_**主题上次修改时间：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="bea9d-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="bea9d-104">本部分将指导你完成向组织中的用户部署远程呼叫控制功能的过程。</span><span class="sxs-lookup"><span data-stu-id="bea9d-104">This section guides you through the process of deploying remote call control functionality to users in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bea9d-105">虽然远程呼叫控制功能可供远程用户在您的组织的防火墙外使用，但有关部署外部访问方案的详细信息超出了本文档的范围。</span><span class="sxs-lookup"><span data-stu-id="bea9d-105">Although remote call control features are available to remote users while they are outside of your organization’s firewall, details about deploying external access scenarios are beyond the scope of this documentation.</span></span> <span data-ttu-id="bea9d-106">有关部署外部用户访问的详细信息，请参阅部署文档中<A href="lync-server-2013-deploying-external-user-access.md">Lync Server 2013 中的 "部署外部用户访问</A>"。</span><span class="sxs-lookup"><span data-stu-id="bea9d-106">For details about deploying external user access, see <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bea9d-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="bea9d-107">In This Section</span></span>

  - [<span data-ttu-id="bea9d-108">配置 Lync Server 2013 以路由至 SIP/CSTA 网关</span><span class="sxs-lookup"><span data-stu-id="bea9d-108">Configuring Lync Server 2013 to route to a SIP/CSTA gateway</span></span>](lync-server-2013-configuring-lync-server-to-route-to-a-sip-csta-gateway.md)

  - [<span data-ttu-id="bea9d-109">在 Lync Server 2013 中为远程呼叫控制配置静态路由</span><span class="sxs-lookup"><span data-stu-id="bea9d-109">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)

  - [<span data-ttu-id="bea9d-110">在 Lync Server 2013 中为远程呼叫控制配置受信任的应用程序项</span><span class="sxs-lookup"><span data-stu-id="bea9d-110">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)

  - <span data-ttu-id="bea9d-111">[在 Lync Server 2013 中定义 SIP/CSTA 网关 IP 地址](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)（仅在网关配置为使用 TCP 时）</span><span class="sxs-lookup"><span data-stu-id="bea9d-111">[Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) (only if the gateway is configured to use TCP)</span></span>

  - [<span data-ttu-id="bea9d-112">在 Lync Server 2013 中为 Lync 用户启用远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="bea9d-112">Enable Lync users for remote call control in Lync Server 2013</span></span>](lync-server-2013-enable-lync-users-for-remote-call-control.md)

  - [<span data-ttu-id="bea9d-113">Lync Server 2013 中的远程呼叫控制和电话号码规范化</span><span class="sxs-lookup"><span data-stu-id="bea9d-113">Remote call control and phone number normalization in Lync Server 2013</span></span>](lync-server-2013-remote-call-control-and-phone-number-normalization.md)

  - <span data-ttu-id="bea9d-114">[在 Lync Server 2013 中删除旧式授权主机（可选）](lync-server-2013-remove-a-legacy-authorized-host-optional.md) （仅当迁移以前为远程呼叫控制启用的用户时）</span><span class="sxs-lookup"><span data-stu-id="bea9d-114">[Remove a legacy authorized host in Lync Server 2013 (optional)](lync-server-2013-remove-a-legacy-authorized-host-optional.md) (only if you are migrating users previously enabled for remote call control)</span></span>

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="bea9d-115">相关部分</span><span class="sxs-lookup"><span data-stu-id="bea9d-115">Related Sections</span></span>

[<span data-ttu-id="bea9d-116">在 Lync Server 2013 中规划远程呼叫控制</span><span class="sxs-lookup"><span data-stu-id="bea9d-116">Planning for remote call control in Lync Server 2013</span></span>](lync-server-2013-planning-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

