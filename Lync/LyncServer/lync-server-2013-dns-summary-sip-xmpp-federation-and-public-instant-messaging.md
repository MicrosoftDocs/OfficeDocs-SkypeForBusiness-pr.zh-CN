---
title: DNS 摘要 - SIP、XMPP 联盟和公共即时消息
TOCTitle: DNS 摘要 - SIP、XMPP 联盟和公共即时消息
ms:assetid: 1ed24fb8-a849-44c0-a52e-7aef7527e644
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ618369(v=OCS.15)
ms:contentKeyID: 49312207
ms.date: 03/09/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# DNS 摘要 - SIP、XMPP 联盟和公共即时消息

 

_**上一次修改主题：** 2017-03-09_

定义与 Office Communications Server 或 Lync Server 合作伙伴之间的联盟时需要的域名系统 (DNS) 记录由您的决策决定，即，您是否允许其他各方借助自动 DNS 发现技术发现您的域。如果您发布 \_sipfederationtls.\_tcp. *\<SIP 域名\>* SRV 记录，则任何其他 SIP 联盟域将能够“发现”您的联盟。通过使用 Lync Server 控制面板中的“允许的域”和“被阻止的域”设置，或者通过使用 Lync Server 命令行管理程序以及“Get”、“Set”、“New”、“Remove-CsAllowedDomain”和“-CsBlockedDomain”PowerShell cmdlet 设置允许或被阻止的域，您可以控制哪些联盟域能与您通信。有关如何配置这些设置以及如何使用 PowerShell cmdlet 的其他信息，请参阅本主题结尾的**相关主题**。

DNS 记录摘要表描述开放或可发现联盟所需要的条目。如果不想实现联盟发现，可以决定不配置 \_sipfederationtls.\_tcp. *\<SIP 域名\>* 记录。

> [!IMPORTANT]
> 在某些特定情况下，您必须具有 _sipfederationtls._tcp. <em>&lt;SIP domain name&gt;</em> SRV 记录，但又不想使用可发现联盟。其中一种情况是，您已经为用户部署了移动性。移动性推送通知交换所 (PNCH) 是一种用于使用 Lync 2010 Mobile 客户端的 Apple iPhone 或 iPad 或者使用 Lync 2010 Mobile 或 Lync 2013 移动客户端的 Windows Phone 上的 Microsoft Lync Mobile 客户端的特殊类型的联盟。如果同时部署了移动性和推送通知，则需要使用 _sipfederationtls._tcp. <em>&lt;SIP 域名&gt;</em> SRV SRV 记录。若要缓解此问题并控制可发现性，请清除设置“启用合作伙伴域发现”以关闭发现功能。


要为您的部署配置可扩展消息传递和状态协议 (XMPP)，您需要在外部 DNS 服务器中创建两条域名系统 (DNS) 记录，DNS 服务器随后将这些记录解析为您的 边缘服务器或 边缘池的 访问边缘服务。

在配置公共即时消息连接的域名系统 (DNS) 时，您将发现支持外部用户的配置将支持公共 IM 连接。如果已经配置 边缘服务器或 边缘池，则您应该已拥有支持公共 IM 连接所需的 DNS 记录。

## DNS 摘要 - SIP 联盟


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>位置/类型/端口</th>
<th>FQDN</th>
<th>IP 地址/FQDN 主机记录</th>
<th>映射位置/注释</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部 DNS/SRV/5061</p></td>
<td><p>_sipfederationtls._tcp.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>其他潜在联盟合作伙伴借助自动 DNS 发现技术发现您的联盟所需的访问边缘服务外部接口（称为“允许的 SIP 域”，在以前版本中称为“增强联盟”）。根据需要对具有已启用 Lync 的用户的所有 SIP 域重复此操作。</p>
<div>

> [!IMPORTANT]
> 移动性和推送通知交换所需要此 SRV 记录。当存在多个 SIP 域时，请为将具有 Lync Mobile 客户端的每个域创建并发布一条 SRV 记录。如果部署支持的每个 SIP 域没有显式 SRV 记录，推送通知服务和 Apple 推送通知服务可能无法按预期运行。

</div></td>
</tr>
</tbody>
</table>


## DNS 摘要 - 可扩展消息传递和状态协议 (XMPP)


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>位置/类型/端口</th>
<th>FQDN</th>
<th>IP 地址/FQDN 主机记录</th>
<th>映射位置/注释</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部 DNS/SRV/5269</p></td>
<td><p>_xmpp-server._tcp.contoso.com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>访问边缘服务或 边缘池上的 XMPP 代理外部接口。根据需要对所有满足下列条件的内部 SIP 域重复此过程：其中包含启用了 Lync 的用户，并且通过全局策略、用户所在站点的站点策略或应用于启用了 Lync 的用户的用户策略来配置外部访问策略，允许与 XMPP 联系人进行联系。此外，还必须在 XMPP 联盟伙伴策略中配置允许的 XMPP 域。有关其他详细信息，请参阅 <strong>另请参见</strong>中的主题</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>xmpp.contoso.com（例如）</p></td>
<td><p>承载 XMPP 代理的 边缘服务器或 边缘池上的 访问边缘服务的 IP 地址</p></td>
<td><p>指向 访问边缘服务或承载 XMPP 代理服务的 边缘池。通常，您创建的 SRV 记录将指向主机（A 或 AAAA）记录</p></td>
</tr>
</tbody>
</table>


## DNS 摘要 – 公共即时消息连接


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>位置/类型/端口</th>
<th>FQDN/DNS 记录</th>
<th>IP 地址/FQDN</th>
<th>映射位置/注释</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>访问边缘服务接口</p></td>
<td><p>访问边缘服务外部接口 (Contoso)。根据需要对包含启用了 Lync 的用户的所有 SIP 域重复。</p></td>
</tr>
</tbody>
</table>


## 另请参阅

#### 任务

[在 Lync Server 2013 中设置 XMPP 联盟](lync-server-2013-setting-up-xmpp-federation.md)  
[在 Lync Server 2013 中配置推送通知](lync-server-2013-configuring-for-push-notifications.md)  
[在 Lync Server 2013 中启用或禁用联盟伙伴发现](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)  

#### 概念

[Lync Server 2013 中的外部用户访问方案](lync-server-2013-scenarios-for-external-user-access.md)  
[确定 Lync Server 2013 的 DNS 要求](lync-server-2013-determine-dns-requirements.md)  

#### 其他资源

[在 Lync Server 2013 中管理组织的 SIP 联盟域](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)

