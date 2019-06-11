---
title: Lync Server 2013：分支站点恢复能力解决方案
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Branch-site resiliency solutions
ms:assetid: 1700f99b-709c-4e47-88eb-c0a5490e26e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398234(v=OCS.15)
ms:contentKeyID: 48183517
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce14328aed7ae4769d2f2aff18edb9c6135fe025
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837745"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-solutions-in-lync-server-2013"></a>Lync Server 2013 中的分支站点恢复能力解决方案

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2014-12-10_

为组织提供分支站点恢复能力的好处显而易见。 尤其是, 如果您失去了与中心站点的连接, 分支网站用户将继续拥有企业语音服务和语音邮件 (如果配置了语音邮件重新路由设置, 请参阅[Lync Server 的分支站点恢复要求2013](lync-server-2013-branch-site-resiliency-requirements.md))。 但是，对于用户少于 25 名的站点，复原解决方案可能无法为投资带来相应的回报。

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
<p>Survivable 分支设备是一个行业标准的刀片式服务器, 其中包含在 Windows Server 2008 R2 上运行的 Lync Server 注册机构和中介服务器。 Survivable 分支装置还包含一个公共交换电话网络 (PSTN) 网关。 合格第三方设备（由 Microsoft 合作伙伴在 Survivable Branch Appliance (SBA) 资格鉴定/认证计划中开发）在 WAN 发生故障时可以提供连续的 PSTN 连接，但不能提供可恢复的状态和会议，因为这些功能依赖于中央站点的前端服务器。</p>
<p>有关 Survivable 分支装置的详细信息, &quot;请参阅本主题&quot;后面的 Survivable 分支装置详细信息。</p>
<p><strong>注意:</strong>如果你决定还将 SIP 中继与你的 Survivable 分支设备配合使用, 请联系 Survivable 分支机构供应商, 了解最适合你的组织的服务提供商。</p></td>
</tr>
<tr class="even">
<td><p>在你的分支站点上的1000和2000用户之间, 缺少弹性 WAN 连接, 并且有经过培训的 Lync 服务器管理员可用</p></td>
<td><p>Survivable 分支服务器或两个 Survivable 分支装置。</p>
<p>Survivable 分支服务器是 Windows Server 会议指定的硬件要求, 其中安装有 Lync Server 注册机构和中介服务器软件。 它必须连接到 PSTN 网关或电话服务提供商的 SIP 中继。</p>
<p>有关 Survivable 分支服务器的详细信息, &quot;请参阅本主题&quot;后面的 Survivable 分支服务器详细信息。</p></td>
</tr>
<tr class="odd">
<td><p>如果除了适用于5000用户的语音功能之外还需要状态和会议功能, 并且有经过培训的 Lync 服务器管理员可用</p></td>
<td><p>将 Standard Edition Server 部署为中央站点，而非分支站点。</p>
<p>在 WAN 出现故障时, 完全缩放的 Lync 服务器部署可提供连续的 PSTN 连接和弹性状态和会议。</p>
<p>有关准备此解决方案的详细信息, 请参阅 lync server <a href="lync-server-2013-planning-for-your-organization.md">2013 的组织规划</a>、<a href="lync-server-2013-determining-your-system-requirements.md">确定 lync server 2013 的系统要求</a>、<a href="lync-server-2013-determining-your-infrastructure-requirements.md">确定 lync server 2013 的基础结构要求</a>以及规划文档的其他相关部分。</p></td>
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

Lync Server Survivable 分支设备包括以下组件:

  - 注册器，用于用户身份验证、注册和呼叫路由

  - 中介服务器，用于处理注册器和 PSTN 网关之间的信号

  - PSTN 网关，用于在 WAN 中断时，将呼叫作为回退传输路由到 PSTN

  - SQL Server Express，用于本地用户数据存储

Survivable 分支装置还包括 PSTN 中继、模拟端口和以太网适配器。

如果分支站点的中心站点的 WAN 连接不可用, 则内部分支用户将继续向 Survivable 分支装置注册机构注册, 并使用 Survivable 分支装置连接获取不中断的语音服务PSTN。 从主机或其他远程位置进行连接的分支站点用户，可在连接到分支站点的 WAN 链路不可用时，在中央站点上的注册服务器中注册。 这些用户将具有完整的统一通信功能，一个例外是分支站点的入站呼叫将转到语音邮件。 WAN 连接可用时，将为分支站点用户恢复完整功能。 故障转移到 Survivable 分支装置和服务还原都不需要 IT 管理员。

Lync 服务器最多支持分支站点上的两个 Survivable 分支装置。

<div>


> [!NOTE]  
> 在 Lync Server Survivable 分支设备上托管的用户无法创建新的聊天室或查看现有聊天室的聊天室卡片。



</div>

<div>

## <a name="survivable-branch-appliance-deployment-overview"></a>Survivable Branch Appliance 部署概述

Survivable 分支装置由原始设备制造商制造, 与 Microsoft 合作, 并由增值零售商进行部署。 此部署应仅在已在中心网站上部署 Lync 服务器之后进行, 并且分支站点的 WAN 连接处于 "已使用" 状态, 并且将为企业语音启用分支网站用户。

有关这些阶段的详细信息, 请参阅部署文档中的[使用 Lync Server 2013 部署 Survivable 分支装置或服务器](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)。


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
<td><p>为 Survivable 分支装置设置 Active Directory 域服务</p></td>
<td><p><strong>在中央站点：</strong></p>
<ol>
<li><p>为将在分支站点安装和激活 Survivable 分支装置的技术人员创建域用户帐户 (或企业标识)。</p></li>
<li><p>为 Active Directory 域服务中的 Survivable 分支设备创建计算机帐户 (具有适用的完全限定的域名 (FQDN))。</p></li>
<li><p>在拓扑生成器中, 创建和发布 Survivable 分支装置。</p></li>
</ol></td>
<td><p>技术人员用户帐户必须是 RTCUniversalSBATechnicians 的成员。 Survivable 分支装置必须属于 RTCSBAUniversalServices 组, 当你使用拓扑生成器时, 该装置会自动发生。</p></td>
</tr>
<tr class="even">
<td><p>安装并激活 Survivable 分支装置。</p></td>
<td><p><strong>在分支站点：</strong></p>
<ol>
<li><p>将 Survivable 分支设备连接到以太网端口和 PSTN 端口。</p></li>
<li><p>启动 Survivable 分支装置。</p></li>
<li><p>将 Survivable 分支设备加入域, 使用为 Survivable 分支装置在中心网站上创建的域用户帐户。 设置 FQDN 和 IP 地址以匹配在计算机帐户中创建的 FQDN。</p></li>
<li><p>使用 OEM 用户界面配置 Survivable 分支装置。</p></li>
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

在拓扑生成器中, 创建分支站点, 将 Survivable 分支服务器添加到该网站, 然后在要安装该角色的计算机上运行 Lync Server 部署向导。

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

