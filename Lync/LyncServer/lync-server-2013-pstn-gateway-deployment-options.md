---
title: Lync Server 2013：PSTN 网关部署选项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PSTN gateway deployment options
ms:assetid: d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398899(v=OCS.15)
ms:contentKeyID: 48185445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 137c9996429e953db22bea0c0dbd382f5a7af9a2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823817"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-gateway-deployment-options-in-lync-server-2013"></a>Lync Server 2013 中的 PSTN 网关部署选项

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-21_

<div>

## <a name="pstn-gateways"></a>PSTN 网关

公共交换式电话网络 (PSTN) 网关是第三方硬件组件, 可直接或通过连接到 SIP 中继在企业语音基础结构和 PSTN 之间转换信号和媒体。 在任一拓扑中, 网关将终止 PSTN。 网关被隔离在其自己的子网中, 并通过中介服务器连接到企业网络。

具有多个网站的企业通常会在每个网站上部署一个或多个网关。 分支站点可以通过网关或通过 Survivable 分支设备连接到 PSTN, 该设备将网关和服务器结合到一个框中。 如果分支站点使用网关, 则在网站上需要注册机构和中介服务器, 除非 WAN 链接是复原的。 一个或多个中介服务器 (在前端服务器上 collocated) 可路由每个站点上的一个或多个网关的呼叫。 我们建议将网站上所需的注册机构、中介服务器和网关部署为 Survivable 分支装置。

确定 PSTN 网关的数量、大小和位置可能是规划企业语音基础结构时必须做出的最重要且昂贵的决策。

下面是要考虑的主要问题。 请记住, 这些问题的答案都是相互依赖的

  - 需要多少个 PSTN 网关？ 答案取决于用户数、预计的同时通话数 (流量负载) 和网站数 (每个网站需要一个)。

  - 网关应具有的大小是多少？ 答案取决于网站上的用户数以及流量负载。

  - 网关应位于何处？ 答案部分取决于拓扑和组织地理位置分布的部分。

你还应考虑网关拓扑选项 (有关详细信息, 请参阅本主题后面的网关拓扑)。

<div>

## <a name="mn-trunk-support"></a>M:N 中继支持

中介服务器可通过多个网关、由 Internet 电话服务提供商提供的会话边界控制器 (SBCs) 或这两者的组合来路由呼叫。 此外, 池中的多个中介服务器可以与多个网关交互。 在中介服务器和网关之间定义的逻辑路由称为*主干*。 当内部用户置入 PSTN 呼叫时, 前端池上的出站路由逻辑将选择哪些干线路由到可能可用于路由特定呼叫的所有可能的组合。 使用 DNS 负载平衡, 如果由于池中的特定中介服务器出现问题而导致呼叫无法到达网关, 则会将该呼叫重试到池中的备用中介服务器。

有关规划多个网关的详细信息, 请参阅[Lync Server 2013 中的 M:N 主干](lync-server-2013-m-n-trunk.md)。

有关其他出站路由增强的详细信息, 请参阅[Lync Server 2013 中的语音路由](lync-server-2013-voice-routes.md)。

</div>

<div>

## <a name="gateway-topologies"></a>网关拓扑

考虑网关部署的基本问题时, 请按照以下步骤操作:

1.  使用企业语音对要提供 PSTN 连接的站点进行计数。

2.  估计每个网站上的流量 (用户数和每个用户每小时平均通话数)。

3.  在每个站点部署一个或多个网关以处理预期的流量。

生成的分布式网关拓扑如下图所示。

**分布式网关拓扑**

![分布式网关拓扑图](images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "分布式网关拓扑图")

在此拓扑中, 每个站点和站点之间的工作人员之间的通话均通过 intranet 进行路由。 对 PSTN 的调用通过企业 IP 网络路由到最接近目标号码位置的网关。但是, 如果您的组织支持数十个或成百上千个站点分布在一个或多个洲内, 那么许多金融机构和其他大型企业都有这些功能？ 在这种情况下, 在每个网站上部署单独的网关是不切实际的。

为了解决此问题, 许多大型公司更喜欢部署一个或几个大型电话中心网站, 如下图所示。

**电话中心站点拓扑**

![数据中心网关拓扑](images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "数据中心网关拓扑")

在此拓扑中, 将在每个中心站点上部署几个大型网关, 足以容纳预期的用户负载。 对企业中的用户的所有呼叫均由公司的电话服务提供商转发到中央站点。 中心网站上的路由逻辑确定是否应通过 intranet 或 PSTN 路由呼叫。

</div>

<div>

## <a name="gateway-location"></a>网关位置

网关位置还可以确定你选择的网关类型以及它们的配置方式。 有许多 PSTN 协议, 它们都不是全球标准。 如果你的所有网关均位于单个国家/地区, 则不会出现问题, 但如果你在多个国家/地区中找到网关, 则每个国家/地区都必须根据该国家/地区的 PSTN 标准进行配置。 此外, 为在加拿大 (例如加拿大) 内操作认证的网关可能未在印度、巴西或欧盟进行认证。

</div>

<div>

## <a name="gateway-size-and-number"></a>网关大小和号码

大多数组织都将考虑从2到多达960端口部署范围内的 PSTN 网关。 (甚至更大的网关, 但主要由电话服务提供商使用。)估计你的组织所需的端口数时, 请使用以下指南:

  - 具有轻型电话使用的组织 (每个用户每小时一个 PSTN 呼叫) 应该为每15个用户分配一个端口。 例如, 如果您有20个用户, 将需要一个具有两个端口的网关。

  - 具有中等电话服务使用率 (每个用户每小时两个 PSTN 呼叫) 的组织应为每10个用户分配一个端口。 例如, 如果您有100用户, 那么您将需要在一个或多个网关之间分配10个端口。

  - 使用大量电话服务的组织 (每个用户每小时的三个或更多 PSTN 呼叫) 应为每五个用户分配一个端口。 例如, 如果您有47000用户, 则需要在至少10个大型网关之间分配的9400端口总数。

  - 在您的组织中增加的用户数或您的组织中的流量量增加时, 可以获得其他端口。

对于任何必须支持的用户数, 您可以选择部署较少、更大的网关或较小的网关。 通常, 建议组织至少两个网关, 以便在一个网关出现故障时保持可用性。

你部署的每个 PSTN 网关都必须至少有一个对应的中介服务器。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

