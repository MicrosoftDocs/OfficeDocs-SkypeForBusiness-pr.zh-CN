---
title: A/V 会议的 Lync Server 2013 部署清单
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for A/V conferencing
ms:assetid: 6d47426f-6559-407b-9ac1-2453f0b7a2a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619183(v=OCS.15)
ms:contentKeyID: 49733684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a0c48d78c33c652f7a28e277600fa957cb6fd1f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043324"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-av-conferencing-in-lync-server-2013"></a>Lync Server 2013 中的 A/V 会议的部署清单

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-30_

与其他 Lync Server 2013 组件的部署一样，部署 A/V 会议需要使用拓扑生成器创建并发布包含会议的拓扑。

<div>

## <a name="deployment-sequence"></a>部署顺序

您可以在部署初始拓扑的同时部署会议，也可以在部署了至少一个前端池或 Standard Edition server 之后部署会议。

</div>

<div>

## <a name="conferencing-deployment-process"></a>会议部署过程

下表提供在现有拓扑中部署会议所需步骤的概述。


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
<th>角色和组成员身份</th>
<th>文档</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>安装必备软硬件</strong></p></td>
<td><p>会议在前端池和 Standard Edition 服务器的前端服务器上运行。 除了需要安装这些服务器外，没有额外的软硬件要求。</p>
<div>

> [!NOTE]  
> Lync Server 2013 使用 Office Web Apps 和 Office Web Apps Server 处理 PowerPoint 演示文稿的共享和呈现。 有关安装和配置 Office Web Apps Server 的详细信息，请参阅<A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">配置与 Office Web Apps server 和 Lync Server 2013 的集成</A>。


</div></td>
<td><p>属于本地 Administrators 组成员的域用户</p></td>
<td><p>可支持性文档中<a href="lync-server-2013-supported-hardware.md">Lync Server 2013 支持的硬件</a></p>
<p>可支持性文档中的<a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync server 2013 中的服务器软件和基础结构支持</a></p>
<p>在规划文档中<a href="lync-server-2013-determining-your-system-requirements.md">确定 Lync Server 2013 的系统要求</a>。</p>
<p>在规划文档中的<a href="lync-server-2013-technical-requirements-for-archiving.md">Lync Server 2013 中存档的技术要求</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>创建相应的内部拓扑以支持会议</strong></p></td>
<td><p>运行拓扑生成器以将会议添加到拓扑，然后发布拓扑。</p></td>
<td><p>要定义拓扑，需具有本地 Users 组成员的帐户</p>
<p>发布拓扑，即 Domain Admins 组和 RTCUniversalServerAdmins 组的成员，以及对用于 Lync Server 2013 文件存储的文件共享具有完全控制权限（读/写/修改）的帐户（以便拓扑生成器可以配置所需的 Dacl）</p></td>
<td><p>在部署文档中<a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">的 Lync Server 2013 拓扑生成器中定义和配置拓扑</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>配置会议策略和支持</strong></p></td>
<td><p>使用 Lync Server 2013 控制面板或 Lync Server 命令行管理程序配置会议设置。</p></td>
<td><p>RTCUniversalServerAdmins 组（仅限 Windows PowerShell）或将用户分配到 [] 或 CSAdministrator 角色</p></td>
<td><p><a href="lync-server-2013-conferencing-policies.md">Lync Server 2013 中的会议策略</a>在操作文档中。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的会议概述](lync-server-2013-overview-of-conferencing.md)  
[在 Lync Server 2013 中定义会议要求](lync-server-2013-defining-your-requirements-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

