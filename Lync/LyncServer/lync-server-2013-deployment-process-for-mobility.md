---
title: Lync Server 2013：移动功能的部署过程
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for mobility
ms:assetid: 5a1cebda-c14b-4ff4-9c36-f7caa868160f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690023(v=OCS.15)
ms:contentKeyID: 48184220
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6f9f7994981a860aaa02d4674d6a3248c3593d6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762590"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-mobility-in-lync-server-2013"></a>Lync Server 2013 中移动功能的部署过程

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-19_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013. It is noted accordingly.

本部分介绍部署 Lync Server 2013 移动功能所需步骤的顺序。

### <a name="mobility-deployment-process"></a>移动性部署过程

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
<th>部署文档</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>创建域名系统（DNS）记录</p></td>
<td><ul>
<li><p>创建内部 DNS CNAME 或 A （host，if IPv6，AAAA）记录来解析内部自动发现服务 URL。</p></li>
<li><p>创建外部 DNS CNAME 或 A （host，if IPv6，AAAA）记录以解析外部自动发现服务 URL。</p></li>
</ul></td>
<td><p>Domain Admins</p>
<p>DnsAdmins</p></td>
<td><p><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">在 Lync Server 2013 中为自动发现服务创建 DNS 记录</a></p></td>
</tr>
<tr class="even">
<td><p>修改证书</p></td>
<td><p>将 "主题备用名称" 条目添加到以下证书以支持移动用户的安全连接：</p>
<ul>
<li><p>导演证书</p></li>
<li><p>前端池证书</p></li>
<li><p>反向代理证书</p></li>
</ul></td>
<td><p>本地管理员</p></td>
<td><p><a href="lync-server-2013-modifying-certificates-for-mobility.md">在 Lync Server 2013 中修改证书以实现移动功能</a></p></td>
</tr>
<tr class="odd">
<td><p>配置反向代理</p></td>
<td><ul>
<li><p>将使用 "使用者备用名称" 更新的证书分配给安全套接字层（SSL）侦听器。</p></li>
<li><p>重新配置外部自动发现服务 URL 的 web 发布规则。</p></li>
<li><p>请确保你的前端池中的外部 Lync Server 2013 Web 服务 URL 存在 web 发布规则。</p></li>
</ul>
<p>或</p>
<ul>
<li><p>如果你选择将 HTTP 用于初始自动发现请求，并且不更新证书上的使用者备用名称列表，请为端口 80 HTTP 配置新的 web 发布规则或重新配置现有发布规则。</p></li>
</ul></td>
<td><p>本地管理员</p></td>
<td><p><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">在 Lync Server 2013 中配置反向代理以实现移动功能</a></p></td>
</tr>
<tr class="even">
<td><p>使用 Mcx 移动服务测试适用于 Lync 2010 Mobile 的移动部署</p></td>
<td><p>运行<strong>test-CsMcxP2PIM</strong>以测试将即时消息从一个人发送到另一个人。</p>
<p>有关选项的完整列表，请参阅 Lync Server Management Shell cmdlet 文档中的<a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">CsMcxP2PIM</a> 。</p></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verifying-your-mobility-deployment.md">在 Lync Server 2013 中验证您的移动功能部署</a></p></td>
</tr>
<tr class="odd">
<td><p>使用 UCWA Web 组件测试适用于 Lync 2013 移动客户端的移动部署</p></td>
<td><p>使用<strong>CsUcwaConference</strong> cmdlet 测试和验证预定义的测试用户或一对实际用户是否可以使用 UCWA 创建和参与会议。</p>
<p>有关选项的完整列表，请参阅 Lync Server Management Shell cmdlet 文档中的<a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">CsUcwaConference</a> 。</p></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verifying-your-mobility-deployment.md">在 Lync Server 2013 中验证您的移动功能部署</a></p></td>
</tr>
<tr class="even">
<td><p>配置推送通知</p></td>
<td><ul>
<li><p>对于 Lync Server 2013 Edge 服务器，添加 Lync Server online 托管提供商和配置托管提供商联合身份验证。</p></li>
<li><p>对于 Lync Server 2010 Edge 服务器，添加 Lync Server online 托管提供商和配置托管提供商联合身份验证。</p></li>
<li><p>对于 Office 通信服务器 2007 R2 Edge 服务器，请添加联盟伙伴。</p></li>
<li><p>如果想要通过 Wi-fi 网络支持推送通知，请为 TCP 端口5223配置出站防火墙规则。</p></li>
<li><p>使用<strong>CsPushNotificationConfiguration</strong> Cmdlet 启用 Apple 推送通知服务（APNS）和 Microsoft 推送通知服务（MPNS）的推送通知。 默认情况下，此功能处于禁用状态。</p></li>
<li><p>使用<strong>CsFederatedPartner</strong> cmdlet 测试联合身份验证配置和<strong>CsMCXPushNotification</strong> cmdlet 以测试推送通知。</p>
<div>

> [!NOTE]  
> 推送通知用于 Apple 设备和 Windows Phone 上的 Lync 2010 移动客户端<BR>仅 Windows Phone 上的 Lync 2013 移动客户端需要推送通知


</div></li>
</ul></td>
<td><p>RtcUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configuring-for-push-notifications.md">在 Lync Server 2013 中配置推送通知</a></p></td>
</tr>
<tr class="odd">
<td><p>配置移动策略</p></td>
<td><p>将<strong>CsMobilityPolicy</strong> cmdlet 用于允许或禁止：</p>
<ul>
<li><p>通过工号拨号</p></li>
<li><p>启用 IP 音频和 IP 视频</p></li>
<li><p>IP 音频和/或 IP 视频需要 WiFi</p></li>
</ul></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configuring-mobility-policy.md">在 Lync Server 2013 中配置移动策略</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

