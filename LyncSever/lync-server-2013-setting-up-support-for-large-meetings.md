---
title: 设置对大型会议的支持
TOCTitle: 设置对大型会议的支持
ms:assetid: 8e22d34b-b395-408d-9d48-8f2a3abe9513
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205074(v=OCS.15)
ms:contentKeyID: 49313553
ms.date: 07/21/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 设置对大型会议的支持

 

_**上一次修改主题：** 2014-05-12_

若要支持最多包含 1000 个用户的大型会议，需要创建适当的拓扑、会议硬件和软件必备组件并适当地配置环境。

## 拓扑要求

一个大型会议至少需要一个 前端服务器和一个 后端服务器。但为了提供高可用性，建议使用双 前端服务器池和镜像的 后端服务器。

主持大型会议的用户的用户帐户必须驻留在此池中。但建议您不要在此池中承载其他用户帐户，而是仅将其用于大型会议。最佳实践是，在此池中创建一个仅用于主持大型会议的特殊用户帐户。由于大型会议设置的性能经过优化，当涉及 PSTN 终结点时，使用它作为常规用户可能会引起问题，例如无法将 P2P 会话提升到会议。

在管理刚好包含两个前端服务器的池时，有一些特别注意事项。有关详细信息，请参阅[Lync Server 2013 中适用于前端服务器、即时消息和状态的拓扑和组件](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)。

此外，如果您希望选择性地提供针对用于大型会议的池的灾难恢复备份和故障转移，您可以将该池与其他数据中心内类似的设置专用池配对。有关详细信息，请参阅 [在 Lync Server 2013 中规划高可用性和灾难恢复](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。

![大型会议池配置](images/JJ205074.ee00e1c0-c3b2-464d-aa89-a1e877cd034d(OCS.15).jpg "大型会议池配置")

有关拓扑的其他说明包括：

  - 文件共享是存储会议内容所必需的，如果已部署和启用 存档服务器，则文件共享是存储存档文件所必需的。文件共享可专用于池，也可以是已部署该池的站点中的另一个池所使用的同一文件共享。有关配置文件共享的详细信息，请参阅 [为 Lync Server 2013 配置文件存储](lync-server-2013-configure-dfs-file-storage.md)。

  - Office Web Apps Server 是在大型会议中启用 PowerPoint 演示文稿功能所必需的。 Office Web Apps Server 可专用于大型会议池，也可以是已部署专用池的站点中的其他池所使用的同一 Office Web Apps Server。

  - 若要实现 前端服务器的负载平衡，则需要实现 HTTP 流量（如会议内容下载）的硬件负载平衡。建议对 SIP 流量实现 DNS 负载平衡。有关详细信息，请参阅 [Lync Server 2013 的负载平衡要求](lync-server-2013-load-balancing-requirements.md)。

  - 若要对专用的大型会议池使用 监控服务器，建议使用 监控服务器及其数据库，这些数据库将在 Lync Server 部署中的所有 前端服务器池中共享。

## 软硬件要求

专用大型会议池中服务器的硬件要求与其他 Lync Server 2013 服务器的硬件要求相同。有关硬件要求的详细信息，请参阅 [适用于 Lync Server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)。

专用大型会议池中的服务器必须满足所有 Lync Server 2013 软件要求。有关软件要求的详细信息，请参阅以下文档：

  - [Lync Server 2013 中的服务器和工具操作系统支持](lync-server-2013-server-and-tools-operating-system-support.md)

  - [Lync Server 2013 中的数据库软件支持](lync-server-2013-database-software-support.md)

  - [Lync Server 2013 的其他软件要求](lync-server-2013-additional-software-requirements.md)

此外， Lync Server 2013 和所有 Lync Server 2013 客户端必须具有最新更新。

## 配置要求

建议您创建一个专用于大型会议的新会议策略，然后将此会议策略分配给驻留在专用大型会议池中的用户。使用以下设置配置会议策略：

  - 将 **MaxMeetingSize** 选项设置为 **1000**。（默认值为 **250**。）

  - 将 **AllowLargeMeetings** 选项设置为 **True**。

  - 将 **EnableAppDesktopSharing** 选项设置为“无”。

  - 将 **AllowUserToScheduleMeetingsWithAppSharing** 选项设置为 **False**。

  - 将 **AllowSharedNotes** 选项设置为 **False**。

  - 将 **AllowAnnotations** 选项设置为 **False**。

  - 将 **DisablePowerPointAnnotations** 选项设置为 **True**。

  - 将 **AllowMultiview** 选项设置为 **False**。

  - 将 **EnableMultiviewJoin** 选项设置为 **False**。

> [!NOTE]  
> 若要在 Lync Server 2013 中支持包含 1000 个用户的大型会议，则需要将会议计划程序的会议策略中的 <strong>AllowLargeMeetings</strong> 设置设为 True。若将此设置设为 True，则 Lync 体验将在用户参加超大型会议时针对此类会议进行优化。具体而言，在大型会议中， Lync 不显示完整会议参与者列表的初始或更新情况，对于客户端和 Lync Server 2013 而言，这是一个性能瓶颈。相反， Lync 仅显示有关用户和会议演示者列表的信息。 Lync 仍将正确显示大型会议中可用的参与者的总数。



若要禁用大型会议中不需要的会议功能，需要使用此处指定的所有会议策略设置（“最大会议规模”设置除外）。

此外，您需要配置专用大型会议池，以便驻留在池中并负责管理会议日程的每个 Lync Server 2013 用户均具有适当的权限。为此，请执行以下操作：

  - 将“指定为演示者”选项设置为“无”。通常，大型会议的所有参与者中仅一个或几个用户可成为演示者，因此不应自动允许参与者以演示者身份参加大型会议。相反，应在计划会议时明确指定演示者，或在大型会议进行中将参与者显式提升为演示者。

  - 确保未选中“默认分配的会议类型”复选框。此设置控制 Lync 2013 联机会议外接程序是否始终使用组织者的已分配会议来计划会议，这意味着计划的会议将具有相同的加入 URL 和音频信息。在小组协作方案中，可确保此类分配的会议类型很好地进行，因为每个用户均具有自己的单独分配的会议，并且持续加入 URL 和音频信息有助于推动更快的会议加入。但是，在大型会议方案中，大型会议支持人员将使用一组用户凭据来计划大型会议，然后向会议请求者提供加入 URL 和音频信息。在此情况下，使用不同的 URL 加入各个会议所达到的效果会更佳。

  - 确保未选中“默认允许匿名用户”复选框，除非需要这样做。此设置在未使用分配的会议时将影响 Lync 2013 联机会议外接程序所计划的默认会议访问类型。此设置的相应选项取决于您的组织需求。如果您组织的大多数大型会议是内部会议，请不要选择此选项。如果大多数大型会议需要外部用户能够加入，请选择此选项。

