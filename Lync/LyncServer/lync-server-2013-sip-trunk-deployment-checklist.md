---
title: Lync Server 2013：SIP 中继部署清单
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunk deployment checklist
ms:assetid: 94f4f03e-19d5-4198-92be-e4076dbb959a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398755(v=OCS.15)
ms:contentKeyID: 48184891
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef670fc4ae9e8a9acba3277a00fc0daf6ff766b3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764488"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunk-deployment-checklist-for-lync-server-2013"></a>Lync Server 2013 的 SIP 中继部署清单

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-21_

你和你的服务提供商必须交换有关你的各个 SIP 中继终结点的一些基本连接信息，你才能部署 SIP 主干。

获取将连接到的每个 ITSP 网关的以下信息：

  - IP 地址

  - 完全限定的域名（FQDN）

<div>


> [!NOTE]  
> 服务提供商可能要求您连接到多个 ITSP 网关。 在这种情况下，必须在池中的每个 ITSP 网关和每个中介服务器之间配置连接。



</div>

您提供给服务提供商的信息取决于 SIP 中继连接类型：

  - 对于多协议标签交换（MPLS）或专用网络连接，请为 ITSP 提供你的外围网络（也称为 DMZ、隔离区域和屏蔽子网）中的路由器的公共可路由 IP 地址。 验证 ITSP 上的网关或会话边界控制器（SBC）是否可以访问此地址。 还为 ITSP 提供中介服务器的 FQDN。

  - 对于虚拟专用网络（VPN）连接，请为 ITSP 提供 VPN 服务器的 IP 地址。

<div>

## <a name="certificate-considerations"></a>证书注意事项

若要确定是否需要用于 SIP 中继的证书，请查看有关协议支持的 ITSP：

1.  如果你的 ITSP 仅支持传输控制协议（TCP），则不需要证书。

2.  如果你的 ITSP 支持传输层安全（TLS），则 ITSP 必须为你提供证书。

<div>


> [!NOTE]  
> SIP 与实时传输协议（RTP）或安全实时传输协议（SRTP）结合使用，这些协议通过 Internet 协议（VoIP）呼叫以语音方式管理实际语音数据。



</div>

</div>

<div>

## <a name="deployment-process"></a>部署过程

若要实现 SIP 中继连接的 Lync Server 一方，请按照下列步骤操作：

1.  使用 Lync Server 拓扑生成器创建和配置 SIP 域拓扑。 有关详细信息，请参阅在部署文档中的[Lync Server 2013 的拓扑生成器中定义和配置拓扑](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)。

2.  使用 Lync Server "控制面板" 为新的 SIP 域配置语音路由。 有关详细信息，请参阅部署文档中[Lync Server 2013 中的 "配置中继](lync-server-2013-configuring-trunks.md)"。

3.  使用**CsPstnOutboundCall** cmdlet 测试连接性。 有关详细信息，请参阅 lync server Management Shell 文档或 Lync Server 命令行管理程序的帮助。

</div>

</div>

<span> </span>

</div>

</div>

</div>

