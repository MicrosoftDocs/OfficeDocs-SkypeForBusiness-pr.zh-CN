---
title: Skype for Business 中呼叫允许控制的组件和拓扑
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
description: 规划呼叫允许控制 (CAC) ，如果有 MPLS 网络、SIP 中继或第三方 PSTN 网关或 PBX。 适用于 Skype for Business Server 企业语音。
ms.openlocfilehash: 771b98e10c28248bc917bff2b8128b6258c140c5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109188"
---
# <a name="components-and-topologies-for-call-admission-control-in-skype-for-business"></a>Skype for Business 中呼叫允许控制的组件和拓扑

规划呼叫允许控制 (CAC) ，如果有 MPLS 网络、SIP 中继或第三方 PSTN 网关或 PBX。 适用于 Skype for Business Server 企业语音。

本节中的主题提供了有关通过各种类型的网络拓扑部署呼叫允许控制 (CAC) 的特殊注意事项的信息。

## <a name="call-admission-control-on-an-mpls-network"></a>MPLS 网络上呼叫允许控制

在多协议标签交换 (MPLS) 网络中，所有站点均以全连通的方式连接。也就是说，所有站点都直接连接到 Internet 服务提供商的 MPLS 主干线，并且每个站点都设置了带宽，以用于通过 WAN 链路连接到 MPLS 云。没有控制 IP 路由的网络集线器或中心站点。下图显示了基于 MPLS 技术的简单网络。

**MPLS 网络示例**

![CAC 与 MPLS](../../media/CAC_MPLS_1.jpg)

要在 MPLS 网络中部署呼叫允许控制 (CAC)，需创建代表 MPLS 云的网络区域，以及代表每个 MPLS 分支站点的网络站点。下图说明如何配置代表上图中的示例 MPLS 网络的网络区域和网络站点。之后，总体带宽限制和带宽会话限制将取决于从每个网络站点连接到代表 MPLS 云的网络区域的 WAN 链路容量。

**MPLS 网络的网络区域和网络站点**

![呼叫允许控制 (CAC) MPLS 图](../../media/CAC_MPLS_2.jpg)

## <a name="call-admission-control-on-a-sip-trunk"></a>SIP 中继上的呼叫允许控制

要在 SIP 中继上部署呼叫允许控制 (CAC)，请创建一个代表 Internet 电话服务提供商 (ITSP) 的网络站点。要在 SIP 中继上应用带宽策略值，请创建一个企业内部网络站点和所创建的用于代表 ITSP 的网络站点之间的站点间策略。

下图显示 SIP 中继上的 CAC 部署示例。

**SIP 中继上的 CAC 配置**

![呼叫允许控制 SIP 中继图](../../media/CAC_SIP_trunk_1.jpg)

要在 SIP 中继上配置 CAC，必须在 CAC 部署过程中执行以下任务：

1. 创建一个网络站点，代表 ITSP。 将网络站点与相应的网络区域相关联，然后为该网络站点的音频和视频分配零带宽。 有关详细信息，请参阅部署文档中的[Configure Network Sites for CAC](/previous-versions/office/lync-server-2013/lync-server-2013-configure-network-sites-for-cac)。

    > [!NOTE]
    > 对于 ITSP，该网络站点配置不起作用。 带宽策略值实际是在步骤 2 中应用。

2. 使用在步骤 1 中创建的站点的相关参数值，为 SIP 中继创建站点间链接。 例如，使用企业中的网络站点名称作为参数 NetworkSiteID1 的值，并使用 ITSP 网络站点名称作为参数 NetworkSiteID2 的值。 有关详细信息，请参阅部署文档中的[在 Skype for Business Server](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md)中创建网络站点间策略和[New-CsNetworkInterSitePolicy。](/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)

3. 从 ITSP 获取会话边界控制器 (SCB) 的 IP 地址。 将子网掩码为 32 的 IP 地址添加到代表 ITSP 的网络站点。 有关详细信息，请参阅[Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site)。

## <a name="call-admission-control-with-a-third-party-pstn-gateway-or-pbx"></a>具有第三方 PSTN 网关或 PBX 的呼叫允许控制

本主题介绍如何在中介服务器的网关接口和第三方公用电话交换网 (PSTN) 网关或专用交换机 (PBX) 之间的链接上部署呼叫允许控制 (CAC) 的示例。

### <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a>案例 1：中介服务器和 PSTN 网关之间的 CAC

可以在从中介服务器的网关接口到第三方 PBX 或 PSTN 网关的 WAN 链路上部署 CAC。

**案例 1：中介服务器和 PSTN 网关之间的 CAC**

![案例 1：中介服务器 PSTN 网关之间的 CAC](../../media/CAC_gateways_1.jpg)

本示例在中介服务器和 PSTN 网关之间应用 CAC。 如果网络站点 1 中的 Skype for Business 客户端用户通过网络站点 2 中的 PSTN 网关进行 PSTN 呼叫，则媒体将流经 WAN 链路。 因此，将针对每个 PSTN 会话执行两个 CAC 检查：

- 在 Skype for Business 客户端应用程序和中介服务器之间

- 中介服务器和 PSTN 网关之间

这既适用于到网络站点 1 中客户端的传入 PSTN 呼叫，也适用于从网络站点 1 中的客户端应用程序发出的传出 PSTN 呼叫。

> [!NOTE]
> 确保已配置 PSTN 网关所属的 IP 子网，并且该子网与网络站点 2 相关联。

> [!NOTE]
> 确保已配置中介服务器的两个接口所属的 IP 子网，并且该子网与网络站点 1 关联。

> [!NOTE]
> 有关详细信息，请参阅[Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site)。

### <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a>案例 2：中介服务器与具有媒体终端的第三方 PBX 之间的 CAC

此配置类似于案例 1。 在这两种情况下，中介服务器知道哪些设备终止 WAN 链路的另一端上的媒体，并且 PSTN 网关或具有媒体终端 (MTP) 的 PBX 的 IP 地址在中介服务器上配置为下一个跃点。

**案例 2：中介服务器与具有 MTP 的第三方 PBX 之间的 CAC**

![案例 2：中介服务器 PBX 与 MTP 之间的 CAC](../../media/CAC_gateways_2.jpg)

本示例在中介服务器和 PBX/MTP 之间应用 CAC。 如果网络站点 1 中的 Skype for Business 客户端用户通过位于网络站点 2 中的 PBX/MTP 进行 PSTN 呼叫，则媒体将流经 WAN 链路。 因此，对于每个 PSTN 会话，将执行两个 CAC 检查：

- 在 Skype for Business 客户端应用程序和中介服务器之间

- 在中介服务器和 PBX/MTP 之间

这既适用于网络站点 1 中客户端的传入 PSTN 呼叫，也适用于从网络站点 1 中的客户端发出的传出 PSTN 呼叫。

> [!NOTE]
> 确保已配置 MTP 所属的 IP 子网，并且该子网与网络站点 2 相关联。

> [!NOTE]
> 确保已配置中介服务器的两个接口所属的 IP 子网，并且该子网与网络站点 1 关联。

> [!NOTE]
> 有关详细信息，请参阅[Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site)。

### <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a>案例 3：中介服务器与没有媒体终端的第三方 PBX 之间的 CAC

案例 3 与前两种情况略有不同。 如果第三方 PBX 上没有 MTP，则对于向第三方 PBX 发出的传出会话请求，中介服务器不知道媒体在 PBX 边界中的终止位置。 在这种情况下，媒体直接在中介服务器和第三方终结点设备之间流动。

**案例 3：中介服务器与没有 MTP 的第三方 PBX 之间的 CAC**

![案例 3：中介服务器 PBX 之间没有 MTP 的 CAC](../../media/CAC_gateways_3.jpg)

本示例中，如果网络站点 1 中的 Skype for Business 客户端用户通过 PBX 向用户发送呼叫，则中介服务器仅能对 Skype for Business 客户端应用程序和中介服务器) 之间的代理段 (执行 CAC 检查。 由于在请求会话时中介服务器没有有关终结点设备的信息，因此在呼叫建立之前，无法在中介服务器和第三方终结点 (之间的 WAN 链接) 上执行 CAC 检查。 但是，建立会话后，中介服务器可便于计算中继上使用的带宽。

对于来自第三方终结点的呼叫，有关该终结点设备的信息在会话请求时可用，并且 CAC 检查可在中介服务器的两侧执行。

> [!NOTE]
> 确保已配置终结点设备所属的 IP 子网，并且该子网与网络站点 2 关联。

> [!NOTE]
> 确保已配置中介服务器的两个接口所属的 IP 子网，并且该子网与网络站点 1 关联。

> [!NOTE]
> 有关详细信息，请参阅[Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site)。