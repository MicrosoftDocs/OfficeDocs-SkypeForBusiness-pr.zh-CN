---
title: Lync Server 2013： Internet Information Services （IIS）要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Internet Information Services (IIS) requirements
ms:assetid: 4f57a605-a8a9-4c5a-9a18-05ecb3d9ab6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398321(v=OCS.15)
ms:contentKeyID: 48184128
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2e3914d66576d72d250a96948d45f05aa0a5f41
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145351"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="internet-information-services-iis-requirements-in-lync-server-2013"></a>Lync Server 2013 中的 Internet 信息服务（IIS）要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-06-19_

多个 Lync Server 2013 组件需要 Internet 信息服务（IIS）。 本主题介绍支持 Lync Server 所需的特定 IIS 功能。 本节中的主题介绍 IIS 特定组件的要求。

在 Windows Server 2008 中启用 Web 服务器 (IIS) 角色时，将默认安装多种角色服务。下表介绍在 Windows Server 2008 中启用 Web 服务器 (IIS) 角色时，必须安装的其他角色服务。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>角色服务</th>
<th>功能</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>常见的 HTTP 功能</p></td>
<td><p>HTTP 重定向</p></td>
</tr>
<tr class="even">
<td><p>应用程序开发</p></td>
<td><p>ASP.NET</p></td>
</tr>
<tr class="odd">
<td><p>应用程序开发</p></td>
<td><p>.NET 扩展性</p></td>
</tr>
<tr class="even">
<td><p>应用程序开发</p></td>
<td><p>ISAPI 扩展</p></td>
</tr>
<tr class="odd">
<td><p>应用程序开发</p></td>
<td><p>ISAPI 筛选器</p></td>
</tr>
<tr class="even">
<td><p>运行状况和诊断</p></td>
<td><p>日志记录工具</p></td>
</tr>
<tr class="odd">
<td><p>运行状况和诊断</p></td>
<td><p>追踪</p></td>
</tr>
<tr class="even">
<td><p>安全性</p></td>
<td><p>基本身份验证</p></td>
</tr>
<tr class="odd">
<td><p>安全性</p></td>
<td><p>Windows 身份验证</p></td>
</tr>
<tr class="even">
<td><p>管理工具</p></td>
<td><p>IIS 管理脚本和工具</p></td>
</tr>
<tr class="odd">
<td><p>管理工具</p></td>
<td><p>IIS 6 管理兼容性</p></td>
</tr>
</tbody>
</table>


<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="保护" alt="security" />安全说明：</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>如果您在 Windows Server 2008 操作系统上使用 IIS 7.0，Lync Server 安装程序将在 IIS 中禁用内核模式身份验证。</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a>本部分内容

  - [Lync Server 2013 中的前端池和 Standard Edition 服务器的 IIS 要求](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

