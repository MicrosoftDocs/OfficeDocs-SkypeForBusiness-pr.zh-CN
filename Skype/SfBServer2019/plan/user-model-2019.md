---
title: Skype for business Server 2019 的容量规划
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
description: 本部分中的主题可帮助你了解如何规划和部署 Skype for Business Server，以便你可以充分规划组织中的用户数并规划其活动生成的服务器负载。
ms.openlocfilehash: 15f59d2052a4d73f6e1b1c09b10525b503958fea
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824026"
---
# <a name="capacity-planning-for-skype-for-business-server-2019"></a>Skype for business Server 2019 的容量规划

本文根据[Skype For Business Server 的用户模式](../../SfbServer/plan-your-deployment/capacity/user-models.md)中所述的使用情况，为网站上的用户数所需的服务器数提供指导

## <a name="tested-hardware-platform"></a>受测试的硬件平台

我们已完成对下表中所述的硬件执行性能测试。 我们的所有建议和结果都是以此硬件为基础。 如果您决定使用功能不如这里列出的硬件强大的其他硬件，请注意您可能会遇到功能性问题或性能较差。

**性能测试中使用的硬件**

|**硬件组件**|**推荐**|
|:-----|:-----|
|CPU  <br/> |Intel Xeon E5-2673 v3 双处理器，6 核，2.4 GHz 或更快。  <br/> Skype for Business Server 2019 角色不支持 Intel Itanium 处理器。  <br/> |
|内存  <br/> |32 GB。  <br/> |
|磁盘  <br/> |以下之一：  <br/> • 8 块或更多 10000 RPM 硬盘，至少 72 GB 可用磁盘空间（2 块磁盘使用 RAID 1，6 块磁盘使用 RAID 10）。  <br/> 或  <br/> • 能够提供与 8 块 10000 RPM 机械硬盘相同的可用空间和类似性能的固态硬盘 (SSD)。  <br/> |
|网络  <br/> |1 个双端口网络适配器，1 Gbps 或更高（可使用 2 个网络适配器，但需要通过一个 MAC 地址和一个 IP 地址配合使用）。  <br/> 前端服务器、后端服务器和标准版服务器**不**支持双宿主或多宿主配置。 <br/> 只要它们不接触操作系统并且被用于监控和管理服务器硬件，你就能够拥有带外管理系统，如 DRAC 或 ILO。 这种情况不会形成多宿主服务器，并且受支持。  <br/> |

## <a name="summary-of-results"></a>结果摘要

下表总结了我们的建议。

|**服务器角色**|**受支持的最大用户数**|
|:-----|:-----|
|带有16个前端服务器和后端服务器的前端池，或一对用于高可用性的 SQL 的后端服务器。  <br/> |106000的唯一用户同时登录，以及50% 的多点状态（MPOP），表示非移动实例，还包括为移动计算而启用的40% 的用户，共210000终结点。  <br/> |
|A/V 会议  <br/> |由前端池提供的 A/V 会议服务支持池中的会议，其会议最大为250用户，并且一次仅运行一个这样的大型会议。  <br/> **注意：** 此外，你可以通过部署一个单独的前端池和两个前端服务器来支持250和1000用户之间的大型会议，从而托管大型会议。 有关详细信息，请参阅[在 Skype For Business 服务器中规划大型会议](../../SfbServer/plan-your-deployment/conferencing/large-meetings.md)。 <br/> |
|一台边缘服务器  <br/> |18000并发远程用户。  <br/> |
|一个控制器  <br/> |18000并发远程用户。  <br/> |
|监控和存档  <br/> |监视和存档前端服务在每台前端服务器上运行，而不是在单独的服务器角色上运行。  <br/> 监控和存档仍需要其自己各自的数据库存储。 如果您也运行 Exchange 2013 或更高版本，则可以将存档数据保留在 Exchange 中，而不是在专用 SQL 数据库中。  <br/> |
|一个中介服务器  <br/> |使用前端服务器的中介服务器 collocated 在池中的每个前端服务器上运行，并且应该为池中的用户提供足够的容量。 对于独立的中介服务器，请参阅本主题后面的 "中介服务器" 一节。  <br/> |
|一个标准版服务器  <br/> |如果你使用标准版服务器来托管用户，我们强烈建议你始终使用两台服务器，这两台服务器使用[计划实现高可用性和灾难恢复的建议进行了](https://technet.microsoft.com/library/15a72073-0336-45dd-b2a0-35e7522c6000.aspx)配对。 服务器对中的每台服务器最多可承载 2,500 个用户，如果一台服务器出现故障，则另一台服务器在进行故障转移时可支持 5,000 个用户。  <br/>  如果您的部署包含大量音频或视频流量，当每台服务器用户数超过 2,500 个时，服务器性能可能下降。 在这种情况下，应考虑添加更多标准版服务器或迁移到 Skype for business Server Enterprise Edition。 <br/> |

## <a name="front-end-server"></a>前端服务器

> [!NOTE]
> 此服务器角色不支持扩展池。

在前端池中，假设在池中6660的所有服务器上都启用了超线程，假设在池中的所有服务器上都启用了超线程，并且您使用的是 SQL Server Express Edition，并且服务器硬件满足[Skype For Business server 2019 的服务器要求](system-requirements.md)中的建议。 一个前端池中的最大用户数是106000，它再次假设已启用超线程，并且在池中的所有服务器上使用 SQL Server Express Edition。 如果网站上有超过106000的用户，则可以部署多个前端池。

当你考虑到前端池中的用户数时，请在与此前端池关联的分支机构上包括驻留在 Survivable 分支装置和 Survivable 分支服务器上的任何用户。

活动服务器不可用时，其连接会自动转接给池中的其他服务器。 在拥有30000用户和5个前端服务器的方案中，如果一台服务器不可用，则需要将您的用户的6000连接转移到其他4台剩余的服务器。 其余四台服务器中的每台服务器将拥有 7500 个用户，此数量大于推荐的数量。

如果您的30000用户已开始使用6个前端服务器，而另一个不可用，则总共5000用户需要移到其余五台服务器。 这五台服务器将各承载 6000 个用户，这没有超出推荐的范围。

前端池中的最大用户数是106000。 池中的最大前端服务器数是16。

对于80000用户的前端池，16个前端服务器对于性能，在使用[Skype For Business 服务器中的用户模型](../../SfbServer/plan-your-deployment/capacity/user-models.md)的典型部署中将非常好。 为支持灾难恢复故障转移而设计的部署假设最多可以在两个配对的前端池中托管每个用户，其中每个池都有足够53000的前端服务器以包含两个池中的用户，因此，如果一个池需要在 t 上进行故障转移o 另一种。

由于以下原因，特定前端池支持的具有良好性能的用户数可能与这些数字不同：

- 前端服务器的硬件不符合建议。
- 除了使用 SQL Server Express Edition 之外，你还可以使用另一个 SQL Server 版本，你可以在每个前端池中托管其他用户。
- 你的组织的使用与用户模型有很大区别，例如，如果你有大量的会议流量。

下表显示了在给定用户模型的情况下，IM 和状态的平均带宽，在[Skype For Business 服务器的用户模型](../../SfbServer/plan-your-deployment/capacity/user-models.md)中已定义。

|**每个用户的平均带宽**|**每个具有6660用户的前端服务器的带宽要求**|
|:-----|:-----|
|3-3.75 KBps  <br/> |13 MBps  <br/> |

> [!NOTE]
> 若要提高前端服务器上归置的 A/V 式会议和中介服务器功能的媒体性能，应在前端服务器上的网络适配器上启用接收端缩放（RSS）。 通过启用 RSS，服务器上的多个处理器能够以并行方式处理传入数据包。 有关详细信息，请参阅[Windows Server 2012 文档中的接收端缩放（RSS）](https://go.microsoft.com/fwlink/p/?LinkId=620365)。 有关如何启用 RSS 的详细信息，需要参阅网络适配器文档。

## <a name="conferencing-maximums"></a>会议最大值

如果用户模型中有5% 的用户在同一时间内可能处于会议中，则106000用户可以同时在会议中拥有5300用户。 这些会议可能混合多种媒体（如一些仅含 IM、一些含有 IM 和音频、一些含有音频/视频）并拥有大量参与者。 允许的实际会议数没有硬限制，但实际用法决定了实际性能。 例如，如果您的组织中的多个混合模式会议与用户模型中的假设不同，您可能需要部署更多的前端服务器或 A/V 会议服务器，而不是本文中的建议。 有关用户模型中的假设的详细信息，请参阅[Skype For Business 服务器中的用户模型](../../SfbServer/plan-your-deployment/capacity/user-models.md)。

常规 Skype for business Server 前端池托管的受支持的最大会议大小（也托管用户是250参与者。 在进行拥有 250 个用户的会议时，该池同时还可支持其他会议，从而使总数为 5% 的池用户参加并发会议。 例如，在16前端服务器和106000用户的池中，当 250-用户的会议发生时，Skype for Business 服务器支持5050参与小型会议的其他用户。

无论驻留在前端池或标准版服务器上的用户数不受支持，Skype for Business 服务器最少支持125在同一池或服务器上参与小型会议的其他用户，这些用户是在托管250用户的会议

若要启用250和1000用户之间的会议，您可以设置单独的前端池，只需托管这些会议。 此前端池不会托管任何用户。 有关详细信息，请参阅[Skype For Business 服务器中的大型会议计划](../../SfbServer/plan-your-deployment/conferencing/large-meetings.md)。

如果您的组织拥有的混合模式会议比用户模型中的假设多，则您可能需要部署比本文档中的建议更多的前端服务器（最大限制为16个前端服务器）。 有关用户模型中的假设的详细信息，请参阅[Skype For Business 服务器中的用户模型](../../SfbServer/plan-your-deployment/capacity/user-models.md)。

## <a name="edge-server"></a>边缘服务器

> [!NOTE]
> 此服务器角色不支持扩展池。

你应该为将同时访问网站的每个18000远程用户部署一个 Edge 服务器。 至少我们建议使用两个边缘服务器来实现高可用性。 这些建议假定你的 Edge 服务器的硬件满足[服务器硬件平台](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)中的建议。

当你考虑 Edge 服务器的用户数时，请将驻留在 Survivable 分支装置和 Survivable 分支机构的用户包括在与此站点上的前端池关联的分支机构。

> [!NOTE]
> 若要提高边缘服务器上的 A/V 会议边缘服务的性能，应在边缘服务器上的网络适配器上启用接收端缩放（RSS）。 通过启用 RSS，服务器上的多个处理器能够以并行方式处理传入数据包。 有关详细信息，请检查[Windows Server 2012 中的 "接收方缩放（RSS）](https://go.microsoft.com/fwlink/p/?linkId=268731)"。 有关如何启用 RSS 的详细信息，需要参阅网络适配器文档。

## <a name="director"></a>控制器

> [!NOTE]
> 此服务器角色不支持扩展池。

如果你部署 Director 服务器角色，我们建议你为将同时访问网站的每个18000远程用户部署一个 Director。 至少我们建议使用两个控制器来实现高可用性。 这些建议假定你的 Edge 服务器的硬件满足[服务器硬件平台](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)中的建议。

当你考虑控制器的用户数时，请将驻留在 Survivable 分支机构和 Survivable 分支机构的用户包括在与此站点上的前端池关联的分支机构。

## <a name="mediation-server"></a>中介服务器

> [!NOTE]
> 此服务器角色不支持扩展池。

如果您 collocate 中介服务器与前端服务器，则中介服务器在池中的每个前端服务器上运行，并且应该为池中的用户提供足够的容量。

如果你部署独立的中介服务器池，则要部署多少个中介服务器取决于多个因素，包括用于中介服务器的硬件、你拥有的 VoIP 用户数、每个中介服务器池的网关对等数量控件、通过这些网关的繁忙工时流量以及绕过中介服务器的媒体的通话百分比。

下表提供了一个有关中介服务器的并发调用数的准则，假定中介服务器的硬件满足[服务器硬件平台](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)中的要求，并且启用了超线程处理。 有关中介服务器可伸缩性的详细信息，请参阅[在 skype for Business 服务器中针对中介服务器的](../../SfbServer/plan-your-deployment/capacity/mediation-server-deployment-guidelines.md)skype For business 服务器和部署指南[估计语音使用情况和流量](../../SfbServer/plan-your-deployment/capacity/estimating-voice-traffic.md)。

下表假定[Skype For Business Server 的用户模型](../../SfbServer/plan-your-deployment/capacity/user-models.md)中总结了使用情况。

**独立中介服务器容量：70% 内部用户，具有非绕过呼叫容量的30% 外部用户（由中介服务器执行的媒体转码）**

|**服务器硬件**|**最大呼叫数**|**最大 T1 线路数**|**最大 E1 线路数**|
|:-----|:-----|:-----|:-----|
|英特尔至强 2673 v3 双处理器、6核、2.4 千兆位（GHz）**或更高**版本，带有 64 GB 内存和一个双端口网络适配器卡。  <br/> |1500  <br/> |64  <br/> |49  <br/> |
|英特尔至强 2673 v3 双处理器、6核、2.4 千兆位（GHz）或更高版本，带有 64 GB 内存和一个双端口网络适配器卡。  <br/> |2000  <br/> |88  <br/> |66  <br/> |

> [!NOTE]
> 尽管使用 64 GB 内存的服务器用于性能测试，但具有 32 GB 内存的服务器对于独立的中介服务器受支持，并且足以提供此表中所示的性能。

**中介服务器容量（中介服务器 Collocated 前端服务器）70% 内部用户、30% 外部用户、非绕过呼叫容量（由中介服务器执行的媒体处理）**

|**服务器硬件**|**最大呼叫数**|
|:-----|:-----|
|英特尔至强 2673 v3 双处理器、6核、2.4 千兆位（GHz）或更高版本，以及 64 GB 内存和2个1GB 网络适配器卡。  <br/> |200  <br/> |

> [!NOTE]
> 此数字比独立中介服务器的号码小得多。 这是因为除了语音通话所需的转换程序之外，前端服务器还必须处理驻留在其上的6600用户的其他功能和功能。

> [!NOTE]
> 若要提高中介服务器的性能，应在中介服务器上的网络适配器上启用接收端缩放（RSS）。 通过启用 RSS，服务器上的多个处理器能够以并行方式处理传入数据包。 有关详细信息，请参阅 "[Windows Server 2012 中的接收端缩放](https://go.microsoft.com/fwlink/p/?linkId=268731)"。 有关如何启用 RSS 的详细信息，需要参阅网络适配器文档。

## <a name="back-end-server"></a>后端服务器

虽然大部分数据库信息存储在前端服务器上，但你应该确保后端服务器满足本部分前面和[服务器硬件平台](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)中列出的硬件建议。

为了提供后端服务器的高可用性，我们建议部署 AlwaysOn 可用性组或服务器镜像。 有关详细信息，请参阅 [Back End Server high availability in Skype for Business Server](../../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md)。

## <a name="monitoring-and-archiving"></a>监控和存档

如果你部署监视或存档，这些服务的前端功能将在前端服务器上运行，监视和存档各自使用其自己的数据库存储，与后端存储分开。 或者，如果已部署 Exchange 2013，则可以在 Exchange 中（而不是在专用的 SQL 应用商店中）存储即时消息存档数据。

下表说明了每个用户每天监控和存档数据所需的数据库存储的大致数量。

||**CDR（监控）** <br/> |**QoE（监控）** <br/> |**存档** <br/> |
|:-----|:-----|:-----|:-----|
|每个用户每天所需的磁盘空间  <br/> |49 KB  <br/> |28 KB  <br/> |57 KB  <br/> |

Microsoft 在其性能测试期间对用于监控和存档的数据库服务器使用了下表中的硬件。 测试收集了两个前端池的数据，每个池包含80000用户。

**监控和存档性能测试中使用的硬件**

|**硬件组件**|**推荐**|
|:-----|:-----|
|CPU  <br/> |Intel Xeon E5-2673 v3 双处理器，6 核，2.4 GHz 或更快。  <br/> |
|内存  <br/> |48 GB  <br/> |
|磁盘  <br/> | 以下之一：<br/> • 4 块或更多 10000 RPM 硬盘，至少 72 GB 可用磁盘空间（磁盘应采用双 RAID 1 配置）。 <br/>或 <br/>• 能够提供与 4 块 10000 RPM 机械硬盘相同的可用空间和类似性能的固态硬盘 (SSD)。   <br/> |
|网络  <br/> | 1 个双端口网络适配器，1 Gbps 或更高（建议为 2 Gbps，这要求与一个 MAC 地址和一个 IP 地址结合使用）。  <br/> |

**推荐的磁盘配置**

|**驱动器** <br/> |**RAID 配置** <br/> |**磁盘数** <br/> |
|:-----|:-----|:-----|
|单个驱动器上的 CDR、QoE 和存档数据库数据文件  <br/> |1+0  <br/> |utf-16  <br/> |
|CDR 数据库日志文件  <br/> |1  <br/> |ppls-2  <br/> |
|QoE 数据库日志文件  <br/> |1  <br/> |ppls-2  <br/> |
|存档数据库日志文件  <br/> |1  <br/> |ppls-2  <br/> |

## <a name="video-interop-server-capacity"></a>视频互操作服务器容量

如果你部署视频互操作服务器，并且需要确定容量，请查看将同时拨打的视频 Teleconferencing 系统（VTCs）的最大数量。 例如，如果您的组织中有 250 个 VTC，并且您的用户模型估计最多有 20% 的 VTC 可能存在于并发呼叫中，应以 50 个并发 VTC 为基础进行容量规划。

