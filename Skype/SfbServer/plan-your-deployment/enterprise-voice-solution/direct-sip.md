---
title: 直接 SIP 连接Skype for Business Server
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
ms.assetid: 0a37737d-9628-4e36-b27b-c134fa5a3882
description: PSTN 网关和 PSTN Skype for Business Server IP-PBX 之间支持直接 SIP 企业语音。
ms.openlocfilehash: cac0cf06843ed3bf623bd2d3bbe9e92cf6b32a091fd434ac4d422812cc59e60f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54343366"
---
# <a name="direct-sip-connections-in-skype-for-business-server"></a>直接 SIP 连接Skype for Business Server

PSTN 网关和 PSTN Skype for Business Server IP-PBX 之间支持直接 SIP 企业语音。

可以使用直接 SIP 连接将Skype for Business Server连接到以下任一项：

- IP-PBX

- PSTN 网关

要实现直接 SIP 连接，必须按照与实现 SIP 中继基本相同的部署步骤进行操作。 在这两种情况下，都使用中介服务器的外部接口实现连接。 唯一的区别是，应将 SIP 中继连接到外部实体，如 ITSP 网关，而将直接 SIP 连接连接到本地网络中的内部实体，如 IP-PBX 或公用电话交换网 (PSTN) 网关。

## <a name="direct-sip-deployment-options"></a>直接 SIP 部署选项

### <a name="skype-for-business-server-stand-alone"></a>Skype for Business Server Stand-Alone
<a name="BKMK_CommunicationsServerStand-Alone"> </a>

如果您的组织使用本节中所述的部署之一，您可以使用 Skype for Business Server 作为组织部分或所有组织的唯一电话解决方案。 本节详细介绍以下部署：

- **增量部署：** 此选项假定您具有现有的专用交换机 (PBX) 基础结构，并且打算将 企业语音 逐步引入到组织中较小的组或团队。

- **仅 VoIP 部署**：此选项假定您考虑企业语音电话基础结构的站点上部署网络。

#### <a name="incremental-deployment"></a>增量部署

在增量部署中，Skype for Business Server是单个团队或部门的唯一电话解决方案，而组织中其他用户继续使用 PBX。 此增量部署策略提供了一种方法，通过受控试点计划将 IP 电话引入企业。 将通信需求由 Microsoft 统一通信最满足的工作组移至企业语音，而其他用户仍保留在现有 PBX 上。 根据需要，可以将其他工作组企业语音迁移至其他工作组。

如果您明确定义了具有共同通信要求且适合集中管理的用户组，则建议使用增量选项。 如果你的团队或部门分布在广泛的地理区域，其中节省的长途费用可能很大，则此选项也有效。 事实上，此选项可用于创建其成员可能分散在全球的虚拟团队。 可以创建、修改或取消此类团队，以快速响应变化中的业务需求。

下图显示了用于部署 PBX 企业语音的常规拓扑。 这是建议用于增量部署的拓扑。

**增量部署选项**

![部门迁移选项图](../../media/Fig28_Departmental_migration_option.jpg)

> [!NOTE]
> 如果要将 Skype for Business Server 部署连接到经过认证的直接 SIP 合作伙伴，则不需要中介服务器与 PBX 之间的公用电话交换网 (PSTN) 网关。 有关经认证的直接 SIP 合作伙伴的列表，请参阅  [Microsoft 统一通信开放式互操作性计划](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md)。

> [!NOTE]
> 此图中显示的媒体路径已启用媒体旁路 (推荐配置) 。 如果选择禁用媒体旁路，则媒体路径将通过中介服务器进行路由。

在此拓扑中，选定的部门或工作组已启用企业语音。 PSTN 网关将启用了 VoIP (的 VoIP) 语音连接到 PBX。 启用了远程企业语音包括远程工作者）通过 IP 网络进行通信。 用户企业语音 PSTN 和未启用 PSTN 服务的同事企业语音呼叫将路由到相应的 PSTN 网关。 来自仍在 PBX 系统的同事或 PSTN 上的呼叫者的呼叫将路由到 PSTN 网关，PSTN 网关将呼叫转发Skype for Business Server路由。

有两种建议的配置企业语音连接到现有 PBX 基础结构实现互操作性：企业语音 PBX 企业语音 PBX 前面。

#### <a name="enterprise-voice-behind-the-pbx"></a>企业语音PBX 后面

在 PBX 企业语音时，来自 PSTN 的所有呼叫都到达 PBX，PBX 将呼叫路由至 企业语音 用户到 PSTN 网关，而将 PBX 用户的呼叫路由到 PBX。

#### <a name="enterprise-voice-in-front-of-the-pbx"></a>企业语音 PBX 前面

在 PBX 企业语音时，所有呼叫都到达 PSTN 网关，PSTN 网关将 企业语音 用户的呼叫路由至 Skype for Business Server PBX 用户的呼叫路由至 PBX。 来自用户和 PBX 用户企业语音 PSTN 的呼叫通过 IP 网络路由到最经济高效的 PSTN 网关。 下表显示了此配置的优缺点。

**在 PBX 企业语音部署的优缺点**

|**优点**|**缺点**|
|:-----|:-----|
|PBX 仍为未启用此功能企业语音。  <br/> |现有网关可能不支持您需要的功能或容量。  <br/> |
|PBX 处理所有早期设备。  <br/> |需要从网关到 PBX 以及从网关到中介服务器的中继。 您可能需要来自服务提供商的更多中继。  <br/> |
|企业语音用户保留相同的电话号码。  <br/> | <br/> |

#### <a name="voip-only-deployment"></a>VoIP-Only部署

企业语音 提供了新业务以及现有企业的新办公网站，从而有机会实现功能齐全的 VoIP 解决方案，而无需担心 PBX 集成或产生大量 IP-PBX 基础结构的部署和维护成本。 此解决方案支持现场和远程工作者。

在此部署中，所有呼叫均通过 IP 网络路由。 对 PSTN 的呼叫将路由到相应的 PSTN 网关。 Skype for Business或 Lync 电话 Edition 充当软电话。 由于没有 PBX 电话可让用户控制，因此远程呼叫控制不可用且不必要。 语音邮件和自动助理服务通过统一消息和 UM Exchange的可选 (提供) 。

> [!NOTE]
> 除了支持传真机所需的网络基础结构Skype for Business Server，仅 VoIP 部署可以使用一个合格的小型网关来支持传真机和模拟设备。

下图显示了仅 VoIP 部署的典型拓扑。

**仅 VoIP 部署选项**

![绿色部署选项](../../media/Fig29_Greenfield_deployment_option.jpg)

> [!NOTE]
> 此图中显示的媒体路径已启用媒体旁路 (推荐配置) 。 如果选择禁用媒体旁路，则媒体路径将通过中介服务器进行路由。

## <a name="pstn-gateway-deployment-options"></a>PSTN 网关部署选项

### <a name="pstn-gateways"></a>PSTN 网关

公用电话交换网 (PSTN) 网关是第三方硬件组件，可直接或通过到 SIP 中继的连接转换企业语音基础结构和 PSTN 之间的信号和媒体。 在任一拓扑中，网关都终止 PSTN。 网关隔离在其自己的子网中，并通过中介服务器连接到企业网络。

具有多个站点的企业通常在每个站点部署一个或多个网关。 分支站点可以通过网关或 Survivable Branch Appliance 连接到 PSTN，该分支设备将网关和服务器组合在一个框中。 如果分支站点使用网关，则站点上需要注册器服务器和中介服务器，除非 WAN 链路具有弹性。 一个或多个并位于前端服务器的中介服务器可以路由每个站点上一个或多个网关的呼叫。 我们建议将站点上所需的注册器、中介服务器和网关部署为 Survivable Branch Appliance。

确定 PSTN 网关的数量、大小和位置可能是在规划 PSTN 基础结构时必须做出的最重要且企业语音决定。

以下是需要考虑的主要问题。请记住，这些问题的答案都是相互依存的

- 需要多少个 PSTN 网关？答案取决于用户数量、预期的同时呼叫数（流量负载）以及站点数（每个站点需要一个）。

- 网关应当为多大？答案取决于站点中的用户数以及流量负载。

- 网关应当位于何处？答案部分取决于贵组织的拓扑和地理分布。

  还应该考虑网关拓扑选项（有关详细信息，请参阅本主题后面的“网关拓扑”）。

#### <a name="mn-trunk-support"></a>M:N 中继支持

中介服务器可以通过多个网关、会话边界控制器 (Internet) 服务提供商提供的 SDC 或两者的组合来路由呼叫。 此外，池中的多个中介服务器可以与多个网关交互。 中介服务器和网关之间定义的逻辑路由称为中继。 当内部用户拨打 PSTN 呼叫时，前端池上的出站路由逻辑会从可用于路由该特定呼叫的所有可能的组合中选择要路由的中继。 通过 DNS 负载平衡，如果呼叫因池中特定中介服务器的问题而无法到达网关，则呼叫将重试池中的备用中介服务器。

有关规划多个网关的详细信息，请参阅[M：N trunk in Skype for Business Server](m-n-trunk.md)。

有关其他出站路由增强功能，请参阅[Call Routes](/previous-versions/office/lync-server-2013/lync-server-2013-voice-routes)。

#### <a name="gateway-topologies"></a>网关拓扑

考虑网关部署的基本问题时，请执行以下步骤：

1. 使用 PSTN 连接计算要提供 PSTN 连接的企业语音。

2. 估计每个站点的流量（用户数和每小时每个用户的平均呼叫数）。

3. 在每个站点部署一个或多个网关来处理预期的流量。

使用此拓扑，每个站点内工作者之间的呼叫以及站点之间的呼叫都将通过 Intranet 路由。对 PSTN 的呼叫将通过企业 IP 网络路由到与目标号码所在位置最接近的网关。但是，如果贵组织像许多财务机构和其他大型企业那样，支持数十、数百甚至数千个跨越一个或多个大陆的站点，该怎么办？在这种情况下，在每个站点都部署一个单独的网关是不切实际的。

为了解决此问题，许多大型公司倾向于部署一个或几个大型电话中央站点。

在此拓扑中，每个中央站点都部署了几个足以容纳预期用户负载的大型网关。 对于企业中各个用户的所有呼叫都将由公司的电话服务提供商转发到某个中央站点。 中央站点的路由逻辑确定呼叫是应该通过 Intranet 路由还是路由到 PSTN。

#### <a name="gateway-location"></a>网关的位置

网关的位置还可能决定所选网关的类型及其配置方式。目前有许多 PSTN 协议，但没有一种成为全球标准。如果您所有的网关都位于同一个国家/地区，这不会带来任何问题。但是，如果您在多个国家/地区设置了网关，则必须按照该国家/地区的 PSTN 标准来配置每个网关。而且，经过认证能够在某个国家/地区（例如加拿大）正常工作的网关可能未在印度、巴西或欧盟获得认证。

#### <a name="gateway-size-and-number"></a>网关的大小和数量

大多数组织都考虑部署大小在 2 到 960 个端口之间的 PSTN 网关。（还有更大的网关，但是这些网关主要由电话服务提供商使用。）请按照下列准则来估计贵组织所需的端口数：

- 对于电话呼叫数量较少的组织（每个用户每小时一个 PSTN 呼叫），则应当为每 15 个用户分配一个端口。例如，如果有 20 个用户，则需要一个具有两个端口的网关。

- 对于电话呼叫数量适中的组织（每个用户每小时两个 PSTN 呼叫），则应当为每 10 个用户分配一个端口。例如，如果您有 100 个用户，则将需要在一个或多个网关之间总共分配 10 个端口。

- 对于电话呼叫数量较多的组织（每个用户每小时三个或更多个 PSTN 呼叫），则应当为每 5 个用户分配一个端口。例如，如果您有 47,000 个用户，则将至少在 10 个较大网关之间总共分配 9,400 个端口。

- 当贵组织中的用户数量或流量增加时，可以获取额外的端口。

对于您必须支持的任何给定数量的用户，您可以选择部署少量大型网关，也可以选择部署小型网关。通常，建议在一个组织中至少部署两个网关，以便在其中一个网关出现故障时保持可用性。

部署的每个 PSTN 网关都必须至少有一个对应的中介服务器。