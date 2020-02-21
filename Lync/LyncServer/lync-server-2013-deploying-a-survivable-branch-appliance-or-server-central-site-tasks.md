---
title: 部署 Survivable 分支设备或服务器中心网站任务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a Survivable Branch Appliance or Server - central site tasks
ms:assetid: 0f631a36-fc2e-41cd-8a0d-f27e84f4a89e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398189(v=OCS.15)
ms:contentKeyID: 48183422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ced7b5262880b23540bf3465f787f6512781f2e3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213968"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013---central-site-tasks"></a>使用 Lync Server 2013 部署 Survivable 分支设备或服务器-中心站点任务

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-18_

在中央站点完成本节中的任务。 如果要部署 Survivable 分支服务器，请跳过第一个任务。

<div>


> [!IMPORTANT]
> 执行本节中的任务之前，必须满足以下条件： 
> <UL>
> <LI>
> <P>必须在中央站点上设置 Lync Server。</P>
> <LI>
> <P>必须将分支站点的安装技术人员添加到 RTCUniversalSBATechnicians 组。</P></LI></UL>此外，建议执行以下操作：
> <UL>
> <LI>
> <P>在每个分支站点部署 DHCP 服务器，以便客户端能够获取 IP 地址。</P>
> <LI>
> <P>在每个分支站点上部署 DHCP 服务器的另一种方法是，使用 Lync Server Management Shell cmdlet <STRONG>CsRegistrarConfiguration – EnableDHCPServer $true</STRONG>在 Survivable 分支设备或 Survivable 分支服务器上启用 LYNC server DHCP。 有关详细信息，请参阅规划文档中的<A href="lync-server-2013-branch-site-resiliency-requirements.md">Lync Server 2013 分支站点恢复要求</A>的 "硬件和软件要求" 一节。</P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a>本部分内容

  - [在 Lync Server 2013 中将 Survivable 分支设备添加到 Active Directory](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)

  - [在 Lync Server 2013 中向拓扑添加分支站点](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [在 Lync Server 2013 中定义 Survivable 分支设备或服务器](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

