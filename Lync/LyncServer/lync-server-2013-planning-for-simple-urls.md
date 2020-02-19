---
title: Lync Server 2013：规划简单 Url
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for simple URLs
ms:assetid: 20e4f4b6-b7ff-4297-b00d-d1211ee800ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398287(v=OCS.15)
ms:contentKeyID: 48183610
ms.date: 12/12/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 85b01956d901d5c4060dc1cf14f9991fdfce261c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139293"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-simple-urls-in-lync-server-2013"></a>在 Lync Server 2013 中规划简单 Url

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2015-12-11_

简单 Url 使用户加入会议变得更加容易，并使管理员更轻松地进入 Lync Server 管理工具。

Lync Server 支持三个简单的 Url：

  - ****“会议”用作站点或组织中所有会议的基 URL。 一个符合简单 URL 的示例是https://meet.contoso.com。 特定会议的 URL 可能为https://meet.contoso.com/ *username*/7322994。
    
    通过使用会议简单 URL，用于加入会议的链接将易于理解且易于传达和分发。

  - ****“拨入”允许访问“电话拨入式会议设置”网页。 此页显示会议的拨入号码及其可用语言、分配的会议信息（即，对于不需要预定的会议）以及会议中的 DTMF 控制，并支持对个人标识号 (PIN) 和分配的会议信息的管理。 拨入简单 URL 包含在所有会议邀请中，因此要拨号加入会议的用户可以访问所需的电话号码和 PIN 信息。 拨入式简单 URL 的一个示例是https://dialin.contoso.com。

  - **管理员**可以快速访问 Lync Server 控制面板。 通过组织的防火墙中的任何计算机，管理员都可以通过在浏览器中键入管理员简单的 URL 来打开 Lync Server 控制面板。 管理简单 URL 是组织内部的。 管理员简单 URL 的一个示例是https://admin.contoso.com

<div>

## <a name="simple-url-scope"></a>简单 URL 作用域

可以将简单 URL 配置为具有 global 作用域，也可以为组织中的每个中央站点指定不同的简单 URL。 如果同时指定全局范围简单 URL 和网站范围简单 URL，则网站范围简单 URL 具有优先权。

在大多数情况下，我们建议您只设置全局级别的简单 URL，这样，如果从一个站点移至另一个站点，用户的会议简单 URL 不会更改。例外情况是对于不同站点的拨入用户需要使用不同电话号码的组织。请注意，如果要将某个站点上的一个简单 URL（如拨入简单 URL）设置为站点级别的简单 URL，您还必须将该站点上的其他简单 URL 设置为站点级别。

<div>


> [!NOTE]  
> 如果选择使用网站范围的简单 Url，则用户将无法在不同网站中的前端池之间移动，而不会导致这些用户在会议简单 Url 不同的网站之间进行重新计划所有计划会议。 这包括故障转移方案，其中备份关系中的池位于不同的网站中。 如果需要在部署网站范围简单 Url 的网站之间进行故障转移，则用户将无法加入其会议，因为 URL 的范围。 有关详细信息，请检查<A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">CsSimpleUrlConfiguration</A>。



</div>

您可以在拓扑生成器中设置全局简单 Url。 要在站点级别设置简单 URL，必须使用 Set-CsSimpleURLConfiguration cmdlet。

</div>

<div>

## <a name="naming-your-simple-urls"></a>命名简单 URL

有三种推荐的选项可用于命名简单 URL。您选择的选项会暗示设置支持简单 URL 的 DNS A 记录和证书的方式。在每个选项中，您必须为组织中的每个 SIP 域配置一个会议简单 URL。

无论具有多少个 SIP 域，整个组织始终只需要一个拨入简单 URL 和一个管理简单 URL。

有关所需 DNS A 记录和证书的详细信息，请参阅规划文档中的 lync server 2013 中的[针对简单 url](lync-server-2013-dns-requirements-for-simple-urls.md)和在[lync server 2013 中的内部服务器的证书要求](lync-server-2013-certificate-requirements-for-internal-servers.md)中的 dns 要求。

在选项 1 中，为每个简单 URL 创建新的 SIP 域名。

如果使用此选项，则需要为每个简单 URL 配置单独的 DNS A 记录，而且必须在证书中命名每个会议简单 URL。

### <a name="simple-url-naming-option-1"></a>简单 URL 命名选项 1

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
<td><p>法规</p></td>
<td><p>https://meet.contoso.com、 https://meet.fabrikam.com等，依此类推（组织中的每个 SIP 域一个）</p></td>
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

### <a name="simple-url-naming-option-2"></a>简单 URL 命名选项 2

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
<td><p>法规</p></td>
<td><p>https://lync.contoso.com/Meet、 https://lync.fabrikam.com/Meet等，依此类推（组织中的每个 SIP 域一个）</p></td>
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

### <a name="simple-url-naming-option-3"></a>简单 URL 命名选项 3

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
<td><p>法规</p></td>
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


<div>

## <a name="simple-url-naming-and-validation-rules"></a>简单 URL 命名和验证规则

拓扑生成器和 Lync Server 命令行管理程序 cmdlet 对简单 Url 强制实施几种验证规则。 您必须设置会议简单 URL 和拨入简单 URL，但可以选择设置管理简单 URL。 每个 SIP 域都必须具有单独的会议简单 URL，但整个组织只需要一个拨入简单 URL 和一个管理简单 URL。

组织中的每个简单 URL 必须具有唯一的名称，且不能是其他简单 URL 的前缀（例如，不能将 lync.contoso.com/Meet 设置为会议简单 URL，也不能将 lync.contoso.com/Meet/Dialin 设置为拨入简单 URL）。 简单 URL 名称不能包含任何池的 FQDN，也不能包含任何端口信息（例如， https://FQDN:88/meet不允许）。 所有简单 URL 都必须以 https:// 前缀开头。

简单 URL 只能包含字母数字字符（即，a-z、A-Z、0-9 和圆点 (.)）。如果使用其他字符，则简单 URL 可能不会正常工作。

</div>

<div>

## <a name="changing-simple-urls-after-deployment"></a>部署后更改简单 URL

如果在初始部署后更改简单 URL，您必须注意更改如何影响简单 URL 的 DNS 记录和证书。 如果简单 URL 的基础发生更改，则还必须更改 DNS 记录和证书。 例如，从https://lync.contoso.com/Meet更改为将https://meet.contoso.com基 URL 从 lync.contoso.com 更改为 meet.contoso.com，因此您需要将 DNS 记录和证书更改为引用 meet.contoso.com。 如果将简单 URL 从https://lync.contoso.com/Meet更改为https://lync.contoso.com/Meetings，lync.contoso.com 的基 url 将保持不变，因此不需要任何 DNS 或证书更改。

但是，只要您更改简单的 URL 名称，就必须在每个控制器和前端服务器上运行**CsComputer**以注册更改。

</div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中简单 Url 的 DNS 要求](lync-server-2013-dns-requirements-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

