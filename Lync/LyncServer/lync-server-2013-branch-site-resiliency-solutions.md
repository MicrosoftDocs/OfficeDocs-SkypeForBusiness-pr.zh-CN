---
title: Lync Server 2013：分支站点恢复解决方案
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency solutions
ms:assetid: 1700f99b-709c-4e47-88eb-c0a5490e26e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398234(v=OCS.15)
ms:contentKeyID: 48183517
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 25541f7681ece7b299d6e4c8076fb190382650ba
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512979"
---
# <a name="branch-site-resiliency-solutions-in-lync-server-2013"></a>Lync Server 2013 中的分支站点恢复解决方案

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-12-10_

为组织提供分支站点复原的好处显而易见。 具体来说，如果您失去了与中央站点的连接，分支站点用户将继续拥有企业语音服务和语音邮件 (如果您配置了语音邮件重新路由设置，则有关详细信息，请参阅 [Lync Server 2013) 的分支站点恢复要求](lync-server-2013-branch-site-resiliency-requirements.md) 。 但是，对于用户少于 25 名的站点，复原解决方案可能无法为投资带来相应的回报。

如果决定提供分支站点复原，有三个选项可供使用。使用下表帮助确定最适合贵组织的选项。

<div>



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>如果...</th>
<th>建议使用...</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>分支站点承载 25 到 1000 位用户，并且投资回报不支持完整部署，或本地管理支持不可用</p></td>
<td><p>Survivable Branch Appliance</p>
<p>Survivable 分支设备是行业标准刀片服务器，其中包含在 Windows Server 2008 R2 上运行的 Lync Server 注册台和中介服务器。 Survivable 分支设备还包含公开交换电话网络 (PSTN) 网关。 合格第三方设备（由 Microsoft 合作伙伴在 Survivable Branch Appliance (SBA) 资格鉴定/认证计划中开发）在 WAN 发生故障时可以提供连续的 PSTN 连接，但不能提供可恢复的状态和会议，因为这些功能依赖于中央站点的前端服务器。</p>
<p>有关 Survivable 分支设备的详细信息，请参阅 &quot; &quot; 本主题后面的 Survivable 分支设备详细信息。</p>
<p><strong>注意：</strong> 如果您决定还要将 SIP 中继与您的 Survivable 分支设备一起使用，请联系您的 Survivable 分支设备供应商，了解最适合您的组织的服务提供商。</p></td>
</tr>
<tr class="even">
<td><p>在分支站点上的1000和2000用户之间的主机，缺少一个强健的 WAN 连接，并且已培训的 Lync Server 管理员可用</p></td>
<td><p>Survivable 分支服务器或两个 Survivable 分支装置。</p>
<p>Survivable 分支服务器是一个 Windows Server 会议指定的硬件要求，其中安装了 Lync Server 注册器和中介服务器软件。 它必须连接到 PSTN 网关或电话服务提供商的 SIP 中继。</p>
<p>有关 Survivable 分支服务器的详细信息，请参阅 &quot; &quot; 本主题后面的 Survivable 分支服务器详细信息。</p></td>
</tr>
<tr class="odd">
<td><p>如果你除了支持最高5000个用户的语音功能之外还需要状态和会议功能，并且已培训的 Lync Server 管理员可用</p></td>
<td><p>将 Standard Edition Server 部署为中央站点，而非分支站点。</p>
<p>在出现 WAN 故障时，完全规模的 Lync Server 部署可提供连续的 PSTN 连接和弹性状态和会议。</p>
<p>有关准备此解决方案的详细信息，请参阅 <a href="lync-server-2013-planning-for-your-organization.md">组织规划 Lync server 2013</a>、 <a href="lync-server-2013-determining-your-system-requirements.md">确定 lync server 2013 的系统要求</a>、 <a href="lync-server-2013-determining-your-infrastructure-requirements.md">确定 lync server 2013 的基础结构要求</a>以及规划文档的其他相关部分。</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="resiliency-topologies"></a>复原拓扑

下图显示了推荐的分支站点复原拓扑。

**分支站点复原选项**

![语音分支复原选项](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "语音分支复原选项")

</div>

<div>

## <a name="survivable-branch-appliance-details"></a>Survivable Branch Appliance 详细信息

Lync Server Survivable 分支设备包括以下组件：

  - 注册器，用于用户身份验证、注册和呼叫路由

  - 中介服务器，用于处理注册器和 PSTN 网关之间的信号

  - PSTN 网关，用于在 WAN 中断时，将呼叫作为回退传输路由到 PSTN

  - SQL Server Express，用于本地用户数据存储

Survivable 分支设备还包括 PSTN 中继、模拟端口和以太网适配器。

如果到中央站点的分支站点的 WAN 连接不可用，则内部分支用户将继续使用 Survivable 分支设备注册器进行注册，并通过使用 Survivable 分支装置连接到 PSTN 来获得不间断的语音服务。 从主机或其他远程位置进行连接的分支站点用户，可在连接到分支站点的 WAN 链路不可用时，在中央站点上的注册服务器中注册。 这些用户将具有完整的统一通信功能，一个例外是分支站点的入站呼叫将转到语音邮件。 WAN 连接可用时，将为分支站点用户恢复完整功能。 无论是故障转移到 Survivable 分支设备还是服务还原，都不需要 IT 管理员。

Lync Server 最高支持分支站点上的两个 Survivable 分支装置。

<div>


> [!NOTE]  
> 驻留在 Lync Server Survivable 分支设备上的用户无法创建新的聊天室或查看现有聊天室的会议室卡片。



</div>

<div>

## <a name="survivable-branch-appliance-deployment-overview"></a>Survivable Branch Appliance 部署概述

Survivable 分支设备由与 Microsoft 合作的原始设备制造商生产，并由增值零售商代表它们部署。 只有在中央站点部署了 Lync Server，与分支站点的 WAN 连接已就位，并为其启用了企业语音的分支站点用户，才应进行此部署。

有关这些阶段的详细信息，请参阅部署文档中的 [使用 Lync Server 2013 部署 Survivable 分支装置或服务器](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) 。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>阶段</th>
<th>步骤</th>
<th>用户权限</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>为 Survivable 分支设备设置 Active Directory 域服务</p></td>
<td><p><strong>在中央站点：</strong></p>
<ol>
<li><p>为将在分支站点安装和激活 Survivable 分支设备的技术人员创建域用户帐户 (或企业标识) 。</p></li>
<li><p>使用 Active Directory 域服务中 Survivable 分支设备的适用的完全限定的域名 (FQDN) # A3 创建计算机帐户 (。</p></li>
<li><p>在拓扑生成器中，创建并发布 Survivable 分支设备。</p></li>
</ol></td>
<td><p>技术人员用户帐户必须是 RTCUniversalSBATechnicians 的成员。 Survivable 分支设备必须属于 RTCSBAUniversalServices 组，这是在使用拓扑生成器时自动发生的。</p></td>
</tr>
<tr class="even">
<td><p>安装并激活 Survivable 分支设备。</p></td>
<td><p><strong>在分支站点：</strong></p>
<ol>
<li><p>将 Survivable 分支设备连接到以太网端口和 PSTN 端口。</p></li>
<li><p>启动 Survivable 分支设备。</p></li>
<li><p>使用为在中心站点上的 Survivable 分支设备创建的域用户帐户将 Survivable 分支设备加入域。 设置 FQDN 和 IP 地址以匹配在计算机帐户中创建的 FQDN。</p></li>
<li><p>使用 OEM 用户界面配置 Survivable 分支设备。</p></li>
<li><p>测试 PSTN 连接。</p></li>
</ol></td>
<td><p>技术人员用户帐户必须是 RTCUniversalSBATechnicians 的成员。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="survivable-branch-server-details"></a>Survivable Branch Server 详细信息

在拓扑生成器中，创建分支站点，将 Survivable 分支服务器添加到该站点，然后在要安装该角色的计算机上运行 Lync Server 部署向导。

</div>

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

