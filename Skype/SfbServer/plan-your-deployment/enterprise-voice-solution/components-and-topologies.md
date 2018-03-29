---
title: Skype for Business 2015 中的呼叫允许控制组件和拓扑
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
description: 在有 MPLS 网络、SIP 中继或第三方 PSTN 网关或 PBX 情况下，规划呼叫允许控制 (CAC)。 对于业务服务器企业语音适用于 Skype。
ms.openlocfilehash: a49c0184c445481146496a9ce90e948f0b1c2f71
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="components-and-topologies-for-call-admission-control-in-skype-for-business-2015"></a>Skype for Business 2015 中的呼叫允许控制组件和拓扑
 
在有 MPLS 网络、SIP 中继或第三方 PSTN 网关或 PBX 情况下，规划呼叫允许控制 (CAC)。 对于业务服务器企业语音适用于 Skype。
  
本节中的主题提供了有关通过各种类型的网络拓扑部署呼叫允许控制 (CAC) 的特殊注意事项的信息。
  
## <a name="call-admission-control-on-an-mpls-network"></a>MPLS 网络上的呼叫允许控制

在多协议标签交换 (MPLS) 网络中，所有站点均以全连通的方式连接。也就是说，所有站点都直接连接到 Internet 服务提供商的 MPLS 主干线，并且每个站点都设置了带宽，以用于通过 WAN 链路连接到 MPLS 云。没有控制 IP 路由的网络集线器或中心站点。下图显示了基于 MPLS 技术的简单网络。
  
**MPLS 网络的示例**

![使用 MPLS 的 CAC](../../media/CAC_MPLS_1.jpg)
  
要在 MPLS 网络中部署呼叫允许控制 (CAC)，需创建代表 MPLS 云的网络区域，以及代表每个 MPLS 分支站点的网络站点。下图说明如何配置代表上图中的示例 MPLS 网络的网络区域和网络站点。之后，总体带宽限制和带宽会话限制将取决于从每个网络站点连接到代表 MPLS 云的网络区域的 WAN 链路容量。
  
**网络区域和 MPLS 网络的网络站点**

![使用 MPLS 的呼叫允许控制 (CAC) 图](../../media/CAC_MPLS_2.jpg)
  
## <a name="call-admission-control-on-a-sip-trunk"></a>SIP 中继上的呼叫允许控制

要在 SIP 中继上部署呼叫允许控制 (CAC)，请创建一个代表 Internet 电话服务提供商 (ITSP) 的网络站点。要在 SIP 中继上应用带宽策略值，请创建一个企业内部网络站点和所创建的用于代表 ITSP 的网络站点之间的站点间策略。
  
下图显示 SIP 中继上的 CAC 部署示例。
  
**CAC SIP 中继配置**

![呼叫允许控制 SIP 中继图](../../media/CAC_SIP_trunk_1.jpg)
  
要在 SIP 中继上配置 CAC，必须在 CAC 部署过程中执行以下任务：
  
1. 创建一个网络站点，代表 ITSP。 将网络站点与相应的网络区域相关联，然后为该网络站点的音频和视频分配零带宽。 有关详细信息，请参见[配置 CAC 的网络站点](http://technet.microsoft.com/library/afcea38f-5789-45ec-97af-c6e38364950c.aspx)部署文档中
    
    > [!NOTE]
    > 对于 ITSP，该网络站点配置不起作用。带宽策略值实际是在步骤 2 中应用。 
  
2. 使用在步骤 1 中创建的站点的相关参数值，为 SIP 中继创建站点间链接。 例如，使用企业中的网络站点名称作为参数 NetworkSiteID1 的值，并使用 ITSP 网络站点名称作为参数 NetworkSiteID2 的值。 细节，请参见部署文档和[新建 CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)中的[业务服务器 2015年的 Skype 在创建站点间的网络策略](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md)。
    
3. 获取会话边框控制器的 (SCB) 的 IP 地址从您的 ITSP 媒体终结点。 将子网掩码为 32 的 IP 地址添加到代表 ITSP 的网络站点。 有关详细信息，请参阅[与网络站点建立子网关联](http://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)。
    
## <a name="call-admission-control-with-a-third-party-pstn-gateway-or-pbx"></a>使用第三方 PSTN 网关或 PBX 时的呼叫允许控制

本主题介绍如何部署中介服务器的网关接口和第三方公共交换的电话网络 (PSTN) 网关或专用分组交换机 (PBX) 之间的链接上调用许可控制 (CAC) 的示例。
  
### <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a>示例 1：中介服务器与 PSTN 网关之间的 CAC

CAC 可部署在 WAN 上到第三方 PBX 或 PSTN 网关中介服务器的网关接口链接。
  
**案例 1: CAC 中介服务器和 PSTN 网关之间**

![示例 1：中介服务器与 PSTN 网关之间的 CAC](../../media/CAC_gateways_1.jpg)
  
在此示例中，CAC 应用中介服务器和 PSTN 网关之间。 如果网络站点 1 处业务客户端用户的 Skype 网络站点 2 中放通过 PSTN 网关呼叫 PSTN，媒体流通过 WAN 链接。 因此，将对每个 PSTN 会话执行以下两个 CAC 检查：
  
- Skype 业务客户端应用程序之间的中介服务器
    
- 中介服务器和 PSTN 网关之间
    
这同时适用于网络站点 1 中的客户端接收的传入 PSTN 呼叫，以及网络站点 1 中的客户端应用程序发送的传出 PSTN 呼叫。
  
> [!NOTE]
> 请确保 PSTN 网关所属的 IP 子网已配置并与网络站点 2 相关联。 
  
> [!NOTE]
> 确保属于中介服务器的两个接口的 IP 子网配置并与网络站点 1 相关联。 
  
> [!NOTE]
> 有关详细信息，请参阅[与网络站点建立子网关联](http://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)。 
  
### <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a>案例 2： 中介服务器和第三方 PBX 与媒体终结点之间的 CAC

此配置与示例 1 类似。 在这两种情况下，中介服务器知道什么设备终止在 WAN 链接另一端的媒体和中介为下一个跃点服务器上配置的 PSTN 网关或 PBX 与媒体终止点 (MTP) 的 IP 地址。
  
**案例 2: CAC 中介服务器和第三方 PBX 与 MTP 之间**

![示例 2：中介服务器与具有 MTP 的 PBX 之间的 CAC](../../media/CAC_gateways_2.jpg)
  
在此示例中，CAC 中介服务器和 PBX MTP 之间应用。 如果业务在网络站点 1 的客户端用户的 Skype 发出 PBX/MTP 网络站点 2 中通过 PSTN 呼叫，媒体流通过 WAN 链接。 因此，将对每个 PSTN 会话执行以下两个 CAC 检查：
  
- Skype 业务客户端应用程序之间的中介服务器
    
- 中介服务器和 PBX MTP 之间
    
这同时适用于网络站点 1 中的客户端接收的传入 PSTN 呼叫，以及网络站点 1 中的客户端发送的传出 PSTN 呼叫。
  
> [!NOTE]
> 请确保 MTP 所属的 IP 子网已配置并与网络站点 2 相关联。 
  
> [!NOTE]
> 确保属于中介服务器的两个接口的 IP 子网配置并与网络站点 1 相关联。 
  
> [!NOTE]
> 有关详细信息，请参阅[与网络站点建立子网关联](http://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)。 
  
### <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a>案例 3: CAC 中介服务器和第三方媒体终结点没有 PBX 之间

示例 3 与前两个示例略有不同。 如果没有任何 MTP 第三方 PBX，传出会话请求向第三方 PBX 中介服务器不知道地方媒体将终止在 PBX 边界。 在这种情况下，媒体流的中介服务器的第三方终结点设备之间的直接。
  
**案例 3: CAC 中介服务器和第三方没有 MTP PBX 之间**

![示例 3：中介服务器与不具有 MTP 的 PBX 之间的 CAC](../../media/CAC_gateways_3.jpg)
  
在此示例中，如果网络站点 1 处业务客户端用户的 Skype 用户通过 PBX、 对中介服务器就可以执行 (Skype 业务客户端应用程序) 之间的中介服务器代理腿上的仅 CAC 检查。 而该会话正在请求中介服务器不具有终结点设备的信息，因为无法在广域网上执行 CAC 检查之前调用建立 （中介服务器和第三方端点） 之间的链接。 建立会话后，但是，中介服务器有助于在主干上所使用的带宽的核算中。
  
对于来自第三方终结点的调用，该终结点设备的有关信息时的会话请求也可 CAC 检查可执行的中介服务器的两面。
  
> [!NOTE]
> 请确保终结点设备所属的 IP 子网已配置并与网络站点 2 相关联。 
  
> [!NOTE]
> 确保属于中介服务器的两个接口的 IP 子网配置并与网络站点 1 相关联。 
  
> [!NOTE]
> 有关详细信息，请参阅[与网络站点建立子网关联](http://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)。 
  

