---
title: 容量规划的 Skype 业务服务器 2019
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 本节中的主题帮助您了解如何规划和部署 Skype 业务服务器，以便您可以充分规划您的组织和 plan for 其活动生成服务器负载中的用户数。
ms.openlocfilehash: 996fd1df51442bcaadbd0ae548e9cf57e580279a
ms.sourcegitcommit: 112dc19075f9213207fde9e30bcde5681324b7c9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2018
ms.locfileid: "25696343"
---
# <a name="capacity-planning-for-skype-for-business-server-2019"></a>服务器容量规划的 Skype 业务 2019

本文提供有关该站点的用户数针对某个站点需要多少台服务器根据[Skype 业务服务器中的 User models](../../SfbServer/plan-your-deployment/capacity/user-models.md)中所述的使用情况的指南

## <a name="tested-hardware-platform"></a>受测试的硬件平台

我们已完成对下表中所述的硬件执行性能测试。 我们的所有建议和结果都是以此硬件为基础。 如果您决定使用功能不如这里列出的硬件强大的其他硬件，请注意您可能会遇到功能性问题或性能较差。

**性能测试中使用的硬件**

|**硬件组件**|**推荐**|
|:-----|:-----|
|CPU  <br/> |Intel Xeon E5 2673 v3 双处理器、 6 核 2.4 ghz 或更高版本。  <br/> Intel Itanium 处理器不支持 Skype 业务服务器 2019年角色。  <br/> |
|内存  <br/> |32 GB。  <br/> |
|磁盘  <br/> |以下之一：  <br/> • 8 块或更多 10000 RPM 硬盘，至少 72 GB 可用磁盘空间（2 块磁盘使用 RAID 1，6 块磁盘使用 RAID 10）。  <br/> 或  <br/> • 能够提供与 8 块 10000 RPM 机械硬盘相同的可用空间和类似性能的固态硬盘 (SSD)。  <br/> |
|网络  <br/> |1 个双端口网络适配器，1 Gbps 或更高（可使用 2 个网络适配器，但需要通过一个 MAC 地址和一个 IP 地址配合使用）。  <br/> 双处理器或多宿主配置是**不**支持前端服务器、 后端服务器，和 Standard Edition 服务器。 <br/> 只要它们不公开给操作系统，并且正在使用监视和管理服务器硬件，您可以通过带管理系统，如 DRAC 或 ILO。 这种情况不会形成多宿主服务器，并且受支持。  <br/> |

## <a name="summary-of-results"></a>结果摘要

下表总结了我们的建议。

|**服务器角色**|**受支持的最大用户数**|
|:-----|:-----|
|高可用性的前端池与十六个前端服务器和后端服务器或后端服务器与 SQL Always On 一对。  <br/> |106,000 唯一用户同时登录，以及 50%多点登录 (mpop) 表示非移动实例，以及 40%的 210,000 终结点总数为 Mobility 启用的用户。  <br/> |
|A/V 会议  <br/> |A / V 会议服务提供的前端池支持假定最大会议大小为 250 个用户的池的会议和运行一次只能有一个此类大型会议。  <br/> **注意：** 此外，您可以支持大型会议的部署独立的前端池与两个前端服务器来承载的大型会议的 250 到 1000 位用户之间。 有关详细信息，请参阅[规划中的业务服务器 Skype 的大型会议](../../SfbServer/plan-your-deployment/conferencing/large-meetings.md)。 <br/> |
|一台边缘服务器  <br/> |18000 并发远程用户。  <br/> |
|一台控制器  <br/> |18000 并发远程用户。  <br/> |
|监控和存档  <br/> |在上运行每个前端服务器，而不是单独的服务器角色监控和存档前端服务。  <br/> 监控和存档仍需要其自己各自的数据库存储。 如果您还可以运行 Exchange 2013 或更高版本，您可以在 Exchange 中，而不是专用的 SQL 数据库中保留存档数据。  <br/> |
|一台中介服务器  <br/> |中介服务器与池，每个前端服务器上运行的前端服务器并置，并应能提供足够的容量池中的用户。 独立的中介服务器，请参阅本主题后面的"中介服务器"部分。  <br/> |
|一台 Standard Edition server  <br/> |我们强烈建议如果您使用向承载用户的 Standard Edition 服务器，则您始终使用两台服务器，配对使用中[的高可用性和灾难恢复的规划](https://technet.microsoft.com/library/15a72073-0336-45dd-b2a0-35e7522c6000.aspx)建议。 服务器对中的每台服务器最多可承载 2,500 个用户，如果一台服务器出现故障，则另一台服务器在进行故障转移时可支持 5,000 个用户。  <br/>  如果您的部署包含大量音频或视频流量，当每台服务器用户数超过 2,500 个时，服务器性能可能下降。 在这种情况下，您应考虑添加更多的 Standard Edition 服务器或业务 Server Enterprise edition 移动到 Skype。 <br/> |

## <a name="front-end-server"></a>前端服务器

> [!NOTE]
> 此服务器角色不支持扩展池。

在前端池中，您应具有一个前端服务器的每个 6,660 个用户驻留在您的池、 服务器硬件假定超线程是所有服务器上启用该池，在您使用的 SQL Server Express Edition，并且符合的建议中[的业务服务器 2019年的 Skype 的服务器要求](system-requirements.md)。 一个前端池中的用户的最大数是 106,000，再次假定启用了超线程和 SQL Server Express Edition 在池中的所有服务器上使用。 如果您在站点有多个 106,000 用户，则可以部署多个前端池。

当您帐户的前端池中的用户数包括任何用户驻留在 Survivable Branch Appliance 和 Survivable Branch Server 与此前端池关联的分支机构上。

活动服务器不可用时，其连接会自动转接给池中的其他服务器。 在方案中了 3 万名用户和五个前端服务器，如果一台服务器不可用，需要转接到其他四个其余服务器 6000 个用户的连接。 其余四台服务器中的每台服务器将拥有 7500 个用户，此数量大于推荐的数量。

如果改为具有与六个前端服务器启动 30,000 用户和一个变得不可用，5000 位用户，总计需要将移动到的剩余的五台服务器。 这五台服务器将各承载 6000 个用户，这没有超出推荐的范围。

前端池中的用户的最大数量为 106,000。 池中前端服务器的最大数量为 16。

对于具有 80,000 名用户的前端池，16 前端服务器将良好的性能，请按照[Skype 业务服务器中的用户模型](../../SfbServer/plan-your-deployment/capacity/user-models.md)的典型部署中。 部署旨在支持灾难恢复故障转移假定最多 53,000 用户可以承载在每两个池中的前端池，其中每个池都有足够的前端服务器以包含这两个池中，用户应一个池需要进行故障转移 to 其他。

支持具有良好性能的特定的前端池的用户数可能不同从这些号码，原因如下：

- 前端服务器的硬件不符合建议。
- 而不是使用 SQL Server Express Edition，则使用另一个 SQL Server Edition，您可以向主机中每个前端池的其他用户。
- 贵组织的使用率较大的不同用户模型，例如，如果您有更多会议流量。

下表显示了 IM 和状态的用户模型， [Skype 业务服务器中的用户模型](../../SfbServer/plan-your-deployment/capacity/user-models.md)中定义的平均带宽。

|**每个用户的平均带宽**|**每个前端服务器拥有 6,660 个用户的带宽要求**|
|:-----|:-----|
|3 3.75 kBps  <br/> |13 MBps  <br/> |

> [!NOTE]
> 改进的共同位于媒体性能 A / V 会议和中介服务器在前端服务器上的功能，您应启用接收端扩展在前端服务器上的网络适配器 (RSS)。 通过启用 RSS，服务器上的多个处理器能够以并行方式处理传入数据包。 有关详细信息，请参阅[ Windows Server 2012 中的接收方缩放 (RSS)](https://go.microsoft.com/fwlink/p/?LinkId=620365) 文档。 有关如何启用 RSS 的详细信息，需要参阅网络适配器文档。

## <a name="conferencing-maximums"></a>会议最大值

给定 5%的池中的用户在任何时刻可能会在会议中的用户模型，106,000 用户池无法具有大约 5300 用户在会议中同时。 这些会议可能混合多种媒体（如一些仅含 IM、一些含有 IM 和音频、一些含有音频/视频）并拥有大量参与者。 允许的实际会议数没有硬限制，但实际用法决定了实际性能。 例如，如果您的组织有混合模式会议中的用户模型假定比，您可能需要部署多个前端服务器或 A / V 会议服务器比建议在本文中找到。 有关用户模型中的假设详细信息，请参阅[Skype 业务服务器中的用户模型](../../SfbServer/plan-your-deployment/capacity/user-models.md)。

由业务 Server 前端池，这还承载用户的正则 Skype 承载受支持的最大会议大小为 250 的参与者。 在进行拥有 250 个用户的会议时，该池同时还可支持其他会议，从而使总数为 5% 的池用户参加并发会议。 例如，16 前端服务器和 106,000 用户的池，在 250 个用户会议进行过程，Skype 业务服务器将支持 5,050 其他用户参加较小的会议。

无论用户数驻留在前端池或 Standard Edition server，Skype 业务服务器支持 125 在同一个池或服务器承载 250 个用户会议上的小型会议参与其他用户的最小值。

若要启用已之间 250 到 1000 位用户的会议，您可以设置单独的前端池只需以承载这些会议。 此前端池不承载任何用户。 有关详细信息，请参阅[Plan for Business Server 的 Skype 中的大型会议](../../SfbServer/plan-your-deployment/conferencing/large-meetings.md)。

如果您的组织具有更多混合模式会议中的用户模型假定比，您可能需要部署多个前端服务器比我们 （最多 16 前端服务器的限制） 本文档中的建议。 有关用户模型中的假设详细信息，请参阅[Skype 业务服务器中的用户模型](../../SfbServer/plan-your-deployment/capacity/user-models.md)。

## <a name="edge-server"></a>边缘服务器

> [!NOTE]
> 此服务器角色不支持扩展池。

您应部署一台边缘服务器的每个 18000 远程用户将同时访问网站。 至少建议的高可用性的两个边缘服务器。 这些建议假定为边缘服务器的硬件满足[硬件与 Server Hardware Platforms](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)中的建议。

当您帐户的边缘服务器的用户数量的用户包括驻留在 Survivable Branch Appliance 与前端池在此站点关联的分支机构的 Survivable Branch Server 上。

> [!NOTE]
> 以提高性能的 A / V 会议边缘服务上边缘服务器，您应在边缘服务器上启用接收端扩展 (RSS) 网络适配器上的。 通过启用 RSS，服务器上的多个处理器能够以并行方式处理传入数据包。 有关详细信息，请检查[接收端扩展 (RSS) Windows Server 2012 中](https://go.microsoft.com/fwlink/p/?linkId=268731)。 有关如何启用 RSS 的详细信息，需要参阅网络适配器文档。

## <a name="director"></a>控制器

> [!NOTE]
> 此服务器角色不支持扩展池。

如果您部署控制器服务器角色，我们建议您部署的每个 18000 远程用户将同时访问网站的一台控制器。 至少建议高可用性的两个的控制器。 这些建议假定为边缘服务器的硬件满足[硬件与 Server Hardware Platforms](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)中的建议。

当您帐户的用户包括控制器，用户数的驻留在 Survivable Branch Appliance 分支机构与前端池在此站点关联的 Survivable Branch Server 上。

## <a name="mediation-server"></a>中介服务器

> [!NOTE]
> 此服务器角色不支持扩展池。

如果您将并置中介服务器与前端服务器，中介服务器池中，每个前端服务器上运行，并应能提供足够的容量池中的用户。

如果您部署独立的中介服务器池，然后多少台中介服务器部署取决于许多因素，包括用于中介服务器，必须 VoIP 用户数的硬件，网关数同级的每个中介服务器池控件，通过这些网关和使用媒体绕过中介服务器的呼叫的百分比的忙时流量。

下表提供了有关多少并发呼叫中介服务器可以处理，假定中介服务器的硬件满足[硬件与 Server Hardware Platforms](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)中的要求和启用了超线程的准则。 有关中介服务器可伸缩性的详细信息，请参阅[估算语音用法和 Skype 业务服务器通信](../../SfbServer/plan-your-deployment/capacity/estimating-voice-traffic.md)和[Skype 业务服务器中的中介服务器的部署指南](../../SfbServer/plan-your-deployment/capacity/mediation-server-deployment-guidelines.md)。

下面的所有表都将用法都假定为[Skype 业务服务器中的 User models](../../SfbServer/plan-your-deployment/capacity/user-models.md)中总结。

**独立的中介服务器容量： 70%内部用户，30%外部用户，带有无绕过呼叫容量 （由中介服务器执行的媒体转码）**

|**服务器硬件**|**最大呼叫数**|**最大 T1 线路数**|**最大 E1 线路数**|
|:-----|:-----|:-----|:-----|
|Intel Xeon E5 2673 v3 双处理器、 6 核、 2.4 ghz 或更高版本**超线程禁用**，带 64 GB 内存和一个个双端口网络适配器卡。  <br/> |1500  <br/> |64  <br/> |49  <br/> |
|Intel Xeon E5 2673 v3 双处理器、 6 核 2.4 ghz 或更高版本，带 64 GB 内存和一个个双端口网络适配器卡。  <br/> |2000  <br/> |88  <br/> |66  <br/> |

> [!NOTE]
> 尽管 64 GB 的内存服务器用于测试的性能，32 GB 内存的服务器支持的独立的中介服务器，并且足以提供此表中所示的性能。

**中介服务器容量 （前端服务器与中介服务器并置） 70%内部用户，30%外部用户，无绕过呼叫容量 （由中介服务器执行媒体处理）**

|**服务器硬件**|**最大呼叫数**|
|:-----|:-----|
|Intel Xeon E5 2673 v3 双处理器、 6 核 2.4 ghz 或更高版本。、 带 64 GB 内存和 2 个 1GB 网络适配器卡。  <br/> |200  <br/> |

> [!NOTE]
> 此数字是远远小于独立的中介服务器的号码。 这是因为前端服务器必须处理其他功能和函数的 6600 用户驻留在除了转码所需的语音呼叫。

> [!NOTE]
> 若要提高中介服务器的性能，应中介服务器上启用接收端扩展 (RSS) 网络适配器上。 通过启用 RSS，服务器上的多个处理器能够以并行方式处理传入数据包。 有关详细信息，请参阅"[Windows Server 2012 中接收端扩展](https://go.microsoft.com/fwlink/p/?linkId=268731)"。 有关如何启用 RSS 的详细信息，需要参阅网络适配器文档。

## <a name="back-end-server"></a>后端服务器

虽然大部分数据库信息存储在前端服务器上的主要，您应该确保您的后端服务器满足和[与 Server Hardware Platforms](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)中本节前面列出的硬件建议。

若要提供的您的后端服务器高可用性，建议部署 AlwaysOn 可用性组或 server 镜像。 有关详细信息，请参阅 [Back End Server high availability in Skype for Business Server](../../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md)。

## <a name="monitoring-and-archiving"></a>监控和存档

如果您部署监控或存档，在前端服务器上运行这些服务的前端功能，监控和存档使用自己数据库存储分开的后端存储。 或者，如果已部署的 Exchange 2013，也可以存储即时消息存档数据在 Exchange 而不是专用的 SQL 存储中。

下表说明了每个用户每天监控和存档数据所需的数据库存储的大致数量。

||**CDR（监控）** <br/> |**QoE（监控）** <br/> |**存档** <br/> |
|:-----|:-----|:-----|:-----|
|每个用户每天所需的磁盘空间  <br/> |49 KB  <br/> |28 KB  <br/> |57 KB  <br/> |

Microsoft 在其性能测试期间对用于监控和存档的数据库服务器使用了下表中的硬件。 测试收集两个前端池，其中每个包含 80,000 用户的数据。

**监控和存档性能测试中使用的硬件**

|**硬件组件**|**推荐**|
|:-----|:-----|
|CPU  <br/> |Intel Xeon E5 2673 v3 双处理器、 6 核 2.4 ghz 或更高版本。  <br/> |
|内存  <br/> |48 GB  <br/> |
|磁盘  <br/> |
任一: • 4 或更多 10000 RPM 硬盘驱动器具有至少 72 GB 可用磁盘的空间 （磁盘应为 2 个 RAID 1 配置中）。 或 • 固态驱动器 (Ssd) 能够提供相同释放空间和类似于 4 10000 RPM 机械磁盘驱动器的性能。   <br/> | |网络  <br/> |1 个双端口网络适配器，1 Gbps 或更高 （建议为 2，这要求与一个 MAC 地址和一个 IP 地址结合使用）。  <br/> |

**建议的磁盘配置**

|**驱动器** <br/> |**RAID 配置** <br/> |**磁盘数** <br/> |
|:-----|:-----|:-----|
|单个驱动器上的 CDR、QoE 和存档数据库数据文件  <br/> |1+0  <br/> |16  <br/> |
|CDR 数据库日志文件  <br/> |1  <br/> |2  <br/> |
|QoE 数据库日志文件  <br/> |1  <br/> |2  <br/> |
|存档数据库日志文件  <br/> |1  <br/> |2  <br/> |

## <a name="video-interop-server-capacity"></a>视频互操作服务器容量

如果您部署视频互操作服务器，您需要确定容量，您将看的最大视频电话会议系统 (VTCs) 将并发呼叫数。 例如，如果您的组织中有 250 个 VTC，并且您的用户模型估计最多有 20% 的 VTC 可能存在于并发呼叫中，应以 50 个并发 VTC 为基础进行容量规划。

