---
title: 容量规划用户模型Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 902ab23e-94d6-482a-9d6e-c0b28dc3e03d
description: 本文根据网站中的用户模型中所述的用法，提供有关网站中需要多少台服务器的指南。Skype for Business Server。
ms.openlocfilehash: 4f2027debf7a8c2f787a77149212bccf2f8c90c0
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60750001"
---
# <a name="capacity-planning-user-model-usage-for-skype-for-business-server"></a>容量规划用户模型Skype for Business Server

本文根据 user [models in Skype for Business Server](user-models.md)中所述的用法，提供有关网站中需要多少台服务器的指南。

> [!NOTE]
> 本文中所有建议均假定你已Skype for Business 2015 年 11 月版累积更新或更高版本。

## <a name="tested-hardware-platform"></a>测试的硬件平台

我们已对下表中描述的硬件执行性能测试。 我们的所有建议和结果都基于此硬件。 如果你决定尝试使用比此处列出的硬件功能更少的硬件，请注意，你可能遇到功能问题或性能不佳。 这些硬件建议与 Lync Server 2013 相同，如果这对升级 (，则可能会) 。

**性能测试中使用的硬件**

|硬件组件|建议|
|:-----|:-----|
|CPU   |64 位双处理器、十六核、2.26 GHz (GHz) 或更高。  <br/> Intel Itanium 处理器不支持用于Skype for Business Server角色。   |
|内存   |32 GB (GB) 。   |
|磁盘   |具有至少 72 GB 可用磁盘空间的 8 个或多个 10，000 RPM 硬盘驱动器。 其中两个磁盘驱动器应使用 RAID 1，另外六个磁盘驱动器应使用 RAID 10。  <br/> - 或者 - <br/>固态硬盘 (SSD) 提供的性能类似于 8 个 10，000 RPM 机械磁盘驱动器。  |
|网络   |1 个双端口网络适配器，建议使用 1 Gbps (2 gbps，这需要与单个 MAC 地址和单个 IP 地址) 。   |

## <a name="summary-of-results"></a>结果摘要

下表总结了我们的建议。

|服务器角色|受支持的最大用户数|
|:-----|:-----|
|具有 12 台前端服务器和一台后端服务器或一对镜像后端服务器的前端池。   |80，000 个同时登录的唯一用户，以及 50% 多点登录 (MPOP) （代表非移动实例）以及 40% 的用户（共 152，000 个终结点）启用了移动性。   |
|A/V 会议   |前端池提供的 A/V 会议服务支持池的会议（假定最大会议大小为 250 个用户，且一次仅运行一个这样的大型会议）。  <br/> **注意：** 此外，通过部署具有两台前端服务器的单独前端池来承载大型会议，您可以支持 250 到 1000 个用户的大型会议。 有关详细信息，请参阅在 Skype for Business Server 中[规划大型Skype for Business Server。](../../plan-your-deployment/conferencing/large-meetings.md)   |
|一台边缘服务器   |12，000 个并发远程用户。   |
|一台控制器   |12，000 个并发远程用户。   |
|监控和存档   |监控和存档前端服务在每个前端服务器上运行，而不是在单独的服务器角色中运行。  <br/> 监控和存档仍然需要各自的数据库存储。 如果还运行 Exchange 2013 或更高版本，可以将存档数据Exchange，而不是专用存档SQL数据库中。   |
|一台中介服务器   |与前端服务器并排的中介服务器在池中的前端服务器上运行，并且应为池中的用户提供足够容量。 有关独立的中介服务器，请参阅本主题稍后介绍的"中介服务器"部分。   |
|一台 Standard Edition Server   |我们强烈建议使用 Standard Edition 服务器来托管用户，请始终使用两台服务器，使用规划高可用性和灾难恢复中的建议[进行配对](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-high-availability-and-disaster-recovery)。 对中的每台服务器可承载多达 2，500 个用户，如果一台服务器出现故障，则其余服务器可以在故障转移方案中支持 5，000 个用户。  <br/>  如果您的部署包含大量音频或视频流量，则每台服务器的用户数超过 2，500 名时，服务器性能可能会下降。 在这种情况下，应考虑向服务器添加更多Standard Edition或移动到Skype for Business Server Enterprise Edition。  |

## <a name="front-end-server"></a>Front End Server － 前端服务器

> [!NOTE]
> 此服务器角色不支持拉伸池。

在前端池中，假定池中所有服务器上都启用了超线程，并且服务器硬件符合[server requirements for Skype for Business Server 2015](../requirements-for-your-environment/server-requirements.md)或 System requirements for Skype for Business Server [2019](../../../SfBServer2019/plan/system-requirements.md)中的建议，则对于池中每 6，660 个用户应拥有一台前端服务器。 一个前端池中的最大用户数为 80，000，同样假定池中的所有服务器上都启用了超线程。 如果站点上的用户数超过 80,000，则可部署多个前端池。

在考虑到前端池中的用户数时，请包含分支机构中与此前端池关联的 Survivable Branch Appliances 和 Survivable Branch Servers 上的任何用户。

活动服务器不可用时，其连接会自动转接给池中的其他服务器。 在具有 30，000 个用户和五台前端服务器的方案中，如果一台服务器不可用，则需要将 6000 个用户的连接转移到其他四台服务器。 这四个其余服务器将拥有 7500 个用户，这比建议的数量大。

如果您改为为 30，000 个用户启动六台前端服务器，而一台不可用，则共有 5000 个用户需要移动到其余五台服务器。 这五台其余服务器随后将承载 6000 个用户，这位于建议的范围内。

前端池的最大用户数是 80,000。 池中前端服务器的最大数量为 12 台。

对于具有 80，000 个用户的前端池，在采用 Skype for Business Server 中的用户模型的典型部署中，12 台前端服务器[将适用于Skype for Business Server。](user-models.md) 设计为支持灾难恢复故障转移的部署假定在两个配对前端池中最多可承载 40，000 个用户，其中每个池具有足够的前端服务器以包含两个池中的用户（如果一个池需要故障转移到另一个池）。

由于以下原因，特定前端池支持具有良好性能的用户数量可能与这些数字不同：

- 前端服务器的硬件不符合建议。

- 组织的使用情况与用户模型大为不同，例如，如果会议流量很大。

下表显示了在给定用户模型的情况下 IM 和状态的平均带宽，如 Skype for Business Server 中的用户[Skype for Business Server。](user-models.md)

|每个用户的平均带宽|用户数为 6，660 的前端服务器的带宽要求|
|:-----|:-----|
|1.3 Kpbs   |13 Mbps   |

> [!NOTE]
> 若要提高前端服务器上位于同一位置的 A/V 会议和中介服务器的媒体性能，应在前端服务器上网络适配器上启用接收端缩放 (RSS) 。 通过启用 RSS，服务器上的多个处理器能够以并行方式处理传入数据包。 有关详细信息，请参阅接收[侧缩放 (RSS) 文档Windows Server 2012 RSS。](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11)) 若要详细了解如何启用 RSS，需要参阅网络适配器文档。

## <a name="conferencing-maximums"></a>会议最大值

根据用户模型，池中 5% 的用户可能随时参加会议，则 80，000 个用户的池可以同时有约 4，000 个用户参加会议。 这些会议可能混合多种媒体（如一些仅含 IM、一些含有 IM 和音频、一些含有音频/视频）并拥有大量参与者。 对于允许的实际会议数没有硬性限制，实际使用将决定实际性能。 例如，如果贵组织具有的混合模式会议多于用户模型中假定的混合模式会议，您可能需要部署比本文中的建议更多的前端服务器或 A/V 会议服务器。 有关用户模型中的假设的详细信息，[请参阅用户模型中](user-models.md)Skype for Business Server。

由常规前端池（Skype for Business Server托管用户）承载的最大支持会议大小为 250 个参与者。 在召开具有 250 个用户的会议时，池仍支持其他会议，因此共有 5% 的池用户参加并发会议。 例如，在 12 台前端服务器和 80，000 个用户的池中，当召开具有 250 个用户的会议时，Skype for Business Server 支持 3，750 个其他用户参加小型会议。

无论前端池或 Standard Edition 服务器上托管的用户数量如何，Skype for Business Server 都至少支持 125 个其他用户参与承载 250 个用户的会议的同一池或服务器上较小的会议。

若要启用用户数在 250 到 1000 之间的会议，可以设置单独的前端池来承载这些会议。 此前端池不会托管任何用户。 有关详细信息，请参阅在 Skype for Business Server[中规划大型Skype for Business Server。](../../plan-your-deployment/conferencing/large-meetings.md)

如果您的组织具有的混合模式会议的数量多于用户模型中假定的混合模式会议的数量，您可能需要部署的前端服务器数超过本文档中的建议 (最多部署 12 台前端服务器) 。 有关用户模型中的假设的详细信息，[请参阅用户模型中](user-models.md)Skype for Business Server。

## <a name="edge-server"></a>边缘服务器

> [!NOTE]
> 此服务器角色不支持拉伸池。

应为将同时访问站点的每 12，000 个远程用户部署一台边缘服务器。 为实现高可用性，建议至少部署两台边缘服务器。 这些建议假定边缘服务器的硬件符合服务器硬件平台 [中的建议](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms)。

在计算边缘服务器的用户数时，请将分支机构中与此站点的前端池关联的 Survivable Branch Appliance 和 Survivable Branch Server 上驻留的用户包括在内。

> [!NOTE]
> 要提高边缘服务器上的 A/V 会议边缘服务的性能，应在边缘服务器的网络适配器上启用接收方缩放 (RSS)。 通过启用 RSS，服务器上的多个处理器能够以并行方式处理传入数据包。 有关详细信息，请检查"[接收侧缩放 (RSS) 中Windows Server 2012"。](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11)) 若要详细了解如何启用 RSS，需要参阅网络适配器文档。

## <a name="director"></a>主管

> [!NOTE]
> 此服务器角色不支持拉伸池。

如果部署控制器服务器角色，我们建议您为将同时访问网站的每 12，000 个远程用户部署一个控制器。 为实现高可用性，建议至少部署两台控制器。 这些建议假定边缘服务器的硬件符合服务器硬件平台 [中的建议](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms)。

在计算控制器的用户数时，请将分支机构中与此站点的前端池关联的 Survivable Branch Appliance 和 Survivable Branch Server 上驻留的用户包括在内。

## <a name="mediation-server"></a>中介服务器

> [!NOTE]
> 此服务器角色不支持拉伸池。

如果将中介服务器与前端服务器并并，则中介服务器在池中的前端服务器上运行，并且应为池中的用户提供足够容量。

如果部署独立的中介服务器池，则要部署的中介服务器数量取决于许多因素，包括用于中介服务器的硬件、您拥有 VoIP 用户的数量、每个中介服务器池所控制网关对等方的数量、通过这些网关的忙碌时间流量以及具有绕过中介服务器的媒体的呼叫百分比。

下表提供了中介服务器可以处理的并发呼叫数的指南，前提是中介服务器的硬件满足服务器硬件平台中的要求，并且启用了超线程。 [](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms) 有关中介服务器可伸缩性的详细信息，请参阅[Estimating voice usage and traffic for Skype for Business Server](estimating-voice-traffic.md) and Deployment guidelines for Mediation Server in [Skype for Business Server](mediation-server-deployment-guidelines.md)。

以下所有表都假定用法如 user [models in Skype for Business Server 中汇总](user-models.md)。

**独立中介服务器容量：70% 为内部用户，30% 为具有非旁路呼叫容量的外部用户 (中介服务器执行媒体转码)**

|服务器硬件|最大呼叫数|最大 T1 线路数|最大 E1 线路数|
|:-----|:-----|:-----|:-----|
|双处理器、十六核、禁用超线程的 2.26 GHz 超线程CPU、32 GB 内存和一个双端口网络适配器卡。   |1100   |46   |35   |
|双处理器、十六核、2.26 GHz 超线程 CPU、32 GB 内存和一个双端口网络适配器卡。   |1500   |63   |47   |

> [!NOTE]
> 虽然性能测试使用的是内存为 32 GB 的服务器，但内存为 16 GB 的服务器也可用作独立中介服务器，并且足以提供此表中显示的性能。

**中介服务器容量 (中介服务器与前端服务器并置的) 70% 内部用户、30% 的外部用户、不绕过呼叫容量 (中介服务器执行媒体处理)**

|服务器硬件|最大呼叫数|
|:-----|:-----|
|双处理器、十六核、2.26 GHz 超线程 CPU，具有 32 GB 内存和 2 个 1GB 网络适配器卡。   |150   |

> [!NOTE]
> 此数字远小于独立中介服务器的数字。 这是因为前端服务器除了处理语音呼叫所需的转码之外，还必须处理其上 6600 个用户的其他特性和功能。

> [!NOTE]
> 若要提高中介服务器的性能，应在中介服务器的网络适配器 (RSS) 启用接收端缩放。 通过启用 RSS，服务器上的多个处理器能够以并行方式处理传入数据包。 有关详细信息，请参阅"[Receive-Side Scaling in Windows Server 2012"。](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11)) 若要详细了解如何启用 RSS，需要参阅网络适配器文档。

## <a name="back-end-server"></a>后端服务器

尽管大部分数据库信息主要存储在前端服务器上，但应确保后端服务器满足本节前面和服务器硬件平台中列出的 [硬件建议](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms)。

若要提供后端服务器的高可用性，我们建议部署 AlwaysOn 可用性组或服务器镜像。 有关详细信息，请参阅 Skype for Business Server 中的后端[服务器高可用性](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md)。

## <a name="monitoring-and-archiving"></a>监控和存档

如果部署监控或存档，这些服务的前端功能在前端服务器上运行，监控和存档各自使用自己的数据库存储，独立于后端存储。 或者，如果部署了 Exchange 2013，可以将即时消息存档数据存储在 Exchange 而非专用 SQL 存储中。

下表指示每个用户每天监控和存档数据所需的数据库存储量。

|&nbsp;|CDR (Monitoring)   |QoE (监控)   |存档  |
|:-----|:-----|:-----|:-----|
|每个用户每天所需的磁盘空间   |49 KB   |28 KB   |57 KB   |

Microsoft 在其性能测试期间将下表中的硬件数据库服务器用于监控和存档。 测试收集了两个前端池的数据，每个前端池包含 80，000 个用户。

**监控和存档性能测试中使用的硬件**

|硬件组件|建议|
|:-----|:-----|
|CPU   |64 位双处理器、六核、2.26 GHz 或更快   |
|内存   |48 GB (GB)    |
|磁盘   |25 个 10，000 RPM 硬盘驱动器，每个磁盘上具有 300 GB，下表中的配置   |
|网络   | 1 个双端口网络适配器，1 Gbps 或更高（建议为 2 Gbps，这要求与一个 MAC 地址和一个 IP 地址结合使用）   |

**建议的磁盘配置**

|驱动器  |RAID 配置  |磁盘数  |
|:-----|:-----|:-----|
|单个驱动器上的 CDR、QoE 和存档数据库数据文件   |1+0   |16   |
|CDR 数据库日志文件   |1   |2   |
|QoE 数据库日志文件   |1   |2   |
|存档数据库日志文件   |1   |2   |

## <a name="video-interop-server-capacity"></a>视频互操作服务器容量

如果部署视频互操作服务器并且需要确定容量，则查看并发呼叫中视频电话会议系统 (VTC) 的最大数量。 例如，如果组织中有 250 个 VTC，并且用户模型估计其中最多有 20% 可能是并发呼叫，则容量规划基于 50 个并发 VTC。