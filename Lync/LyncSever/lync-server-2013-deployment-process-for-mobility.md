---
title: Lync Server 2013：移动功能的部署过程
TOCTitle: 移动功能的部署过程
ms:assetid: 5a1cebda-c14b-4ff4-9c36-f7caa868160f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh690023(v=OCS.15)
ms:contentKeyID: 49312941
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中移动功能的部署过程

 

_**上一次修改主题：** 2015-03-09_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013. It is noted accordingly.

本节介绍部署 Lync Server 2013 移动功能所需的步骤的顺序。

### 移动功能部署过程

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
<li><p>创建内部 DNS CNAME 或 A（主机，如果为 IPv6，则为 AAAA）记录来解析内部自动发现服务 URL。</p></li>
<li><p>创建外部 DNS CNAME 或 A（主机，如果为 IPv6，则为 AAAA）记录来解析外部自动发现服务 URL。</p></li>
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
<td><p><a href="lync-server-2013-modifying-certificates-for-mobility.md">在 Lync Server 2013 中修改证书以实现移动功能</a></p></td>
</tr>
<tr class="odd">
<td><p>配置反向代理</p></td>
<td><ul>
<li><p>将利用使用者替代名称更新的证书分配给安全套接字层 (SSL) 侦听器。</p></li>
<li><p>为外部自动发现服务 URL 重新配置 Web 发布规则。</p></li>
<li><p>确保 前端池上的外部 Lync Server 2013 Web 服务 URL 存在 Web 发布规则。</p></li>
</ul>
<p>或</p>
<ul>
<li><p>如果您选择将 HTTP 用于初始自动发现请求并且不更新证书上的使用者替代名称列表，请为端口 80 HTTP 配置新的 Web 发布规则或重新配置现有发布规则。</p></li>
</ul></td>
<td><p>本地管理员</p></td>
<td><p><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">在 Lync Server 2013 中配置反向代理以实现移动功能</a></p></td>
</tr>
<tr class="even">
<td><p>使用 Mcx 移动服务测试 Lync 2010 Mobile 的移动部署。</p></td>
<td><p>运行 <strong>Test-CsMcxP2PIM</strong> 以测试将即时消息从一个用户发送给另一个用户的情况。</p>
<p>有关选项的完整列表，请参阅 <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsMcxP2PIM">Test-CsMcxP2PIM</a> 的 Lync Server 命令行管理程序 cmdlet 文档。</p></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verifying-your-mobility-deployment.md">在 Lync Server 2013 中验证您的移动功能部署</a></p></td>
</tr>
<tr class="odd">
<td><p>使用 UCWA Web 组件测试 Lync 2013 移动客户端的移动部署</p></td>
<td><p>使用 <strong>Test-CsUcwaConference</strong> cmdlet 来测试和验证预定义测试用户或一对实际用户是否可以使用 UCWA 创建和参与会议。</p>
<p>有关选项的完整列表，请参阅 <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsUcwaConference">Test-CsUcwaConference</a> 的 Lync Server 命令行管理程序 cmdlet 文档。</p></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verifying-your-mobility-deployment.md">在 Lync Server 2013 中验证您的移动功能部署</a></p></td>
</tr>
<tr class="even">
<td><p>配置推送通知</p></td>
<td><ul>
<li><p>对于 Lync Server 2013边缘服务器，添加 Lync Server 联机宿主提供商并配置宿主提供商联盟。</p></li>
<li><p>对于 Lync Server 2010  边缘服务器，添加 Lync Server 联机宿主提供商并配置宿主提供商联盟。</p></li>
<li><p>对于 Office Communications Server 2007 R2边缘服务器，添加联盟伙伴。</p></li>
<li><p>如果您希望通过 Wi-Fi 网络支持推送通知，请为 TCP 端口 5223 配置出站防火墙规则。</p></li>
<li><p>使用 <strong>Set-CsPushNotificationConfiguration</strong> cmdlet 启用 Apple 推送通知服务 (APNS) 和 Microsoft 推送通知服务 (MPNS) 的推送通知。默认情况下，此功能已禁用。</p></li>
<li><p>使用 <strong>Test-CsFederatedPartner</strong> cmdlet 测试联盟配置，并使用 <strong>Test-CsMCXPushNotification</strong> cmdlet 测试推送通知。</p>
<div>

> [!NOTE]  
> 推送通知用于 Apple 设备和 Windows Phone 上的 Lync 2010 Mobile 客户端<br />
推送通知仅对 Windows Phone 上的 Lync 2013 移动客户端是必需的


</div></li>
</ul></td>
<td><p>RtcUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configuring-for-push-notifications.md">在 Lync Server 2013 中配置推送通知</a></p></td>
</tr>
<tr class="odd">
<td><p>配置移动策略</p></td>
<td><p>使用 <strong>Set-CsMobilityPolicy</strong> cmdlet 允许或不允许：</p>
<ul>
<li><p>工作电话呼叫</p></li>
<li><p>启用 IP 音频和 IP 视频</p></li>
<li><p>IP 音频和/或 IP 视频需要 WiFi</p></li>
</ul></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configuring-mobility-policy.md">在 Lync Server 2013 中配置移动策略</a></p></td>
</tr>
</tbody>
</table>

