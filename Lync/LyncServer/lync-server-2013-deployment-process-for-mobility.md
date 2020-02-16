---
title: Lync Server 2013：移动性部署过程
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
ms.openlocfilehash: 337e85520cb2a285f4e4743837aafa4136c89f27
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035314"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-mobility-in-lync-server-2013"></a>Lync Server 2013 中的移动性部署过程

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-19_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013. It is noted accordingly.

本节介绍部署 Lync Server 2013 移动功能所需的步骤序列。

### <a name="mobility-deployment-process"></a>移动功能部署过程

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
<td><p>创建域名系统 (DNS) 记录</p></td>
<td><ul>
<li><p>创建内部 DNS CNAME 或 A （host，如果 IPv6，AAAA）记录以解析内部自动发现服务 URL。</p></li>
<li><p>创建外部 DNS CNAME 或 A （host，如果 IPv6，AAAA）记录以解析外部自动发现服务 URL。</p></li>
</ul></td>
<td><p>Domain Admins</p>
<p>DnsAdmins</p></td>
<td><p><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">在 Lync Server 2013 中为自动发现服务创建 DNS 记录</a></p></td>
</tr>
<tr class="even">
<td><p>修改证书</p></td>
<td><p>向以下证书添加使用者替代名称条目以支持移动用户的安全连接：</p>
<ul>
<li><p>控制器证书</p></li>
<li><p>前端池证书</p></li>
<li><p>反向代理证书</p></li>
</ul></td>
<td><p>本地管理员</p></td>
<td><p><a href="lync-server-2013-modifying-certificates-for-mobility.md">在 Lync Server 2013 中修改证书的移动性</a></p></td>
</tr>
<tr class="odd">
<td><p>配置反向代理</p></td>
<td><ul>
<li><p>将利用使用者替代名称更新的证书分配给安全套接字层 (SSL) 侦听器。</p></li>
<li><p>重新配置外部自动发现服务 URL 的 web 发布规则。</p></li>
<li><p>请确保前端池上的外部 Lync Server 2013 Web 服务 URL 存在 web 发布规则。</p></li>
</ul>
<p>或</p>
<ul>
<li><p>如果选择将 HTTP 用于初始自动发现请求，并且不更新证书上的主题备用名称列表，请为端口 80 HTTP 配置新的 web 发布规则或重新配置现有发布规则。</p></li>
</ul></td>
<td><p>本地管理员</p></td>
<td><p><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">在 Lync Server 2013 中配置反向代理以实现移动功能</a></p></td>
</tr>
<tr class="even">
<td><p>使用 Mcx 移动服务测试 Lync 2010 Mobile 的移动部署</p></td>
<td><p>运行 <strong>Test-CsMcxP2PIM</strong> 以测试将即时消息从一个用户发送给另一个用户的情况。</p>
<p>有关选项的完整列表，请参阅 Lync Server 命令行管理程序 cmdlet 文档中的<a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">test-csmcxp2pim</a> 。</p></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verifying-your-mobility-deployment.md">在 Lync Server 2013 中验证移动性部署</a></p></td>
</tr>
<tr class="odd">
<td><p>使用 UCWA Web 组件测试 Lync 2013 移动客户端的移动性部署</p></td>
<td><p>使用<strong>test-csucwaconference</strong> cmdlet 测试并验证预定义的测试用户或一对实际用户是否可以使用 UCWA 创建和参与会议。</p>
<p>有关选项的完整列表，请参阅 Lync Server 命令行管理程序 cmdlet 文档中的<a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">test-csucwaconference</a> 。</p></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verifying-your-mobility-deployment.md">在 Lync Server 2013 中验证移动性部署</a></p></td>
</tr>
<tr class="even">
<td><p>配置推送通知</p></td>
<td><ul>
<li><p>对于 Lync Server 2013 边缘服务器，添加 Lync Server online 承载提供程序并配置托管提供程序联合身份验证。</p></li>
<li><p>对于 Lync Server 2010 边缘服务器，添加 Lync Server online 承载提供程序并配置托管提供程序联合身份验证。</p></li>
<li><p>对于 Office 通信服务器 2007 R2 边缘服务器，添加联盟伙伴。</p></li>
<li><p>如果您希望通过 Wi-Fi 网络支持推送通知，请为 TCP 端口 5223 配置防火墙出站规则。</p></li>
<li><p>使用 <strong>Set-CsPushNotificationConfiguration</strong> cmdlet 启用 Apple 推送通知服务 (APNS) 和 Microsoft 推送通知服务 (MPNS) 的推送通知。 默认情况下，此功能已禁用。</p></li>
<li><p>使用 <strong>Test-CsFederatedPartner</strong> cmdlet 测试联盟配置，并使用 <strong>Test-CsMCXPushNotification</strong> cmdlet 测试推送通知。</p>
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
<td><p>使用<strong>set-csmobilitypolicy</strong> cmdlet 可以允许或禁止：</p>
<ul>
<li><p>通过工作进行呼叫</p></li>
<li><p>启用 IP 音频和 IP 视频</p></li>
<li><p>要求提供 IP 音频和/或 IP 视频的 WiFi</p></li>
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

