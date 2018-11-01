---
title: 管理与外部用户和组织的通信
TOCTitle: 管理与外部用户和组织的通信
ms:assetid: 8a64f0fe-1e79-47d8-835e-548d7ac0757e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362813(v=OCS.15)
ms:contentKeyID: 56271176
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 管理与外部用户和组织的通信

 

_**上一次修改主题：** 2015-06-22_

以下 cmdlet 可用于管理与外部域和公共即时消息 (IM) 提供商的联盟：


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Cmdlet</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="new-csedgeallowallknowndomains.md">New-CsEdgeAllowAllKnownDomains</a></p></td>
<td><p>允许用户与所有域（阻止的域列表上指定的那些域除外）进行通信。</p>
<p>联盟是一种使用户能够与其他域中的用户交换即时消息和状态信息的服务。通常，管理员使用允许的域和阻止的域列表指定用户可以与之通信的外部域。</p></td>
</tr>
<tr class="even">
<td><p><a href="new-csedgeallowlist.md">New-CsEdgeAllowList</a></p></td>
<td><p>将用户通信限制为指定的域集合。</p>
<p>用户仅允许与允许的域列表中上出现的域进行通信。</p></td>
</tr>
<tr class="odd">
<td><p><a href="new-csedgedomainpattern.md">New-CsEdgeDomainPattern</a></p></td>
<td><p>修改允许的域或阻止的域列表。</p></td>
</tr>
<tr class="even">
<td><p><a href="get-cstenantfederationconfiguration.md">Get-CsTenantFederationConfiguration</a><br />
<a href="set-cstenantfederationconfiguration.md">Set-CsTenantFederationConfiguration</a></p></td>
<td><p>启用和禁用与其他域的联盟和与公共提供商的联盟。</p></td>
</tr>
<tr class="odd">
<td><p><a href="get-cstenanthybridconfiguration.md">Get-CsTenantHybridConfiguration</a><br />
<a href="set-cstenanthybridconfiguration.md">Set-CsTenantHybridConfiguration</a></p></td>
<td><p>向混合配置设置分配合适的值。</p>
<p>在混合或“拆分域”部署中，组织的一些用户的帐户驻留在 Skype for Business Online 上，同时，其他用户的帐户驻留在 Lync Server 2013 上。默认情况下，驻留在 Skype for Business Online 上的用户无法访问企业语音提供的整套功能。要向 Skype for Business Online 用户提供对这些企业语音功能的访问权限，管理员需要向混合配置设置分配合适的值。可以使用 <strong>CsTenantHybridConfiguration</strong> cmdlet 管理这些值。</p></td>
</tr>
<tr class="even">
<td><p><a href="get-cstenantpublicprovider.md">Get-CsTenantPublicProvider</a><br />
<a href="set-cstenantpublicprovider.md">Set-CsTenantPublicProvider</a></p></td>
<td><p>管理与公共提供商的联盟。</p>
<p>公共提供商是为普通公众提供 SIP 通信服务的组织。当您与某个公共提供商建立联盟关系后，实际上便与具有该提供商所托管的帐户的所有用户都建立了联盟关系。</p></td>
</tr>
</tbody>
</table>


您也可以使用 Skype for Business Online 管理中心管理联盟域和公共提供商的联盟设置。

![Lync Online 管理中心 - 组织设置](images/Dn362813.f860d03f-5906-49b0-bcc7-7634afe7005e(OCS.15).png "Lync Online 管理中心 - 组织设置")

## 另请参阅

#### 概念

[Lync Online Cmdlet](the-skype-for-business-online-cmdlets.md)  
[快速参考：使用 Windows PowerShell 执行常见的 Lync Online 管理任务](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

