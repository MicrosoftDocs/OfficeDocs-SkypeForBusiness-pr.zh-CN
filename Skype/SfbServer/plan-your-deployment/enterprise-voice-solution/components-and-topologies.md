---
title: Skype for Business 中的呼叫许可控制的组件和拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 在有 MPLS 网络、SIP 中继或第三方 PSTN 网关或 PBX 情况下，规划呼叫允许控制 (CAC)。 适用于 Skype for business 服务器企业版语音。
ms.openlocfilehash: 7fcbc3e8c7fc7b4139fd9c83718db59af099f47f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803112"
---
# <a name="components-and-topologies-for-call-admission-control-in-skype-for-business"></a>Skype for Business 中的呼叫许可控制的组件和拓扑

在有 MPLS 网络、SIP 中继或第三方 PSTN 网关或 PBX 情况下，规划呼叫允许控制 (CAC)。 适用于 Skype for business 服务器企业版语音。

本节中的主题提供了有关通过各种类型的网络拓扑部署呼叫允许控制 (CAC) 的特殊注意事项的信息。

## <a name="call-admission-control-on-an-mpls-network"></a>MPLS 网络上的呼叫允许控制

在多协议标签交换 (MPLS) 网络中，所有站点均以全连通的方式连接。也就是说，所有站点都直接连接到 Internet 服务提供商的 MPLS 主干线，并且每个站点都设置了带宽，以用于通过 WAN 链路连接到 MPLS 云。没有控制 IP 路由的网络集线器或中心站点。下图显示了基于 MPLS 技术的简单网络。

**MPLS 网络示例**

![使用 MPLS 的 CAC](../../media/CAC_MPLS_1.jpg)

要在 MPLS 网络中部署呼叫允许控制 (CAC)，需创建代表 MPLS 云的网络区域，以及代表每个 MPLS 分支站点的网络站点。下图说明如何配置代表上图中的示例 MPLS 网络的网络区域和网络站点。之后，总体带宽限制和带宽会话限制将取决于从每个网络站点连接到代表 MPLS 云的网络区域的 WAN 链路容量。

**MPLS 网络的网络区域和网络站点**

![使用 MPLS 的呼叫允许控制 (CAC) 图](../../media/CAC_MPLS_2.jpg)

## <a name="call-admission-control-on-a-sip-trunk"></a>SIP 中继上的呼叫允许控制

要在 SIP 中继上部署呼叫允许控制 (CAC)，请创建一个代表 Internet 电话服务提供商 (ITSP) 的网络站点。要在 SIP 中继上应用带宽策略值，请创建一个企业内部网络站点和所创建的用于代表 ITSP 的网络站点之间的站点间策略。

下图显示 SIP 中继上的 CAC 部署示例。

**SIP 中继上的 CAC 配置**

![呼叫允许控制 SIP 中继图](../../media/CAC_SIP_trunk_1.jpg)

要在 SIP 中继上配置 CAC，必须在 CAC 部署过程中执行以下任务：

1. 创建一个网络站点，代表 ITSP。将网络站点与相应的网络区域相关联，然后为该网络站点的音频和视频分配零带宽。有关详细信息，请参阅部署文档中的 [Configure Network Sites for CAC](https://technet.microsoft.com/library/afcea38f-5789-45ec-97af-c6e38364950c.aspx)。

    > [!NOTE]
    > 对于 ITSP，该网络站点配置不起作用。带宽策略值实际是在步骤 2 中应用。

2. 使用在步骤 1 中创建的站点的相关参数值，为 SIP 中继创建站点间链接。 例如，使用企业中的网络站点名称作为参数 NetworkSiteID1 的值，并使用 ITSP 网络站点名称作为参数 NetworkSiteID2 的值。 有关详细信息，请参阅部署文档中的[Skype For Business 服务器中的 "创建网络站点间策略](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md)" 和 "[新建-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)"。

3. 从 ITSP 中获取会话边框控制器（SCB）媒体终结点的 IP 地址。 将子网掩码为 32 的 IP 地址添加到代表 ITSP 的网络站点。 有关详细信息，请参阅 [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)。

## <a name="call-admission-control-with-a-third-party-pstn-gateway-or-pbx"></a>使用第三方 PSTN 网关或 PBX 时的呼叫允许控制

本主题介绍了如何在中介服务器的网关界面和第三方公共交换电话网络（PSTN）网关或专用分支交换（PBX）之间的链接上部署呼叫许可控制（CAC）的示例。

### <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a>示例 1：中介服务器与 PSTN 网关之间的 CAC

CAC 可以从中介服务器的网关接口部署到第三方 PBX 或 PSTN 网关的 WAN 链接上。

**示例 1：中介服务器与 PSTN 网关之间的 CAC**

![示例 1：中介服务器与 PSTN 网关之间的 CAC](../../media/CAC_gateways_1.jpg)

在此示例中，在中介服务器和 PSTN 网关之间应用 CAC。 如果网络站点1中的 Skype for Business 客户端用户通过网络站点2中的 PSTN 网关放置 PSTN 呼叫，则媒体将通过 WAN link 流动。 因此，将对每个 PSTN 会话执行以下两个 CAC 检查：

- 在 Skype for Business 客户端应用程序和中介服务器之间

- 在中介服务器和 PSTN 网关之间

这同时适用于网络站点 1 中的客户端接收的传入 PSTN 呼叫，以及网络站点 1 中的客户端应用程序发送的传出 PSTN 呼叫。

> [!NOTE]
> 请确保 PSTN 网关所属的 IP 子网已配置并与网络站点 2 相关联。

> [!NOTE]
> 确保将中介服务器的两个接口所属的 IP 子网配置和与网络站点1相关联。

> [!NOTE]
> 有关详细信息，请参阅 [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)。

### <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a>情况2：中介服务器和具有媒体终结点的第三方 PBX 之间的 CAC

此配置与示例 1 类似。 在这两种情况下，中介服务器都知道在 WAN 链接的另一端终止媒体的设备，并且在中介服务器上配置了具有媒体终结点（MTP）的 PSTN 网关或 PBX 的 IP 地址作为下一跃点。

**示例 2：中介服务器与具有 MTP 的第三方 PBX 之间的 CAC**

![示例 2：中介服务器与具有 MTP 的 PBX 之间的 CAC](../../media/CAC_gateways_2.jpg)

在此示例中，在中介服务器和 PBX/MTP 之间应用 CAC。 如果网络站点1中的 Skype for Business 客户端用户通过位于网络 Site 2 中的 PBX/MTP 放置 PSTN 呼叫，则媒体将通过 WAN 链接进行流动。 因此，将对每个 PSTN 会话执行以下两个 CAC 检查：

- 在 Skype for Business 客户端应用程序和中介服务器之间

- 在中介服务器和 PBX/MTP 之间

这同时适用于网络站点 1 中的客户端接收的传入 PSTN 呼叫，以及网络站点 1 中的客户端发送的传出 PSTN 呼叫。

> [!NOTE]
> 请确保 MTP 所属的 IP 子网已配置并与网络站点 2 相关联。

> [!NOTE]
> 确保将中介服务器的两个接口所属的 IP 子网配置和与网络站点1相关联。

> [!NOTE]
> 有关详细信息，请参阅 [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)。

### <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a>情况3：在中介服务器与没有媒体终结点的第三方 PBX 之间使用 CAC

示例 3 与前两个示例略有不同。 如果在第三方 PBX 上没有 MTP，而对于第三方 PBX 的传出会话请求，则中介服务器不知道媒体将在 PBX 边界内终止的位置。 在这种情况下，媒体将直接在中介服务器和第三方终结点设备之间流动。

**示例 3：中介服务器与没有 MTP 的第三方 PBX 之间的 CAC**

![示例 3：中介服务器与不具有 MTP 的 PBX 之间的 CAC](../../media/CAC_gateways_3.jpg)

在此示例中，如果网络站点1上的 Skype for Business 客户端用户通过 PBX 向用户发出呼叫，则中介服务器只能在代理端（Skype for Business 客户端应用程序和中介服务器之间）执行 CAC 检查。 由于中介服务器在请求会话时没有终结点设备的相关信息，因此在建立呼叫之前，无法在 WAN 链接（中介服务器和第三方终结点之间）执行 CAC 检查。 但是，在建立会话后，中介服务器将为主干上使用的带宽提供便利。

对于源自第三方终结点的调用，有关该终结点设备的信息在会话请求时可用，并且可以在中介服务器的两面上执行 CAC 检查。

> [!NOTE]
> 请确保终结点设备所属的 IP 子网已配置并与网络站点 2 相关联。

> [!NOTE]
> 确保将中介服务器的两个接口所属的 IP 子网配置和与网络站点1相关联。

> [!NOTE]
> 有关详细信息，请参阅 [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)。


