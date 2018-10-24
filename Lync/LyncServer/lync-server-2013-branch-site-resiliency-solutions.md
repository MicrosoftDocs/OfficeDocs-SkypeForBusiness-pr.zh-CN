---
title: Lync Server 2013：分支站点恢复能力解决方案
TOCTitle: 分支站点恢复能力解决方案
ms:assetid: 1700f99b-709c-4e47-88eb-c0a5490e26e2
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398234(v=OCS.15)
ms:contentKeyID: 49312118
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的分支站点恢复能力解决方案

 

_**上一次修改主题：** 2015-03-09_

为组织提供分支站点复原的好处显而易见。具体而言，如果与中央站点失去连接，分支站点用户可继续使用 企业语音服务和语音邮件（如果配置了语音邮件重新路由设置；有关详细信息，请参阅 [Lync Server 2013 的分支站点恢复能力要求](lync-server-2013-branch-site-resiliency-requirements.md)）。但是，对于用户少于 25 名的站点，复原解决方案可能无法为投资带来相应的回报。

如果决定提供分支站点复原，有三个选项可供使用。使用下表帮助确定最适合贵组织的选项。



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
<p>Survivable Branch Appliance 是行业标准刀片式服务器，其中带有在 Windows Server 2008 R2 上运行的 Lync Server 注册器和中介服务器。 Survivable Branch Appliance 还包含公用电话交换网 (PSTN) 网关。合格第三方设备（由 Microsoft 合作伙伴在 Survivable Branch Appliance (SBA) 资格鉴定/认证计划中开发）在 WAN 发生故障时可以提供连续的 PSTN 连接，但不能提供可恢复的状态和会议，因为这些功能依赖于中央站点的前端服务器。</p>
<p>有关 Survivable Branch Appliance 的详细信息，请参阅本主题后面的“Survivable Branch Appliance 详细信息”。</p>
<p><strong>注意：</strong> 如果还决定将 SIP 中继与 Survivable Branch Appliance 结合使用，请与您的 Survivable Branch Appliance 供应商联系，以了解最适合贵组织的服务提供商。</p></td>
</tr>
<tr class="even">
<td><p>分支站点承载 1000 到 2000 位用户，缺少可恢复的 WAN 连接，并且具有经过培训的 Lync Server 管理员</p></td>
<td><p>Survivable Branch Server 或两个 Survivable Branch Appliance。</p>
<p>Survivable Branch Server 是满足指定的硬件要求的 Windows Server，其上安装了 Lync Server 注册器和中介服务器软件。它必须连接到 PSTN 网关或电话服务提供商的 SIP 中继。</p>
<p>有关 Survivable Branch Server 的详细信息，请参阅本主题后面的“Survivable Branch Server 详细信息”。</p></td>
</tr>
<tr class="odd">
<td><p>如果除语音功能之外，还需要为最多 5000 位用户提供状态和会议功能，并且具有经过培训的 Lync Server 管理员</p></td>
<td><p>将 Standard Edition Server 部署为中央站点，而非分支站点。</p>
<p>全面的 Lync Server 部署会在 WAN 发生故障时提供连续的 PSTN 连接以及可恢复的状态和会议。</p>
<p>有关准备此解决方案的详细信息，请参阅<a href="lync-server-2013-planning-for-your-organization.md">Lync Server 2013 的组织规划</a>、<a href="lync-server-2013-determining-your-system-requirements.md">确定 Lync Server 2013 的系统要求</a>、<a href="lync-server-2013-determining-your-infrastructure-requirements.md">确定 Lync Server 2013 的基础结构要求</a>以及规划文档中的其他相关部分。</p></td>
</tr>
</tbody>
</table>


## 复原拓扑

下图显示了推荐的分支站点复原拓扑。

**分支站点复原选项**

![语音分支站点恢复能力选项](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "语音分支站点恢复能力选项")

## Survivable Branch Appliance 详细信息

Lync Server Survivable Branch Appliance 包含以下组件：

  - 注册器，用于用户身份验证、注册和呼叫路由

  - 中介服务器，用于处理注册器和 PSTN 网关之间的信号

  - PSTN 网关，用于在 WAN 中断时，将呼叫作为回退传输路由到 PSTN

  - SQL Server Express，用于本地用户数据存储

Survivable Branch Appliance 还包括 PSTN 中继、模拟端口和以太网适配器。

如果分支站点与中央站点之间的 WAN 连接不可用，内部分支用户可继续使用 Survivable Branch Appliance 注册器进行注册，并使用 Survivable Branch Appliance 与 PSTN 的连接获得连续的语音服务。从主机或其他远程位置进行连接的分支站点用户，可在连接到分支站点的 WAN 链路不可用时，在中央站点上的注册服务器中注册。这些用户将具有完整的统一通信功能，一个例外是分支站点的入站呼叫将转到语音邮件。WAN 连接可用时，将为分支站点用户恢复完整功能。无论是故障转移到 Survivable Branch Appliance 还是恢复服务，均不需要 IT 管理员参与。

Lync Server 在分支站点处支持最多两个 Survivable Branch Appliance。

## Survivable Branch Appliance 部署概述

Survivable Branch Appliance 由与 Microsoft 有合作关系的原始设备制造商制造，并由增值零售商代表其进行部署。只有在中央站点部署 Lync Server、具备连接到分支站点的 WAN 连接，并且为分支站点的用户启用 企业语音后，才能进行此部署。

有关这些阶段的详细信息，请参阅部署文档中的[使用 Lync Server 2013 部署 Survivable Branch Appliance 或 Survivable Branch Server](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)。


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
<td><p>为 Survivable Branch Appliance 设置 Active Directory 域服务</p></td>
<td><p><strong>在中央站点：</strong></p>
<ol>
<li><p>为将在分支站点安装并激活 Survivable Branch Appliance 的技术人员创建域用户帐户（或企业标识）。</p></li>
<li><p>在 Active Directory 域服务中为 Survivable Branch Appliance 创建计算机帐户（以及相应的完全限定的域名 (FQDN)）。</p></li>
<li><p>在拓扑生成器中，创建并发布 Survivable Branch Appliance。</p></li>
</ol></td>
<td><p>技术人员用户帐户必须是 RTCUniversalSBATechnicians 的成员。 Survivable Branch Appliance 必须属于 RTCSBAUniversalServices 组，使用拓扑生成器时会自动执行相应操作。</p></td>
</tr>
<tr class="even">
<td><p>安装并激活 Survivable Branch Appliance。</p></td>
<td><p><strong>在分支站点：</strong></p>
<ol>
<li><p>将 Survivable Branch Appliance 连接到以太网端口和 PSTN 端口。</p></li>
<li><p>启动 Survivable Branch Appliance。</p></li>
<li><p>使用在中央站点为 Survivable Branch Appliance 创建的域用户帐户将 Survivable Branch Appliance 加入到域。设置 FQDN 和 IP 地址以匹配在计算机帐户中创建的 FQDN。</p></li>
<li><p>使用 OEM 用户界面配置 Survivable Branch Appliance。</p></li>
<li><p>测试 PSTN 连接。</p></li>
</ol></td>
<td><p>技术人员用户帐户必须是 RTCUniversalSBATechnicians 的成员。</p></td>
</tr>
</tbody>
</table>


## Survivable Branch Server 详细信息

在 拓扑生成器中创建分支站点，将 Survivable Branch Server 添加到该站点，然后在要安装该角色的计算机上运行 Lync Server 部署向导。

## 另请参阅

#### 其他资源

[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md)

