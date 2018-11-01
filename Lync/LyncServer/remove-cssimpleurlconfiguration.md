﻿---
title: Remove-CsSimpleUrlConfiguration
TOCTitle: Remove-CsSimpleUrlConfiguration
ms:assetid: 6cf483ed-7a53-47b0-b87a-6ef70493ba32
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398515(v=OCS.15)
ms:contentKeyID: 49313169
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsSimpleUrlConfiguration

 

_**上一次修改主题：** 2015-03-09_

Removes one or more of the simple URL configuration collections currently in use in your organization. Simple URLs make it easier for users to join meetings and conferences, as well as making it easier for Administrators to log on to the Lync Server 控制面板. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsSimpleUrlConfiguration -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-Tenant <Guid>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 deletes the simple URL configuration collection applied to the Redmond site. This command deletes all the simple URLs assigned to the specified site.

    Remove-CsSimpleUrlConfiguration -Identity "site:Redmond"

## EXAMPLE 2

In Example 2, all the simple URL configuration collections applied at the site scope are deleted. To do this, the command first uses the **Get-CsSimpleUrlConfiguration** cmdlet and the Filter parameter to return all the simple URL collections configured at the site scope; the filter value "site:\*" limits the returned data to those collections that have an Identity that begins with the string value "site:". The filtered collection is then piped to the **Remove-CsSimpleUrlConfiguration** cmdlet, which deletes each item in that collection.

    Get-CsSimpleUrlConfiguration -Filter "site:*" | Remove-CsSimpleUrlConfiguration 

## Detailed Description

In Microsoft Office Communications Server 2007 R2, meetings had URLs similar to this:

https://imdf.litwareinc.com/Join?uri=sip%3Akenmyer%40litwareinc.com%3Bgruu%3Bopaque%3Dapp%3Aconf%3Afocus%3Aid%3A125f95a0b0184dcea706f1a0191202a8\&key=EcznhLh5K5t

However, such URLs are not especially intuitive, and not easy to convey to someone else. The simple URLs introduced in Lync Server 2010 help overcome those problems by providing users with URLs that look more like this:

https://meet.litwareinc.com/kenmyer/071200

Simple URLs are an improvement over the URLs used in Office Communications Server. However, simple URLs are not automatically created for you; instead, you must configure the URLs yourself. In addition, you must also do such things as create Domain Name System (DNS) records for each URL; configure reverse proxy rules for external access; add the simple URLs to the your 前端服务器 certificates; and so on.

Lync Server enables you to create three different simple URLs:

Meet – Used for meetings. You must have at least one Meet URL for each of your SIP domains.

Admin – Used to point administrators to the Lync Server.

Dialin – Used for the dial-in conferencing webpage.

Simple URLs are stored in simple URL configuration collections. When you install Lync Server, a global collection is created for you; you can also create custom collections at the site scope. This gives you the ability to use different simple URLs at each of your sites.

Simple URL configuration collections are created by using the **New-CsSimpleUrlConfiguration** cmdlet; you can then use additional cmdlets (such as the **New-CsSimpleUrlEntry** cmdlet and the **Set-CsSimpleUrlConfiguration** cmdlet) to populate these collections with simple URLs. If you later decide to delete one or more of the site-scoped collections, you can do so by using the **Remove-CsSimpleUrlConfiguration** cmdlet.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Remove-CsSimpleUrlConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsSimpleUrlConfiguration"}

## 参数


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Parameter</th>
<th>Required</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier for the collection of simple URLs to be removed. To remove a collection from the site scope, use syntax similar to this: -Identity &quot;site:Redmond.&quot; Note that you cannot use wildcards when specifying an Identity.</p>
<p>You can also run this cmdlet against the global collection by using this syntax: -Identity global. In that case, however, the global collection will not be deleted. Instead, all the Simple URLs within that collection will be deleted.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>Tenant</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Guid</p></td>
<td><p>Globally unique identifier (GUID) of the Skype for Business Online tenant account for the Simple URL configuration settings being deleted. For example:</p>
<p>–Tenant &quot;38aad667-af54-4397-aaa7-e94c79ec2308&quot;</p>
<p>You can return the tenant ID for each of your tenants by running this command:</p>
<p>Get-CsTenant | Select-Object DisplayName, TenantID</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## Input Types

Microsoft.Rtc.Management.WritableConfig.Settings.SimpleUrl.SimpleUrlConfiguration object. The **Remove-CsSimpleUrlConfiguration** cmdlet accepts pipelined instances of the simple URL configuration object.

## Return Types

None.

## 另请参阅

#### 其他资源

[Get-CsSimpleUrlConfiguration](get-cssimpleurlconfiguration.md)  
[New-CsSimpleUrlConfiguration](new-cssimpleurlconfiguration.md)  
[Set-CsSimpleUrlConfiguration](set-cssimpleurlconfiguration.md)

