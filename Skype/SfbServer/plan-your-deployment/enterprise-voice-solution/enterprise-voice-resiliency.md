---
title: 规划业务服务器 Skype 中的企业语音恢复能力
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b3671dcb-6a8b-4a06-84da-0c8837b35099
description: 了解如何支持在 Skype 业务 Server 企业语音，在中央站点和分支站点语音恢复能力。 分支站点选项包括部署 Survivable Branch Appliance 或 Survivable Branch Server。
ms.openlocfilehash: 76b56d7e7d00ecd6d542be3f936af6f2e834974d
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882301"
---
# <a name="plan-for-enterprise-voice-resiliency-in-skype-for-business-server"></a>规划业务服务器 Skype 中的企业语音恢复能力

了解如何支持在 Skype 业务 Server 企业语音，在中央站点和分支站点语音恢复能力。 分支站点选项包括部署 Survivable Branch Appliance 或 Survivable Branch Server。

语音恢复能力是指用户能够继续发起和接收呼叫，如果中央站点的主机 Skype 业务服务器变得不可用，是否通过广域网 (WAN) 故障或其他原因的网络。 如果中央站点发生故障，企业语音服务必须通过无缝故障转移至备份站点以保持不中断。 如果发生 WAN 故障，分支站点的呼叫必须重定向到本地 PSTN 网关。 本节讨论了如何规划在中央站点或 WAN 发生故障时的语音恢复能力。

## <a name="central-site-resiliency"></a>中央站点恢复能力

企业在全球拥有多个站点的情况日益普遍。 维护紧急服务，access 可帮助桌面，并能够执行中央站点停用时的关键业务任务是非常重要的任何企业语音恢复能力解决方案。 当中央站点不可用时，必须满足以下条件：

- 必须提供语音故障转移。

- 通常注册到中央站点的前端池的用户必须能够注册的替代前端池。 这可以通过创建多个 DNS SRV 记录，其中每个解析为控制器池或每个中央站点中的前端池。 使用户通过该管理中心网站提供获得相应的控制器和前端池之前中其他的 SRV 记录，您可以调整的优先级和权重的 SRV 记录。

- 必须将其他站点的用户发送和接收的呼叫重新路由到 PSTN。

本主题介绍可用于保护中央站点语音恢复能力的安全的推荐解决方案。

### <a name="architecture-and-topology"></a>体系结构和拓扑

规划中央站点语音恢复能力要求基本了解中央扮演的角色 Skype 适用于业务服务器注册器中启用语音故障转移。 适用于业务服务器注册器 Skype 是一种服务，使客户端注册和身份验证并提供了路由服务。 在所有 Standard Edition server、 前端服务器、 Director、 或 Survivable Branch Appliance 上运行。 注册器池包括前端池上运行并驻留在同一站点的注册器服务。 通过下面的发现机制，业务客户端 Skype 发现的前端池：

1. DNS SRV 记录

2. 自动发现 Web 服务

3. DHCP 选项 120

Skype 业务客户端连接到前端池后，它将被定向到一个池中前端服务器负载平衡器的。 该前端服务器，依次重定向到池中首选注册器的客户端。

启用企业语音的每个用户分配给特定的注册器池，这将成为该用户的主注册器池。 在给定的站点上，通常成百上千个用户共享一个主注册器池。 要说明其状态、会议或故障转移依赖于中央站点的任何分支站点用户使用中央站点资源的情况，建议您将每个分支站点用户视作已在中央站点注册的用户。 目前不受限制的分支站点用户，其中包括与 Survivable Branch Appliance 注册的用户数。

为确保中央站点具有发生故障时的语音恢复能力，主注册器池必须有一个单独指定的备份注册器池，该注册器池位于另一个站点。 可以使用拓扑生成器恢复能力设置配置备份。 假定两个站点之间有一个可恢复的 WAN 链路，其主注册器池不再可用的用户将自动定向到备份注册器池。

以下步骤介绍了客户端发现和注册过程：

1. 客户端发现 Skype 业务服务器通过 DNS SRV 记录。 在业务服务器 Skype，可以配置 DNS SRV 记录以返回到 DNS SRV 查询的多个 FQDN。 例如，如果企业 Contoso 具有三个中央站点（北美、欧洲和亚太），且每个中央站点有一个控制器池，则 DNS SRV 记录可以指向每个位置中的控制器池 FQDN。 只要可用位置之一的控制器池，客户端可以连接到第一个跃点 Skype 业务服务器。

    > [!NOTE]
    > 使用控制器池是可选的。 可以改用前端池。

2. 控制器池通知 Skype 业务客户端有关用户的主注册器池和备份注册器池。

3. 业务客户端 Skype 尝试首次连接到用户的主注册器池。 如果主注册器池可用，则该注册器接受注册。 如果主注册器池不可用，业务客户端 Skype 尝试连接到备份注册器池。 如果备份注册器池可用并且已确定用户的主注册器池 （通过指定故障转移间隔内检测缺乏检测信号） 是不可用的备份注册器池接受用户的注册。 备份注册器检测到主注册器再次可用后，备份注册器池会将故障转移客户端重定向到其主池。

### <a name="requirements-and-recommendations"></a>要求与建议

以下有关实现中央站点语音恢复能力的要求和建议适用于大多数组织：

- 主注册器池和备份注册器池所在的站点应由可恢复的 WAN 链路相连。

- 每个中央站点必须包含由一个或多个注册器组成的注册器池。

- 必须使用 DNS 负载平衡和/或硬件负载平衡使每个注册器池负载平衡。 有关规划负载平衡配置的详细信息，请参阅[负载平衡 Skype 的业务要求](../../plan-your-deployment/network-requirements/load-balancing.md)。

- 使用任一 Skype 业务 Server 命令行管理程序**Set-csuser** cmdlet 或 Skype for Business Server Control Panel，必须为每个用户分配给主注册器池。

- 主注册器池必须具有单个备份注册器池，该注册器池位于不同的中央站点。

- 必须将主注册器池配置为可故障转移到备份注册器池。 默认情况下，将主注册器设置为每隔 300 秒故障转移到备份注册器池。 您可以使用适用于业务 Server 拓扑生成器 Skype 更改此间隔。

- 配置故障转移路由。配置该路由后，指定网关，该网关的站点与在主路由中指定的网关的站点不同。

- 如果中央站点包含主管理服务器和网站可能是下, 一段，您将需要重新安装在备份的网站; 您管理工具否则，您将无法更改任何管理设置。

### <a name="dependencies"></a>依赖项

Skype 业务 server 取决于以下的基础结构和软件组件，以确保语音恢复能力：

|**组件** <br/> |**功能** <br/> |
|:-----|:-----|
|DNS  <br/> |解析有关服务器到服务器和服务器到客户端连接的 SRV 记录和 A 记录  <br/> |
|Exchange 和 Exchange Web 服务 (EWS)  <br/> |联系人存储；日历数据  <br/> |
|Exchange 统一消息和 Exchange Web 服务  <br/> |呼叫日志、语音邮件列表、语音邮件  <br/> |
|DHCP 选项 120  <br/> |如果 DNS SRV 不可用，则客户端将尝试使用 DHCP 选项 120 来发现注册器。 为此，必须配置 DHCP 服务器或业务 Server DHCP 的 Skype 必须启用。  <br/> |

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

  - 配置每个用户的 Exchange UM 拨号计划的 Exchange UM 服务器同时中央站点和备份网站，包括但为禁用指定备份的 Exchange UM 服务器。 如果主站点变得不可用，Exchange 管理员必须将备份站点的 Exchange UM 服务器标记为已启用。

    如果上述解决方案均可能，然后 Exchange UM 将不可用在事件的中央站点变得不可用。

- 所有类型的会议

    故障转移到备份站点的用户，可以加入到由其池可用但不能在自己的主池（不再可用）上创建或承载会议的组织者创建或承载的会议。 同样，其他用户无法加入受影响的用户的主池上承载的会议。

在主中央站点停用时，以下语音功能不会工作：

- 会议自动助理

- 基于状态和 DND 的路由

- 更新呼叫转接设置

- 响应组服务和呼叫寄存

- 设置新的电话和客户端

- 通讯簿 Web 搜索

## <a name="branch-site-resiliency"></a>分支站点恢复能力

如果您想要提供分支站点恢复能力，即，高可用性企业语音服务，您有这样的三个选项：

- Survivable Branch Appliance

- Survivable Branch Server

- 对于业务服务器部署在分支站点上完全 Skype

本指南将帮助您评估最适合组织的恢复能力解决方案，并基于您的恢复能力解决方案选择要使用的 PSTN 连接解决方案。还将通过介绍先决条件和其他规划注意事项来帮助您准备部署所选择的解决方案。

### <a name="branch-site-resiliency-features"></a>分支站点恢复能力功能

如果分支站点的 WAN 连接到中央站点失败或无法访问管理中心网站是否提供分支站点恢复能力，以下语音功能应继续可用：

- 入站和出站公用电话交换网 (PSTN) 呼叫

- 同一站点的用户间和两个不同站点的用户间的企业呼叫

- 基本呼叫处理功能（包括呼叫保持、取回和转接）

- 双方即时消息

- 呼叫转接、 同时响铃的终结点、 呼叫委派和团队呼叫服务，但仅当在同一站点配置代理者和代理人 （例如，经理和经理的管理员） 或所有团队成员

- 呼叫详细信息记录 (CDR)

- 使用会议自动助理的 PSTN 电话拨入式会议

- 语音邮件功能，前提是配置了语音邮件重新路由设置。

- 用户身份验证和授权

仅当恢复能力解决方案是分支站点的业务服务器部署全面 Skype，则将可采用以下功能：

- IM、Web 会议和 A/V 会议

- 基于状态和请勿打扰 (DND) 的路由（其中将阻止呼叫在已激活 DND 的分机上响铃）

- 更新呼叫转接设置

- 响应组应用程序和呼叫寄存应用程序

- 设置新的电话和客户端，但仅当分支站点上是存在于 Active Directory 域服务。

- 增强型 9-1-1 (E9-1-1)

    如果部署了 E9-1-1，则在中央站点 SIP 中继不可用，因为在 WAN 链接已关闭，然后是 Survivable Branch Appliance 将 E9-1-1 将呼叫路由到本地分支网关。 若要启用此功能，分支站点用户语音策略应将呼叫路由至本地网关发生 WAN 故障时。

> [!NOTE]
> XMPP 不支持 SBA（survivable branch office，自动恢复分支机构）。 用户驻留在 SBA 配置将无法发送即时消息或与 XMPP 联系人看到的状态。

### <a name="branch-site-resiliency-solutions"></a>分支站点恢复能力解决方案

为组织提供分支站点恢复能力的好处显而易见。 具体而言，如果您丢失与中央站点的连接，将继续分支站点用户具有企业语音服务和语音邮件 （如果您配置语音邮件重新路由设置）。 但是，对于用户少于 25 名的站点，复原解决方案可能无法为投资带来相应的回报。

如果决定提供分支站点复原，有三个选项可供使用。使用下表帮助确定最适合贵组织的选项。

|**如果...**|**建议使用...**|
|:-----|:-----|
|分支站点承载 25 到 1000 位用户，并且投资回报不支持完整部署，或本地管理支持不可用  <br/> |Survivable Branch Appliance  <br/> Survivable Branch Appliance 是与业务服务器注册器 Skype 行业标准刀片服务器和 Windows Server 2008 R2 上运行的中介服务器。 Survivable Branch Appliance 还包含一个公用电话交换网 (pstn) 网关。 合格第三方设备（由 Microsoft 合作伙伴在 Survivable Branch Appliance (SBA) 资格鉴定/认证计划中开发）在 WAN 发生故障时可以提供连续的 PSTN 连接，但不能提供可恢复的状态和会议，因为这些功能依赖于中央站点的前端服务器。  <br/> 有关 Survivable Branch Appliance 的详细信息，请参阅本主题后面的"Survivable Branch Appliance 详细信息"。  <br/> **注意：** 如果您决定在 Survivable Branch Appliance，也使用 SIP 中继，请联系 Survivable Branch Appliance 供应商，以了解有关该服务提供程序最适合于组织。 <br/> |
|承载 1000年到 2000年位分支站点的用户，缺少可恢复的 WAN 连接，并且具有经过 Skype 培训为可用的业务服务器管理员  <br/> |Survivable Branch Server 或两个 Survivable Branch Appliance。  <br/> Survivable Branch Server 是会议指定的硬件要求已安装的业务服务器注册器和中介服务器软件的 Skype 的 Windows 服务器。 它必须连接到 PSTN 网关或电话服务提供商的 SIP 中继。  <br/> 有关 Survivable Branch Server 的详细信息，请参阅本主题后面的"Survivable Branch Server 详细信息"。  <br/> |
|如果您需要中的状态和会议功能对语音功能为最多 5000 位用户，并且具有经过培训 Skype 为可用的业务服务器管理员  <br/> |将 Standard Edition Server 部署为中央站点，而非分支站点。  <br/> 对于业务服务器部署全面 Skype 提供连续的 PSTN 连接和可恢复的状态和会议发生 WAN 故障时。  <br/> |

#### <a name="resiliency-topologies"></a>复原拓扑

下图显示了推荐的分支站点复原拓扑。

**分支站点复原选项**

![语音分支站点恢复能力选项](../../media/Plan_OCS_Voice_BranchResiliencyOptions.jpg)

#### <a name="survivable-branch-appliance-details"></a>Survivable Branch Appliance 详细信息

业务服务器 Survivable Branch appliance Skype 包括以下组件：

- 注册器，用于用户身份验证、注册和呼叫路由

- 中介服务器，用于处理注册器和 PSTN 网关之间的信号

- PSTN 网关，用于在 WAN 中断时，将呼叫作为回退传输路由到 PSTN

- SQL Server Express，用于本地用户数据存储

Survivable Branch Appliance 还包括 PSTN 中继、 模拟端口和以太网适配器。

如果分支站点的 WAN 连接到中央站点变得不可用，内部分支用户继续注册的 Survivable Branch Appliance 注册器，并使用 Survivable Branch Appliance 连接获取不间断的语音服务到 PSTN。 从主机或其他远程位置进行连接的分支站点用户，可在连接到分支站点的 WAN 链路不可用时，在中央站点上的注册服务器中注册。 这些用户将具有完整的统一通信功能，一个例外是分支站点的入站呼叫将转到语音邮件。 WAN 连接可用时，将为分支站点用户恢复完整功能。 既不是 Survivable Branch Appliance 到故障转移，也不恢复服务需要 IT 管理员的状态。

Skype 业务服务器支持在分支站点的最多两个 Survivable Branch Appliance。

#### <a name="survivable-branch-appliance-deployment-overview"></a>Survivable Branch Appliance 部署概述

制造通过与 Microsoft 合作关系中的原始设备制造商和代表其拨打增值零售商部署 Survivable Branch Appliance。 仅在已在中央站点部署的企业服务器的 Skype、 与分支站点的 WAN 连接处于的位置，并分支站点用户启用企业语音后，应进行此部署。

有关这些阶段的详细信息，请参阅部署文档中的[Deploying a Survivable Branch Appliance or Server](https://technet.microsoft.com/library/cb780c14-dc5f-41ba-8092-f20ae905bd16.aspx) 。

|**阶段**|**步骤**|**用户权限**|
|:-----|:-----|:-----|
|设置为 Survivable Branch Appliance 的 Active Directory 域服务  <br/> |**在中央站点：** <br/>  为将安装和激活 Survivable Branch Appliance 分支站点技术人员创建域用户帐户 （或企业标识）。 <br/>  为 Survivable Branch Appliance Active Directory 域服务中创建计算机帐户 （以及适用的完全限定域名 (FQDN) 中）。 <br/>  在拓扑生成器中，创建并发布 Survivable Branch Appliance。 <br/> |技术人员用户帐户必须是 RTCUniversalSBATechnicians 的成员。 Survivable Branch Appliance 必须属于 RTCSBAUniversalServices 组中，如果您使用拓扑生成器将自动清除。  <br/> |
|安装和激活 Survivable Branch Appliance。  <br/> |**在分支站点：** <br/>  将 Survivable Branch Appliance 连接到以太网端口和 PSTN 端口。 <br/>  启动 Survivable Branch Appliance。 <br/>  Survivable Branch Appliance 加入域，使用为中央站点 Survivable Branch Appliance 创建域用户帐户。 设置 FQDN 和 IP 地址以匹配在计算机帐户中创建的 FQDN。 <br/>  配置 Survivable Branch Appliance 使用 OEM 用户界面。 <br/>  测试 PSTN 连接。 <br/> |技术人员用户帐户必须是 RTCUniversalSBATechnicians 的成员。  <br/> |

#### <a name="survivable-branch-server-details"></a>Survivable Branch Server 详细信息

在拓扑生成器创建分支站点中，添加 Survivable Branch Server 到该网站，然后再运行 Skype 业务 Server 部署向导的计算机上要安装角色。

### <a name="branch-site-resiliency-requirements"></a>分支站点恢复能力要求

本主题将帮助您为用户准备分支站点恢复能力和语音邮件生存能力，并且还会指定相关的软硬件要求。

#### <a name="preparing-branch-users-for-branch-site-resiliency"></a>为分支用户准备分支站点恢复能力

通过为 Survivable Branch Appliance (SBA) 或 Survivable Branch Server 设置用户的注册器池用户准备分支站点恢复能力。

#### <a name="registrar-assignments-for-branch-users"></a>分支用户的注册器分配

无论选择哪个分支站点恢复能力解决方案，您都需要将主注册器分配给每个用户。 分支站点用户应始终注册的注册器，在分支站点，而不管是否的注册器驻留在 Survivable Branch Appliance、 Survivable Branch Server 或独立的 Skype 业务 Server Standard 或 Enterprise Edition服务器。 需要域名系统 (DNS) 服务 (SRV) 资源记录，客户端才能发现其注册器池。 如果是 Survivable Branch Appliance 变得不可用，这是分支站点客户端将自动发现的备份注册器。

如果分支站点没有 DNS 服务器，有两种备用方法配置 Survivable Branch Appliance 或 Survivable Branch Server 的发现：

- 将分支站点的动态主机配置协议 (DHCP) 服务器以指向的完全限定的域名 (FQDN) 的 Survivable Branch Appliance 或 Survivable Branch Server 上配置 DHCP 选项 120。

- 配置 Survivable Branch Appliance 或 Survivable Branch Server，以响应 DHCP 120 查询。

#### <a name="voice-routing-for-branch-users"></a>分支用户的语音路由

我们建议您为分支站点中的用户创建单独的用户级别 IP 语音 (VoIP) 策略。 此策略时应使用 Survivable Branch Appliance 或分支服务器网关的主路由和中继使用在中央站点的公用电话交换网 (pstn) 网关的一个或多个备份路由。 如果主路由不可用，则将改用使用一个或多个中央站点网关的备份路由。 这种方式，无论用户注册其中 — 分支站点注册器或中央站点的备份注册器池上 — 用户的 VoIP 策略总是中影响。 这对于处理故障转移的情况是很重要的。 例如，如果您需要重命名 Survivable Branch Appliance 或重新配置 Survivable Branch Appliance 连接到备份注册器池中央站点，然后您必须移动分支站点用户到中心网站的持续时间内。 （有关重命名或重新配置 Survivable Branch Appliance 的详细信息，请参阅[附录 b： 管理 Survivable Branch Appliance](https://technet.microsoft.com/library/2ec9d505-6d39-491c-9524-8cf36866b855.aspx)部署文档中。）如果这些用户不具有用户级 VoIP 策略或用户级拨号计划，当用户移动到另一个网站，中央站点的计划应用于用户默认情况下，而不是分支站点的站点级 VoIP 策略和站点级拨号站点级 VoIP策略和拨号计划、。 在这种情况下，除非备份注册器池所用的站点级别 VoIP 策略和站点级别拨号计划也能应用到这些分支站点用户，否则他们的呼叫将失败。 例如，如果某个位于日本的分支站点上的用户移到位于雷蒙德的中央站点上，那么，其规范化规则是在所有 7 位数字呼叫之前附加 +1425 的拨号计划就可能不会采用适当的方式转换对这些用户的呼叫。

> [!IMPORTANT]
> 创建分支机构备份路由时，建议将两个 PSTN 电话用法记录添加到分支机构用户策略中，并为每个记录分配单独的路由。 路由的第一张、 或主，将指示呼叫到网关的 Survivable Branch Appliance (SBA) 或分支服务器; 相关联第二、 或备份时，路由将指示呼叫到中央站点网关。 在定向呼叫时，SBA 或分支服务器会在尝试所有分配给第一个 PSTN 用法记录的路由后，再尝试第二个用法记录。

为了帮助确保分支网关或 Survivable Branch Appliance 网站的 Windows 组件不可用时为分支站点用户的入站的呼叫，将达到这些用户 (其会发生，例如，如果 Survivable Branch Appliance 或分支网关都进行维护） 创建到中央站点的备份注册器池故障转移路由网关 （或使用您的外线直拨分机 (DID) 提供商） 将重定向传入呼叫。 在此处，呼叫将会通过 WAN 链路路由到分支用户。 确保路由转换遵守与 PSTN 网关或其他中继对等方接受的电话号码格式的号码。 有关创建故障转移路由的详细信息，请参阅[配置故障转移路由](https://technet.microsoft.com/library/76e48df4-3b78-4fb7-b1f7-c1e604b81bad.aspx)。 另外，您还可以为与分支站点网关相关联的中继创建服务级别拨号计划，以规范化传入呼叫。 如果您有两个 Survivable Branch Appliance 分支站点上时，您可以用于创建网站级拨号计划，除非每个单独的服务级别计划是必要。

> [!NOTE]
> 要说明其状态、会议或故障转移依赖于中央站点的任何分支站点用户使用中央站点资源的情况，建议您将每个分支站点用户视作已在中央站点进行注册。 目前不受限制的分支站点用户，其中包括与 Survivable Branch Appliance 注册的用户数。

我们还建议您创建一个用户级别的拨号计划和语音策略，然后将它分配给分支站点用户。 有关详细信息，请参阅[创建或修改拨号计划中 Skype Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md)和部署文档中[创建 VoIP 路由策略为分支用户](https://technet.microsoft.com/library/10deca9f-f870-4a42-b25d-e4fc53108658.aspx)。

#### <a name="routing-extension-numbers"></a>路由分机号

时为分支站点用户准备拨号计划和语音策略，请确保包含规范化规则和转换规则相匹配的字符串和 msRTCSIP 行 （或线路 URI） 中使用的编号格式属性，以便启用 Skype 业务呼叫分支站点用户与中央站点之间用户将被路由正常 — 尤其当呼叫必须重新路由通过 PSTN 因为 WAN 链接不可用。 此外，还需要特别注意包括分机号的已拨号码，而不只是电话号码。

与包含分机号（无论是只包含一个完整的 E.164 电话号码还是包含其他的电话号码）的线路 URI 匹配的标准化规则和转换规则还有其他要求。本节介绍了为带分机号的线路 URI 路由呼叫的几种示例情况。

如果您的组织没有为单个用户配置外线直拨分机 (DID) 电话号码，并且每个用户的线路 URI 只配置了一个分机号，则内部用户只需拨打分机号即可相互呼叫。但是，您必须配置规范化规则，并且这些规则要能应用到与这些分机号相匹配的从分支站点用户发给中央站点用户的呼叫。

如果分支站点和中央站点之间的 WAN 链路可用，那么分支站点用户发给中央站点用户的呼叫就无需通过匹配的规范化规则来转换号码，因为该呼叫不会通过 PSTN 来路由。例如：

|**规则名称**|**说明**|**号码模式**|**转换**|**示例**|
|:-----|:-----|:-----|:-----|:-----|
|5digitExtensions  <br/> |不要转换 5 位数字  <br/> |^(\d{5})$  <br/> |$1  <br/> |10001 无法转换  <br/> |

您还必须针对特定的方案考虑分机号，如分支站点和中央站点之间的 WAN 链路不可用，以及必须通过 PSTN 路由来自分支站点的呼叫等情况。 在 WAN 中断，如果分支站点用户只能由拨中央站点用户的分机，调用管理中心网站用户必须具有添加中央站点用户的完整电话号码的出站转换规则。 如果用户的线路 URI 包含贵组织的完整电话号码和用户的唯一的分机号，而不是特定于用户的完整电话号码，则您必须将您的组织的完整的电话号码添加改为出站转换规则. 例如：

|**说明**|**匹配模式**|**转换**|**示例**|
|:-----|:-----|:-----|:-----|
|将 5 位数号码为用户的电话号码和分机号转换  <br/> |^(\d{5})$  <br/> |+14255550123;ext=$1  <br/> |10001 将转换为 +14255550123;ext=10001  <br/> |
|将 5 位数号码为贵组织的电话号码和用户的分机号转换  <br/> |^(\d{5})$  <br/> |+14255550100;ext=$1  <br/> |10001 将转换为 +14255550100;ext=10001  <br/> |

在这种情况下，如果处理 PSTN 重新路由任务的中继对等方不支持分机号，则出站转换规则还必须删除分机号。例如：

|**说明**|**匹配模式**|**转换**|**示例**|
|:-----|:-----|:-----|:-----|
|从包含分机号的电话号码中删除分机号  <br/> |^\+(\d\*); ext=(\d\*)$  <br/> |+$1  <br/> |+14255550123;ext=10001 将转换为 +14255550123  <br/> |

WAN 链接是否可用，如果您的组织没有 DID 号码配置为单个用户和用户的线路 URI 包含贵组织的电话号码和用户的唯一的分机号，则必须配置您组织的电话号码线路 URI 与通过中继对等方或 PSTN 网关在分支站点上可以访问号码。 您还必须配置贵组织的电话号码线路 URI 包括其自己的呼叫路由到该号码的唯一扩展名。

#### <a name="preparing-for-voice-mail-survivability"></a>准备语音邮件生存能力

仅在中央站点，而不是在分支站点，通常被安装 Exchange 统一消息 (UM)。 即使分支站点和中央站点之间的 WAN 链路不可用，呼叫者也应能够留下语音邮件。 因此，配置为分支站点用户提供语音邮件的 Exchange UM 自动助理电话号码的线路 URI 需要特殊的注意事项，语音策略中，除了拨号计划和规范化规则适用于该语音邮件数。

Survivable Branch Appliance (Sba) 和 Survivable Branch Server 提供语音邮件生存能力为分支用户 WAN 中断期间。 具体而言，如果您使用的 Survivable Branch Appliance 或 Survivable Branch Server 和 WAN 变得不可用，SBA 或 Survivable Branch Server 重排未应答的呼叫通过 PSTN 到 Exchange UM 在中央站点。 与 SBA 或 Survivable Branch Server，用户还可以检索语音邮件通过 PSTN WAN 中断期间。 最后，Survivable Branch Appliance 或 Survivable Branch Server WAN 中断期间使错过的呼叫通知排队，然后 WAN 还原时将其上载到 Exchange UM 服务器。 为了帮助确保是弹性语音邮件重新路由，请确保添加一个条目的中央站点池 FQDN 和一个条目的边缘服务器 fqdn 到 Survivable Branch Server 上的主机文件。 否则，在分支站点上没有 DNS 服务器的情况下，DNS 解析可能会超时。

我们建议使用以下配置为分支站点用户配置语音邮件生存能力：

- Microsoft Exchange 管理员应配置 Exchange UM 自动助理 (AA) 仅接受消息。 该配置禁用所有其他常规功能（例如，转接给用户或转接给操作员）并将 AA 限制为仅接受邮件。 或者，Exchange 管理员也可以使用常规 AA 或自定义 AA 将呼叫路由至操作员。

- 业务服务器管理员 Skype 应采取 AA 电话号码，并为**exchange um 自动助理**号码的语音邮件重新路由设置 Survivable Branch Appliance 或 branch server 中使用该电话号码。

- Skype 业务服务器管理员应获取 Exchange UM 订阅者访问电话号码并将该号码用作语音邮件重新路由设置 Survivable Branch Appliance 或 Survivable Branch Server 中的**订阅者访问**号码.

- Skype 业务服务器管理员应配置 Exchange UM，以便只有一个拨号计划与在 WAN 中断期间需访问语音邮件的所有分支用户关联。

- WAN 链接不可用时，为分支站点用户的呼叫可以路由到用户的 Exchange 统一消息 (UM) 的语音邮箱，但仅当的语音策略应用于调用指定是唯一的不包含扩展名的语音邮件电话号码数。

#### <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a>分支站点恢复能力的软硬件要求

根据您的恢复能力解决方案，软硬件要求可能会有所不同。

#### <a name="requirements-for-survivable-branch-appliances"></a>Survivable Branch Appliance 的要求

Survivable Branch Appliance 内置是必需的硬件和软件。 但是，我们还是建议每个分支站点部署 DHCP 服务器以获取客户端 IP 地址；否则，当 DHCP 租赁到期时，客户端将失去 IP 连接。

如果企业 DNS 服务器位于仅在中央站点中，分支站点用户将无法在 WAN 中断，连接到其并因此 Skype 的业务服务器发现使用 DNS SRV （服务 (SRV) 资源记录），将失败。 要确保在 WAN 中断期间提示重新路由，必须在分支站点上缓存 DNS 记录。 如果分支路由器支持 DNS 缓存，则为分支路由器启用 DNS 缓存。 或者，可以在分支上部署 DNS 服务器。 这可以是独立服务器或支持 DNS 功能是 Survivable Branch Appliance 的版本。 有关详细信息，请与您 Survivable Branch Appliance 的提供商。

> [!NOTE]
> 分支站点中不必有域控制器。 Survivable Branch Appliance 进行客户端使用特殊的时其登录以响应客户端的证书请求发送客户端证书身份验证。

Skype 业务客户端可以使用 DHCP 选项 120 （SIP 注册器选项） 的业务服务器发现 Skype。 可通过以下两种方法之一配置该功能：

- 在分支站点来答复 DHCP 120 查询，返回的注册器 FQDN Survivable Branch Appliance 或 Survivable Branch Server 配置 DHCP 服务器。

- 为 Business Server DHCP 打开 Skype。 这打开时，适用于业务服务器注册器 Skype 响应 DHCP 选项 120 查询。 请注意，该注册器不会响应除 DHCP 选项 120 之外的任何 DHCP 查询。

此外，对于具有多个子网的大型分支站点，应启用 DHCP 中继代理来将 DHCP 选项 120 查询转发给 DHCP 服务器（配置 1）或注册器（配置 2）。

最后，必须为企业语音配置分支站点用户并将其设置使用适当的统一的通信终结点。

#### <a name="requirements-for-survivable-branch-servers"></a>Survivable Branch Server 的要求

Survivable Branch Server 的要求是前端服务器的要求相同。 有关详细信息，请参阅[业务服务器 2015年的 Skype 服务器要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。

#### <a name="requirements-for-full-scale-skype-for-business-server-branch-site-deployments"></a>全面的 Skype for Business Server 分支站点部署的要求

有关详细信息，请参阅规划文档中的[业务服务器 2015年的 Skype 服务器要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。

### <a name="example-configuring-a-failover-route"></a>示例：配置故障转移路由

 以下示例显示在 Dallas-GW1 因维护而关闭或因其他原因不可用时，管理员如何定义故障转移路由以供使用。下面的表显示了所需的配置更改。

**表 1. 用户策略**

|**用户策略**|**电话用法**|
|:-----|:-----|
|默认呼叫策略  <br/> |Local  <br/> GlobalPSTNHopoff  <br/> |
|Redmond 本地策略  <br/> |RedmondLocal  <br/> |
|Dallas 呼叫策略  <br/> |名为 DallasUsers  <br/> GlobalPSTNHopoff  <br/> |

**表 2. 路由**

|**路由名称**|**号码模式**|**电话用法**|**中继**|**网关**|
|:-----|:-----|:-----|:-----|:-----|
|Redmond 本地路由  <br/> |^\+1 (425|206|253)(\d{7})$  <br/> |Local  <br/> RedmondLocal  <br/> |Trunk1  <br/> Trunk2  <br/> |Red-GW1  <br/> Red-GW2  <br/> |
|Dallas 本地路由  <br/> |^\+1 (972|214|469)(\d{7})$  <br/> |Local  <br/> |Trunk3  <br/> |Dallas-GW1  <br/> |
|通用路由  <br/> |^\+?(\d\*)$  <br/> |GlobalPSTNHopoff  <br/> |Trunk1  <br/> Trunk2  <br/> Trunk3  <br/> |Red-GW1  <br/> Red-GW2  <br/> Dallas-GW1  <br/> |
|Dallas 用户路由  <br/> |^\+?(\d\*)$  <br/> |名为 DallasUsers  <br/> |Trunk3  <br/> |Dallas-GW1  <br/> |

在表 1 中，名为 GlobalPSTNHopoff 的电话用法添加到 Dallas Calling Policy 中的 DallasUsers 电话用法的后面。这样，当 DallasUsers 电话用法的路由不可用时，具有 Dallas Calling Policy 的呼叫就可以使用针对 GlobalPSTNHopoff 电话用法配置的路由。


