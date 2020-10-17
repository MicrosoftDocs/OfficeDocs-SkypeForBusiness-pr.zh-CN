---
title: Lync Server 2013：部署 Survivable 分支设备或服务器
description: Lync Server 2013：部署 Survivable 分支装置或服务器。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a Survivable Branch Appliance or Server
ms:assetid: cb780c14-dc5f-41ba-8092-f20ae905bd16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398849(v=OCS.15)
ms:contentKeyID: 48185643
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8c8610ab85b61d33a5f181f1d5f51d0e5095f49
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558588"
---
# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013"></a>使用 Lync Server 2013 部署 Survivable 分支设备或服务器

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-12-10_

复原企业语音是指分支站点恢复能力，即，在指向中央站点的链接不可用的情况下，能够向分支站点用户提供连续的企业语音服务。

对于小型和中型分支站点 (25 到1000个用户) 的分支站点，我们建议部署 Survivable 分支设备，这将通过使用其内置 PSTN 网关或到电话服务提供商的 SIP 中继来终止公开交换的电话网络 (PSTN) 呼叫。 Survivable 分支设备是一种第三方设备，其中包括运行 Windows Server 2008 R2 操作系统的刀片服务器、Lync Server 2013 注册器、中介服务器软件和 PSTN 网关（全部位于单个设备机箱中）。

对于1000到5000用户且无弹性 WAN 的分支站点，我们建议将 Survivable 分支服务器连接到与电话服务提供商的 PSTN 网关或 SIP 中继。 Survivable 分支服务器是一台基于 Windows Server 的计算机，其中安装了注册器和中介服务器软件。

<div>


> [!NOTE]  
> 对于具有超过5000个用户和专用 Lync Server 管理员的分支站点，我们建议使用完整的 Lync Server 2013 部署，并将其与中心站点的部署分开。<BR>有关为组织中的分支站点选择最佳恢复解决方案的详细信息（包括先决条件和规划注意事项），请参阅规划文档中的 <A href="lync-server-2013-branch-site-resiliency-requirements.md">Lync Server 2013 的分支站点恢复要求</A> 。



</div>

<div>


> [!NOTE]  
> 驻留在 Lync Server Survivable 分支设备上的用户无法创建新的聊天室或查看现有聊天室的会议室卡片。



</div>

<div>

## <a name="in-this-section"></a>本部分内容

  - [使用 Lync Server 2013 部署 Survivable 分支设备或服务器-中心站点任务](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)

  - [使用 Lync Server 2013 部署 Survivable 分支设备或服务器-分支站点任务](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

  - [在 Lync Server 2013 中为用户配置分支站点恢复能力](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

  - [Lync Server 2013 中的 Survivable 分支装置或服务器上的家庭用户](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)

  - [附录： Lync Server 2013 中的 Survivable 分支装置和服务器](lync-server-2013-appendices-survivable-branch-appliances-and-servers.md)

</div>

<div>

## <a name="see-also"></a>另请参阅


[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

