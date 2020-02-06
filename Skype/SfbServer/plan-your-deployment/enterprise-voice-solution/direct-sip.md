---
title: Skype for Business 服务器中的直接 SIP 连接
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
ms.assetid: 0a37737d-9628-4e36-b27b-c134fa5a3882
description: 在企业语音版 Skype for Business 服务器以及 PSTN 网关和 IP PBX 之间支持直接 SIP 连接。
ms.openlocfilehash: 1948e08d63aed9d49c70443a386adce6dc65f78e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803052"
---
# <a name="direct-sip-connections-in-skype-for-business-server"></a>Skype for Business 服务器中的直接 SIP 连接

在企业语音版 Skype for Business 服务器以及 PSTN 网关和 IP PBX 之间支持直接 SIP 连接。

您可以使用直接 SIP 连接将 Skype for Business 服务器连接到以下任一操作：

- IP PBX

- PSTN 网关

若要实现直接 SIP 连接，请遵循与实现 SIP 主干基本相同的部署步骤。 在这两种情况下，通过使用中介服务器的外部接口实现连接。 唯一的区别是，你可以将 SIP 中继连接到外部实体（如 ITSP 网关），并将直接 SIP 连接连接到本地网络内的内部实体，如 IP PBX 或公共交换电话网络（PSTN）网关。

## <a name="direct-sip-deployment-options"></a>直接 SIP 部署选项

### <a name="skype-for-business-server-stand-alone"></a>Skype for business Server 独立版
<a name="BKMK_CommunicationsServerStand-Alone"> </a>

如果你的组织使用本部分中介绍的部署之一，则可以使用 Skype for Business 服务器作为组织的部分或全部服务的唯一电话服务解决方案。 本部分详细介绍以下部署：

- **增量部署：** 此选项假设你有现有的专用分支 exchange （PBX）基础结构，并且想要将企业语音增量引入组织内较小的组或团队。

- **仅限 VoIP 的部署：** 此选项假定你考虑在没有传统的电话基础结构的网站上部署企业语音。

#### <a name="incremental-deployment"></a>增量部署

在增量部署中，Skype for business 服务器是单个团队或部门的唯一电话服务解决方案，而组织中的其他用户仍在使用 PBX。 此增量部署策略提供了一种通过受控试点计划在企业中引入 IP 电话的方法。 Microsoft 统一通信最适合使用其通信需求的工作组被移动到企业语音，而其他用户则保留在现有 PBX 上。 可根据需要将其他工作组迁移到企业语音。

如果明确定义的用户组具有共同的通信要求，并且该用户组适用于集中管理，则建议使用 "增量" 选项。 如果你有团队或部门分布在地理区域上方，而您的长途费用成本可能很大，此选项也很有效。 实际上，此选项对于创建其成员可能分散在全球各地的虚拟团队非常有用。 你可以创建、修改或解散此类团队，以便快速响应对业务需求的变化。

下图显示了用于在 PBX 背后部署企业语音的一般拓扑。 这是增量部署的推荐拓扑。

**增量部署选项**

![部门迁移选项图](../../media/Fig28_Departmental_migration_option.jpg)

> [!NOTE]
> 如果您将 Skype for Business 服务器部署连接到认证的直接 SIP 合作伙伴，则不需要在中介服务器和 PBX 之间使用公共交换式电话网络（PSTN）网关。 有关认证直接 SIP 合作伙伴的列表，请参阅[Microsoft 统一通信打开互操作性计划](https://go.microsoft.com/fwlink/p/?linkId=203309)。

> [!NOTE]
> 此图所示的媒体路径启用了媒体旁路（推荐配置）。 如果选择禁用 "绕过媒体"，则媒体路径将通过中介服务器进行路由。

在此拓扑中，将为企业语音启用选定的部门或工作组。 PSTN 网关将启用了 Internet 协议（VoIP）的工作组的语音链接到 PBX。 已启用企业语音的用户（包括远程工作人员）通过 IP 网络进行通信。 通过企业语音用户呼叫 PSTN 和未启用企业语音的同事将路由到相应的 PSTN 网关。 来自仍在 PBX 系统或来自 PSTN 的呼叫者的同事的呼叫将路由到 PSTN 网关，该网关会将呼叫转发到 Skype for Business 服务器进行路由。

有两种推荐配置，可用于将企业语音连接到现有 PBX 基础结构以实现互操作：在 PBX 前面的 PBX 和企业语音背后的企业语音。

#### <a name="enterprise-voice-behind-the-pbx"></a>PBX 背后的企业语音

当企业语音部署在 PBX 背后时，PSTN 的所有调用都将到达 PBX，它将呼叫企业语音用户到 PSTN 网关，并与 pbx 用户通话。

#### <a name="enterprise-voice-in-front-of-the-pbx"></a>PBX 前面的企业语音

如果在 PBX 前面部署了企业语音，所有通话都将进入 PSTN 网关，该网关将呼叫企业语音用户至 Skype for business 服务器，并与 PBX 用户通话。 从企业语音和 PBX 用户到 PSTN 的通话均通过 IP 网络路由到最经济高效的 PSTN 网关。 下表显示了此配置的优点和缺点。

**在 PBX 前面部署企业语音的优点和缺点**

|**最终**|**一些**|
|:-----|:-----|
|PBX 仍可为未启用企业语音的用户提供服务。  <br/> |现有网关可能不支持所需的功能或容量。  <br/> |
|PBX 处理所有较早的设备。  <br/> |需要从 PBX 到 PBX 以及从网关到中介服务器的网关之间的主干。 您可能需要来自服务提供商的更多中继。  <br/> |
|企业语音用户保持相同的电话号码。  <br/> | <br/> |

#### <a name="voip-only-deployment"></a>仅限 VoIP 的部署

企业语音为现有企业提供新的企业和新的 office 网站，从而实现了一个功能完备的 VoIP 解决方案，而无需担心 PBX 集成或导致真正的部署和维护。IP PBX 基础结构的成本。 此解决方案支持现场和远程工作人员。

在此部署中，所有通话都通过 IP 网络进行路由。 对 PSTN 的调用将路由到相应的 PSTN 网关。 Skype for Business 或 Lync Phone Edition 用作 softphone。 远程呼叫控制不可用，因为没有可供用户控制的 PBX 手机。 通过 Exchange 统一消息（UM）的可选部署提供语音邮件和自动助理服务。

> [!NOTE]
> 除了支持 Skype for Business 服务器所需的网络基础结构之外，仅有 VoIP 的部署可以使用小型的合格网关来支持传真机和模拟设备。

下图显示了仅限 VoIP 的部署的典型拓扑。

**仅限 VoIP 的部署选项**

![绿场部署选项](../../media/Fig29_Greenfield_deployment_option.jpg)

> [!NOTE]
> 此图所示的媒体路径启用了媒体旁路（推荐配置）。 如果选择禁用 "绕过媒体"，则媒体路径将通过中介服务器进行路由。

## <a name="pstn-gateway-deployment-options"></a>PSTN 网关部署选项

### <a name="pstn-gateways"></a>PSTN 网关

公共交换式电话网络（PSTN）网关是第三方硬件组件，可直接或通过连接到 SIP 中继在企业语音基础结构和 PSTN 之间转换信号和媒体。 在任一拓扑中，网关将终止 PSTN。 网关被隔离在其自己的子网中，并通过中介服务器连接到企业网络。

具有多个网站的企业通常会在每个网站上部署一个或多个网关。 分支站点可以通过网关或通过 Survivable 分支设备连接到 PSTN，该设备将网关和服务器结合到一个框中。 如果分支站点使用网关，则在网站上需要注册机构和中介服务器，除非 WAN 链接是复原的。 一个或多个中介服务器（在前端服务器上 collocated）可路由每个站点上的一个或多个网关的呼叫。 我们建议将网站上所需的注册机构、中介服务器和网关部署为 Survivable 分支装置。

确定 PSTN 网关的数量、大小和位置可能是规划企业语音基础结构时必须做出的最重要且昂贵的决策。

下面是要考虑的主要问题。 请记住，这些问题的答案都是相互依赖的

- 需要多少个 PSTN 网关？ 答案取决于用户数、预计的同时通话数（流量负载）和网站数（每个网站需要一个）。

- 网关应具有的大小是多少？ 答案取决于网站上的用户数以及流量负载。

- 网关应位于何处？ 答案部分取决于拓扑和组织地理位置分布的部分。

  你还应考虑网关拓扑选项（有关详细信息，请参阅本主题后面的网关拓扑）。

#### <a name="mn-trunk-support"></a>M:N 中继支持

中介服务器可通过多个网关、由 Internet 电话服务提供商提供的会话边界控制器（SBCs）或这两者的组合来路由呼叫。 此外，池中的多个中介服务器可以与多个网关交互。 在中介服务器和网关之间定义的逻辑路由称为主干。 当内部用户置入 PSTN 呼叫时，前端池上的出站路由逻辑将选择哪些干线路由到可能可用于路由特定呼叫的所有可能的组合。 使用 DNS 负载平衡，如果由于池中的特定中介服务器出现问题而导致呼叫无法到达网关，则会将该呼叫重试到池中的备用中介服务器。

有关规划多个网关的详细信息，请参阅[Skype For Business 服务器中的 M:N 主干](m-n-trunk.md)。

有关其他出站路由增强的详细信息，请参阅[呼叫路由](https://technet.microsoft.com/library/a2ddf327-2ec4-407b-af0f-276f2b13eefd.aspx)。

#### <a name="gateway-topologies"></a>网关拓扑

考虑网关部署的基本问题时，请按照以下步骤操作：

1. 使用企业语音对要提供 PSTN 连接的站点进行计数。

2. 估计每个网站上的流量（用户数和每个用户每小时平均通话数）。

3. 在每个站点部署一个或多个网关以处理预期的流量。

在此拓扑中，每个站点和站点之间的工作人员之间的通话均通过 intranet 进行路由。 对 PSTN 的调用通过企业 IP 网络路由到最接近目标号码位置的网关。但是，如果您的组织支持数十个或成百上千个站点分布在一个或多个洲内，那么许多金融机构和其他大型企业都有这些功能？ 在这种情况下，在每个网站上部署单独的网关是不切实际的。

为了解决此问题，许多大型公司更喜欢部署一个或几个大型电话中心站点。

在此拓扑中，将在每个中心站点上部署几个大型网关，足以容纳预期的用户负载。 对企业中的用户的所有呼叫均由公司的电话服务提供商转发到中央站点。 中心网站上的路由逻辑确定是否应通过 intranet 或 PSTN 路由呼叫。

#### <a name="gateway-location"></a>网关位置

网关位置还可以确定你选择的网关类型以及它们的配置方式。 有许多 PSTN 协议，它们都不是全球标准。 如果你的所有网关均位于单个国家/地区，则不会出现问题，但如果你在多个国家/地区中找到网关，则每个国家/地区都必须根据该国家/地区的 PSTN 标准进行配置。 此外，为在加拿大（例如加拿大）内操作认证的网关可能未在印度、巴西或欧盟进行认证。

#### <a name="gateway-size-and-number"></a>网关大小和号码

大多数组织都将考虑从2到多达960端口部署范围内的 PSTN 网关。 （甚至更大的网关，但主要由电话服务提供商使用。）估计你的组织所需的端口数时，请使用以下指南：

- 具有轻型电话使用的组织（每个用户每小时一个 PSTN 呼叫）应该为每15个用户分配一个端口。 例如，如果您有20个用户，将需要一个具有两个端口的网关。

- 具有中等电话服务使用率（每个用户每小时两个 PSTN 呼叫）的组织应为每10个用户分配一个端口。 例如，如果您有100用户，那么您将需要在一个或多个网关之间分配10个端口。

- 使用大量电话服务的组织（每个用户每小时的三个或更多 PSTN 呼叫）应为每五个用户分配一个端口。 例如，如果您有47000用户，则需要在至少10个大型网关之间分配的9400端口总数。

- 在您的组织中增加的用户数或您的组织中的流量量增加时，可以获得其他端口。

对于任何必须支持的用户数，您可以选择部署较少、更大的网关或较小的网关。 通常，建议组织至少两个网关，以便在一个网关出现故障时保持可用性。

你部署的每个 PSTN 网关都必须至少有一个对应的中介服务器。


