---
title: 2019 Skype for Business Server容量规划
ms.reviewer: ''
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: ''
description: 本节中的主题可帮助您了解如何计划和部署 Skype for Business Server，以便您可以充分规划组织中用户的数量并规划其活动生成的服务器负载。
ms.openlocfilehash: aaa34d4ec935735215da36d888ab3c5155f158b89fd366546eac14b3f6259482
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54277637"
---
# <a name="capacity-planning-for-skype-for-business-server-2019"></a>2019 Skype for Business Server容量规划

本文根据网站中的用户模型中所述的用法，提供有关站点中需要多少台服务器的指南。Skype for Business Server [](../../SfbServer/plan-your-deployment/capacity/user-models.md)

## <a name="tested-hardware-platform"></a>测试的硬件平台

我们已对下表中描述的硬件执行性能测试。 我们的所有建议和结果都基于此硬件。 如果你决定尝试使用比此处列出的硬件功能更少的硬件，请注意，你可能遇到功能问题或性能不佳。

**性能测试中使用的硬件**

|**硬件组件**|**建议**|
|:-----|:-----|
|CPU  <br/> |Intel Xeon E5-2673 v3 双处理器，6 核，2.4 GHz (GHz) 或更高。  <br/> Intel Itanium 处理器不受 Skype for Business Server 2019 角色支持。  <br/> |
|内存  <br/> |32 GB (GB) 。  <br/> |
|磁盘  <br/> |任一：  <br/> • 具有至少 72 GB 可用磁盘空间的 8 个或 10000 RPM 硬盘驱动器 (两个磁盘使用 RAID 1，6 个磁盘使用 RAID 10) 。  <br/> 或  <br/> • 固态硬盘 (SSD) 提供与 8 个 10000 RPM 机械磁盘驱动器相同的可用空间和类似性能。  <br/> |
|网络  <br/> |1 个双端口网络适配器，1 Gbps 或更高 (2 个网络适配器，但它们需要与一个 MAC 地址和一个 IP 地址) 。  <br/> 前端服务器、后端服务器和服务器不支持双Standard Edition配置。 <br/> 只要它们未向操作系统公开，并且用于监视和管理服务器硬件，就可以拥有带外管理系统，如 DRAC 或则使用。 此方案不构成多主服务器，并且受支持。  <br/> |

## <a name="summary-of-results"></a>结果摘要

下表总结了我们的建议。

|**服务器角色**|**受支持的最大用户数**|
|:-----|:-----|
|具有 16 台前端服务器和后端服务器的前端池或一对后端服务器，SQL Always On 的高可用性。  <br/> |106，000 个同时登录的唯一用户，以及 50% 多点登录 (MPOP) （代表非移动实例）以及 40% 的用户（共 210，000 个终结点）启用了移动功能。  <br/> |
|A/V 会议  <br/> |前端池提供的 A/V 会议服务支持池的会议（假定最大会议大小为 250 个用户，且一次仅运行一个这样的大型会议）。  <br/> **注意：** 此外，通过部署具有两台前端服务器的单独前端池来承载大型会议，您可以支持 250 到 1000 个用户的大型会议。 有关详细信息，请参阅在 Skype for Business Server[中规划大型Skype for Business Server。](../../SfbServer/plan-your-deployment/conferencing/large-meetings.md) <br/> |
|一台边缘服务器  <br/> |18，000 个并发远程用户。  <br/> |
|一台控制器  <br/> |18，000 个并发远程用户。  <br/> |
|监控和存档  <br/> |监控和存档前端服务在每个前端服务器上运行，而不是在单独的服务器角色中运行。  <br/> 监控和存档仍然需要各自的数据库存储。 如果还运行 Exchange 2013 或更高版本，可以将存档数据保留Exchange，而不是专用存档SQL数据库中。  <br/> |
|一台中介服务器  <br/> |与前端服务器并排的中介服务器在池中的前端服务器上运行，并且应为池中的用户提供足够容量。 有关独立的中介服务器，请参阅本主题稍后介绍的"中介服务器"部分。  <br/> |
|一台 Standard Edition Server  <br/> |强烈建议在使用 Standard Edition 服务器来托管用户时，始终使用两台服务器，使用规划高可用性和灾难恢复中的建议[进行配对](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-high-availability-and-disaster-recovery)。 对中的每台服务器可承载多达 2，500 个用户，如果一台服务器出现故障，则其余服务器可以在故障转移方案中支持 5，000 个用户。  <br/>  如果您的部署包含大量音频或视频流量，则每台服务器的用户数超过 2，500 名时，服务器性能可能会下降。 在这种情况下，应考虑向服务器添加更多Standard Edition或移动到Skype for Business Server Enterprise Edition。 <br/> |

## <a name="front-end-server"></a>Front End Server － 前端服务器

> [!NOTE]
> 此服务器角色不支持拉伸池。

在前端池中，应为池中每 6，660 个用户设置一台前端服务器，前提是池中的所有服务器上都启用了超线程，且使用的是 SQL Server Express Edition，并且服务器硬件符合[server requirements for Skype for Business Server 2019](system-requirements.md)中的建议。 一个前端池中的最大用户数为 106，000，同样假定已启用超线程，并且池中的所有服务器上都使用了 SQL Server Express Edition。 如果站点上的用户数超过 106，000，可以部署多个前端池。

在考虑到前端池中的用户数时，请包含分支机构中与此前端池关联的 Survivable Branch 设备和 Survivable Branch Servers 上的任何用户。

活动服务器不可用时，其连接会自动转接给池中的其他服务器。 在具有 30，000 个用户和五台前端服务器的方案中，如果一台服务器不可用，则需要将 6000 个用户的连接转移到其他四台服务器。 其余四台服务器将拥有 7500 个用户，这比建议的数量大。

如果您改为为 30，000 个用户启动六台前端服务器，而一台不可用，则总共 5000 个用户需要移动到其余五台服务器。 这五台其余服务器随后将承载 6000 个用户，这位于建议的范围内。

前端池中的最大用户数为 106，000。 池中前端服务器的最大数量为 16。

对于具有 80，000 个用户的前端池，在遵循 Skype for Business Server 中的用户模型的典型部署中，16 台前端[服务器将适用于性能](../../SfbServer/plan-your-deployment/capacity/user-models.md)。 设计为支持灾难恢复故障转移的部署假定在两个配对前端池中最多可承载 53，000 个用户，其中每个池具有足够的前端服务器以包含这两个池中的用户（如果一个池需要故障转移到另一个池）。

由于以下原因，特定前端池支持具有良好性能的用户数量可能与这些数字不同：

- 前端服务器的硬件不符合建议。
- 无需使用 SQL Server Express Edition，而是使用另一个 SQL Server Edition，您可以在每个前端池中承载其他用户。
- 组织的使用情况与用户模型大为不同，例如，如果你的会议流量更多。

下表显示了在给定用户模型的情况下 IM 和状态的平均带宽，如 Skype for Business Server 中的[用户模型所定义](../../SfbServer/plan-your-deployment/capacity/user-models.md)。

|**每个用户的平均带宽**|**用户数为 6，660 的前端服务器的带宽要求**|
|:-----|:-----|
|3-3.75 KBps  <br/> |13 MBps  <br/> |

> [!NOTE]
> 若要提高前端服务器上位于同一位置的 A/V 会议和中介服务器的媒体性能，应在前端服务器上网络适配器上启用接收端缩放 (RSS) 。 通过启用 RSS，服务器上的多个处理器能够以并行方式处理传入数据包。 有关详细信息，请参阅文档文档中 ([RSS) 侧Windows Server 2012缩放](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11))。 若要详细了解如何启用 RSS，需要参阅网络适配器文档。

## <a name="conferencing-maximums"></a>会议最大值

根据用户模型，池中 5% 的用户可能随时参加会议，106，000 个用户的池可以同时有约 5，300 个用户参加会议。 这些会议可能混合多种媒体（如一些仅含 IM、一些含有 IM 和音频、一些含有音频/视频）并拥有大量参与者。 对于允许的实际会议数没有硬性限制，实际使用将决定实际性能。 例如，如果贵组织具有的混合模式会议多于用户模型中假定的混合模式会议，您可能需要部署比本文中的建议更多的前端服务器或 A/V 会议服务器。 有关用户模型中的假设的详细信息，[请参阅用户模型中](../../SfbServer/plan-your-deployment/capacity/user-models.md)Skype for Business Server。

由同时承载用户的常规Skype for Business Server托管的最大支持会议大小为 250 个参与者。 在召开具有 250 个用户的会议时，池仍支持其他会议，因此共有 5% 的池用户参加并发会议。 例如，在具有 16 台前端服务器和 106，000 个用户的池中，当召开具有 250 个用户的会议时，Skype for Business Server 支持 5，050 个其他用户参加规模较小的会议。

无论前端池或 Standard Edition 服务器上托管的用户数量如何，Skype for Business Server 都至少支持 125 个其他用户在承载 250 个用户的会议的同一池或服务器上参加小型会议。

若要启用用户数在 250 到 1000 之间的会议，可以设置单独的前端池来承载这些会议。 此前端池不会托管任何用户。 有关详细信息，请参阅在 Skype for Business Server[中规划大型Skype for Business Server。](../../SfbServer/plan-your-deployment/conferencing/large-meetings.md)

如果您的组织具有的混合模式会议的数量多于用户模型中假定的混合模式会议的数量，您可能需要部署的前端服务器数超过本文档中的建议 (最多部署 16 台前端服务器) 。 有关用户模型中的假设的详细信息，[请参阅用户模型中](../../SfbServer/plan-your-deployment/capacity/user-models.md)Skype for Business Server。

## <a name="edge-server"></a>边缘服务器

> [!NOTE]
> 此服务器角色不支持拉伸池。

应为将同时访问站点的每 18，000 个远程用户部署一台边缘服务器。 为实现高可用性，建议至少部署两台边缘服务器。 这些建议假定边缘服务器的硬件符合服务器硬件平台 [中的建议](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms)。

在计算边缘服务器的用户数时，请将分支机构中与此站点的前端池关联的 Survivable Branch Appliance 和 Survivable Branch Server 上驻留的用户包括在内。

> [!NOTE]
> 要提高边缘服务器上的 A/V 会议边缘服务的性能，应在边缘服务器的网络适配器上启用接收方缩放 (RSS)。 通过启用 RSS，服务器上的多个处理器能够以并行方式处理传入数据包。 有关详细信息，请参阅接收[侧缩放 (RSS) 在Windows Server 2012。](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11)) 若要详细了解如何启用 RSS，需要参阅网络适配器文档。

## <a name="director"></a>主管

> [!NOTE]
> 此服务器角色不支持拉伸池。

如果部署控制器服务器角色，我们建议您为将同时访问网站的每 18，000 个远程用户部署一个控制器。 为实现高可用性，建议至少部署两台控制器。 这些建议假定边缘服务器的硬件符合服务器硬件平台 [中的建议](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms)。

在计算控制器的用户数时，请将分支机构中与此站点的前端池关联的 Survivable Branch Appliance 和 Survivable Branch Server 上驻留的用户包括在内。

## <a name="mediation-server"></a>中介服务器

> [!NOTE]
> 此服务器角色不支持拉伸池。

如果将中介服务器与前端服务器并并，则中介服务器在池中的前端服务器上运行，并且应为池中的用户提供足够容量。

如果部署独立的中介服务器池，则要部署的中介服务器数量取决于许多因素，包括用于中介服务器的硬件、您拥有的 VoIP 用户数、每个中介服务器池所控制网关对等方的数量、通过这些网关的忙碌时间流量，以及具有绕过中介服务器的媒体的呼叫百分比。

下表提供了中介服务器可以处理的并发呼叫数的指南，前提是中介服务器的硬件满足服务器硬件平台中的要求，并且启用了超线程。 [](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms) 有关中介服务器可伸缩性的详细信息，请参阅[Estimating voice usage and traffic for Skype for Business Server](../../SfbServer/plan-your-deployment/capacity/estimating-voice-traffic.md) and Deployment guidelines for Mediation Server in [Skype for Business Server](../../SfbServer/plan-your-deployment/capacity/mediation-server-deployment-guidelines.md)。

以下所有表都假定用法如 user [models in Skype for Business Server 中Skype for Business Server。](../../SfbServer/plan-your-deployment/capacity/user-models.md)

**独立中介服务器容量：70% 为内部用户，30% 为具有非旁路呼叫容量的外部用户 (中介服务器执行媒体转码)**

|**服务器硬件**|**最大呼叫数**|**最大 T1 线路数**|**最大 E1 线路数**|
|:-----|:-----|:-----|:-----|
|Intel Xeon E5-2673 v3 双处理器，6 核，2.4 GHz (GHz) 或更高，禁用超线程，具有 64 GB 内存和一个双端口网络适配器卡。  <br/> |1500  <br/> |64  <br/> |49  <br/> |
|Intel Xeon E5-2673 v3 双处理器，6 核，2.4 GHz (GHz) 或更高版本，具有 64 GB 内存和一个双端口网络适配器卡。  <br/> |2000  <br/> |88  <br/> |66  <br/> |

> [!NOTE]
> 尽管内存为 64 GB 的服务器用于性能测试，但具有 32 GB 内存的服务器支持独立中介服务器，并且足以提供此表中所示的性能。

**中介服务器容量 (中介服务器与前端服务器并置的) 70% 内部用户、30% 的外部用户、不绕过呼叫容量 (中介服务器执行媒体处理)**

|**服务器硬件**|**最大呼叫数**|
|:-----|:-----|
|Intel Xeon E5-2673 v3 双处理器，6 核，2.4 GHz (GHz) 或更高版本，具有 64 GB 内存和 2 个 1GB 网络适配器卡。  <br/> |200  <br/> |

> [!NOTE]
> 此数字远小于独立中介服务器的数字。 这是因为前端服务器除了处理语音呼叫所需的转码之外，还必须处理其上 6600 个用户的其他特性和功能。

> [!NOTE]
> 若要提高中介服务器的性能，应在中介服务器的网络适配器 (RSS) 启用接收端缩放。 通过启用 RSS，服务器上的多个处理器能够以并行方式处理传入数据包。 有关详细信息，请参阅"[Receive-Side Scaling in Windows Server 2012"。](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11)) 若要详细了解如何启用 RSS，需要参阅网络适配器文档。

## <a name="back-end-server"></a>后端服务器

尽管大部分数据库信息主要存储在前端服务器上，但应确保后端服务器满足本节前面和服务器硬件平台中列出的 [硬件建议](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms)。

若要提供后端服务器的高可用性，我们建议部署 AlwaysOn 可用性组或服务器镜像。 有关详细信息，请参阅 Skype for Business Server 中的后端[服务器高可用性](../../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md)。

## <a name="monitoring-and-archiving"></a>监控和存档

如果部署监控或存档，这些服务的前端功能在前端服务器上运行，监控和存档各自使用自己的数据库存储，独立于后端存储。 或者，如果部署了 Exchange 2013，可以将即时消息存档数据存储在 Exchange 而非专用 SQL 存储中。

下表指示每个用户每天监控和存档数据所需的数据库存储量。

||**CDR (Monitoring)** <br/> |**QoE (监控)** <br/> |**存档** <br/> |
|:-----|:-----|:-----|:-----|
|每个用户每天所需的磁盘空间  <br/> |49 KB  <br/> |28 KB  <br/> |57 KB  <br/> |

Microsoft 在其性能测试期间将下表中的硬件数据库服务器用于监控和存档。 测试收集了两个前端池的数据，每个前端池包含 80，000 个用户。

**监控和存档性能测试中使用的硬件**

|**硬件组件**|**建议**|
|:-----|:-----|
|CPU  <br/> |Intel Xeon E5-2673 v3 双处理器，6 核，2.4 GHz (GHz) 或更高。  <br/> |
|内存  <br/> |48 GB  <br/> |
|磁盘  <br/> | 任一：<br/> • 具有至少 72 GB 可用磁盘空间的 4 个或多个 10000 RPM 硬盘驱动器 (磁盘应处于 2x RAID 1 配置) 。 <br/>或 <br/>• 固态硬盘 (SSD) 提供与 4 个 10000 RPM 机械磁盘驱动器相同的可用空间和类似性能。   <br/> |
|网络  <br/> | 1 个双端口网络适配器，建议使用 1 Gbps (2 Gbps 或更高，这需要与单个 MAC 地址和单个 IP 地址) 。  <br/> |

**建议的磁盘配置**

|**Drive** <br/> |**RAID 配置** <br/> |**磁盘数** <br/> |
|:-----|:-----|:-----|
|单个驱动器上的 CDR、QoE 和存档数据库数据文件  <br/> |1+0  <br/> |16   <br/> |
|CDR 数据库日志文件  <br/> |1  <br/> |2  <br/> |
|QoE 数据库日志文件  <br/> |1  <br/> |2  <br/> |
|存档数据库日志文件  <br/> |1  <br/> |2  <br/> |

## <a name="video-interop-server-capacity"></a>视频互操作服务器容量

如果部署视频互操作服务器并需要确定容量，则查看并发呼叫中视频电话会议系统 (VTC) 的最大数量。 例如，如果组织中有 250 个 VTC，并且用户模型估计其中最多有 20% 可能是并发呼叫，则容量规划基于 50 个并发 VTC。