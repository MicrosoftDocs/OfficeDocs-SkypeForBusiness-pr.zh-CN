---
title: Lync Server 2013：持久聊天服务器的部署清单
TOCTitle: 持久聊天服务器的部署清单
ms:assetid: b1108f8f-88a2-4660-8086-d25ba76f7239
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412851(v=OCS.15)
ms:contentKeyID: 49313974
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的持久聊天服务器的部署清单

 

_**上一次修改主题：** 2015-03-09_

Lync Server 2013持久聊天服务器的部署要求您以正确的顺序进行部署，并要求您完成所有必需的部署步骤。

## 部署顺序

可以在部署初始拓扑之后部署 持久聊天服务器，至少包括一个 Lync Server 2013前端池或一台 Lync Server 2013Standard Edition Server。本主题介绍如何通过将 持久聊天服务器 添加到现有部署来对其进行部署。

## 部署过程

下表列出了部署 持久聊天服务器的基本步骤，并提供了更多详细信息的链接。

### 持久聊天服务器部署过程

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
<li><p>在 持久聊天服务器前端服务器上：</p></li>
</ul>
<ul>
<li><p>满足系统要求的操作系统</p></li>
<li><p>运行 Lync Server 2013 的计算机的必备软件</p></li>
<li><p>将承载 持久聊天服务器数据库的服务器上的 SQL Server</p></li>
</ul>
<p>如果需要 持久聊天服务器合规性：</p>
<ul>
<li><p>将承载 持久聊天服务器合规性数据库的服务器上的 SQL Server</p></li>
</ul></td>
<td><p>属于本地 Administrators 组成员的任何用户。</p></td>
<td><p>可支持性文档中的 <a href="lync-server-2013-supported-hardware.md">支持的适用于 Lync Server 2013 的硬件</a></p>
<p>可支持性文档中的<a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync Server 2013 中的服务器软件和基础结构支持</a></p>
<p><a href="lync-server-2013-determining-your-system-requirements.md">确定 Lync Server 2013 的系统要求</a></p>
<p><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Lync Server 2013 中持久聊天服务器的技术要求</a></p></td>
</tr>
<tr class="even">
<td><p><strong>创建适当的内部拓扑以支持 持久聊天服务器（或者，也可以是 持久聊天合规性）</strong></p></td>
<td><p>运行 拓扑生成器以将 持久聊天服务器池添加到您的拓扑：</p>
<ul>
<li><p>将 持久聊天服务器组件添加到拓扑</p></li>
<li><p>为 持久聊天服务器存储创建 SQL Server 数据库（以及为灾难恢复创建备份 SQL Server）</p></li>
<li><p>为 持久聊天服务器文件定义新 Lync 文件存储或使用现有 Lync 文件存储</p></li>
<li><p>关联可将请求路由到此 持久聊天服务器池的 Lync Server 2013 池</p></li>
</ul>
<p>如果需要 持久聊天合规性：</p>
<ul>
<li><p>添加 持久聊天合规性存储</p></li>
<li><p>单击“持久聊天服务器池定义”复选框以启用合规性</p></li>
<li><p>发布拓扑</p></li>
</ul>
<p>如果您在 标准版 上安装 持久聊天服务器，则 持久聊天服务器池的完全限定域名 (FQDN) 必须与 Standard Edition Server匹配，并且将 SQL Server 数据库并置在 Standard Edition Server 的 SQL Server Express 实例上</p></td>
<td><p>要定义拓扑，需要具有本地 Users 组成员身份的帐户。</p>
<p>要发布拓扑，需要具有 Domain Admins 组和 RTCUniversalServerAdmins 组成员身份的帐户，该用户还需在要用于 持久聊天服务器文件的 Lync 文件存储上具有完全控制权限（读取/写入/修改），以使拓扑生成器可以配置所需的 DACL。</p></td>
<td><p>部署文档中的<a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">在 Lync Server 2013 中将持久聊天服务器添加到部署</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>部署 持久聊天服务器</strong></p></td>
<td><p>在所有运行 持久聊天服务器的计算机上运行 Lync Server 安装程序。 持久聊天服务器安装程序将集成到 Lync Server 2013 部署向导中，该向导提供了以下说明：</p>
<ul>
<li><p>部署本地管理存储</p></li>
<li><p>安装 持久聊天服务器服务</p></li>
<li><p>请求和分配证书</p></li>
<li><p>运行并启动服务</p></li>
</ul></td>
<td><p>属于本地 Administrators 组成员的任何用户。</p></td>
<td><p>部署文档中的<a href="lync-server-2013-deploying-persistent-chat-server.md">在 Lync Server 2013 中部署持久聊天服务器</a></p></td>
</tr>
<tr class="even">
<td><p><strong>创建 持久聊天管理员</strong></p></td>
<td><p>将用户添加到 CsPersistentChatAdministrator 安全组。</p></td>
<td><p>属于域管理员成员的任何用户。</p></td>
<td><p>部署文档中的<a href="lync-server-2013-adding-a-persistent-chat-administrator.md">在 Lync Server 2013 中添加持久聊天管理员</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>配置 持久聊天服务器</strong></p></td>
<td><p>配置用户：</p>
<ul>
<li><p>用户必须通过策略启用才能访问 持久聊天服务器。默认情况下，该策略对所有用户都处于关闭状态，并且可以在全局/站点/池/用户范围进行定义。</p></li>
<li><p>配置设置</p></li>
</ul></td>
<td><p>用户必须是 CsPersistentChatAdministrator 的成员。要更改策略，用户必须至少属于 CsUserAdministrator。</p></td>
<td><p>部署文档中的<a href="lync-server-2013-configuring-persistent-chat-server.md">在 Lync Server 2013 中配置持久聊天服务器</a></p></td>
</tr>
</tbody>
</table>


> [!IMPORTANT]
> 您可以部署一个或多个 持久聊天服务器池。出于管理原因，我们支持多个 持久聊天服务器池，借此需要在给定区域中生成的数据保留在该区域。例如，如果您在芝加哥部署一个 持久聊天服务器池，而在苏黎世部署了另一个持久聊天服务器池，以符合瑞士的数据法规，则用户可以连接到这两个 持久聊天服务器池中的聊天室，但前提是这些用户具有访问权。

