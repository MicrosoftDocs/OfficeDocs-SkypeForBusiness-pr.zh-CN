---
title: Lync Server 2013：规划会议
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for conferencing
ms:assetid: 983a272a-e1b3-4d70-8f84-836b092fe526
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398781(v=OCS.15)
ms:contentKeyID: 48184937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca0fd8edb6e2939b82711392c53b0e5bef3e7740
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152932"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-conferencing-in-lync-server-2013"></a>在 Lync Server 2013 中规划会议

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-01-29_

Lync Server 2013 提供了一组丰富的会议功能：

  - Web 会议，其中包括文档协作、应用程序共享和桌面共享。 Lync Server 2013 使用 Office Web Apps 和 Office Web Apps Server 处理 PowerPoint 演示文稿的共享和呈现。 有关安装和配置 Office Web Apps Server 的详细信息，请参阅[配置与 Office Web Apps server 和 Lync Server 2013 的集成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。

  - 音频/视频（A/V）会议，使用户可以在不需要外部服务（如 Microsoft Live Meeting 服务或第三方音频网桥）的情况下进行实时音频或视频会议。

  - 电话拨入式会议，它允许用户在不需要第三方音频会议提供商的情况下使用公用电话交换网（PSTN）电话加入 Lync Server 2013 会议的音频部分。

  - 即时消息（IM）会议，在一个 IM 会话中有两个以上的参与方进行通信。 有关 IM 会议的详细信息，请参阅[在 Lync Server 2013 中规划前端服务器、即时消息和状态](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md)。

Lync Server 2013 支持安排的会议和即席会议。

当您部署 Lync Server 2013 （前端服务器）时，您可以选择是否还要部署 web 会议、A/V 会议和电话拨入式会议功能。 IM 会议功能总是随 Lync Server 2013 前端服务器上的 IM 对话功能一起自动部署。

<div>


> [!NOTE]  
> 如果您的部署包括使用 Office Communicator 2007 R2 客户端（包括 Live Meeting 控制台或 Microsoft Office Outlook 的会议外接程序）组织的会议，则在将会议迁移到 Lync 后，会有以下限制：服务器2013： 
> <UL>
> <LI>
> <P>会议中的用户将不能使用数据协作功能，包括文档协作、应用程序共享和桌面共享。</P>
> <LI>
> <P>由于 Lync Server 2013 不支持 Office Communicator 2007 R2 客户端，因此可能会出现稳定性问题。</P></LI></UL>若要避免这些问题，请使用 2013 Lync Online 的联机会议外接程序 for Lync 2010 或联机会议外接程序，重新安排使用 Office Communicator 2007 R2 客户端与 Outlook 2010 或 Outlook 2013 组织的任何会议。



</div>

以下各节介绍了部署各种类型的会议功能所需的内容，包括规划过程、组件、硬件和软件要求以及部署过程。

<div>

## <a name="in-this-section"></a>本部分内容

  - [Lync Server 2013 中的会议概述](lync-server-2013-overview-of-conferencing.md)

  - [在 Lync Server 2013 中定义会议要求](lync-server-2013-defining-your-requirements-for-conferencing.md)

  - [Lync Server 2013 中的会议的组件和拓扑](lync-server-2013-components-and-topologies-for-conferencing.md)

  - [Lync Server 2013 中的会议的技术要求](lync-server-2013-technical-requirements-for-conferencing.md)

  - [Lync Server 2013 中的会议的部署清单](lync-server-2013-deployment-checklist-for-conferencing.md)

  - [在 Lync Server 2013 中支持大型会议](lync-server-2013-support-for-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

