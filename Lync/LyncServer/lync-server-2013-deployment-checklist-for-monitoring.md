---
title: Lync Server 2013：用于监视的部署清单
description: Lync Server 2013：用于监视的部署清单。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for monitoring
ms:assetid: 4e798370-277c-4391-84b4-13a972b45ca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204874(v=OCS.15)
ms:contentKeyID: 48184080
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe3d3293accf6e25c20ae8391f9107ae75fef338
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568319"
---
# <a name="deployment-checklist-for-monitoring-in-lync-server-2013"></a>Lync Server 2013 中用于监视的部署清单

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-05_

虽然已在每台前端服务器上安装并激活了监视，但在实际准备收集 Microsoft Lync Server 2013 的监视数据之前，您必须执行几个步骤。 以下清单中概述了这些步骤：


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>阶段</p></td>
<td><p>步骤</p></td>
<td><p>角色和组成员身份</p></td>
<td><p>文档</p></td>
</tr>
<tr class="even">
<td><p><strong>安装必备软硬件</strong></p></td>
<td><p>在将充当要进行监视的后端数据存储的计算机上安装受支持版本的 Microsoft SQL Server。</p></td>
<td><p>还是本地管理员组的成员的域用户。</p></td>
<td><p>可支持性指南中的<a href="lync-server-2013-supported-hardware.md">Lync Server 2013 支持的硬件</a></p>
<p>可支持性指南中的<a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync server 2013 中的服务器软件和基础结构支持</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>创建相应的内部拓扑以支持监控</strong></p></td>
<td><p>使用 Lync Server 2013 拓扑生成器将监视数据库添加到拓扑，然后发布更新后的拓扑。</p></td>
<td><p>若要定义拓扑，则为是本地用户组成员的用户。</p>
<p>若要发布拓扑，则为 Domain Administrators 组和 RTCUniversalServerAdmins 组的成员的用户。</p></td>
<td><p>在部署指南中将<a href="lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md">监视存储与 Lync Server 2013 中的前端池相关联</a></p></td>
</tr>
<tr class="even">
<td><p><strong>启用相应的监控设置</strong></p></td>
<td><p>启用全局和/或站点作用域的呼叫详细信息记录 (CDR) 和/或用户体验质量 (QoE) 监视。</p></td>
<td><p>为 RTCUniversalServerAdmins 组的用户，或分配有提供对 CsCdrConfiguration 和 CsQoEConfiguration cmdlet 的访问权限的 RBAC 角色的用户。</p></td>
<td><p>在操作指南中<a href="lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md">配置 Lync Server 2013 中的呼叫详细信息记录和体验质量设置</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

