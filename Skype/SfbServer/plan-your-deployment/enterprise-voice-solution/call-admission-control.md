---
title: 在 Skype for Business Server 中规划呼叫允许控制
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/16/2018
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
ms.assetid: 6fda0195-4c89-4dea-82e8-624f03e3d062
description: 了解 Skype for Business Server 企业语音 中的呼叫允许控制，如果呼叫的媒体质量较差，它可以阻止企业语音。
ms.openlocfilehash: 07b1e057e9edc296d0eee694e323e3c3c27ef05f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825952"
---
# <a name="plan-for-call-admission-control-in-skype-for-business-server"></a>在 Skype for Business Server 中规划呼叫允许控制

了解 Skype for Business Server 企业语音 中的呼叫允许控制，如果呼叫的媒体质量较差，它可以阻止企业语音。

对于电话、视频和应用程序共享等基于 IP 的应用程序，通常不会将企业网络的可用带宽视为 LAN 环境中的限制因素。 但是，在相互连接站点的 WAN 链路中，可以限制网络带宽。

当网络流量过度订阅 WAN 链路时，使用排队、缓冲和数据包丢弃等当前机制来解决拥塞问题。 额外的流量通常会延迟，直到网络拥塞问题得以缓解，或者必要时会丢弃流量。 对于这些情况下的传统数据流量，接收客户端可以恢复。 但是，对于统一通信等实时流量，无法这样解决网络拥塞问题，因为统一通信流量对延迟和数据包丢失都敏感。 WAN 上的拥塞会导致用户的用户体验质量 (QoE) 降低。 对于拥堵情况中的实时流量，拒绝呼叫实际上比提供质量较差的连接更好。

呼叫允许控制 (CAC) 可确定是否有足够的网络带宽来建立质量可接受的实时会话。 在 Skype for Business Server 中，CAC 仅控制音频和视频实时流量，但不会影响数据流量。 如果默认 WAN 路径不具备所需的带宽，则 CAC 可尝试通过 Internet 路径或公用电话交换网 (PSTN) 路由呼叫。

本节介绍了呼叫允许控制功能，并解释了如何规划 CAC。

> [!NOTE]
> Skype for Business Server 具有三个高级 企业语音 功能：呼叫允许控制 (CAC) 、紧急服务 (E9-1-1) 和媒体旁路。 有关这三项功能共同的规划信息的概述，请参阅 Skype for [Business Server](network-settings-for-advanced-features.md)中高级 企业语音 功能的网络设置。

Skype for Business Server 中的 CAC 设计提供四个主要属性：

- 不需要使用其他设备（如经过特殊配置的路由器），即可轻松部署和管理。

- 它可处理关键的统一通信用例，例如漫游用户和多点登录。根据终结点的位置（而非用户的驻留位置）实施 CAC 策略。

- 除了语音呼叫，它还可以应用于其他通信，例如视频呼叫和音频/视频会议会话。

- 能够灵活地表示各种网络拓扑。

如果新语音会话或视频会话超出您在 WAN 链路上设置的带宽限制，该会话将被阻止或（仅在电话呼叫情况下）重新路由至 PSTN。

CAC 仅控制实时语音和视频流量，不控制数据流量。

管理员定义 CAC 策略，这些策略由随每个前端池一起安装的带宽策略服务强制执行。 CAC 设置会自动传播到网络中所有 Skype for Business Server 前端服务器。

对于因 CAC 策略而失败的呼叫，重新路由呼叫的优先顺序如下：

1. Internet

2. PSTN

3. 语音邮件

呼叫详细信息记录 (CDR) 捕获有关重新路由至 PSTN 或语音邮件的呼叫的信息。CDR 不会捕获有关重新路由至 Internet 的呼叫的信息，因为 Internet 被视为备用路径而非次要选项。

> [!NOTE]
> 语音邮件处理不会因为带宽限制而被拒绝。

带宽策略服务生成两种逗号分隔值 (CSV) 格式的日志文件。“检查失败”日志文件捕获带宽请求被拒绝时的信息。“链接利用率”日志文件捕获网络拓扑快照和 WAN 链路带宽用量。这两种日志文件都有助于根据利用率微调 CAC 策略。

## <a name="call-admission-control-considerations"></a>呼叫允许控制注意事项

管理员选择将带宽策略服务安装在中央站点中配置的第一个池上。 由于每个网络区域有一个中央站点，因此每个网络区域只有一个带宽策略服务，它管理用于该区域、其关联站点和到这些站点的链接的带宽策略。 带宽策略服务作为前端服务器的一部分运行，因此高可用性内置于该池中。 每台前端服务器上运行的带宽策略服务每 15 秒同步一次。 如果前端池出现故障，则不再为该站点强制执行 CAC 策略，直到前端池，因此带宽策略服务再次运行。 这意味着，在带宽策略服务停用期间，所有呼叫都将通过。 因此，在此期间可能会出现链接的带宽订阅过度的情况。

带宽策略服务在前端池中提供高可用性;但是，它不跨前端池提供冗余。 带宽策略服务无法从一个前端池故障转移到另一个前端池。 还原前端池的服务后，将恢复带宽策略服务，并可以再次强制执行带宽策略检查。

### <a name="network-considerations"></a>网络注意事项

尽管音频和视频的带宽限制由 Skype for Business Server 中的带宽策略服务强制执行，但第 2 层和 3 层网络路由器 (实施此) 。 CAC 无法阻止数据应用程序，例如，阻止占用 WAN 链路的整个网络带宽，包括 CAC 策略为音频和视频保留的带宽。 要提供必需的网络带宽保护，您可以部署服务质量 (QoS) 协议，例如差分服务 (DiffServ)。 因此，最佳实践是协调按照您可能部署的任何 QoS 设置定义的 CAC 带宽策略。

### <a name="media-and-signaling-paths-over-vpn"></a>VPN 上的媒体和信号路径

如果您的企业支持通过 VPN 的媒体，则请确保媒体流和信号流都能通过 VPN，或两者都通过 Internet 进行路由。默认情况下，媒体流和信号流通过 VPN 通道。

### <a name="call-admission-control-of-outside-users"></a>外部用户的呼叫允许控制

未超出 Skype for Business Server 组织的限制强制执行呼叫允许控制。 CAC 不能应用于通过 Internet 的媒体流量，该流量不由 Skype for Business Server 管理。 如果被叫终结点属于组织，并且边缘服务器已添加到网络配置，则 CAC 检查将针对通过企业网络的呼叫部分执行，如呼叫允许控制部署 [：Skype for Business Server](../../deploy/deploy-enterprise-voice/final-checklist.md)的最终清单中所述。 如果被叫终结点不属于组织，例如联盟或 PIC 用户，则不执行带宽策略检查，传出呼叫将忽略任何 CAC 限制。

### <a name="call-admission-control-of-pstn-connections"></a>PSTN 连接的呼叫允许控制

无论呼叫允许控制是连接到 IP/PBX、PSTN 网关还是 SIP 中继，都可以在中介服务器上实施。 由于中介服务器是 B2BUA (后端) 代理，因此它将终止媒体。 它具有两个连接端：连接到 Skype for Business Server 的端和连接到 PSTN 网关、IP/PBX 或 SIP 中继的网关端。 有关 PSTN 连接的详细信息，请参阅 [Plan for PSTN connectivity in Skype for Business Server](pstn-connectivity-0.md).

除非启用了媒体旁路，否则可以在中介服务器的两侧强制实施 CAC。 如果启用了媒体旁路，则媒体流量不会遍历中介服务器，而是直接在 Skype for Business 客户端和网关之间流动。 在这种情况下，不需要使用 CAC。 有关详细信息，请参阅 [Skype for Business 中的媒体旁路计划](media-bypass.md)。

下图说明了如何在启用和不启用媒体旁路的情况下在 PSTN 连接上实施 CAC。

**在 PSTN 连接上实施呼叫允许控制**

![语音 CAC 媒体旁路连接强制](../../media/Plan_CS_VoiceCAC_enforcementofconnectionstoPSTN.jpg)

## <a name="defining-your-requirements-for-call-admission-control"></a>定义呼叫允许控制要求

规划 CAC (CAC) 需要有关企业网络拓扑的详细信息。 为了帮助规划呼叫允许控制策略，请按照以下步骤操作。

1. 确定企业网络内 (网络区域) 网络区域。

2. 确定每个网络 (称为网络站点) 或位置。

3. 确定每对网络区域之间的网络路由。

4. 确定每个 WAN 链路的带宽限制。

    > [!NOTE]
    > 带宽限制是指 WAN 链路上分配给音频企业语音/视频流量的带宽量。 当 WAN 链路描述为"带宽受限"时，WAN 链路的带宽限制低于通过该链路的预期峰值流量。

5. 标识分配给每个网络站点的 IP 子网。

为了说明这些概念，我们将使用下图中所示的示例网络拓扑。

**呼叫允许控制的示例拓扑**

![Litware Inc. 网络拓扑示例](../../media/Plan_CS_VoiceCAC_Litwarenetworktopo.jpg)

> [!NOTE]
> 所有网络站点都与一个网络区域关联。 例如，波特兰、里诺和阿尔伯克基包含在北美区域。 在此图中，只显示应用了 CAC 策略的 WAN 链路，并包含带宽限制。 芝加哥、纽约和底特律的网络站点显示在北美区域椭圆内，因为它们不受带宽限制，因此不需要 CAC 策略。

以下各节介绍了此示例拓扑的组件。 有关此拓扑的规划方式（包括带宽限制）的详细信息，请参阅示例：收集 Skype for Business Server 中呼叫 [允许控制的要求](example-gathering-requirements.md)。

### <a name="identify-network-regions"></a>标识网络区域

网络区域代表网络中枢或网络中心。

网络中枢或中心是计算机网络基础结构的一部分，该基础结构将网络的不同部分相互连接，从而提供在不同 LAN 或子网之间交换信息的路径。 网络中枢可以将各种网络（从一个小位置到一个广的地理区域）连接在一起。 网络中枢的容量通常大于连接到它的网络的容量。

示例拓扑具有三个网络区域：北美、EMEA 和 APAC。 网络区域包含一组网络站点 (请参阅本主题稍后介绍的网络站点) 。 与网络运营团队一起确定网络区域。

### <a name="associating-a-central-site-with-each-network-region"></a>将中央站点与每个网络区域关联

CAC 要求为每个网络区域定义 Skype for Business Server 中央站点。 选择中央站点时，将具有与该网络区域内所有其他站点的最佳网络连接和最高带宽。 前面的网络拓扑示例显示了三个网络区域，每个网络区域都有一个管理 CAC 决策的中央站点。 从前面的示例中，相应的关联如下表所示。

> [!NOTE]
> 中央站点不一定与网络站点对应。 在本文档的示例中，某些中央站点（芝加哥、伦敦和北京）与网络站点共享同一名称。 但是，即使中央站点和网络站点共享同一名称，中央站点也是 Skype for Business Server 拓扑的元素，而网络站点是 Skype for Business Server 拓扑所在的整个网络的一部分。

**网络区域、中央站点和网络站点**

|**网络区域**|**中央站点**|**网络站点**|
|:-----|:-----|:-----|
|北美  <br/> |Chicago  <br/> |Chicago  <br/> 纽约  <br/> 底特律  <br/> 波特兰  <br/> Reno  <br/> Albuquerque  <br/> |
|EMEA  <br/> |伦敦  <br/> |伦敦  <br/> 百里  <br/> |
|APAC  <br/> |北京  <br/> |北京  <br/> 马吉拉  <br/> |

### <a name="identify-network-sites"></a>标识网络站点

网络站点表示组织具有物理位置的位置，例如办公室、一组建筑或校园。 具有 LAN 且具有与其他站点的 WAN 连接的物理位置被视为网络站点。 首先清点组织的所有办公室。 在我们的示例拓扑中，北美网络区域由以下网络站点组成：纽约、芝加哥、波特兰、波特兰、里诺和阿尔伯克基。

必须将每个网络站点与一个网络区域关联。 根据网络站点是否具有受约束的 WAN 链路，带宽策略与网络站点关联。 有关 CAC 策略以及使用 CAC 策略分配的带宽的详细信息，请参阅本主题稍后介绍的"定义带宽策略"。 若要配置 CAC，可以将网络站点与网络区域关联，然后创建带宽分配策略，以应用于给定站点或区域之间的带宽受限连接以及站点与区域之间的 WAN 连接。

### <a name="identify-network-links"></a>标识网络链接

网络链接表示到链接到不同地区和站点的物理 WAN 的连接。 在我们的示例拓扑中，有两个区域网络链接、五个区域和站点之间的网络链接以及两个站点之间的一个网络链接。

这两个区域链接位于北美和 EMEA 之间（表示为 NA-EMEA-LINK）以及 APAC 和 EMEA（表示为 EMEA-APAC-LINK）之间。

站点链接由将波特兰、里诺和阿尔伯克基连接到北美地区、将西雅图连接到 APAC 区域以及连接到 EMEA 地区的线路指示。 Reno 和 Albuquerque 之间的线路显示这两个站点之间的直接网络链接。

### <a name="define-bandwidth-policies"></a>定义带宽策略

与您的网络运营团队一起确定可用于组织中 WAN 链路中的实时音频和视频流量的 WAN 带宽。 带宽策略通常在带宽使用量受限时应用于 WAN 链路;即，如果预期大于可分配给音频和视频模态的带宽。

CAC 带宽策略定义可保留用于实时音频和视频形式的最大带宽。 由于 CAC 不限制其他流量的带宽，因此它无法阻止其他数据流量（如大型文件传输、音乐流）占用所有网络带宽。

CAC 带宽策略可以定义以下任一或所有内容：

- 为音频分配的最大总带宽。

- 为视频分配的最大总带宽。

- 为单个音频呼叫分配的最大带宽 (会话) 。

- 为单个视频呼叫分配的最大带宽 (会话) 。

> [!NOTE]
> 所有 CAC 带宽值都表示最大  *单向带宽*  限制。

> [!NOTE]
> Skype for Business Server 语音策略功能提供覆盖带宽策略检查的功能，以便向用户发送的传入呼叫 (而不是由用户发出的传出呼叫) 。 建立会话后，将准确计算带宽消耗。 应慎用此设置。 有关详细信息，请参阅部署文档中的"创建或修改语音策略"和"在 Skype for Business 中配置 [PSTN](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md) 用法记录"或"修改语音策略和配置 [PSTN 用法](https://technet.microsoft.com/library/6c53aaf5-218b-4bd4-8cea-31bc9d53f1bd.aspx) 记录"。

若要基于每个会话优化带宽利用率，请考虑将使用的音频和视频编解码器的类型。 特别是，避免为预期经常使用的编解码器分配带宽不足。 相反，如果要阻止媒体使用需要更多带宽的编解码器，则应该将每个会话的最大带宽设置为低到足以阻止此类使用。 对于音频，并非每个编解码器都适用于每个方案。 例如：

- 在将编解码器带宽和优先顺序考虑时，Skype for Business 终结点之间的对等音频呼叫将使用 RTAudio (8kHz) 或 RTAudio (16kHz) 。

- Skype for Business 终结点和 A/V 会议服务之间的电话会议将使用 G.722 或 Siren。

- 对公用电话交换网 (PSTN) 的呼叫将使用 G.711 或 RTAudio (8kHz) 。

使用下表可帮助优化每个会话的最大带宽设置。

**编解码器带宽利用率**

|**编解码器**|**FEC 服务器没有前向错误 (带宽)**|**FEC 报告具有前向 (要求)**|
|:-----|:-----|:-----|
|RTAudio (8kHz)   <br/> |49.8 kbps  <br/> |61.6 kbps  <br/> |
|RTAudio (16kHz)   <br/> |67 kbps  <br/> |96 kbps  <br/> |
|Siren  <br/> |57.6 kbps  <br/> |73.6 kbps  <br/> |
|G.711  <br/> |102 kbps  <br/> |166 kbps  <br/> |
|G.722  <br/> |105.6 kbps  <br/> |169.6 kbps  <br/> |
|RTVideo (CIF 15 fps)   <br/> |260 kbps  <br/> |不适用  <br/> |
|RTVideo (VGA 30 fps)   <br/> |610 kbps  <br/> |不适用  <br/> |

> [!NOTE]
> 带宽要求将以下各项的开销考虑在内：以太网 II、IP、用户数据报协议 (UDP) 、RTP (实时传输协议) 和 SRTP (安全实时传输协议) 。 它们还包括 10 kbps 的 RTCP 开销。

G.722.1 和 Siren 编解码器相似，但它们提供不同的比特率。

G.722 是 Skype for Business Server 会议的默认编解码器，与 G.722.1 和 Siren 编解码器完全不同。

在下列情况下，在 Skype for Business Server 中使用 Siren 编解码器：

- 如果带宽策略设置得太低，无法使用 G.722。

- 如果 Communications Server 2007 或 Communications Server 2007 R2 客户端连接到 Skype for Business Server 会议服务 (因为这些客户端不支持 G.722 编解码器) 。

**按方案表示的带宽利用率**

|**应用场景**|**针对数量优化的带宽 (kbps)**|**平衡模式带宽要求 (kbps)**|**针对质量要求优化的带宽 (kbps)**|
|:-----|:-----|:-----|:-----|
|对等音频呼叫  <br/> |45 kbps  <br/> |62 kbps  <br/> |91 kbps  <br/> |
|电话会议  <br/> |53 kbps  <br/> |101 kbps  <br/> |165 kbps  <br/> |
|PSTN 呼叫 (Skype for Business 和 PSTN 网关之间，媒体旁路)   <br/> |97 kbps  <br/> |97 kbps  <br/> |161 kbps  <br/> |
|PSTN 呼叫 (Skype for Business 和中介服务器之间，没有媒体旁路)   <br/> |45 kbps  <br/> |97 kbps  <br/> |161 kbps  <br/> |
|PSTN 呼叫 (中介服务器和 PSTN 网关之间，没有媒体旁路)   <br/> |97 kbps  <br/> |97 kbps  <br/> |161 kbps  <br/> |
|Skype for Business - Polycom 呼叫  <br/> |101 Kbps  <br/> |101 Kbps  <br/> |101 Kbps  <br/> |

### <a name="identify-ip-subnets"></a>标识 IP 子网

对于每个网络站点，您需要与网络管理员一起确定分配给每个网络站点的 IP 子网。 如果网络管理员已经将 IP 子网组织到网络区域和网络站点中，则您的工作将大为简化。

在我们的示例中，为北美地区的纽约站点分配了以下 IP 子网：172.29.80.0/23、157.57.216.0/25、172.29.91.0/23、172.29.81.0/24。 假设通常在底特律工作的 Bob 出差到纽约办事处接受培训。 打开计算机并连接到网络时，他的计算机将获取为纽约保留的四个范围之一中的 IP 地址，例如 172.29.80.103。

> [!CAUTION]
> 在服务器上的网络配置期间指定的 IP 子网必须与客户端计算机提供的格式相匹配，才能正确用于媒体旁路。 Skype for Business 客户端采用其本地 IP 地址，并屏蔽具有关联子网掩码的 IP 地址。 在确定与每个客户端关联的绕过 ID 时，注册器将与每个网络站点关联的 IP 子网列表与客户端提供的子网进行比较，以确定完全匹配。 因此，在服务器上的网络配置期间输入的子网是实际子网而不是虚拟子网，这一点很重要。  (如果部署呼叫允许控制， 但不是媒体旁路，即使配置虚拟子网，呼叫允许控制也将正常工作。例如) 例如，如果 IP 地址为 172.29.81.57 的计算机上 IP 子网掩码为 255.255.255.0，则 Skype for Business 将请求与子网 172.29.81.0 关联的绕过 ID。 如果子网定义为 172.29.0.0/16，那么即使客户端属于虚拟子网，注册器也不会将此看做匹配，因为注册器会专门查找子网 172.29.81.0。 因此，管理员必须完全按照 Skype for Business 客户端提供的子网输入子网 (这些子网在网络配置期间静态或由 DHCP.) 

## <a name="best-practices-for-call-admission-control"></a>呼叫允许控制最佳做法

为了提高性能并加快部署，在部署呼叫允许控制时，请应用以下最佳做法：

- 确保为当前和预期的媒体流量充分预配了 WAN。

    > [!NOTE]
    > 建议根据带宽限制考虑缓冲区。 有些方案（如竞争条件）会影响使用的总带宽，并可能导致超出带宽限制的情况。 例如，如果两个呼叫尝试在媒体流量接近带宽限制时启动，其中一个呼叫可能会被拒绝，因为另一个呼叫先被管理启动。

- 监视网络使用情况和呼叫详细信息记录，以便可以选择最佳 CAC 设置，并随着网络使用率的变化更新 CAC 设置。

- 使用 CAC 带宽策略补充 QoS 设置。

- 如果要将阻止的呼叫重新路由到 PSTN，请验证 PSTN 功能和容量。 有关详细信息，请参阅 [规划出站呼叫路由](https://technet.microsoft.com/library/37c55fa4-175a-4190-b9e4-c2e5ac7b9261.aspx)。

    > [!NOTE]
    > 容量是指支持潜在 PSTN 重新路由所需的打开端口数。


