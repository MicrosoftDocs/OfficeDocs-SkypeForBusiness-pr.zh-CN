---
title: 部署 Survivable Branch Appliance 或 Survivable Branch Server - 中央站点任务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying a Survivable Branch Appliance or Server - central site tasks
ms:assetid: 0f631a36-fc2e-41cd-8a0d-f27e84f4a89e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398189(v=OCS.15)
ms:contentKeyID: 48183422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2b31e191dc2726c7e7962b0daa4ee5655245117
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830570"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013---central-site-tasks"></a>使用 Lync Server 2013 部署 Survivable Branch Appliance 或 Survivable Branch Server  - 中央站点任务

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-18_

在中心网站完成本部分中的任务。 如果要部署 Survivable 分支服务器, 请跳过第一个任务。

<div>


> [!IMPORTANT]
> 在执行本部分中的任务之前, 必须具备以下条件: 
> <UL>
> <LI>
> <P>必须在中心网站上设置 Lync 服务器。</P>
> <LI>
> <P>分支站点上的安装技术人员必须添加到 RTCUniversalSBATechnicians 组。</P></LI></UL>此外, 我们建议你执行以下操作:
> <UL>
> <LI>
> <P>在每个分支站点上部署 DHCP 服务器, 以使客户能够获取 IP 地址。</P>
> <LI>
> <P>除了在每个分支站点上部署 DHCP 服务器之外, 在 Survivable 分支机构或 Survivable 分支服务器上启用 Lync Server DHCP, 方法是使用 Lync Server Management Shell cmdlet <STRONG>Set-CsRegistrarConfiguration-EnableDHCPServer $true</STRONG>. 有关详细信息, 请参阅规划文档中<A href="lync-server-2013-branch-site-resiliency-requirements.md">Lync Server 2013 的分支站点恢复要求</A>的 "硬件和软件要求" 部分。</P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a>本节内容

  - [在 Lync Server 2013 中向 Active Directory 中添加 Survivable Branch Appliance](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)

  - [在 Lync Server 2013 中向拓扑添加分支站点](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [在 Lync Server 2013 中定义 Survivable Branch Appliance 或 Survivable Branch Server](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

