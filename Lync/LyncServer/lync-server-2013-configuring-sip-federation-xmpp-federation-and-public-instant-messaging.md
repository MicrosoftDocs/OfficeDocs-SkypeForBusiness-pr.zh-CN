---
title: 配置 SIP 联盟、XMPP 联盟和公共即时消息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring SIP federation, XMPP federation and public instant messaging
ms:assetid: a6d04f0b-5cb8-4084-a3a2-d501938971f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205134(v=OCS.15)
ms:contentKeyID: 48184998
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94590e669c17328a33b8af62eda46e861aec6bdf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204518"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-sip-federation-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>在 Lync Server 2013 中配置 SIP 联盟、XMPP 联盟和公共即时消息

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-10-07_

联盟、公共即时消息连接和可扩展消息传递和状态协议 (XMPP) 定义了一类不同的外部用户 – 联盟用户。 联合 Lync Server 部署或 XMPP 部署的用户可以访问有限的一组服务，并通过外部部署进行身份验证。 远程用户是 Lync Server 部署的成员，并且具有对部署提供的所有服务的访问权限。

<div>


> [!NOTE]
> AOL 和 Yahoo！的生命周期结束日期为2014年6月 已宣布。 有关详细信息，请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的支持公用即时信使连接</A>。



</div>

公共即时消息连接是一种特殊类型的联盟，允许 Lync Server 客户端使用 Lync 2013 访问已配置的公用即时消息伙伴。 以下是当前公共即时消息连接合作伙伴：

  - <span></span>  
    America Online

  - <span></span>  
    Windows Live

  - <span></span>  
    Yahoo\!

利用公共即时消息连接配置，Lync 用户可按以下内容访问公共即时消息连接用户：

  - IM 和状态

  - Lync 客户端中公共即时消息连接联系人的可见性

  - 与联系人的面对面 IM 会话

  - 与 Windows Live 用户的音频和视频呼叫

Lync Server 联盟定义 Lync Server 部署与其他 Office Communications Server 2007 R2 或 Lync Server 部署之间的协议。利用 Lync Server 联盟配置，Lync 用户可按以下内容访问联盟用户：

  - IM 和状态

  - Lync 客户端中联盟联系人的创建

XMPP 联盟基于可扩展消息传递和状态协议定义外部部署。利用 XMPP 配置，Lync 用户可按以下内容访问允许的 XMPP 域用户：

  - IM 和状态 – 仅限于面对面

  - Lync 客户端中 XMPP 联盟联系人的创建

<div>


> [!IMPORTANT]
> Microsoft 对 Lync Server 2013 的 XMPP 功能进行了测试，并支持 Microsoft 实现与 Google 谈话的即时消息联盟。 对于任何其他 XMPP 系统，请联系第三方供应商以验证它们是否支持与 Lync Server 2013 联合，以及任何部署或疑难解答建议。



</div>

<div>

## <a name="edge-server-external-federation-public-instant-messaging-connectivity-and-xmpp-users-deployment-process"></a>边缘服务器外部联盟、公共即时消息连接和 XMPP 用户部署过程


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
<td><p>运行拓扑生成器以编辑边缘服务器设置并创建和发布拓扑。 现有的边缘拓扑会将更改从中央管理存储复制到边缘服务器。</p></td>
<td><p>Domain Admins 组和 RTCUniversalServerAdmins 组</p>



> [!NOTE]
> 可以使用属于本地用户组成员的帐户来编辑拓扑，但发布拓扑需要属于 Domain Admins 组和 RTCUniversalServerAdmins 组的成员的帐户。

</td>
<td><p><a href="lync-server-2013-building-an-edge-and-director-topology.md">在 Lync Server 2013 中构建边缘和控制器拓扑</a></p></td>
</tr>
<tr class="even">
<td><p>准备安装</p></td>
<td><ol>
<li><p>确保满足系统先决条件。</p></li>
<li><p>配置内部和外部 DNS 记录以支持公共即时消息连接、Lync 联盟和 XMPP 联盟</p></li>
<li><p>在防火墙上配置端口和协议以支持要部署的联盟的类型</p></li>
<li><p>获取和安装公共证书。获取证书所需的时间取决于颁发证书的证书颁发机构 (CA)。此步骤在部署的这一时间点是可选的。如果在此时间点不执行此步骤，则必须在边缘服务器配置过程中执行此步骤。在获取证书前，边缘服务器服务无法启动</p></li>
</ol></td>
<td><p>根据组织的需要，这些角色通常会被分到各种工作组中时</p></td>
<td><p><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">在 Lync Server 2013 中规划 SIP、XMPP 联合身份验证和公共即时消息</a></p></td>
</tr>
<tr class="odd">
<td><p>为联盟方案设置边缘服务器</p></td>
<td><ol>
<li><p>将导出的拓扑配置文件传输到每台边缘服务器或允许复制完成</p></li>
<li><p>重新运行部署向导以安装联盟的支持组件</p></li>
<li><p>配置边缘服务器</p></li>
<li><p>为每台边缘服务器请求和安装证书</p></li>
<li><p>重新启动边缘服务器服务</p></li>
</ol></td>
<td><p>Administrators 组</p></td>
<td><p><a href="lync-server-2013-setting-up-lync-federation.md">在 Lync Server 2013 中设置 Lync 联合</a></p>
<p><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">在 Lync Server 2013 中设置公共即时消息连接</a></p>
<p><a href="lync-server-2013-setting-up-xmpp-federation.md">在 Lync Server 2013 中设置 XMPP 联盟</a></p></td>
</tr>
<tr class="even">
<td><p>配置对外部用户访问的支持。</p></td>
<td><ol>
<li><p>使用 Lync Server 控制面板外部用户访问</p></li>
<li><p>配置外部访问策略以实现与联盟用户或公共用户的通信</p></li>
<li><p>配置 SIP 联盟域以允许或阻止域</p></li>
<li><p>为公共即时消息连接提供程序启用 SIP 联盟提供程序</p></li>
<li><p>为每个 XMPP 域配置 XMPP 联盟伙伴</p></li>
</ol></td>
<td><p>分配给 CSAdministrator 角色的 RTCUniversalServerAdmins 组或用户帐户</p></td>
<td><p><a href="lync-server-2013-configuring-support-for-external-user-access.md">在 Lync Server 2013 中配置对外部用户访问的支持</a></p>
<p><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">在 Lync Server 2013 中为公用提供程序配置媒体加密</a></p></td>
</tr>
<tr class="odd">
<td><p>验证边缘服务器配置</p></td>
<td><p>验证服务器连接和对内部服务器中的配置数据的复制</p></td>
<td><p>对于复制验证，为分配给 CSAdministrator 角色的 RTCUniversalServerAdmins 组或用户帐户。对于用户连接验证，则为每种类型的联盟用户的用户</p></td>
<td><p><a href="lync-server-2013-verifying-your-edge-deployment.md">在 Lync Server 2013 中验证边缘部署</a></p>
<p><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Lync Server 2013 中的示例 XMPP 配置–与 Google 对话的 XMPP 联盟</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

