---
title: Lync Server 2013：SQL Server 的部署权限
TOCTitle: SQL Server 的部署权限
ms:assetid: 56ea0c02-bcf5-4d45-aa13-570531c29074
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398375(v=OCS.15)
ms:contentKeyID: 49312899
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中 SQL Server 的部署权限

 

_**上一次修改主题：** 2015-03-09_

安装并部署 Lync Server 2013 时， Microsoft SQL Server 2012 具有特定的要求。由于 Windows 和 SQL Server 对其安全性的定义不同，因此以 Active Directory 域中的管理员身份登录时不会隐式授予 SQL Server 的权限。您还必须是正配置的基于 SQL Server 的服务器上 sysadmin 实体的成员。

## 数据库和 Lync Server 安装所需的权限

以下选项详细描述了安装 Lync Server 2013 文件和 SQL Server 数据库所需的三个权限和组成员身份关联。选择最符合组织要求的方案。

### 权限和组成员身份关联

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>SQL Server 或 Lync Server 2013 角色</th>
<th>典型角色的 SQL Server 权限和组成员身份</th>
<th>典型角色的 Lync Server 2013 权限和组成员身份</th>
<th>权限结果</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013 管理员</p></td>
<td><p>必须授予 sysadmin SQL Server 安全组和 SQL Server 本地 Administrators 组的成员身份</p></td>
<td><p>必须是 RTCUniversalServerAdmins 组的成员</p></td>
<td><p>Lync Server 2013 管理员具有同时安装 Lync Server 2013 和 SQL Server 数据库的相应权限。</p></td>
</tr>
<tr class="even">
<td><p>SQL Server 管理员</p></td>
<td><p>SQL Server sysadmin 组成员（或等效身份）和 SQL Server 本地 Administrators 组的成员</p></td>
<td><p>必须是 RTCUniversalServerReadOnly 组的成员</p></td>
<td><p>SQL Server 管理员具有同时安装 Lync Server 2013 和 SQL Server 数据库的相应权限。</p></td>
</tr>
<tr class="odd">
<td><p>两个管理员共同承担安装职责</p></td>
<td><p>SQL Server 管理员是 sysadmin 组的成员（或等效身份）和 SQL Server 本地 Administrators 组的成员</p></td>
<td><p>Lync Server 2013 管理员是 RTCUniversalServerAdmins 的成员</p></td>
<td><p>Lync Server 2013 管理员可以安装 Lync Server 2013，但不能安装数据库。SQL Server 管理员使用由 Lync Server 2013 管理员提供的 Lync Server 命令行管理程序和 Windows PowerShell cmdlet 来安装数据库。SQL Server 管理员使用的 Lync Server 2013 命令行管理程序安装在 前端服务器上。这样就不必在基于 SQL Server 的服务器上安装 Lync Server 2013 管理工具。</p></td>
</tr>
</tbody>
</table>

