---
title: Lync Server 2013：Internet Information Services (IIS) 要求
TOCTitle: Internet Information Services (IIS) 要求
ms:assetid: 4f57a605-a8a9-4c5a-9a18-05ecb3d9ab6b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398321(v=OCS.15)
ms:contentKeyID: 49312819
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 Internet Information Services (IIS) 要求

 

_**上一次修改主题：** 2015-03-09_

某些 Lync Server 2013 组件需要 Internet Information Services (IIS)。本主题介绍支持 Lync Server 所需的特定 IIS 功能。本节中的主题介绍 IIS 特定组件的要求。

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
<td><p>跟踪</p></td>
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


> [!NOTE]  
> 如果在 Windows Server 2008 操作系统上使用 IIS 7.0， Lync Server 安装程序将禁用 IIS 中的内核模式身份验证。


## 本部分内容

  - [Lync Server 2013 中前端池和 Standard Edition 服务器的 IIS 要求](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)

