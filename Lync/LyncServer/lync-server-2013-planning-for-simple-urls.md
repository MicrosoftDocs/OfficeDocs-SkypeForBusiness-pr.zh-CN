---
title: Lync Server 2013：规划简单 URL
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
ms.openlocfilehash: 224ca0315aff2618500182398cfe792c9626b883
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41750462"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-simple-urls-in-lync-server-2013"></a>在 Lync Server 2013 中规划简单 URL

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2015-12-11_

简单的 Url 使你的用户加入会议更容易，并且让你的管理员更容易获得 Lync Server 管理工具。

Lync 服务器支持三个简单的 Url：

  - "**开会**" 用作网站或组织中的所有会议的基本 URL。 一个 "匹配" 简单 URL 的示例https://meet.contoso.com是。 特定会议的 URL 可能是https://meet.contoso.com/ *username*/7322994。
    
    通过 "满足简单 URL"，加入会议的链接易于理解，并且易于沟通和分发。

  - 通过**拨入功能**，可以访问 "电话拨入式会议设置" 网页。 此页面显示会议拨入号码，其中包含其可用语言、分配的会议信息（即，对于不需要安排的会议）和会议 DTMF 控件，并支持个人识别码的管理（PIN）和分配的会议信息。 拨入式简单 URL 包含在所有会议邀请中，以便希望拨入会议的用户可以访问必要的电话号码和 PIN 信息。 拨入式简单 URL 的示例是https://dialin.contoso.com。

  - **管理员**可快速访问 Lync Server 控制面板。 在你组织的防火墙内的任何计算机中，管理员可以通过在浏览器中键入管理员简单的 URL 来打开 Lync Server 控制面板。 管理员简单的 URL 是您的组织内部的。 管理员简单的 URL 的一个示例是https://admin.contoso.com

<div>

## <a name="simple-url-scope"></a>简单的 URL 范围

你可以将简单 Url 配置为具有全局范围，或者你可以为你的组织中的每个中心网站指定不同的简单 Url。 如果同时指定全局范围简单 URL 和网站范围简单 URL，则网站范围的简单 URL 优先。

在大多数情况下，我们建议你仅在全局级别设置简单的 Url，以便用户的 "满足简单 URL" 从一个网站移动到另一个网站时不会更改。 例外情况是需要对不同站点上的电话拨入用户使用不同电话号码的组织。 请注意，如果在网站上将一个简单的 URL （如拨入式简单 URL）设置为网站级简单 URL，则还必须将该网站上的其他简单 Url 设置为网站级别。

<div>


> [!NOTE]  
> 如果你选择使用网站范围简单的 Url，你的用户将无法在不同网站中的前端池之间移动，并且这些用户无需重新计划所有计划会议，因为会议的简单 Url 在网站之间不同。 这包括故障转移方案，其中备份关系中的池位于不同的网站中。 如果需要在部署网站范围内的简单 Url 的网站之间进行故障转移，用户将无法加入其会议，因为 URL 的范围。 有关详细信息，请查看<A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">CsSimpleUrlConfiguration</A>。



</div>

可以在拓扑生成器中设置全局简单的 Url。 若要在网站级别设置简单的 URL，必须使用 CsSimpleURLConfiguration cmdlet。

</div>

<div>

## <a name="naming-your-simple-urls"></a>命名简单 Url

有三个推荐选项可用于命名简单 Url。 选择哪个选项对您设置 DNS A 记录和支持简单 Url 的证书有何影响。 在每个选项中，必须为组织中的每个 SIP 域配置一个 "满足简单 URL"。

你始终只需要在整个组织中使用一个简单的 URL 进行拨入，一个用于管理，无论你拥有多少个 SIP 域。

有关必要的 DNS A 记录和证书的详细信息，请参阅[Lync server 2013 中的简单 url 的 DNS 要求](lync-server-2013-dns-requirements-for-simple-urls.md)和规划文档中[lync server 2013 内部服务器的证书要求](lync-server-2013-certificate-requirements-for-internal-servers.md)。

在选项1中，为每个简单的 URL 创建一个新的 SIP 域名。

如果使用此选项，则每个简单 URL 都需要一个单独的 DNS A 记录，并且每个 "满足简单 URL" 都必须在证书中命名。

### <a name="simple-url-naming-option-1"></a>简单的 URL 命名选项1

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>简单的 URL</strong></p></td>
<td><p><strong>示例</strong></p></td>
</tr>
<tr class="even">
<td><p>会议</p></td>
<td><p>https://meet.contoso.com， https://meet.fabrikam.com等等（组织中的每个 SIP 域一个）</p></td>
</tr>
<tr class="odd">
<td><p>拨入</p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>Iis</p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


通过选项2，简单 Url 基于域名 lync.contoso.com。 因此，只需一个 DNS A 记录即可启用所有三种类型的简单 Url。 此 DNS A 记录引用 lync.contoso.com。 此外，你的组织中的其他 SIP 域仍需要单独的 DNS A 记录。

### <a name="simple-url-naming-option-2"></a>简单的 URL 命名选项2

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>简单的 URL</strong></p></td>
<td><p><strong>示例</strong></p></td>
</tr>
<tr class="even">
<td><p>会议</p></td>
<td><p>https://lync.contoso.com/Meet， https://lync.fabrikam.com/Meet等等（组织中的每个 SIP 域一个）</p></td>
</tr>
<tr class="odd">
<td><p>拨入</p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p>Iis</p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


如果你有多个 SIP 域，而你希望它们具有单独的符合简单的 Url，但希望尽量减少这些简单 Url 的 DNS 记录和证书要求，则选项3非常有用。

### <a name="simple-url-naming-option-3"></a>简单的 URL 命名选项3

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>简单的 URL</strong></p></td>
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
<td><p>Iis</p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="simple-url-naming-and-validation-rules"></a>简单的 URL 命名和验证规则

拓扑生成器和 Lync Server Management Shell cmdlet 针对你的简单 Url 强制执行几条验证规则。 您需要为 "满足" 和 "拨入" 设置简单的 Url，但为 "管理员" 设置一个是可选的。 每个 SIP 域都必须具有单独的 "匹配" 的 "匹配" 简单 URL，但对于整个组织，只需一个拨入简单的 url 和一个管理员简单的 URL。

组织中的每个简单 URL 都必须具有唯一的名称，并且不能是另一个简单 URL 的前缀（例如，不能将 lync.contoso.com/Meet 设置为您的 "满足简单 url" 和 "lync.contoso.com/Meet/Dialin" 作为拨入简单 URL）。 简单的 URL 名称不能包含任何池的 FQDN，也不能包含任何端口信息（例如https://FQDN:88/meet ，不允许）。 所有简单的 Url 必须以 https://前缀开头。

简单 Url 只能包含字母数字字符（即 a-z、a-z、0-9 和句号（.）。 如果使用其他字符，则简单 Url 可能不会按预期工作。

</div>

<div>

## <a name="changing-simple-urls-after-deployment"></a>在部署后更改简单的 Url

如果你在初始部署后更改简单的 URL，你必须知道更改对简单 Url 的 DNS 记录和证书有何影响。 如果简单 URL 的基础发生更改，则您还必须更改 DNS 记录和证书。 例如，从https://lync.contoso.com/Meet https://meet.contoso.com lync.contoso.com 更改为 meet.contoso.com 的基本 URL，因此你需要更改 DNS 记录和证书才能引用 meet.contoso.com。 如果将简单 URL 更改https://lync.contoso.com/Meet为 "与https://lync.contoso.com/Meetings"，lync.contoso.com 的基 url 保持不变，因此不需要任何 DNS 或证书更改。

但是，当您更改简单的 URL 名称时，必须在每个 Director 和前端服务器上运行**Enable-CsComputer**以注册更改。

</div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中简单 URL 的 DNS 要求](lync-server-2013-dns-requirements-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

