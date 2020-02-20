---
title: Lync Server 2013： SIP 中继部署清单
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
ms.openlocfilehash: a2d584b507f677632b28deb1cae28ebfa4cc7bfa
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142698"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sip-trunk-deployment-checklist-for-lync-server-2013"></a>Lync Server 2013 的 SIP 中继部署清单

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-21_

您和服务提供商必须先交换有关各自 SIP 中继终结点的一些基本连接信息，然后才能部署 SIP 中继。

为您将连接到的每个 ITSP 网关获取以下信息：

  - IP 地址

  - 完全限定的域名 (FQDN)

<div>


> [!NOTE]  
> 服务提供商可能会要求您连接到多个 ITSP 网关。 在这种情况下，必须在池中的每个 ITSP 网关和每个中介服务器之间配置连接。



</div>

您为服务提供商提供的信息取决于您的 SIP 中继连接类型：

  - 对于多协议标签交换（MPLS）或专用网络连接，请为 ITSP 提供外围网络（也称为 DMZ、网络隔离区域和屏蔽子网）中的路由器的可公开路由的 IP 地址。 验证 ITSP 上的网关或会话边界控制器（SBC）是否可以访问此地址。 同时为 ITSP 提供中介服务器的 FQDN。

  - 对于虚拟专用网络（VPN）连接，请为 ITSP 提供 VPN 服务器的 IP 地址。

<div>

## <a name="certificate-considerations"></a>证书注意事项

若要确定是否需要用于 SIP 中继的证书，请咨询您的 ITSP 关于协议支持：

1.  如果您的 ITSP 仅支持传输控制协议（TCP），则不需要证书。

2.  如果您的 ITSP 支持传输层安全性（TLS），则 ITSP 必须为你提供证书。

<div>


> [!NOTE]  
> SIP 与实时传输协议（RTP）或安全实时传输协议（SRTP）（用于管理通过 Internet 协议（VoIP）呼叫中的实际语音数据）相关的协议协同工作。



</div>

</div>

<div>

## <a name="deployment-process"></a>部署过程

若要实现 SIP 中继连接的 Lync Server 端，请按照以下步骤操作：

1.  使用 Lync Server 拓扑生成器创建并配置 SIP 域拓扑。 有关详细信息，请参阅部署文档中的在[拓扑生成器中定义和配置拓扑，以使用 Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) 。

2.  使用 "Lync Server 控制面板" 为新的 SIP 域配置语音路由。 有关详细信息，请参阅部署文档中的在[Lync Server 2013 中配置中继](lync-server-2013-configuring-trunks.md)。

3.  使用**CsPstnOutboundCall** cmdlet 测试连接性。 有关详细信息，请参阅 lync server 命令行管理程序文档或 Lync Server 命令行管理程序帮助。

</div>

</div>

<span> </span>

</div>

</div>

</div>

