---
title: Lync Server 2013：如何实现 SIP 中继？
description: Lync Server 2013：如何实现 SIP 中继？。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: How do I implement SIP trunking?
ms:assetid: 273a22b1-8a4c-4187-acf8-c57d5c6598ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425743(v=OCS.15)
ms:contentKeyID: 48183666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10882adc0bff573868dcd07268ed0446385d895c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553148"
---
# <a name="how-do-i-implement-sip-trunking-in-lync-server-2013"></a>如何在 Lync Server 2013 中实现 SIP 中继？

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-03-18_

若要实现 SIP 中继，您必须通过中介服务器路由连接，该服务器充当 Lync Server 2013 客户端与服务提供商和 transcodes 媒体之间的通信会话的代理（如有必要）。

每个中介服务器都有一个内部网络接口和一个外部网络接口。 内部接口连接到前端服务器。 外部接口通常称为网关接口，因为它通常用于将中介服务器连接到公开交换的电话网络， (PSTN) 网关或 ip-pbx。 若要实现 SIP 中继，请将中介服务器的外部接口连接到 ITSP 的外部边缘组件。

<div>


> [!NOTE]  
> ITSP 的外部边缘组件可以是会话边界控制器 (SBC)、路由器或网关。



</div>

有关中介服务器的详细信息，请参阅 [Lync server 2013 中的中介服务器组件](lync-server-2013-mediation-server-component.md)。

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a>集中 SIP 中继和分布式 SIP 中继

*集中* SIP 中继通过您的中心站点路由所有 Internet 协议 (VoIP) 流量，包括分支站点流量。 集中部署模型简单、经济高效，通常是使用 Lync Server 2013 实现 SIP 中继的推荐方法。

*分布式* SIP 中继是一种部署模型，可在其中实现一个或多个分支站点的本地 SIP 中继。 然后，将 VoIP 流量从分支站点直接路由到服务提供商，而无需通过中央站点。

仅在出现以下情况时才需要使用分布式 SIP 中继：

  - 分支站点需要 survivable 电话连接 (例如，如果 WAN 向下) 。 应为每个分支站点分析此要求;某些分支可能需要冗余和故障转移，而其他分支可能不需要。

  - 两个中央站点之间需要弹性。 您需要确保 SIP 中继在每个中央站点终止。 例如，如果您有都柏林和 Tukwila 中心站点，并且两者都仅使用一个站点的 SIP 中继，则其他站点的用户不能发出 PSTN 呼叫。

  - 分支站点和中央站点位于不同的国家/地区。 出于兼容性和合法性考虑，每个国家/地区至少需要一个 SIP 中继。 例如，在欧盟，如果某个国家/地区的通信没有本地终止于中央点，则无法离开该国家/地区。

根据网站的地理位置和您在企业中预期的流量，您可能不希望通过中心 SIP 中继路由所有用户，也可以选择通过分支站点的 SIP 中继路由某些用户。 为分析您的需求，请回答以下问题：

  - 每个网站的大小是多少 (也就是说，为企业语音) 启用了多少个用户？

  - 每个站点中哪个外线直拨分机 (DID) 号码收到的电话呼叫最多？

确定部署集中 SIP 中继还是分布式 SIP 中继之前需要进行成本效益分析。 某些情况下，虽然并不是必需的，但选择分布式部署模型可能会比较有益。 在完全集中的部署中，所有分支站点流量都通过 WAN 链路进行路由。 如果您不想支付 WAN 链路所需的带宽费用，则可能需要使用分布式 SIP 中继。 例如，您可能希望在与中心站点具有联合的分支站点上部署 Standard Edition 服务器，或者您可能想要使用小型网关部署 Survivable 分支设备或 Survivable 分支服务器。

<div>


> [!NOTE]  
> 有关分布式 SIP 中继的详细信息，请参阅 <A href="lync-server-2013-branch-site-sip-trunking.md">Lync Server 2013 中的分支站点 SIP 中继</A>。



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a>支持的 SIP 中继连接类型

Lync Server 支持 SIP 中继的以下连接类型：

  - 多协议标签交换 (MPLS) 是一种专用网络，用于定向数据并将其从一个网络节点传送到下一个网络节点。MPLS 网络中的带宽可与其他订阅者共享，并为每个数据包分配一个标签以便区别每个订阅者的数据。这种连接类型无需使用虚拟专用网 (VPN)。潜在的缺点是过多的 IP 流量会干扰 VoIP 操作，除非为 VoIP 流量指定优先级。

  - 没有其他流量的专用连接（例如，租用的光纤连接或 T1 线路）通常是最安全可靠的连接类型。此连接类型提供最大的呼叫传送容量，但通常也是最昂贵的。无需使用 VPN。专用连接适用于具有大量呼叫或严格的安全和可用性要求的组织。

  - Internet 是成本最低的连接类型，但也是最不可靠的。 Internet 连接是唯一需要 VPN 的 Lync Server SIP 中继连接类型。

<div>

## <a name="selecting-a-connection-type"></a>选择连接类型

最适用于企业的 SIP 中继连接类型取决于企业的需求和预算。

  - 对于大中型企业，MPLS 网络通常是最佳选择。它能提供必需的带宽，且费率比专用网络更低。

  - 大型企业可能需要专用的光纤、T1、T3 或更高连接（在欧盟为 E1、E3 或更高）。

  - 对于呼叫量较低的小型企业或分支站点，通过 Internet 的 SIP 中继可能是最佳选择。 建议大中型站点不要使用此连接类型。

</div>

</div>

<div>

## <a name="bandwidth-requirements"></a>带宽要求

实现所要求的带宽量取决于呼叫容量（必须能够支持的并发呼叫数）。需考虑到带宽可用性，以便能够充分利用购买的峰值容量。使用以下公式计算 SIP 中继峰值带宽的要求：

SIP 中继峰值带宽 = 最大并发呼叫数 x（64 kbps + 标头大小）

<div>


> [!NOTE]  
> 标头最大大小为 20 字节。



</div>

</div>

<div>

## <a name="codec-support"></a>编解码器支持

Lync Server 2013 仅支持以下编解码器：

  - G.711 a-law（主要在北美以外的国家/地区使用）

  - G.711 µ-law（在北美使用）

</div>

<div>

## <a name="internet-telephony-service-provider"></a>Internet 电话服务提供商

SIP 中继连接的服务提供商端的实现方式因 ITSP 而异。 有关部署信息，请与服务提供商联系。 有关认证的 SIP 中继服务提供商的列表，请参阅 [Microsoft 统一通信开放式互操作性计划网站](https://go.microsoft.com/fwlink/?linkid=287029)。

有关 Microsoft 认证的 SIP 中继提供商的详细信息，请与 Microsoft 代表联系。

<div>


> [!IMPORTANT]  
> 您必须使用 Microsoft 认证的服务提供商，才能确保 ITSP 支持遍历 SIP 中继的所有功能（例如，设置和管理会话以及支持所有扩展 VoIP 服务）。Microsoft 技术支持没有扩展到使用非认证提供商的配置。如果当前使用的是未认证 SIP 中继的 Internet 服务提供商，您可以选择继续使用该提供商作为您的 ISP，同时使用 Microsoft 认证的 SIP 中继提供商。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

