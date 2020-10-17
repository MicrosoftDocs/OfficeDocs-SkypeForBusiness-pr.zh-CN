---
title: Lync Server 2013： PSTN 网关部署选项
description: Lync Server 2013： PSTN 网关部署选项。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN gateway deployment options
ms:assetid: d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398899(v=OCS.15)
ms:contentKeyID: 48185445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 871bc4d573e927f83cdb07d4fb2b5d5b954e6383
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565588"
---
# <a name="pstn-gateway-deployment-options-in-lync-server-2013"></a>Lync Server 2013 中的 PSTN 网关部署选项

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-21_

<div>

## <a name="pstn-gateways"></a>PSTN 网关

公用电话交换网 (PSTN) 网关是第三方硬件组件，可直接或通过到 SIP 中继的连接转换企业语音基础结构和 PSTN 之间的信号和媒体。 在任一拓扑中，网关都终止 PSTN。 网关被隔离在其自己的子网中，并通过中介服务器连接到企业网络。

具有多个站点的企业通常在每个站点部署一个或多个网关。 分支站点可以通过网关或通过将网关和服务器组合到单个机箱中的 Survivable 分支设备连接到 PSTN。 如果分支站点使用网关，则在站点上需要注册器和中介服务器，除非 WAN 链路是可恢复的。 在前端服务器上并置的一个或多个中介服务器可以在每个站点上路由一个或多个网关的呼叫。 建议将网站上所需的注册器、中介服务器和网关部署为 Survivable 分支设备。

确定 PSTN 网关的数量、大小和位置可能是规划企业语音基础结构时必须做出的最重要且昂贵的决策。

以下是需要考虑的主要问题。请记住，这些问题的答案都是相互依存的

  - 需要多少个 PSTN 网关？答案取决于用户数量、预期的同时呼叫数（流量负载）以及站点数（每个站点需要一个）。

  - 网关应当为多大？答案取决于站点中的用户数以及流量负载。

  - 网关应当位于何处？答案部分取决于贵组织的拓扑和地理分布。

还应该考虑网关拓扑选项（有关详细信息，请参阅本主题后面的“网关拓扑”）。

<div>

## <a name="mn-trunk-support"></a>M:N 中继支持

中介服务器可以通过多个网关路由呼叫，会话边界控制器 (由 Internet 电话服务提供商提供的) ，也可以是两者的组合。 此外，池中的多个中介服务器可以与多个网关进行交互。 在中介服务器和网关之间定义的逻辑路由称为 *中继*。 当内部用户放置 PSTN 呼叫时，前端池的出站路由逻辑将选择要路由的所有可能可用于路由该特定呼叫的可能组合的中继。 使用 DNS 负载平衡时，如果由于池中的特定中介服务器出现问题而导致呼叫无法到达网关，则会将该呼叫重试到池中的备用中介服务器。

有关规划多个网关的详细信息，请参阅 [Lync Server 2013 中的 M:N 中继](lync-server-2013-m-n-trunk.md)。

有关其他出站路由增强功能的详细信息，请参阅 [Lync Server 2013 中的语音路由](lync-server-2013-voice-routes.md)。

</div>

<div>

## <a name="gateway-topologies"></a>网关拓扑

考虑网关部署的基本问题时，请执行以下步骤：

1.  使用企业语音对要提供 PSTN 连接的网站进行计数。

2.  估计每个站点的流量（用户数和每小时每个用户的平均呼叫数）。

3.  在每个站点部署一个或多个网关来处理预期的流量。

下图显示的是所得到的分布式网关拓扑。

**分布式网关拓扑**

![分布式网关拓扑示意图](images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "分布式网关拓扑示意图")

使用此拓扑，每个站点内工作者之间的呼叫以及站点之间的呼叫都将通过 Intranet 路由。对 PSTN 的呼叫将通过企业 IP 网络路由到与目标号码所在位置最接近的网关。但是，如果贵组织像许多财务机构和其他大型企业那样，支持数十、数百甚至数千个跨越一个或多个大陆的站点，该怎么办？在这种情况下，在每个站点都部署一个单独的网关是不切实际的。

为解决此问题，许多大型公司更愿意部署一个或几个大型电话中心站点，如下图所示。

**电话中央站点拓扑**

![数据中心网关拓扑](images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "数据中心网关拓扑")

在此拓扑中，多个大型网关足以容纳预期的用户负载，在每个中央站点部署。 对于企业中各个用户的所有呼叫都将由公司的电话服务提供商转发到某个中央站点。 中心站点的路由逻辑决定了是应通过 intranet 还是 PSTN 路由呼叫。

</div>

<div>

## <a name="gateway-location"></a>网关的位置

网关的位置还可能决定所选网关的类型及其配置方式。目前有许多 PSTN 协议，但没有一种成为全球标准。如果您所有的网关都位于同一个国家/地区，这不会带来任何问题。但是，如果您在多个国家/地区设置了网关，则必须按照该国家/地区的 PSTN 标准来配置每个网关。而且，经过认证能够在某个国家/地区（例如加拿大）正常工作的网关可能未在印度、巴西或欧盟获得认证。

</div>

<div>

## <a name="gateway-size-and-number"></a>网关的大小和数量

大多数组织都考虑部署大小在 2 到 960 个端口之间的 PSTN 网关。（还有更大的网关，但是这些网关主要由电话服务提供商使用。）请按照下列准则来估计贵组织所需的端口数：

  - 对于电话呼叫数量较少的组织（每个用户每小时一个 PSTN 呼叫），则应当为每 15 个用户分配一个端口。例如，如果有 20 个用户，则需要一个具有两个端口的网关。

  - 对于电话呼叫数量适中的组织（每个用户每小时两个 PSTN 呼叫），则应当为每 10 个用户分配一个端口。例如，如果您有 100 个用户，则将需要在一个或多个网关之间总共分配 10 个端口。

  - 对于电话呼叫数量较多的组织（每个用户每小时三个或更多个 PSTN 呼叫），则应当为每 5 个用户分配一个端口。例如，如果您有 47,000 个用户，则将至少在 10 个较大网关之间总共分配 9,400 个端口。

  - 当贵组织中的用户数量或流量增加时，可以获取额外的端口。

对于您必须支持的任何给定数量的用户，您可以选择部署少量大型网关，也可以选择部署小型网关。通常，建议在一个组织中至少部署两个网关，以便在其中一个网关出现故障时保持可用性。

您部署的每个 PSTN 网关都必须至少有一个对应的中介服务器。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

