---
title: 证书摘要 - 自动发现
TOCTitle: 证书摘要 - 自动发现
ms:assetid: 16ac96bb-882a-4141-b75c-9530637548d9
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ945616(v=OCS.15)
ms:contentKeyID: 52060965
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 证书摘要 - 自动发现

 

_**上一次修改主题：** 2015-03-09_

Lync Server 2013 自动发现服务在控制器和前端池服务器上运行，并且在 DNS 中发布时可由 Lync 客户端用于查找服务器和用户服务。如果您要从 Lync Server 2010 升级并且在客户端使用自动发现之前未部署 Mobility，则必须在任何运行自动发现服务的控制器和前端服务器上修改证书使用者替代名称列表。此外，可能还必须修改证书上的供反向代理上的外部 Web 服务发布规则使用的使用者替代名称列表。

有关是否在反向代理上利用使用者替代名称列表的决定基于您是在端口 80 还是端口 443 上发布自动发现服务：

  - **在端口 80 上发布**   如果在端口 80 上发起对自动发现服务的初始查询，则不需要对证书进行任何更改。这是因为运行 Lync 的移动设备将从外部访问端口 80 上的反向代理，然后从内部桥接至端口 8080 上的控制器或前端服务器。有关详细信息，请参阅“使用端口 80 的初始自动发现过程”一节[Lync Server 2013 中的移动性技术要求](lync-server-2013-technical-requirements-for-mobility.md)。

  - **在端口 443 上发布**   外部 Web 服务发布规则使用的证书上的使用者替代名称列表必须为您组织中的每个 SIP 域包含一个 *lyncdiscover.\<sipdomain\>* 条目。
    
    > [!IMPORTANT]  
	> 强烈建议您使用 HTTPS 而不是 HTTP。HTTPS 使用证书来加密流量。HTTP 不提供加密功能，发送的任何数据都将是纯文本格式。


使用内部证书颁发机构重新颁发证书通常是一个简单的过程，但对于 Web 服务发布规则所使用的公共证书，添加多个使用者替代名称条目的成本会很高。为了解决此问题，我们支持端口 80 上的初始自动发现连接，该连接随后会重定向到控制器或前端服务器上的端口 8080。

> [!NOTE]  
> 如果您的 Lync Server 2013 基础结构使用由内部证书颁发机构 (CA) 颁发的内部证书，并且您计划支持移动设备以无线方式进行连接，则必须在移动设备上安装来自内部 CA 的根证书链，或者您必须更改为在您的 Lync Server 2013 基础结构上使用公共证书。



本主题介绍控制器、前端服务器和反向代理所需的添加的使用者替代名称。只引用添加的使用者替代名称 (SAN)。请参阅规划章节以获取证书上其他条目的相关指导。有关详细信息，请参阅[Lync Server 2013 中的控制器方案](lync-server-2013-scenarios-for-the-director.md)、[Lync Server 2013 中的外部用户访问方案](lync-server-2013-scenarios-for-external-user-access.md)和[Lync Server 2013 中的反向代理方案](lync-server-2013-scenarios-for-reverse-proxy.md)。

下表定义了控制器池、前端池和反向代理的自动发现 SAN 条目：

### 控制器池证书要求

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>说明</th>
<th>使用者替代名称条目</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>内部自动发现服务 URL</p></td>
<td><p>SAN=lyncdiscoverinternal.<em>&lt;内部域名&gt;</em></p></td>
</tr>
<tr class="even">
<td><p>外部自动发现服务 URL</p></td>
<td><p>SAN=lyncdiscover.<em>&lt;sip 域&gt;</em></p></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> 您可使用新的 SAN 条目将最新更新的证书分配给默认证书。或者，您也可以使用 SAN=*.<em>&lt;sip 域&gt;</em>。



### 前端池证书要求

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>说明</th>
<th>使用者替代名称条目</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>内部自动发现服务 URL</p></td>
<td><p>SAN=lyncdiscoverinternal.<em>&lt;内部域名&gt;</em></p></td>
</tr>
<tr class="even">
<td><p>外部自动发现服务 URL</p></td>
<td><p>SAN=lyncdiscover.<em>&lt;sip 域&gt;</em></p></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> 您可使用新的 SAN 条目将最新更新的证书分配给默认证书。或者，您也可以使用 SAN=*.<em>&lt;sip 域&gt;</em>



### 反向代理（公共 CA）证书要求

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>说明</th>
<th>使用者替代名称条目</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部自动发现服务 URL</p></td>
<td><p>SAN=lyncdiscover.<em>&lt;sip 域&gt;</em></p></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> 您可使用新的 SAN 条目将最新更新的证书分配给反向代理上的 SSL 侦听器。


