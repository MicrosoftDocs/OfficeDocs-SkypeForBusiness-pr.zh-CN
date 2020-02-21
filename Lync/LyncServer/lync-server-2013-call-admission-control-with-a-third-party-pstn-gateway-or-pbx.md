---
title: 使用第三方 PSTN 网关或 PBX 的呼叫允许控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control with a third-party PSTN gateway or PBX
ms:assetid: 95dc4ceb-bcad-48ee-86ec-af911727f853
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398762(v=OCS.15)
ms:contentKeyID: 48184850
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e9223722b37fa703bcc0410092ebdf933beb5d8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181495"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-admission-control-in-lync-server-2013-with-a-third-party-pstn-gateway-or-pbx"></a>使用第三方 PSTN 网关或 PBX 的 Lync Server 2013 中的呼叫允许控制

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-20_

本主题介绍如何在中介服务器的网关接口和第三方公用电话交换电话网络（PSTN）网关或专用交换机（PBX）之间的链路上部署呼叫允许控制（CAC）的示例。

<div>

## <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a>案例1：中介服务器与 PSTN 网关之间的 CAC

可以在从中介服务器的网关接口到第三方 PBX 或 PSTN 网关的 WAN 链路上部署 CAC。

**案例1：中介服务器与 PSTN 网关之间的 CAC**

![案例1：中介服务器 PSTN 网关之间的 CAC](images/Gg398762.4bebf9ee-2732-4ea6-bbe5-0269b2903d8c(OCS.15).jpg "案例1：中介服务器 PSTN 网关之间的 CAC")

在此示例中，在中介服务器和 PSTN 网关之间应用 CAC。 如果网络站点1上的 Lync 客户端用户通过网络站点2中的 PSTN 网关放置 PSTN 呼叫，则媒体将通过 WAN 链路流动。 因此，每个 PSTN 会话都会执行两个 CAC 检查：

  - Lync 客户端应用程序和中介服务器之间

  - 中介服务器和 PSTN 网关之间

这适用于对网络站点1中的客户端的传入 PSTN 呼叫以及源自网络站点1中的客户端应用程序的传出 PSTN 呼叫。

<div>


> [!NOTE]
> 请确保 PSTN 网关所属的 IP 子网已配置并与网络站点2相关联。<BR>确保中介服务器的两个接口所属的 IP 子网已配置并与网络站点1相关联。<BR>有关详细信息，请参阅<A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">在 Lync Server 2013 中将子网与网络站点关联</A>。



</div>

</div>

<div>

## <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a>示例2：中介服务器与具有媒体终结点的第三方 PBX 之间的 CAC

此配置类似于 Case 1。 在这两种情况下，中介服务器都知道在 WAN 链路的另一端终止媒体的设备，并且将中介服务器上的 PSTN 网关或 PBX 的 IP 地址配置为下一个跃点（MTP）。

**示例2：中介服务器与具有 MTP 的第三方 PBX 之间的 CAC**

![示例2：中介服务器 PBX 与 MTP 之间的 CAC](images/Gg398762.1c0b5263-c053-4cca-842f-85dd670760c8(OCS.15).jpg "示例2：中介服务器 PBX 与 MTP 之间的 CAC")

在此示例中，在中介服务器和 PBX/MTP 之间应用 CAC。 如果网络站点1上的 Lync 客户端用户通过位于网络站点2中的 PBX/MTP 发出 PSTN 呼叫，则媒体将流经 WAN 链路。 因此，每个 PSTN 会话都会执行两个 CAC 检查：

  - Lync 客户端应用程序和中介服务器之间

  - 中介服务器与 PBX/MTP 之间的关系

这适用于对网络站点1中的客户端的传入 PSTN 呼叫和从网络站点1中的客户端发起的传出 PSTN 呼叫。

<div>


> [!NOTE]
> 确保 MTP 所属的 IP 子网已配置并与网络站点2相关联。<BR>确保中介服务器的两个接口所属的 IP 子网已配置并与网络站点1相关联。<BR>有关详细信息，请参阅<A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">在 Lync Server 2013 中将子网与网络站点关联</A>。



</div>

</div>

<div>

## <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a>示例3：中介服务器与不带媒体终结点的第三方 PBX 之间的 CAC

Case 3 与前两个事例略有不同。 如果第三方 PBX 没有 MTP，则对于第三方 PBX 的传出会话请求，中介服务器不知道媒体将在 PBX 边界中终止的位置。 在这种情况下，媒体将直接在中介服务器和第三方终结点设备之间流动。

**示例3：中介服务器与不含 MTP 的第三方 PBX 之间的 CAC**

![示例3：中介服务器 PBX 之间的 CAC 无 MTP](images/Gg398762.f4bcf800-3a68-4037-bb3f-adb2fdf50d32(OCS.15).jpg "示例3：中介服务器 PBX 之间的 CAC 无 MTP")

在此示例中，如果网络站点1上的 Lync 客户端用户通过 PBX 向用户发出呼叫，中介服务器只能在代理端（Lync 客户端应用程序和中介服务器之间）执行 CAC 检查。 由于中介服务器在请求会话时没有终结点设备的相关信息，因此在建立呼叫之前，不能在 WAN 链路（中介服务器和第三方终结点之间）上执行 CAC 检查。 但是，在建立会话之后，中介服务器将为中继上使用的带宽简化记帐。

对于源自第三方终结点的呼叫，有关该终结点设备的信息在会话请求时可用，并且可以在中介服务器的双方执行 CAC 检查。

<div>


> [!NOTE]
> 确保终结点设备所属的 IP 子网已配置并与网络站点2相关联。<BR>确保中介服务器的两个接口所属的 IP 子网已配置并与网络站点1相关联。<BR>有关详细信息，请参阅<A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">在 Lync Server 2013 中将子网与网络站点关联</A>。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

