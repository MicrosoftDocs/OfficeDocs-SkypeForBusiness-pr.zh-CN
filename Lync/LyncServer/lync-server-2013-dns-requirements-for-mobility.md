---
title: 移动的 DNS 要求
TOCTitle: 移动的 DNS 要求
ms:assetid: df6962bc-2a16-440e-a333-022ebd14f957
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh690040(v=OCS.15)
ms:contentKeyID: 49314484
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 移动的 DNS 要求

 

_**上一次修改主题：** 2015-03-09_

在部署 Lync Server 2013 移动功能时，您可以使用随 Microsoft Lync Server 2013 自动发现服务一起提供的新 URL，也可以使用现有的 Web 服务 URL。如果您使用现有 URL，则用户需要在其移动设备设置中手动输入 URL。此选项通常用于进行故障排除。在使用新 URL 时，移动客户端可以自动发现 Lync Server 2013 资源。在支持自动发现功能时，您需要添加新的域名系统 (DNS) 记录。本节介绍自动发现功能所需的 DNS 记录。

若要支持自动发现功能，您需要为每个 SIP 域创建以下 DNS 记录：

  - 支持从组织网络内部进行连接的移动用户的内部 DNS 记录

  - 支持从 Internet 进行连接的移动用户的外部或公共 DNS 记录

应无法从网络外部对内部自动发现 URL 进行寻址。应无法从网络内部对外部自动发现 URL 进行寻址。但是，如果您无法满足外部 URL 的此要求，则不会影响移动客户端的功能。

DNS 记录可以是 CNAME 记录或 A（主机）记录。

**内部 DNS 记录**

您需要创建下列内部 DNS 记录之一：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>记录类型</th>
<th>主机名称或 SRV 定义</th>
<th>解析为</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>lyncdiscoverinternal.<em>&lt;sipdomain&gt;</em></p></td>
<td><p>控制器池（若有）或前端池（如果您没有控制器）的内部 Web 服务完全限定的域名 (FQDN)</p></td>
</tr>
<tr class="even">
<td><p>A（主机）</p></td>
<td><p>lyncdiscoverinternal.<em>&lt;sipdomain&gt;</em></p></td>
<td><p>控制器池（若有）或前端池（如果您没有控制器）的内部 Web 服务 IP 地址（如果您使用负载平衡器，则为虚拟 IP (VIP) 地址）</p></td>
</tr>
</tbody>
</table>


**外部 DNS 记录**

您需要创建下列外部 DNS 记录之一：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>记录类型</th>
<th>主机名</th>
<th>解析为</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>lyncdiscover. <em>&lt;sipdomain&gt;</em></p></td>
<td><p>控制器池（若有）或前端池（如果您没有 控制器）的外部 Web 服务 FQDN</p></td>
</tr>
<tr class="even">
<td><p>A（主机）</p></td>
<td><p>lyncdiscover. <em>&lt;sipdomain&gt;</em></p></td>
<td><p>反向代理的外部或公用 IP 地址（如果使用负载平衡器，则为 VIP 地址）</p></td>
</tr>
<tr class="odd">
<td><p>SRV</p></td>
<td><p>_sipfederationtls._tcp. <em>&lt;sipdomain&gt;</em></p>
<p>解析为访问边缘服务的主机（A 或 AAAA）记录</p></td>
<td><p>要支持推送通知服务和 Apple 推送通知服务，应为每个具有 Microsoft Lync Mobile 客户端的 SIP 域创建一条 SRV 记录。</p>
<div>

> [!IMPORTANT]
> 此要求仅适用于基于 Apple 或 Microsoft 的移动设备上的 Microsoft Lync Mobile 客户端。Andriod 和 Nokia Symbian 设备不使用推送通知。

</div></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> Lyncdiscover（又称自动发现）流量会通过反向代理。SRV 记录指向通过访问边缘服务解析的一条记录。


