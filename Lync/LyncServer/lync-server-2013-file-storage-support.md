---
title: Lync Server 2013 文件存储支持
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: File storage support
ms:assetid: ed66430d-3c19-4267-938c-956a51005073
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399073(v=OCS.15)
ms:contentKeyID: 48185743
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 000f3357c8b30b83a2d2cecf74bdbec44d867d96
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743402"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="file-storage-support-in-lync-server-2013"></a>Lync Server 2013 中的文件存储支持

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-16_

Lync Server 2013 对所有文件存储使用相同的文件存储。 文件存储支持包括以下内容：

  - 直接连接存储（DAS）或存储区域网络（SAN）上的文件共享，包括分布式文件系统（DFS）和文件存储的独立磁盘冗余阵列（RAID）。 有关存储要求的详细信息，请参阅在[Lync server 2013 中的技术要求、即时消息和状态显示在 lync server 的技术要求](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md)和规划文档中的[lync server 2013 中的控制器的硬件和软件要求](lync-server-2013-hardware-and-software-requirements-for-the-director.md)。 有关 DFS for Windows Server 2008 操作系统的详细信息，请参阅 Windows Server 2008 的 DFS 分步指南[http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835)。

  - 文件共享的共享群集。 如果使用共享群集，则应使用运行 Windows Server 2008 或 Windows Server 2008 R2 的群集服务器。 使用运行旧版本 Windows 的群集服务器可能会导致权限问题，防止某些功能可用。 使用群集管理器创建文件共享。 有关使用群集管理器的详细信息，请参阅 Microsoft 知识库文章284838，"如何在上[http://go.microsoft.com/fwlink/p/?linkId=140899](http://go.microsoft.com/fwlink/p/?linkid=140899)创建服务器群集文件共享"。

</div>

<span> </span>

</div>

</div>

</div>

