---
title: 为 Lync Server 2013 启用的用户帐户
TOCTitle: 为 Lync Server 2013 启用的用户帐户
ms:assetid: 8021087e-5084-4a39-9fef-ab9376c6d371
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg182543(v=OCS.15)
ms:contentKeyID: 49313404
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 为 Lync Server 2013 启用的用户帐户

 

_**上一次修改主题：** 2015-03-09_

本节中的主题提供了可使用 Lync Server 2013 控制面板执行的用户设置配置的分步过程。

> [!IMPORTANT]
> 不能使用 Lync Server 控制面板管理 Active Directory Domain Admins 组的成员用户。对于 Domain Admins 用户，只能使用 Lync Server 控制面板执行只读搜索操作。要对 Domain Admins 用户执行写入操作（例如，启用或禁用 Lync Server 控制面板、更改池或策略分配、电话设置、SIP 地址），必须在以 Domain Admins 用户身份登录后使用 Windows PowerShell cmdlet。有关使用 Windows PowerShell cmdlet 管理用户的详细信息，请参阅 <a href="lync-server-2013-lync-server-management-shell.md">Lync Server 命令行管理程序</a>。


在执行任何涉及搜索用户或筛选用户搜索结果的 Lync Server 2013 管理任务时，有些用户属性 (Property) 作为 Active Directory 域服务 中的属性 (Attribute) 存在，但在部署 Microsoft Exchange Server 之前，它们不会复制到全局编录中。 Microsoft Exchange 而非 Lync Server 会在安装时将以下属性标记为要复制到全局编录中：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>用户信息</th>
<th>地址和电话</th>
<th>组织</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>缩写</p></td>
<td><p>街道地址</p>
<p>国家/地区</p>
<p>寻呼机</p>
<p>传真</p>
<p>手机</p></td>
<td><p>职务</p>
<p>公司</p>
<p>部门</p>
<p>办公室</p></td>
</tr>
</tbody>
</table>


## 本部分内容

  - [查看为 Lync Server 2013 启用的用户帐户的信息](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)

  - [启用和禁用 Lync Server 2013 的用户](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

  - [管理用户的企业语音](lync-server-2013-managing-enterprise-voice-for-users.md)

  - [修改用户帐户属性](lync-server-2013-modifying-user-account-properties.md)

  - [在 Lync Server 2013 中管理组织的外部访问策略](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [分配每用户策略](lync-server-2013-assigning-per-user-policies.md)

## 另请参阅

#### 概念

[用户管理 Cmdlet](lync-server-2013-user-management-cmdlets.md)  

#### 其他资源

[在 Lync Server 2013 中管理用户](lync-server-2013-managing-users-in-lync-server.md)

