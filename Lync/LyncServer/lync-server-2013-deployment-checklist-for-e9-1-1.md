---
title: Lync Server 2013： E9-1-1 的部署清单
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for E9-1-1
ms:assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398864(v=OCS.15)
ms:contentKeyID: 48185655
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52920c81e2055b5151280bbd65e9b2b6a90c0b73
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522799"
---
# <a name="deployment-checklist-for-e9-1-1-in-lync-server-2013"></a>Lync Server 2013 中的 E9-1-1 的部署清单

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-03_

要有效规划增强型 9-1-1 (E9-1-1)，请确保包括以下部署要求：

  - 部署 E9-1-1 的先决条件。

  - 部署 E9-1-1 所需的步骤。

<div>

## <a name="deployment-prerequisites-for-e9-1-1"></a>E9-1-1 的部署先决条件

在部署 E9-1-1 之前，必须已经部署了 Lync Server 内部服务器，包括中央管理存储、前端池或 Standard Edition 服务器、一个或多个中介服务器或中介服务器池以及 Lync Server 客户端。 此外，E9-1-1 部署需要指向已认证 E9-1-1 服务提供商的 SIP 中继或指向公用电话交换网 (PSTN) 的紧急位置标识号 (ELIN) 网关。 Lync Server 仅支持在美国境内使用 E9-1-1 服务提供商。

</div>

<div>

## <a name="deployment-process"></a>部署过程

下表概述了 E9-1-1 部署过程。 有关部署步骤的详细信息，请参阅部署文档中的在 [Lync Server 2013 中配置增强型 9-1-1](lync-server-2013-configure-enhanced-9-1-1.md) 。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>阶段</th>
<th>步骤</th>
<th>角色</th>
<th>部署文档</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>配置语音用法、路由和中继配置</p></td>
<td><ol>
<li><p>创建新的 PSTN 用法记录。这与位置策略中的“PSTN 用法”<strong></strong>设置所用的名称相同。</p></li>
<li><p>创建或分配一个语音路由给上一步中创建的 PSTN 用法记录，然后将网关属性指向 E9-1-1 SIP 中继或 ELIN 网关。</p></li>
<li><p>对于 SIP 中继 E9-1-1 服务提供商，设置将使用 <strong>Set-CsTrunkConfiguration –EnablePIDFLOSupport</strong> cmdlet 处理 SIP 上的 E9-1-1 呼叫以传递 PIDF-LO 数据的中继。</p></li>
<li><p>（可选）对于 SIP 中继 E9-1-1 服务提供商，为未被 E9-1-1 服务提供商的 SIP 中继处理的呼叫创建并分配本地 PSTN 路由。如果与 E9-1-1 服务提供商的连接不可用，将使用此路由。如果受 E9-1-1 服务提供商支持，则向网关分配一个中继配置规则，以便将 911 拨号字符串转换为国家和/或地区紧急呼叫响应中心 (ECRC) 的外线直拨分机 (DID) 号码。</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p></td>
<td><p><a href="lync-server-2013-configure-an-e9-1-1-voice-route.md">在 Lync Server 2013 中配置 E9-1-1 语音路由</a></p></td>
</tr>
<tr class="even">
<td><p>创建位置策略，并将其分配给用户和子网</p></td>
<td><ol>
<li><p>查看全局位置策略。</p></li>
<li><p>创建包含用户级范围的位置策略；或者，如果组织具有包含不同紧急情况用法的多个站点，则创建包含网络级范围的位置策略。</p></li>
<li><p>将位置策略分配给网络站点。</p></li>
<li><p>将相应的子网添加到网络站点。</p></li>
<li><p>（可选）将位置策略分配到用户策略。</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p>
<p>CSLocationAdmin（创建位置策略除外）</p></td>
<td><p><a href="lync-server-2013-create-location-policies.md">在 Lync Server 2013 中创建位置策略</a></p>
<p><a href="lync-server-2013-add-a-location-policy-to-a-network-site.md">在 Lync Server 2013 中向网络站点添加位置策略</a></p>
<p><a href="lync-server-2013-associate-subnets-with-network-sites-for-e9-1-1.md">将子网与 Lync Server 2013 中的 E9-1-1 的网络站点相关联</a></p></td>
</tr>
<tr class="odd">
<td><p>配置位置数据库</p></td>
<td><ol>
<li><p>使用网络元素到位置的映射填充数据库。</p></li>
<li><p>对于 ELIN 网关，将 Elin 添加到 " &lt; 公司名称" &gt; 列。</p></li>
<li><p>配置与 E9-1-1 服务提供商的连接以验证地址。</p></li>
<li><p>验证 E9-1-1 服务提供商的地址。</p></li>
<li><p>发布更新的数据库。</p></li>
<li><p>对于 ELIN 网关，将 ELIN 上传到 PSTN 运营商的自动位置标识 (ALI) 数据库。</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p>
<p>CSLocationAdmin</p></td>
<td><p><a href="lync-server-2013-configure-the-location-database.md">在 Lync Server 2013 中配置位置数据库</a></p></td>
</tr>
<tr class="even">
<td><p>配置高级功能（可选）</p></td>
<td><ol>
<li><p>配置 SNMP 应用程序的 URL。</p></li>
<li><p>配置辅助位置信息服务的位置的 URL。</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p></td>
<td><p><a href="lync-server-2013-configure-an-snmp-application.md">在 Lync Server 2013 中配置 SNMP 应用程序</a></p>
<p><a href="lync-server-2013-configure-a-secondary-location-information-service.md">在 Lync Server 2013 中配置辅助位置信息服务</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

