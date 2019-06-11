---
title: 配置 SIP 联盟、XMPP 联盟和公共即时消息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring SIP federation, XMPP federation and public instant messaging
ms:assetid: a6d04f0b-5cb8-4084-a3a2-d501938971f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205134(v=OCS.15)
ms:contentKeyID: 48184998
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f82e154347c0a77dd4367678fefd518b1abf2fc7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837180"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-sip-federation-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>在 Lync Server 2013 中配置 SIP 联盟、XMPP 联盟和公共即时消息

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-10-07_

联盟、公共即时消息连接和可扩展消息和状态协议 (XMPP) 定义不同的外部用户类-联合用户。 联合 Lync Server 部署或 XMPP 部署的用户有权访问有限的一组服务, 并通过外部部署进行身份验证。 远程用户是 Lync Server 部署的成员, 并且有权访问你的部署提供的所有服务。

<div>


> [!NOTE]
> AOL 和 Yahoo! 的有效期结束日期为2014年6月 已宣布。 有关详细信息, 请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公共即时消息连接支持</A>。



</div>

公共即时消息连接是一种特殊类型的联盟, 允许 Lync Server 客户端使用 Lync 2013 访问配置的公共即时消息合作伙伴。 当前公共即时消息连接合作伙伴包括:

  - <span></span>  
    美洲在线

  - <span></span>  
    Windows Live

  - <span></span>  
    Yahoo\!

公共即时消息连接配置允许 Lync 用户通过以下方式访问公共即时消息连接用户:

  - IM 和状态

  - Lync 客户端中的公共即时消息连接联系人的可见性

  - 某人与联系人进行即时消息对话

  - 与 Windows Live 用户进行音频和视频通话

Lync 服务器联合在 Lync Server 部署和其他 Office 通信服务器 2007 R2 或 Lync Server 部署之间定义协议。 Lync 服务器联合配置允许 Lync 用户通过以下方式访问联盟用户:

  - IM 和状态

  - 在 Lync 客户端中创建联盟联系人

XMPP 联合身份验证基于可扩展消息和状态协议定义外部部署。 XMPP 配置允许 Lync 用户通过以下方式访问允许的 XMPP 域用户:

  - IM 和状态-仅限人员

  - 在 Lync 客户端中创建 XMPP 联盟联系人

<div>


> [!IMPORTANT]
> Microsoft 已测试 Lync Server 2013 的 XMPP 功能，并且支持该功能与 Google Talk 进行即时消息传递联盟。对于任何其他 XMPP 系统，请与第三方供应商联系，以确认它们是否支持与 Lync Server 2013 联盟以及获取任何部署或疑难解答建议。



</div>

<div>

## <a name="edge-server-external-federation-public-instant-messaging-connectivity-and-xmpp-users-deployment-process"></a>边缘服务器外部联合身份验证、公共即时消息连接和 XMPP 用户部署过程


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
<th>权限</th>
<th>文档</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>确定要添加到现有边缘部署的选项</p></td>
<td><p>运行拓扑生成器以编辑边缘服务器设置并创建和发布拓扑。 现有的边缘拓扑会将中央管理存储中的更改复制到边缘服务器。</p></td>
<td><p>域管理员组和 RTCUniversalServerAdmins 组</p>



> [!NOTE]
> 你可以使用本地 users 组的成员帐户编辑拓扑, 但发布拓扑需要一个帐户, 该帐户是域管理员组和 RTCUniversalServerAdmins 组的成员

</td>
<td><p><a href="lync-server-2013-building-an-edge-and-director-topology.md">在 Lync Server 2013 中构建边缘和控制器拓扑</a></p></td>
</tr>
<tr class="even">
<td><p>准备安装</p></td>
<td><ol>
<li><p>确保满足系统先决条件。</p></li>
<li><p>配置内部和外部 DNS 记录, 以支持公共即时消息连接、Lync 联合身份验证和 XMPP 联合身份验证</p></li>
<li><p>在防火墙上配置端口和协议以支持要部署的联合身份验证类型</p></li>
<li><p>获取并安装公共证书。 获取证书所需的时间取决于证书颁发机构 (CA) 颁发的证书。 此步骤在部署中的这一点是可选的。 如果此时不执行此步骤, 则必须在边缘服务器配置期间执行此操作。 在获取证书之前无法启动 Edge 服务器服务</p></li>
</ol></td>
<td><p>根据你的组织的需要, 因为这些角色通常会拆分到多个工作组中</p></td>
<td><p><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">在 Lync Server 2013 中规划 SIP、XMPP 联盟和公共即时消息</a></p></td>
</tr>
<tr class="odd">
<td><p>为联盟方案设置边缘服务器</p></td>
<td><ol>
<li><p>将导出的拓扑配置文件传输到每台边缘服务器或允许复制完成</p></li>
<li><p>重新运行部署向导以安装联盟的支持组件</p></li>
<li><p>配置边缘服务器</p></li>
<li><p>为每台边缘服务器请求和安装证书</p></li>
<li><p>重新启动 Edge 服务器服务</p></li>
</ol></td>
<td><p>管理员组</p></td>
<td><p><a href="lync-server-2013-setting-up-lync-federation.md">在 Lync Server 2013 中设置 Lync 联盟</a></p>
<p><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">在 Lync Server 2013 中设置公共即时消息连接</a></p>
<p><a href="lync-server-2013-setting-up-xmpp-federation.md">在 Lync Server 2013 中设置 XMPP 联盟</a></p></td>
</tr>
<tr class="even">
<td><p>配置对外部用户访问的支持。</p></td>
<td><ol>
<li><p>使用 Lync Server "控制面板" 外部用户访问</p></li>
<li><p>配置外部访问策略以启用与联盟用户或公共用户的通信</p></li>
<li><p>将 SIP 联盟域配置为允许或阻止域</p></li>
<li><p>为公共即时消息连接提供程序启用 SIP 联合提供程序</p></li>
<li><p>配置每个 XMPP 域的 XMPP 联盟合作伙伴</p></li>
</ol></td>
<td><p>分配给 CSAdministrator 角色的 RTCUniversalServerAdmins 组或用户帐户</p></td>
<td><p><a href="lync-server-2013-configuring-support-for-external-user-access.md">在 Lync Server 2013 中配置对外部用户访问的支持</a></p>
<p><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">在 Lync Server 2013 中配置公共提供商的媒体加密</a></p></td>
</tr>
<tr class="odd">
<td><p>验证 Edge 服务器配置</p></td>
<td><p>验证服务器连接和来自内部服务器的配置数据的复制</p></td>
<td><p>对于复制的验证, RTCUniversalServerAdmins 组或分配给 CSAdministrator roleFor 验证用户连接的用户帐户, 每种类型的联合用户的用户</p></td>
<td><p><a href="lync-server-2013-verifying-your-edge-deployment.md">在 Lync Server 2013 中验证边缘部署</a></p>
<p><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Lync Server 2013 中的示例 XMPP 配置 –  与 Google Talk 的 XMPP 联盟</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

