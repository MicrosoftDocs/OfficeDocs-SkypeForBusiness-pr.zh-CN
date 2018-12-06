---
title: Lync Server 2013：规划简单 URL
TOCTitle: 规划简单 URL
ms:assetid: 20e4f4b6-b7ff-4297-b00d-d1211ee800ac
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398287(v=OCS.15)
ms:contentKeyID: 49312228
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中规划简单 URL

 

_**上一次修改主题：** 2015-12-11_

简单 URL 既便于用户加入会议，又便于管理员登录到 Lync Server 管理工具。

Lync Server 支持三种简单 URL：

  - “会议”用作站点或组织中所有会议的基 URL。会议简单 URL 的一个示例是 https://meet.contoso.com。特定会议的 URL 可能是 https://meet.contoso.com/*username*/7322994。
    
    通过使用会议简单 URL，用于加入会议的链接将易于理解且易于传达和分发。

  - “拨入”允许访问“电话拨入式会议设置”网页。此页显示会议的拨入号码及其可用语言、分配的会议信息（即，对于不需要预定的会议）以及会议中的 DTMF 控制，并支持对个人标识号 (PIN) 和分配的会议信息的管理。拨入简单 URL 包含在所有会议邀请中，因此要拨号加入会议的用户可以访问所需的电话号码和 PIN 信息。拨入简单 URL 的一个示例是 https://dialin.contoso.com。

  - “管理”允许快速访问 Lync Server 控制面板。通过将管理简单 URL 键入到浏览器，管理员可以从组织防火墙内的任何计算机打开 Lync Server 控制面板。管理简单 URL 是组织内部的。管理简单 URL 的一个示例是 https://admin.contoso.com。

## 简单 URL 作用域

可以将简单 URL 配置为具有 global 作用域，也可以为组织中的每个中央站点指定不同的简单 URL。如果同时指定全局简单 URL 和站点简单 URL，则站点简单 URL 具有优先权。

在大多数情况下，我们建议您只设置全局级别的简单 URL，这样，如果从一个站点移至另一个站点，用户的会议简单 URL 不会更改。例外情况是对于不同站点的拨入用户需要使用不同电话号码的组织。请注意，如果要将某个站点上的一个简单 URL（如拨入简单 URL）设置为站点级别的简单 URL，您还必须将该站点上的其他简单 URL 设置为站点级别。

您可以在 拓扑生成器中设置全局简单 URL。要在站点级别设置简单 URL，必须使用 Set-CsSimpleURLConfiguration cmdlet。

## 命名简单 URL

有三种推荐的选项可用于命名简单 URL。您选择的选项会暗示设置支持简单 URL 的 DNS A 记录和证书的方式。在每个选项中，您必须为组织中的每个 SIP 域配置一个会议简单 URL。

无论具有多少个 SIP 域，整个组织始终只需要一个拨入简单 URL 和一个管理简单 URL。

有关所需的 DNS A 记录和证书的详细信息，请参阅规划文档中的[Lync Server 2013 中简单 URL 的 DNS 要求](lync-server-2013-dns-requirements-for-simple-urls.md)和[Lync Server 2013 中内部服务器的证书要求](lync-server-2013-certificate-requirements-for-internal-servers.md)。

在选项 1 中，为每个简单 URL 创建新的 SIP 域名。

如果使用此选项，则需要为每个简单 URL 配置单独的 DNS A 记录，而且必须在证书中命名每个会议简单 URL。

### 简单 URL 命名选项 1

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>简单 URL</strong></p></td>
<td><p><strong>示例</strong></p></td>
</tr>
<tr class="even">
<td><p>会议</p></td>
<td><p>https://meet.contoso.com、https://meet.fabrikam.com 等（组织中的每个 SIP 域都有一个）</p></td>
</tr>
<tr class="odd">
<td><p>拨入</p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>管理员</p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


对于选项 2，简单 URL 基于域名 lync.contoso.com。因此，只需一个可启用全部三种类型简单 URL 的 DNS A 记录。此 DNS A 记录会引用 lync.contoso.com。此外，仍需要为组织中的其他 SIP 域配置单独的 DNS A 记录。

### 简单 URL 命名选项 2

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>简单 URL</strong></p></td>
<td><p><strong>示例</strong></p></td>
</tr>
<tr class="even">
<td><p>会议</p></td>
<td><p>https://lync.contoso.com/Meet、https://lync.fabrikam.com/Meet 等（组织中的每个 SIP 域都有一个）</p></td>
</tr>
<tr class="odd">
<td><p>拨入</p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p>管理员</p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


如果具有许多 SIP 域，并且希望每个 SIP 域具有单独的会议简单 URL，但希望最大程度地减少这些简单 URL 所要求的 DNS 记录和证书，则选项 3 是最有用的。

### 简单 URL 命名选项 3

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>简单 URL</strong></p></td>
<td><p><strong>示例</strong></p></td>
</tr>
<tr class="even">
<td><p>会议</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p>拨入</p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p>管理员</p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


## 简单 URL 命名和验证规则

拓扑生成器和 Lync Server 命令行管理程序 cmdlet 对简单 URL 强制实施多个验证规则。您必须设置会议简单 URL 和拨入简单 URL，但可以选择设置管理简单 URL。每个 SIP 域都必须具有单独的会议简单 URL，但整个组织只需要一个拨入简单 URL 和一个管理简单 URL。

组织中的每个简单 URL 必须具有唯一的名称，且不能是其他简单 URL 的前缀（例如，不能将 lync.contoso.com/Meet 设置为会议简单 URL，也不能将 lync.contoso.com/Meet/Dialin 设置为拨入简单 URL）。简单 URL 名称不能包含任何池的 FQDN 或任何端口信息（例如，不允许使用 https://FQDN:88/meet）。所有简单 URL 都必须以 https:// 前缀开头。

简单 URL 只能包含字母数字字符（即，a-z、A-Z、0-9 和圆点 (.)）。如果使用其他字符，则简单 URL 可能不会正常工作。

## 部署后更改简单 URL

如果在初始部署后更改简单 URL，您必须注意更改如何影响简单 URL 的 DNS 记录和证书。如果简单 URL 的基础发生更改，则还必须更改 DNS 记录和证书。例如，将 https://lync.contoso.com/Meet 更改为 https://meet.contoso.com 时，会将基 URL 由 lync.contoso.com 更改为 meet.contoso.com，因此需要更改 DNS 记录和证书，以引用 meet.contoso.com。如果将简单 URL 由 https://lync.contoso.com/Meet 更改为 https://lync.contoso.com/Meetings，其中基 URL lync.contoso.com 保持不变，则无需更改 DNS 或证书。

但是，每次更改简单 URL 名称时，都必须在每台控制器和前端服务器上运行 **Enable-CsComputer**，以注册该更改。

## 另请参阅

#### 概念

[Lync Server 2013 中简单 URL 的 DNS 要求](lync-server-2013-dns-requirements-for-simple-urls.md)

