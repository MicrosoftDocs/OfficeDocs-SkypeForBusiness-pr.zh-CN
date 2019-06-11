---
title: 使用第三方 PSTN 网关或 PBX 时的呼叫允许控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call admission control with a third-party PSTN gateway or PBX
ms:assetid: 95dc4ceb-bcad-48ee-86ec-af911727f853
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398762(v=OCS.15)
ms:contentKeyID: 48184850
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1996b56a50dbe616c8dc6e9b9b1c779c564b185
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837711"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-in-lync-server-2013-with-a-third-party-pstn-gateway-or-pbx"></a>使用第三方 PSTN 网关或 PBX 时 Lync Server 2013 中的呼叫允许控制

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-20_

本主题举例说明如何在中介服务器的网关接口与第三方公用电话交换网 (PSTN) 网关或专用交换机 (PBX) 之间的链接上部署呼叫允许控制 (CAC)。

<div>

## <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a>示例 1：中介服务器与 PSTN 网关之间的 CAC

可以在从中介服务器的网关接口连接到第三方 PBX 或 PSTN 网关的 WAN 链路上部署 CAC。

**示例 1：中介服务器与 PSTN 网关之间的 CAC**

![情况 1: 中介服务器 PSTN 网关之间的 CAC](images/Gg398762.4bebf9ee-2732-4ea6-bbe5-0269b2903d8c(OCS.15).jpg "情况 1: 中介服务器 PSTN 网关之间的 CAC")

在此示例中, 在中介服务器和 PSTN 网关之间应用 CAC。 如果网络站点1中的 Lync 客户端用户通过网络站点2中的 PSTN 网关放置 PSTN 呼叫, 则媒体将通过 WAN 链接进行流动。 因此，将对每个 PSTN 会话执行以下两个 CAC 检查：

  - 在 Lync 客户端应用程序和中介服务器之间

  - 在中介服务器和 PSTN 网关之间

这同时适用于网络站点 1 中的客户端接收的传入 PSTN 呼叫，以及网络站点 1 中的客户端应用程序发送的传出 PSTN 呼叫。

<div>


> [!NOTE]
> 请确保 PSTN 网关所属的 IP 子网已配置并与网络站点 2 相关联。<BR>确保将中介服务器的两个接口所属的 IP 子网配置和与网络站点1相关联。<BR>有关详细信息, 请参阅<A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">在 Lync Server 2013 中将子网与网络站点关联</A>。



</div>

</div>

<div>

## <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a>情况 2: 中介服务器和具有媒体终结点的第三方 PBX 之间的 CAC

此配置与示例 1 类似。 在这两种情况下, 中介服务器都知道在 WAN 链接的另一端终止媒体的设备, 并且在中介服务器上配置了具有媒体终结点 (MTP) 的 PSTN 网关或 PBX 的 IP 地址作为下一跃点。

**示例 2：中介服务器与具有 MTP 的第三方 PBX 之间的 CAC**

![情况 2: 中介服务器 PBX 与 MTP 之间的 CAC](images/Gg398762.1c0b5263-c053-4cca-842f-85dd670760c8(OCS.15).jpg "情况 2: 中介服务器 PBX 与 MTP 之间的 CAC")

在此示例中, 在中介服务器和 PBX/MTP 之间应用 CAC。 如果网络站点1中的 Lync 客户端用户通过位于网络 Site 2 中的 PBX/MTP 放置 PSTN 呼叫, 则媒体将通过 WAN 链接进行流动。 因此，将对每个 PSTN 会话执行以下两个 CAC 检查：

  - 在 Lync 客户端应用程序和中介服务器之间

  - 在中介服务器和 PBX/MTP 之间

这同时适用于网络站点 1 中的客户端接收的传入 PSTN 呼叫，以及网络站点 1 中的客户端发送的传出 PSTN 呼叫。

<div>


> [!NOTE]
> 请确保 MTP 所属的 IP 子网已配置并与网络站点 2 相关联。<BR>确保将中介服务器的两个接口所属的 IP 子网配置和与网络站点1相关联。<BR>有关详细信息, 请参阅<A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">在 Lync Server 2013 中将子网与网络站点关联</A>。



</div>

</div>

<div>

## <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a>情况 3: 在中介服务器与没有媒体终结点的第三方 PBX 之间使用 CAC

示例 3 与前两个示例略有不同。 如果在第三方 PBX 上没有 MTP, 而对于第三方 PBX 的传出会话请求, 则中介服务器不知道媒体将在 PBX 边界内终止的位置。 在这种情况下, 媒体将直接在中介服务器和第三方终结点设备之间流动。

**示例 3：中介服务器与没有 MTP 的第三方 PBX 之间的 CAC**

![情况 3: 中介服务器 PBX 之间的 CAC 无 MTP](images/Gg398762.f4bcf800-3a68-4037-bb3f-adb2fdf50d32(OCS.15).jpg "情况 3: 中介服务器 PBX 之间的 CAC 无 MTP")

在此示例中, 如果网络站点1上的 Lync 客户端用户通过 PBX 向用户发出呼叫, 则中介服务器只能在代理端 (Lync 客户端应用程序和中介服务器之间) 执行 CAC 检查。 由于中介服务器在请求会话时没有终结点设备的相关信息, 因此在建立呼叫之前, 无法在 WAN 链接 (中介服务器和第三方终结点之间) 执行 CAC 检查。 但是, 在建立会话后, 中介服务器将为主干上使用的带宽提供便利。

对于源自第三方终结点的调用, 有关该终结点设备的信息在会话请求时可用, 并且可以在中介服务器的两面上执行 CAC 检查。

<div>


> [!NOTE]
> 请确保终结点设备所属的 IP 子网已配置并与网络站点 2 相关联。<BR>确保将中介服务器的两个接口所属的 IP 子网配置和与网络站点1相关联。<BR>有关详细信息, 请参阅<A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">在 Lync Server 2013 中将子网与网络站点关联</A>。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

