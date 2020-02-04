---
title: Lync Server 2013：证书摘要 - 反向代理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Reverse proxy
ms:assetid: f2b9a53f-aead-413d-81e9-4a294a010fbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205381(v=OCS.15)
ms:contentKeyID: 48185820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42e52fa8522de53404fee3f3b5798f159361dbf5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736612"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---reverse-proxy-in-lync-server-2013"></a>Lync Server 2013 中的证书摘要 - 反向代理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-11-14_

反向代理的证书要求比边缘服务器的证书要求更简单。 所提供的流程图提供了必要的要求。 随附的表提供了典型的证书主题名称和主题备用名称，这些名称与我们在 Edge 服务器讨论中审阅的方案相关。 有关 Edge 服务器方案的更多详细信息，请参阅[Lync server 2013 中的外部用户访问方案](lync-server-2013-scenarios-for-external-user-access.md)。

**反向代理的证书流图表**

![边缘服务器的流程图](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "边缘服务器的流程图")

### <a name="reverse-proxy-external-interface"></a>反向代理：外部接口

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>组件</th>
<th>主题名称</th>
<th>使用者备用名称（SAN）/Order</th>
<th>备注</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>反向代理</p></td>
<td><p>webext.contoso.com</p></td>
<td><p>webext.contoso.com</p>
<p>webdirext.contoso.com</p>
<p>dialin.contoso.com</p>
<p>meet.contoso.com</p>
<p>officewebapps01.contoso.com</p>
<p>lyncdiscover.contoso.com</p>
<p>（可选）:* contoso.com</p></td>
<td><p>证书必须由公共 CA 和服务器 EKU 颁发。 服务包括通讯簿服务、通讯组扩展 Office Web Apps for 电话会议和 Lync IP 设备发布规则。 主题备用名称包括：</p>
<ul>
<li><p>前端服务器或前端池的外部 Web 服务 FQDN</p></li>
<li><p>主管或控制器池的外部 Web 服务 FQDN</p></li>
<li><p>电话拨入式会议</p></li>
<li><p>联机会议发布规则</p></li>
<li><p>适用于会议的 Office Web Apps</p></li>
<li><p>Lyncdiscover （自动发现）</p></li>
</ul>
<p>可选通配符替换了 "满足" 和 "拨入" SAN</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

