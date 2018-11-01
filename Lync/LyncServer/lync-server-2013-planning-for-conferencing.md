---
title: Lync Server 2013：规划会议
TOCTitle: 规划会议
ms:assetid: 983a272a-e1b3-4d70-8f84-836b092fe526
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398781(v=OCS.15)
ms:contentKeyID: 49313692
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中规划会议

 

_**上一次修改主题：** 2013-01-29_

Lync Server 2013 提供了一组丰富的会议功能：

  - Web 会议，包括文档协作、应用程序共享以及桌面共享。 Lync Server 2013 使用 Office Web Apps 和 Office Web Apps Server 处理 PowerPoint 演示文稿的共享和呈现。有关安装和配置 Office Web Apps Server 的详细信息，请参阅 [配置与 Office Web Apps Server 和 Lync Server 2013 的集成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。

  - 音频/视频 (A/V) 会议，无需外部服务（如 Microsoft Live Meeting 服务或第三方音频桥）即可使用户进行实时音频或视频会议。

  - 电话拨入式会议，无需第三方音频会议提供商即可使用户通过使用公用电话交换网 (PSTN) 电话来加入 Lync Server 2013 会议的音频部分。

  - 即时消息 (IM) 会议，其中两个以上的用户可在单个 IM 会话中进行通信。有关 IM 会议的详细信息，请参阅 [在 Lync Server 2013 中规划前端服务器、即时消息和状态](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md)。

Lync Server 2013 同时支持计划内会议和临时会议。

部署 Lync Server 2013前端服务器时，可以选择是否还部署 Web 会议、A/V 会议和电话拨入式会议功能。IM 会议功能始终与 IM 对话功能一起自动部署在 Lync Server 2013前端服务器上。

> [!NOTE]  
> 如果您的部署包括使用 Office Communicator 2007 R2 客户端（包括 Live Meeting 控制台或 Microsoft Office Outlook 会议外接程序）组织的会议，则当这些会议迁移到 Lync Server 2013 后，它们将具有以下限制：
<ul>
<li><p>会议中的用户将不能使用数据协作功能，包括文档协作、应用程序共享和桌面共享。</p></li>
<li><p>可能出现稳定性问题，因为不能通过 Lync Server 2013 支持 Office Communicator 2007 R2 客户端。</p></li>
</ul>
为避免这些问题，请使用 Lync 2010 联机会议外接程序或 Lync 2013 联机会议外接程序重新计划使用包含 Outlook 2010 或 Outlook 2013 的 Office Communicator 2007 R2 客户端组织的会议。



以下各节介绍部署各种会议功能所要求的事项，包括规划过程、组件、软硬件要求和部署过程。

## 本部分内容

  - [Lync Server 2013 中的会议概述](lync-server-2013-overview-of-conferencing.md)

  - [在 Lync Server 2013 中定义会议要求](lync-server-2013-defining-your-requirements-for-conferencing.md)

  - [Lync Server 2013 中用于会议的组件和拓扑](lync-server-2013-components-and-topologies-for-conferencing.md)

  - [Lync Server 2013 中的会议技术要求](lync-server-2013-technical-requirements-for-conferencing.md)

  - [Lync Server 2013 中会议的部署清单](lync-server-2013-deployment-checklist-for-conferencing.md)

  - [Lync Server 2013 中的大型会议支持](lync-server-2013-support-for-large-meetings.md)

