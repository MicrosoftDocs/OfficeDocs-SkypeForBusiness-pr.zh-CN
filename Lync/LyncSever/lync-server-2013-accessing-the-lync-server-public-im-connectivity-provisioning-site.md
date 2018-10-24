---
title: Lync Server 2013：访问 Lync Server 公共 IM 连接设置站点
TOCTitle: 访问 Lync Server 公共 IM 连接设置站点
ms:assetid: 77a08234-6bcf-4f59-b43b-ee5fc1926585
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn440174(v=OCS.15)
ms:contentKeyID: 59602826
ms.date: 03/09/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 从 Lync Server 2013 访问 Lync Server 公共 IM 连接设置站点

 

_**上一次修改主题：** 2017-03-09_

与以前的 PIC 设置方法相比，Lync-Skype 连接的设置过程已更改。此设置过程最多需要 30 天才能完成。建议您在完成文档中的其余步骤之前先开始此过程。在为您的帐户完成 Lync-Skype 设置过程后，该帐户将被激活，并且将为符合资格的用户启用公共 IM 连接。

### 要设置 Lync-Skype 连接，您需要以下信息：

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p>Microsoft 协议编号</p></li>
<li><p>访问边缘服务完全限定的域名 (FQDN)</p></li>
<li><p>会话初始协议 (SIP) 域</p></li>
<li><p>任何其他访问边缘服务 FQDN</p></li>
<li><p>联系信息</p></li>
</ol></td>
</tr>
<tr class="even">
<td><ol>
<li><p>Microsoft 协议编号</p></li>
<li><p>访问边缘服务完全限定的域名 (FQDN)</p></li>
<li><p>会话初始协议 (SIP) 域</p></li>
<li><p>任何其他访问边缘服务 FQDN</p></li>
<li><p>联系信息</p></li>
</ol></td>
</tr>
</tbody>
</table>


### 要启动 Lync-Skype 连接的设置过程，请执行下列操作：

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p>使用您的 Microsoft Windows Live ID 登录网站 <strong>https://pic.lync.com</strong>。</p></li>
<li><p>选择 Microsoft 许可协议类型。</p></li>
<li><p>选中复选框，确保您已阅读并接受 Lync Server 产品使用权利。</p></li>
<li><p>在“<strong>启动设置请求</strong>”页面上，单击合适的链接以启动设置请求：</p></li>
<li><p>在“<strong>指定设置信息</strong>”页面上，输入 <strong>访问边缘服务 FQDN</strong>。例如，<strong>accessedge.contoso.com</strong>。</p></li>
<li><p>输入至少一个或多个 SIP 域名，然后单击“<strong>添加</strong>”。</p>
<div>

> [!IMPORTANT]  
> 需要至少一个访问边缘服务器和一个 SIP 域才能完成设置过程。SIP 域和访问边缘服务器必须处于活动状态、正在运行并且在网络上可访问。

</div></li>
<li><p>在“<strong>公共 IM 服务提供商</strong>”列表中，选择“<strong>Skype</strong>”，然后单击“<strong>下一步</strong>”以添加联系信息并提交设置请求。</p></li>
</ol></td>
</tr>
<tr class="even">
<td><ol>
<li><p>使用您的 Microsoft Windows Live ID 登录网站 <strong>https://pic.lync.com</strong>。</p></li>
<li><p>选择 Microsoft 许可协议类型。</p></li>
<li><p>选中复选框，确保您已阅读并接受 Lync Server 产品使用权利。</p></li>
<li><p>在“<strong>启动设置请求</strong>”页面上，单击合适的链接以启动设置请求：</p></li>
<li><p>在“<strong>指定设置信息</strong>”页面上，输入 <strong>访问边缘服务 FQDN</strong>。例如，<strong>accessedge.contoso.com</strong>。</p></li>
<li><p>输入至少一个或多个 SIP 域名，然后单击“<strong>添加</strong>”。</p>
<div>

> [!IMPORTANT]  
> 需要至少一个访问边缘服务器和一个 SIP 域才能完成设置过程。SIP 域和访问边缘服务器必须处于活动状态、正在运行并且在网络上可访问。

</div></li>
<li><p>在“<strong>公共 IM 服务提供商</strong>”列表中，选择“<strong>Skype</strong>”，然后单击“<strong>下一步</strong>”以添加联系信息并提交设置请求。</p></li>
</ol></td>
</tr>
</tbody>
</table>


在提交设置请求之后，可能需要多达 30 天帐户才能激活并且才能为用户启用公共 IM 连接。

## 启用联盟和公共 IM 连接 (PIC)

在提交设置请求后，您可以集中精力关注 Lync Server 环境和配置 Lync-Skype 连接所需的管理任务。在此部分中，我们假设 Lync Server 管理员已部署 Lync Server 并配置了外部访问。有关为 Lync Server 配置外部访问的其他信息，请参阅"规划外部用户访问"（网址为 [http://go.microsoft.com/fwlink/p/?LinkID=273772](http://go.microsoft.com/fwlink/p/?linkid=273772)）和"部署外部用户访问"（网址为 [http://go.microsoft.com/fwlink/p/?LinkID=27378](http://go.microsoft.com/fwlink/p/?linkid=27378)）。

要针对 Lync-Skype 连接准备 Lync Server 环境，Lync Server 管理员必须完成以下三个任务：

## 1\. 配置联盟和 PIC

需要联盟，Skype 用户才能与您的组织中的 Lync 用户进行通信。公共即时消息连接 (PIC) 是一种联盟类别，必须配置它，您的 Lync 用户才能够与 Skype 用户进行通信。联盟和 PIC 可使用 Lync Server 控制面板进行配置，如下所示。

> [!IMPORTANT]  
> Live Communication Server 2005 SP1 或 Office Communications Server 2007 不再支持 PIC 联盟。支持 PIC 联盟的平台包括 Lync Server 2013、Lync Server 2010 和 Office Communications Server 2007 R2。


## 2\. 配置至少一个策略以支持联盟的用户访问

使用 Lync Server 控制面板，管理员必须配置一个或多个外部用户访问策略来控制 Skype 用户能否与内部 Lync Server 用户进行协作。

## 3\. 针对 Lync 配置 Skype PIC 提供商设置

使用 Lync Server 命令行管理程序，管理员必须配置 Lync 客户端策略以将 Skype 显示为附加 PIC 提供商。

> [!NOTE]  
> 只有至少再配置一个策略（步骤 2，此过程前面所述）以支持公共 IM 连接，公共即时消息连接 (PIC) 服务提供商的用户才能参与组织中的 IM 或会议。<br />
> 要配置联盟和 PIC，请参阅&quot;启用或禁用联盟和公共 IM 连接&quot;，网址为 <a href="http://go.microsoft.com/fwlink/p/?linkid=306063">http://go.microsoft.com/fwlink/p/?LinkId=306063</a>。<br />
> 要至少配置一个策略以支持联盟的用户访问，请参阅&quot;配置策略以控制公共用户访问&quot;，网址为 <a href="http://go.microsoft.com/fwlink/p/?linkid=306064">http://go.microsoft.com/fwlink/p/?LinkId=306064</a>。



1.  从 Lync Server 前端服务器，打开 Lync Server 命令行管理程序。

2.  运行以下两个命令：
    
      - Remove-CsPublicProvider -Identity Messenger
    
      - New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl "https://images.edge.messenger.live.com/Messenger\_16x16.png" -VerificationLevel 2 -Enabled 1

3.  从 Lync 客户端，您现在可以选择 Skype 作为 PIC 提供商，并通过指定其 Microsoft 帐户来添加 Skype 客户端。此外，已合并并使用其 Microsoft 帐户登录的 Skype 用户可以向 Lync 用户发送联系人请求。有关 Microsoft 帐户的详细信息，请参阅[什么是 Microsoft 帐户？](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account)。有关向 Lync 添加客户端的附加信息，请参阅[在 Lync Server 2013 中使用 Lync-Skype 连接作为最终用户](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)。

4.  有关修改托管提供商的详细信息，请参阅"创建或编辑托管的 SIP 联盟提供商"，网址为 [http://go.microsoft.com/fwlink/p/?LinkId=306065](http://go.microsoft.com/fwlink/p/?linkid=306065)。

这将完成必须在服务器上执行的管理任务。您现在可以设置 Lync-Skype 连接。

## 其他资源

[在 Lync Server 2013 中使用 Lync-Skype 连接作为最终用户](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

[Provisioning guide for Lync-Skype connectivity in Lync Server 2013](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

