---
title: Lync Server 2013：持久聊天服务器的部署清单
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for Persistent Chat Server
ms:assetid: b1108f8f-88a2-4660-8086-d25ba76f7239
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412851(v=OCS.15)
ms:contentKeyID: 48185155
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6234ca4a8a0e7f6edc2069b7bb42f0bae545713b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049454"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-persistent-chat-server-in-lync-server-2013"></a>Lync Server 2013 中持久聊天服务器的部署清单

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-16_

将 Lync Server 2013 与持久聊天服务器的部署要求您按照正确的顺序部署它，并完成所有需要的部署步骤。

<div>

## <a name="deployment-sequence"></a>部署顺序

您可以在部署初始拓扑后部署持久聊天服务器，其中包括至少一个 Lync Server 2013、前端池或一个 Lync Server 2013 （Standard Edition server）。 本主题介绍如何通过将持久聊天服务器添加到现有部署来部署持久聊天服务器。

</div>

<div>

## <a name="deployment-process"></a>部署过程

下表列出了部署持久聊天服务器的基本步骤，并提供了有关更多详细信息的链接。

### <a name="persistent-chat-server-deployment-process"></a>持久聊天服务器部署过程

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>任务</th>
<th>步骤</th>
<th>所需角色和组成员身份</th>
<th>相关主题</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>安装必备硬件和软件</strong></p></td>
<td><p>在满足系统要求的硬件上安装以下内容：</p>
<ul>
<li><p>在持久聊天服务器前端服务器上：</p></li>
</ul>
<ul>
<li><p>满足系统要求的操作系统</p></li>
<li><p>运行 Lync Server 2013 的计算机的必备软件</p></li>
<li><p>将承载持久聊天服务器数据库的服务器上的 SQL Server</p></li>
</ul>
<p>如果需要持久聊天服务器合规性：</p>
<ul>
<li><p>将承载持久聊天服务器合规性数据库的服务器上的 SQL Server</p></li>
</ul></td>
<td><p>属于本地 Administrators 组成员的任何用户。</p></td>
<td><p>可支持性文档中<a href="lync-server-2013-supported-hardware.md">Lync Server 2013 支持的硬件</a></p>
<p>可支持性文档中的<a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync server 2013 中的服务器软件和基础结构支持</a></p>
<p><a href="lync-server-2013-determining-your-system-requirements.md">确定 Lync Server 2013 的系统要求</a></p>
<p><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Lync Server 2013 中持久聊天服务器的技术要求</a></p></td>
</tr>
<tr class="even">
<td><p><strong>创建适当的内部拓扑以支持持久聊天服务器（也可以选择持久聊天合规性）</strong></p></td>
<td><p>运行拓扑生成器以将持久聊天服务器池添加到拓扑中：</p>
<ul>
<li><p>将持久聊天服务器组件添加到拓扑</p></li>
<li><p>为持久聊天服务器存储创建 SQL Server 数据库（以及用于灾难恢复的备份 SQL Server）</p></li>
<li><p>为持久聊天服务器文件定义新的 Lync 文件存储或使用现有的 Lync 文件存储</p></li>
<li><p>关联可将请求路由到此持久聊天服务器池的 Lync Server 2013 池</p></li>
</ul>
<p>如果需要持久聊天合规性：</p>
<ul>
<li><p>添加持久聊天合规性存储</p></li>
<li><p>单击 "持久聊天服务器池定义" 复选框以启用合规性</p></li>
<li><p>发布拓扑</p></li>
</ul>
<p>如果在 Standard Edition 上安装持久聊天服务器，则持久聊天服务器池的完全限定域名（FQDN）必须与 Standard Edition server 相匹配，并且 SQL Server 数据库在标准版的 SQL Server Express 实例上并置。Edition 服务器</p></td>
<td><p>要定义拓扑，需要具有本地 Users 组成员身份的帐户。</p>
<p>若要发布拓扑，该帐户是 Domain Admins 组和 RTCUniversalServerAdmins 组的成员，并且用户还应具有对持久聊天服务器文件的 Lync 文件存储的完全控制权限（读/写/修改）（以便拓扑生成器可以配置所需的 Dacl）。</p></td>
<td><p>在部署文档中<a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">将持久聊天服务器添加到 Lync Server 2013</a>中的部署</p></td>
</tr>
<tr class="odd">
<td><p><strong>部署持久聊天服务器</strong></p></td>
<td><p>在运行持久聊天服务器的所有计算机上运行 Lync Server 安装程序。 持久聊天服务器安装程序已集成到 Lync Server 2013 部署向导中，其中提供了以下说明：</p>
<ul>
<li><p>部署本地管理存储</p></li>
<li><p>安装持久聊天服务器服务</p></li>
<li><p>请求和分配证书</p></li>
<li><p>运行并启动服务</p></li>
</ul></td>
<td><p>属于本地 Administrators 组成员的任何用户。</p></td>
<td><p>在部署文档中的<a href="lync-server-2013-deploying-persistent-chat-server.md">Lync server 2013 中部署持久聊天服务器</a></p></td>
</tr>
<tr class="even">
<td><p><strong>创建持久聊天管理员</strong></p></td>
<td><p>将用户添加到 CsPersistentChatAdministrator 安全组。</p></td>
<td><p>属于域管理员成员的任何用户。</p></td>
<td><p>在部署文档中的<a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Lync Server 2013 中添加持久聊天管理员</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>配置持久聊天服务器</strong></p></td>
<td><p>配置用户：</p>
<ul>
<li><p>必须通过策略启用用户才能访问持久聊天服务器。 默认情况下，该策略对所有用户都处于关闭状态，并且可以在全局/站点/池/用户范围进行定义。</p></li>
<li><p>配置设置</p></li>
</ul></td>
<td><p>用户必须是 CsPersistentChatAdministrator 的成员。要更改策略，用户必须至少属于 CsUserAdministrator。</p></td>
<td><p>在部署文档的<a href="lync-server-2013-configuring-persistent-chat-server.md">Lync server 2013 中配置持久聊天服务器</a></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> 您可以部署一个或多个持久聊天服务器池。 我们支持多个持久聊天服务器池的原因是，在给定区域生成的数据需要保留在该区域中的一些法规原因。 例如，如果在芝加哥部署一个持久聊天服务器池，而另一个在苏黎世中遵守了适用于瑞士的数据的规章，则用户可以在持久聊天服务器池中连接到聊天室，前提是他们有权访问。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

