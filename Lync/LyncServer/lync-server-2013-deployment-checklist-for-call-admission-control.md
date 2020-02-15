---
title: Lync Server 2013：呼叫允许控制的部署清单
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for call admission control
ms:assetid: 7e56a169-3e63-44ab-bf28-1fdeb52381c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398631(v=OCS.15)
ms:contentKeyID: 48184621
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d68f13c636b24729db989f25da7055333968cbbd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043274"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-call-admission-control-in-lync-server-2013"></a>Lync Server 2013 中呼叫允许控制的部署清单

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-08_

若要有效规划呼叫允许控制 (CAC)，则需要考虑以下内容：

  - 部署 CAC 的先决条件。

  - CAC 所需的信息以及在部署前必须做出的配置决策。

<div>

## <a name="deployment-prerequisites-for-call-admission-control"></a>呼叫允许控制的部署先决条件

在部署呼叫允许控制之前，您必须已部署了 Lync Server 2013 内部服务器，包括前端池或 Standard Edition 服务器。

</div>

<div>

## <a name="information-requirements-for-call-admission-control"></a>呼叫允许控制的信息要求

下表汇总了部署呼叫允许控制的必需信息。

### <a name="information-requirements-for-call-admission-control-deployment"></a>呼叫允许控制部署的信息要求

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>信息</th>
<th>所需信息的摘要</th>
<th>文档</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>您的组织所需的 Lync Server 功能</p></td>
<td><ul>
<li><p>组织支持的功能</p></li>
<li><p>为各个用户启用的功能</p></li>
</ul></td>
<td><p><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">在 Lync Server 2013 中定义呼叫允许控制的要求</a></p></td>
</tr>
<tr class="even">
<td><p>要部署的拓扑和组件</p></td>
<td><ul>
<li><p>CAC 相关组件将作为 Lync Server 2013 的一部分自动安装</p></li>
</ul></td>
<td><p><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">在 Lync Server 2013 中定义呼叫允许控制的要求</a></p></td>
</tr>
<tr class="odd">
<td><p>系统要求</p></td>
<td><ul>
<li><p>硬件要求</p></li>
<li><p>软件要求</p></li>
<li><p>并置要求</p></li>
</ul></td>
<td><p><a href="lync-server-2013-determining-your-system-requirements.md">确定 Lync Server 2013 的系统要求</a></p></td>
</tr>
<tr class="even">
<td><p>基础结构要求</p></td>
<td><ul>
<li><p>对 CAC 没有必要的特定基础结构要求</p></li>
</ul></td>
<td><p><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Lync Server 2013 中呼叫允许控制的基础结构要求</a></p></td>
</tr>
<tr class="odd">
<td><p>网络接口要求</p></td>
<td><ul>
<li><p>内部和外部接口信息</p></li>
<li><p>路由信息（包括有关来自 Microsoft Lync Server 团队<a href="http://go.microsoft.com/fwlink/p/?linkid=203149">http://go.microsoft.com/fwlink/p/?LinkId=203149</a>客户响应通道的 NextHop 博客的信息）</p></li>
</ul></td>
<td><p><a href="lync-server-2013-deploying-external-user-access.md">在 Lync Server 2013 中部署外部用户访问</a></p></td>
</tr>
<tr class="even">
<td><p>部署策略</p></td>
<td><ul>
<li><p>部署顺序</p></li>
<li><p>工作组或域</p></li>
<li><p>安全性</p></li>
<li><p>监控和审核</p></li>
<li><p>硬件注意事项</p></li>
</ul></td>
<td><p><a href="lync-server-2013-best-practices-for-call-admission-control.md">Lync Server 2013 中的呼叫允许控制最佳实践</a></p></td>
</tr>
<tr class="odd">
<td><p>部署过程</p></td>
<td><ul>
<li><p>先决条件</p></li>
<li><p>信息要求</p></li>
<li><p>过程和步骤</p></li>
</ul></td>
<td><p><a href="lync-server-2013-configure-call-admission-control.md">在 Lync Server 2013 中配置呼叫允许控制</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

