---
title: 规划Skype for Business Server企业语音复原能力
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b3671dcb-6a8b-4a06-84da-0c8837b35099
description: 了解如何在中心站点和分支站点支持Skype for Business Server 企业语音中的语音复原能力。 分支站点选项包括部署 Survivable Branch Appliance 或 Survivable Branch Server。
ms.openlocfilehash: 493f599f7fbec2a67efaaf59851fd7c2f3b2d144
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675474"
---
# <a name="plan-for-enterprise-voice-resiliency-in-skype-for-business-server"></a>规划Skype for Business Server企业语音复原能力

了解如何在中心站点和分支站点支持Skype for Business Server 企业语音中的语音复原能力。 分支站点选项包括部署 Survivable Branch Appliance 或 Survivable Branch Server。

语音复原是指如果托管Skype for Business Server的中心站点不可用（无论是通过广域网 (WAN) 故障还是其他原因，用户能够继续拨打和接听呼叫。 如果中央站点发生故障，企业语音服务必须通过无缝故障转移至备份站点以保持不中断。 如果发生 WAN 故障，分支站点的呼叫必须重定向到本地 PSTN 网关。 本节讨论了如何规划在中央站点或 WAN 发生故障时的语音恢复能力。

## <a name="central-site-resiliency"></a>中心站点复原能力

企业在全球拥有多个站点的情况日益普遍。 对于任何企业语音复原解决方案来说，维护紧急服务、访问技术支持以及在中心站点服务不足时执行关键业务任务的能力至关重要。 当中央站点不可用时，必须满足以下条件：

- 必须提供语音故障转移。

- 通常向中央站点的前端池注册的用户必须能够向备用前端池注册。 这可以通过创建多个 DNS SRV 记录来完成，其中每个记录解析为每个中心站点中的 Director 池或前端池。 可以调整 SRV 记录的优先级和权重，以便由该中心站点服务的用户在其他 SRV 记录中获得相应的 Director 和前端池。

- 必须将其他站点的用户发送和接收的呼叫重新路由到 PSTN。

本主题介绍可用于保护中央站点语音恢复能力的安全的推荐解决方案。

### <a name="architecture-and-topology"></a>体系结构和拓扑

规划中心站点的语音复原能力需要基本了解Skype for Business Server注册机构在启用语音故障转移方面所发挥的核心作用。 Skype for Business Server注册器是一项支持客户端注册和身份验证并提供路由服务的服务。 它在所有Standard Edition服务器、前端服务器、Director 或 Survivable Branch Appliance 上运行。 注册器池由在前端池上运行并驻留在同一站点的注册器服务组成。 Skype for Business客户端通过以下发现机制发现前端池：

1. DNS SRV 记录

2. 自动发现 Web 服务

3. DHCP 选项 120

Skype for Business客户端连接到前端池后，负载均衡器会将其定向到池中的一个前端服务器。 反过来，该前端服务器会将客户端重定向到池中的首选注册机构。

为企业语音启用的每个用户都分配到特定的注册器池，该池将成为该用户的主要注册器池。 在给定的站点上，通常成百上千个用户共享一个主注册器池。 要说明其状态、会议或故障转移依赖于中央站点的任何分支站点用户使用中央站点资源的情况，建议您将每个分支站点用户视作已在中央站点注册的用户。 分支站点用户数（包括注册到 Survivable Branch Appliance 的用户）目前没有限制。

为确保中央站点具有发生故障时的语音恢复能力，主注册器池必须有一个单独指定的备份注册器池，该注册器池位于另一个站点。 可以通过使用拓扑生成器复原设置来配置备份。 假定两个站点之间有一个可恢复的 WAN 链路，其主注册器池不再可用的用户将自动定向到备份注册器池。

以下步骤介绍了客户端发现和注册过程：

1. 客户端通过 DNS SRV 记录发现Skype for Business Server。 在Skype for Business Server中，可以将 DNS SRV 记录配置为将多个 FQDN 返回到 DNS SRV 查询。 例如，如果企业 Contoso 具有三个中央站点（北美、欧洲和亚太），且每个中央站点有一个控制器池，则 DNS SRV 记录可以指向每个位置中的控制器池 FQDN。 只要其中一个位置中的 Director 池可用，客户端就可以连接到第一个跃点Skype for Business Server。

    > [!NOTE]
    > 使用 Director 池是可选的。 可以改用前端池。

2. Director 池将用户的主要注册器池和备份注册器池告知Skype for Business客户端。

3. Skype for Business客户端首先尝试连接到用户的主注册器池。 如果主注册器池可用，则该注册器接受注册。 如果主注册器池不可用，则Skype for Business客户端会尝试连接到备份注册器池。 如果备份注册器池可用，并且已确定用户的主要注册器池不可用， (检测到指定故障转移间隔缺少检测信号，) 备份注册器池接受用户的注册。 备份注册机构检测到主注册器再次可用后，备份注册器池会将故障转移客户端重定向到其主池。

### <a name="requirements-and-recommendations"></a>要求与建议

以下有关实现中央站点语音恢复能力的要求和建议适用于大多数组织：

- 主注册器池和备份注册器池所在的站点应由可恢复的 WAN 链路相连。

- 每个中央站点必须包含由一个或多个注册器组成的注册器池。

- 每个注册器池必须使用 DNS 负载均衡、硬件负载均衡或两者兼有来实现负载均衡。 有关规划负载均衡配置的详细信息，请参阅[Skype for Business的负载均衡要求](../../plan-your-deployment/network-requirements/load-balancing.md)。

- 必须使用 Skype for Business Server Management Shell **set-CsUser** cmdlet 或 Skype for Business Server 控制面板 将每个用户分配到主注册器池。

- 主注册器池必须具有单个备份注册器池，该注册器池位于不同的中央站点。

- 必须将主注册器池配置为可故障转移到备份注册器池。 默认情况下，将主注册器设置为每隔 300 秒故障转移到备份注册器池。 可以使用Skype for Business Server拓扑生成器更改此间隔。

- 配置故障转移路由。 配置该路由后，指定网关，该网关的站点与在主路由中指定的网关的站点不同。

- 如果中心站点包含主管理服务器，并且站点可能会长时间关闭，则需要在备份站点重新安装管理工具;否则，将无法更改任何管理设置。

### <a name="dependencies"></a>相关性

Skype for Business Server取决于以下基础结构和软件组件，以确保语音复原能力：

|**组件** <br/> |**功能** <br/> |
|:-----|:-----|
|DNS  <br/> |解析有关服务器到服务器和服务器到客户端连接的 SRV 记录和 A 记录  <br/> |
|Exchange 和 Exchange Web 服务 (EWS)  <br/> |联系人存储；日历数据  <br/> |
|Exchange 统一消息和 Exchange Web 服务  <br/> |呼叫日志、语音邮件列表、语音邮件  <br/> |
|DHCP 选项 120  <br/> |如果 DNS SRV 不可用，则客户端将尝试使用 DHCP 选项 120 来发现注册器。 若要使此操作正常工作，必须配置 DHCP 服务器，或者必须启用 Skype for Business Server DHCP。  <br/> |

### <a name="survivable-voice-features"></a>Survivable 语音功能

如果上述要求和建议已付诸实行，则备份注册器池将提供以下语音功能：

- 出站 PSTN 呼叫

- 入站 PSTN 呼叫，前提是电话服务提供商支持故障转移到备份站点的功能

- 同一站点的用户间和两个不同站点的用户间的企业呼叫

- 基本呼叫处理功能（包括呼叫保持、取回和转接）

- 双方即时消息和在同一站点的用户间共享音频和视频

- 呼叫转接、终结点同时响铃、呼叫委派和团队呼叫服务，但前提是在同一站点配置呼叫委派的双方或所有团队成员。

- 现有电话和客户端继续工作。

- 呼叫详细信息记录 (CDR)

- 身份验证和授权

在主中央站点停用时，以下语音功能可能会工作，也可能不会工作，具体取决于配置方式：

- 语音邮件处理和检索

    如果要使 Exchange UM 在主中央站点停用时可用，必须执行以下操作之一：

  - 更改 DNS SRV 记录，使中央站点的 Exchange UM 服务器指向其他站点的备份 Exchange UM 服务器。

  - 将每个用户的Exchange UM 拨号计划配置为包括中央站点和备份站点中的Exchange UM 服务器，但将备份Exchange UM 服务器指定为已禁用。 如果主站点不可用，Exchange管理员必须将备份站点上的Exchange UM 服务器标记为已启用。

    如果上述两种解决方案都不可行，则在中心站点不可用的情况下，Exchange UM 将不可用。

- 所有类型的会议

    故障转移到备份站点的用户，可以加入到由其池可用但不能在自己的主池（不再可用）上创建或承载会议的组织者创建或承载的会议。 同样，其他用户也无法加入在受影响用户的主池上托管的会议。

在主中央站点停用时，以下语音功能不会工作：

- 会议自动助理

- 基于状态和 DND 的路由

- 更新呼叫转接设置

- 响应组服务和呼叫寄存

- 设置新的电话和客户端

- 通讯簿 Web 搜索

## <a name="branch-site-resiliency"></a>分支站点复原能力

如果想要提供分支站点复原能力（即高可用性企业语音服务，则有三种选择：

- Survivable Branch Appliance

- 自动恢复分支服务器

- 分支站点的完整Skype for Business Server部署

本指南将帮助您评估最适合组织的恢复能力解决方案，并基于您的恢复能力解决方案选择要使用的 PSTN 连接解决方案。还将通过介绍先决条件和其他规划注意事项来帮助您准备部署所选择的解决方案。

### <a name="branch-site-resiliency-features"></a>分支站点复原功能

如果提供分支站点复原能力，则如果分支站点与中心站点的 WAN 连接失败或中央站点无法访问，则以下语音功能应继续可用：

- 入站和出站公用电话交换网 (PSTN) 呼叫

- 同一站点的用户间和两个不同站点的用户间的企业呼叫

- 基本呼叫处理功能（包括呼叫保持、取回和转接）

- 双方即时消息

- 呼叫转接、终结点同时响铃、呼叫委派和团队呼叫服务，但前提是仅当委派人和委托 (（例如，经理和经理的管理员) 或所有团队成员）在同一站点上配置

- 呼叫详细信息记录 (CDR)

- 使用会议自动助理的 PSTN 电话拨入式会议

- 如果配置语音邮件重路设置，则语音邮件功能。

- 用户身份验证和授权

仅当复原解决方案是分支站点的全面Skype for Business Server部署时，才能使用以下功能：

- IM、Web 会议和 A/V 会议

- 基于状态和请勿打扰 (DND) 的路由（其中将阻止呼叫在已激活 DND 的分机上响铃）

- 更新呼叫转接设置

- 响应组应用程序和呼叫寄存应用程序

- 预配新电话和客户端，但前提是分支站点存在Active Directory 域服务。

- 增强型 9-1-1 (E9-1-1)

    如果已部署 E9-1-1，并且由于 WAN 链接关闭而无法使用中心站点的 SIP 中继，则 Survivable 分支设备会将 E9-1-1 调用路由到本地分支网关。 若要启用此功能，分支站点用户的语音策略应在 WAN 失败时将呼叫路由到本地网关。

> [!NOTE]
> XMPP 不支持 SBA (可生存分支机构) 。 托管在 SBA 配置中的用户将无法发送 IM 或查看具有 XMPP 联系人的状态。

### <a name="branch-site-resiliency-solutions"></a>分支站点复原解决方案

为组织提供分支站点复原的好处显而易见。 具体而言，如果失去与中心站点的连接，如果在) 配置语音邮件重新路由设置，分支站点用户将继续具有企业语音服务和语音邮件 (。 但是，对于用户少于 25 名的站点，复原解决方案可能无法为投资带来相应的回报。

如果决定提供分支站点复原，有三个选项可供使用。使用下表帮助确定最适合贵组织的选项。

|**如果你...**|**建议使用...**|
|:-----|:-----|
|分支站点承载 25 到 1000 位用户，并且投资回报不支持完整部署，或本地管理支持不可用  <br/> |Survivable Branch Appliance  <br/> Survivable Branch Appliance 是行业标准边栏选项卡服务器，Skype for Business Server注册器和中介服务器在 Windows Server 2008 R2 上运行。 Survivable 分支设备还包含公共交换电话网络 (PSTN) 网关。 合格第三方设备（由 Microsoft 合作伙伴在 Survivable Branch Appliance (SBA) 资格鉴定/认证计划中开发）在 WAN 发生故障时可以提供连续的 PSTN 连接，但不能提供可恢复的状态和会议，因为这些功能依赖于中央站点的前端服务器。  <br/> 有关 Survivable Branch Appliance 的详细信息，请参阅本主题后面的“Survivable Branch Appliance Details”。  <br/> **注意：** 如果还决定将 SIP 中继与 Survivable Branch Appliance 配合使用，请联系 Survivable Branch Appliance 供应商，了解哪个服务提供商最适合你的组织。 <br/> |
|在分支站点托管 1000 到 2000 个用户，缺乏弹性 WAN 连接，并且已训练Skype for Business Server管理员可用  <br/> |Survivable Branch Server 或两个 Survivable 分支设备。  <br/> Survivable Branch Server 是满足指定硬件要求的Windows服务器，其上安装了Skype for Business Server注册器和中介服务器软件。 它必须连接到 PSTN 网关或电话服务提供商的 SIP 中继。  <br/> 有关 Survivable Branch Server 的详细信息，请参阅本主题后面的“Survivable Branch Server 详细信息”。  <br/> |
|如果需要存在和会议功能，以及最多 5000 个用户的语音功能，并且已训练Skype for Business Server管理员可用  <br/> |将 Standard Edition Server 部署为中央站点，而非分支站点。  <br/> 全面Skype for Business Server部署提供持续的 PSTN 连接，并在 WAN 失败时提供复原状态和会议。  <br/> |

#### <a name="resiliency-topologies"></a>复原拓扑

下图显示了推荐的分支站点复原拓扑。

**分支站点复原选项**

![语音分支复原选项。](../../media/Plan_OCS_Voice_BranchResiliencyOptions.jpg)

#### <a name="survivable-branch-appliance-details"></a>Survivable Branch Appliance 详细信息

Skype for Business Server Survivable Branch Appliance 包含以下组件：

- 注册器，用于用户身份验证、注册和呼叫路由

- 中介服务器，用于处理注册器和 PSTN 网关之间的信号

- PSTN 网关，用于在 WAN 中断时，将呼叫作为回退传输路由到 PSTN

- SQL Server Express，用于本地用户数据存储

Survivable Branch Appliance 还包括 PSTN 中继、模拟端口和以太网适配器。

如果分支站点与中心站点的 WAN 连接变得不可用，则内部分支用户将继续向 Survivable Branch Appliance 注册机构注册，并使用与 PSTN 的 Survivable Branch Appliance 连接获取不间断的语音服务。 从主机或其他远程位置进行连接的分支站点用户，可在连接到分支站点的 WAN 链路不可用时，在中央站点上的注册服务器中注册。 这些用户将具有完整的统一通信功能，一个例外是分支站点的入站呼叫将转到语音邮件。 WAN 连接可用时，将为分支站点用户恢复完整功能。 故障转移到 Survivable 分支设备和恢复服务都不需要 IT 管理员。

Skype for Business Server在分支站点最多支持两个 Survivable 分支设备。

#### <a name="survivable-branch-appliance-deployment-overview"></a>Survivable Branch Appliance 部署概述

Survivable Branch Appliance 由原始设备制造商与 Microsoft 合作制造，由增值零售商代表其部署。 只有在中心站点部署了Skype for Business Server、与分支站点建立 WAN 连接并启用分支站点用户企业语音后，才应执行此部署。

有关这些阶段的详细信息，请参阅部署文档中的[Deploying a Survivable Branch Appliance or Server](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-a-survivable-branch-appliance-or-server)。

|**阶段**|**步骤**|**用户权限**|
|:-----|:-----|:-----|
|为 Survivable 分支设备设置Active Directory 域服务  <br/> |**在中央站点：** <br/>  为将在分支站点安装和激活 Survivable Branch 设备的技术人员创建域用户帐户 (或企业标识) 。 <br/>  为 Active Directory 域服务 中的 Survivable Branch Appliance (FQDN) ) 创建具有适用完全限定域名的计算机帐户 (。 <br/>  在拓扑生成器中，创建并发布 Survivable Branch 设备。 <br/> |技术人员用户帐户必须是 RTCUniversalSBATechnicians 的成员。 Survivable Branch Appliance 必须属于 RTCSBAUniversalServices 组，在使用拓扑生成器时自动发生。  <br/> |
|安装并激活 Survivable Branch 设备。  <br/> |**在分支站点：** <br/>  将 Survivable Branch 设备连接到以太网端口和 PSTN 端口。 <br/>  "开始"菜单 Survivable Branch 设备。 <br/>  使用为中心站点的 Survivable Branch 设备创建的域用户帐户将 Survivable Branch 设备加入域。 设置 FQDN 和 IP 地址以匹配在计算机帐户中创建的 FQDN。 <br/>  使用 OEM 用户界面配置 Survivable Branch 设备。 <br/>  测试 PSTN 连接。 <br/> |技术人员用户帐户必须是 RTCUniversalSBATechnicians 的成员。  <br/> |

#### <a name="survivable-branch-server-details"></a>Survivable Branch Server 详细信息

在拓扑生成器中，创建分支站点，将 Survivable Branch Server 添加到该站点，然后在要安装该角色的计算机上运行Skype for Business Server部署向导。

### <a name="branch-site-resiliency-requirements"></a>分支站点复原能力要求

本主题将帮助您为用户准备分支站点恢复能力和语音邮件生存能力，并且还会指定相关的软硬件要求。

#### <a name="preparing-branch-users-for-branch-site-resiliency"></a>为分支用户准备分支站点恢复能力

通过将其注册器池设置为 SBA) 或 Survivable Branch Server (Survivable Branch Appliance，为用户准备分支站点复原能力。

#### <a name="registrar-assignments-for-branch-users"></a>分支用户的注册器分配

无论选择哪个分支站点复原解决方案，都需要为每个用户分配一个主注册机构。 分支站点用户应始终在分支站点向注册机构注册，无论注册器是否驻留在 Survivable Branch Appliance、Survivable Branch Server 或独立Skype for Business Server标准服务器还是Enterprise Edition服务器中。 需要域名系统 (DNS) 服务 (SRV) 资源记录，客户端才能发现其注册器池。 如果 Survivable Branch 设备不可用，分支站点客户端会自动发现备份注册器。

如果分支站点没有 DNS 服务器，则可通过两种替代方法配置 Survivable Branch Appliance 或 Survivable Branch Server 的发现：

- 在分支站点的动态主机配置协议 (DHCP) 服务器上配置 DHCP 选项 120，以指向 Survivable Branch Appliance 或 Survivable Branch Server 的完全限定域名 (FQDN) 。

- 配置 Survivable Branch Appliance 或 Survivable Branch Server 以响应 DHCP 120 查询。

#### <a name="voice-routing-for-branch-users"></a>分支用户的语音路由

我们建议您为分支站点中的用户创建单独的用户级别 IP 语音 (VoIP) 策略。 此策略应包括使用 Survivable Branch Appliance 或分支服务器网关的主要路由，以及一个或多个备份路由，这些备份路由将中继与公共交换电话网络配合使用 (PSTN) 中央站点的网关。 如果主路由不可用，则将改用使用一个或多个中央站点网关的备份路由。 这样，无论用户在何处注册（在分支站点注册机构或中央站点的备份注册器池上），用户的 VoIP 策略始终有效。 这对于处理故障转移的情况是很重要的。 例如，如果需要重命名 Survivable Branch Appliance 或重新配置 Survivable Branch Appliance 以连接到中央站点的备份注册器池，则必须在该持续时间内将分支站点用户移动到中心站点。  (有关重命名或重新配置 Survivable Branch Appliance 的详细信息，请参阅 [附录 B：在部署文档中管理 Survivable Branch 设备](/previous-versions/office/lync-server-2013/lync-server-2013-appendix-b-managing-a-survivable-branch-appliance) 。) 如果这些用户没有用户级 VoIP 策略或用户级拨号计划，则当用户移动到另一个站点时，中心站点的站点级 VoIP 策略和站点级拨号计划默认适用于用户， 而不是分支站点级 VoIP 策略和拨号计划。 在这种情况下，除非备份注册器池所用的站点级别 VoIP 策略和站点级别拨号计划也能应用到这些分支站点用户，否则他们的呼叫将失败。 例如，如果某个位于日本的分支站点上的用户移到位于雷蒙德的中央站点上，那么，其规范化规则是在所有 7 位数字呼叫之前附加 +1425 的拨号计划就可能不会采用适当的方式转换对这些用户的呼叫。

> [!IMPORTANT]
> 创建分支机构备份路由时，建议将两个 PSTN 电话用法记录添加到分支机构用户策略中，并为每个记录分配单独的路由。 第一个或主要路由会将调用定向到与 Survivable Branch Appliance (SBA) 或分支服务器关联的网关;第二个路由或备份会将调用定向到中心站点的网关。 在定向呼叫时，SBA 或分支服务器会在尝试所有分配给第一个 PSTN 用法记录的路由后，再尝试第二个用法记录。

若要帮助确保当代理分支设备站点的分支网关或Windows组件不可用时，对分支站点用户的入站呼叫将访问这些用户， (会发生这种情况， 例如，如果 Survivable Branch 设备或分支网关已关闭以进行维护) ，请在网关 (上创建故障转移路由，或者使用 Direct Inward Dialing (DID) 提供程序) 将传入调用重定向到备份中心站点的注册器池。 在此处，呼叫将会通过 WAN 链路路由到分支用户。 请确保路由转换号码以符合 PSTN 网关或其他中继对等方接受的电话号码格式。 有关创建故障转移路由的详细信息，请参阅[Configuring a Failover Route](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-a-failover-route)。 另外，您还可以为与分支站点网关相关联的中继创建服务级别拨号计划，以规范化传入呼叫。 如果在分支站点上有两个 Survivable Branch Appliance，则可以为两者创建站点级拨号计划，除非需要单独的服务级别计划。

> [!NOTE]
> 要说明其状态、会议或故障转移依赖于中央站点的任何分支站点用户使用中央站点资源的情况，建议您将每个分支站点用户视作已在中央站点进行注册。 分支站点用户数（包括注册到 Survivable Branch Appliance 的用户）目前没有限制。

我们还建议您创建一个用户级别的拨号计划和语音策略，然后将它分配给分支站点用户。 有关详细信息，请参阅[Skype for Business Server中创建或修改拨号计划](../../deploy/deploy-enterprise-voice/dial-plans.md)，并在部署文档中[为分支用户创建 VoIP 路由策略](/previous-versions/office/lync-server-2013/lync-server-2013-create-the-voip-routing-policy-for-branch-users)。

#### <a name="routing-extension-numbers"></a>路由分机号

为分支站点用户准备拨号计划和语音策略时，请务必包括与 msRTCSIP 行 (或 Line URI) 属性中使用的字符串和号码格式匹配的规范化规则和转换规则，以便在分支站点用户和中心站点用户之间启用的Skype for Business调用将正确路由，特别是当必须通过 PSTN 重新路由呼叫时，因为 WAN 链接不可用。 此外，还需要特别注意包括分机号的已拨号码，而不只是电话号码。

与包含分机号（无论是只包含一个完整的 E.164 电话号码还是包含其他的电话号码）的线路 URI 匹配的标准化规则和转换规则还有其他要求。本节介绍了为带分机号的线路 URI 路由呼叫的几种示例情况。

如果您的组织没有为单个用户配置外线直拨分机 (DID) 电话号码，并且每个用户的线路 URI 只 配置了一个分机号，则内部用户只需拨打分机号即可相互呼叫。但是，您必须配置规范化规则，并且这些规则要能应用到与这些分机号相匹配的从分支站点用户发给中央站点用户的呼叫。

如果分支站点和中央站点之间的 WAN 链路可用，那么分支站点用户发给中央站点用户的呼叫就无需通过匹配的规范化规则来转换号码，因为该呼叫不会通过 PSTN 来路由。例如：

|**规则名称**|**说明**|**号码模式**|**翻译**|**示例**|
|:-----|:-----|:-----|:-----|:-----|
|5digitExtensions  <br/> |不要转换 5 位数字  <br/> |^(\d{5})$  <br/> |$1  <br/> |10001 无法转换  <br/> |

您还必须针对特定的方案考虑分机号，如分支站点和中央站点之间的 WAN 链路不可用，以及必须通过 PSTN 路由来自分支站点的呼叫等情况。 在 WAN 中断期间，如果分支站点用户仅通过拨号中心站点用户的扩展来调用中心站点用户，则必须有一个出站翻译规则来添加中心站点用户的完整电话号码。 如果用户的线路 URI 包含组织的完整电话号码和用户的唯一扩展号码，而不是用户唯一的完整电话号码，则必须有一个出站翻译规则来改为添加组织的完整电话号码。 例如：

|**说明**|**匹配模式**|**翻译**|**示例**|
|:-----|:-----|:-----|:-----|
|将 5 位数字转换为用户的电话号码和扩展名  <br/> |^(\d{5})$  <br/> |+14255550123;ext=$1  <br/> |10001 将转换为 +14255550123;ext=10001  <br/> |
|将 5 位数字转换为组织的电话号码和用户的扩展名  <br/> |^(\d{5})$  <br/> |+14255550100;ext=$1  <br/> |10001 将转换为 +14255550100;ext=10001  <br/> |

在这种情况下，如果处理 PSTN 重新路由任务的中继对等方不支持分机号，则出站转换规则还必须删除分机号。例如：

|**说明**|**匹配模式**|**翻译**|**示例**|
|:-----|:-----|:-----|:-----|
|从包含分机号的电话号码中删除分机号  <br/> |^\+ (\d\*) ;ext= (\d\*) $  <br/> |+$1  <br/> |+14255550123;ext=10001 将转换为 +14255550123  <br/> |

如果组织未为单个用户配置 DID 号码，并且用户的 Line URI 包含组织的电话号码和用户的唯一扩展号码，则必须使用分支站点中继对等网关或 PSTN 网关可访问的号码配置组织的电话号码行 URI。 还必须将组织的电话号码行 URI 配置为包含其自己的唯一扩展，以便将呼叫路由到该号码。

#### <a name="preparing-for-voice-mail-survivability"></a>准备语音邮件生存能力

Exchange统一消息传送 (UM) 通常仅安装在中心站点而不是分支站点。 即使分支站点和中央站点之间的 WAN 链路不可用，呼叫者也应能够留下语音邮件。 因此，为为分支网站用户提供语音邮件的Exchange UM 自动助理电话号码配置行 URI 除了适用于该语音邮件号码的语音策略、拨号计划和规范化规则外，还需要特别注意事项。

Survivable Branch Appliance (SVA) 和 Survivable Branch Servers 在 WAN 中断期间为分支用户提供语音邮件生存能力。 具体而言，如果使用的是 Survivable Branch Appliance 或 Survivable Branch Server，并且 WAN 不可用，则 SBA 或 Survivable Branch Server 会通过 PSTN 重新路由未接听的调用，以在中心站点Exchange UM。 使用 SBA 或 Survivable Branch Server，用户还可以在 WAN 中断期间通过 PSTN 检索语音邮件。 最后，在 WAN 中断期间，Survivable Branch Appliance 或 Survivable Branch Server 会排队错过呼叫通知，然后在还原 WAN 时将其上传到Exchange UM 服务器。 若要帮助确保语音邮件重新路由具有复原能力，请确保将中央站点池的 FQDN 条目和 Edge Server FQDN 条目添加到 Survivable Branch Server 上的主机文件。 否则，在分支站点上没有 DNS 服务器的情况下，DNS 解析可能会超时。

我们建议使用以下配置为分支站点用户配置语音邮件生存能力：

- Microsoft Exchange管理员应将 Exchange UM 自动助理 (AA) 配置为仅接受消息。 该配置禁用所有其他常规功能（例如，转接给用户或转接给操作员）并将 AA 限制为仅接受邮件。 或者，Exchange 管理员也可以使用常规 AA 或自定义 AA 将呼叫路由至操作员。

- Skype for Business Server管理员应采用 AA 电话号码，并将该电话号码用作 Survivable 分支设备或分支服务器的语音邮件重路设置中的 **交换 um 自动助理** 号码。

- Skype for Business Server管理员应获取Exchange UM 订阅者访问电话号码，并将该号码用作 Survivable Branch Appliance 或 Survivable Branch Server 的语音邮件重新路由设置中的 **订阅者访问** 号码。

- Skype for Business Server管理员应配置Exchange UM，以便只有一个拨号计划与 WAN 中断期间需要访问语音邮件的所有分支用户相关联。

- 当 WAN 链接不可用时，对分支站点用户的呼叫可以路由到用户的Exchange统一消息 (UM) 语音邮箱，但前提是应用于呼叫的语音策略指定唯一且不包括扩展号码的语音邮件电话号码。

#### <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a>分支站点恢复能力的软硬件要求

根据您的恢复能力解决方案，软硬件要求可能会有所不同。

#### <a name="requirements-for-survivable-branch-appliances"></a>Survivable Branch Appliance 的要求

必需的硬件和软件内置于 Survivable Branch 设备中。 但是，我们还是建议每个分支站点部署 DHCP 服务器以获取客户端 IP 地址；否则，当 DHCP 租赁到期时，客户端将失去 IP 连接。

如果企业 DNS 服务器仅位于中心站点中，分支站点用户将无法在 WAN 中断期间连接到它们，因此Skype for Business Server使用 DNS SRV (服务的发现 (SRV) 资源记录) 将失败。 要确保在 WAN 中断期间提示重新路由语音邮件，必须在分支站点上缓存 DNS 记录。 如果分支路由器支持 DNS 缓存，则为分支路由器启用 DNS 缓存。 或者，可以在分支上部署 DNS 服务器。 这可以是独立服务器，也可以是支持 DNS 功能的 Survivable 分支设备的版本。 有关详细信息，请联系 Survivable Branch Appliance 提供程序。

> [!NOTE]
> 分支站点中不必有域控制器。 Survivable Branch 设备使用特殊证书对客户端进行身份验证，该证书在客户端登录时会向客户端发送证书请求。

Skype for Business客户端可以使用 DHCP 选项 120 (SIP 注册器选项) 来发现Skype for Business Server。 可通过以下两种方法之一配置该功能：

- 在分支站点配置 DHCP 服务器以答复 DHCP 120 查询，这些查询返回 Survivable Branch Appliance 或 Survivable Branch Server 上注册器的 FQDN。

- 打开Skype for Business Server DHCP。 启用后，Skype for Business Server注册器会响应 DHCP 选项 120 查询。 请注意，该注册器不会响应除 DHCP 选项 120 之外的任何 DHCP 查询。

此外，对于具有多个子网的大型分支站点，应启用 DHCP 中继代理来将 DHCP 选项 120 查询转发给 DHCP 服务器（配置 1）或注册器（配置 2）。

最后，必须为分支站点用户配置企业语音并使用适当的统一通信终结点进行预配。

#### <a name="requirements-for-survivable-branch-servers"></a>Survivable Branch Server 的要求

Survivable Branch Server 的要求与前端服务器的要求相同。 有关详细信息，请参阅 [Skype for Business Server 2015 的服务器要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。

#### <a name="requirements-for-full-scale-skype-for-business-server-branch-site-deployments"></a>Full-Scale Skype for Business Server Branch-Site部署的要求

有关详细信息，请参阅“规划”文档中[Skype for Business Server 2015 的服务器要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。

### <a name="example-configuring-a-failover-route"></a>示例：配置故障转移路由

 以下示例显示在 Dallas-GW1 因维护而关闭或因其他原因不可用时，管理员如何定义故障转移路由以供使用。下面的表显示了所需的配置更改。

**表 1. 用户策略**

|**用户策略**|**电话用法**|
|:-----|:-----|
|Default Calling Policy  <br/> |本地  <br/> GlobalPSTNHopoff  <br/> |
|Redmond Local Policy  <br/> |RedmondLocal  <br/> |
|Dallas Calling Policy  <br/> |DallasUsers  <br/> GlobalPSTNHopoff  <br/> |

**表 2. 路由**


| **路由名称**             | **号码模式** | **电话用法**         | **树干**                                 | **网关**                                     |
|:---------------------------|:-------------------|:------------------------|:------------------------------------------|:------------------------------------------------|
| Redmond Local Route  <br/> | ^\+1 (425           | 206                     | 253)  (\d{7}) $  <br/>                       | 本地  <br/> RedmondLocal  <br/>                |
| Dallas Local Route  <br/>  | ^\+1 (972           | 214                     | 469)  (\d{7}) $  <br/>                       | 本地  <br/>                                    |
| Universal Route  <br/>     | ^\+？ (\d\*) $  <br/> | GlobalPSTNHopoff  <br/> | Trunk1  <br/> Trunk2  <br/> Trunk3  <br/> | Red-GW1  <br/> Red-GW2  <br/> 达拉斯-GW1  <br/> |
| Dallas Users Route  <br/>  | ^\+？ (\d\*) $  <br/> | DallasUsers  <br/>      | Trunk3  <br/>                             | 达拉斯-GW1  <br/>                               |

在表 1 中，名为 GlobalPSTNHopoff 的电话用法添加到 Dallas Calling Policy 中的 DallasUsers 电话用法的后面。这样，当 DallasUsers 电话用法的路由不可用时，具有 Dallas Calling Policy 的呼叫就可以使用针对 GlobalPSTNHopoff 电话用法配置的路由。