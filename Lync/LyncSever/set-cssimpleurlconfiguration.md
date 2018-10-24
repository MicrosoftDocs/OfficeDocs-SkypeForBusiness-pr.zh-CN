---
title: Set-CsSimpleUrlConfiguration
TOCTitle: Set-CsSimpleUrlConfiguration
ms:assetid: f0334ae9-e6c1-4134-8749-af202169bb2a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412991(v=OCS.15)
ms:contentKeyID: 49314679
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsSimpleUrlConfiguration

 

_**上一次修改主题：** 2015-03-09_

Modifies an existing simple URL configuration collection. Simple URLs make it easier for users to join meetings and conferences, as well as making it easier for Administrators to log on to the Lync Server 控制面板. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsSimpleUrlConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsSimpleUrlConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-SimpleUrl <PSListModifier>] [-Tenant <Guid>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 removes all the simple URLs from the Redmond site, but does not remove the actual collection of simple URLs. (The collection will still exist, but will no longer contain any URLs.) To do this, the command uses the SimpleUrl parameter and sets the parameter value to null ($Null). This removes all the simple URLs from the collection.

    Set-CsSimpleUrlConfiguration -Identity "site:Redmond" -SimpleUrl $Null

## EXAMPLE 2

Example 2 shows how a new URL can be added to an existing collection of simple URLs. To begin with, the first command in the example uses the **New-CsSimpleUrlEntry** cmdlet to create a URL entry that points to https://meet.fabrikam.com; this URL entry is stored in a variable named $urlEntry.

In the second command, the **New-CsSimpleUrl** cmdlet is used to create an in-memory-only instance of a simple URL. In this example, the URL Component is set to Meet; the domain is set to fabrikam.com; the ActiveUrl is set to https://meet.fabrikam.com; and the SimpleUrl property is set to $urlEntry, with $urlEntry being the URL entry created in the first command.

After the URL has been created (and stored in the object reference $simpleUrl) the final command in the example adds the new URL to the simple URL collection for the Redmond site. This is done by using the **Set-CsSimpleUrlConfiguration** cmdlet, the SimpleUrl parameter, and the parameter value @{Add=$simpleUrl}. This syntax causes the URL stored in the object reference $simpleUrl to be added to the SimpleUrl property.

    $urlEntry = New-CsSimpleUrlEntry -Url "https://meet.fabrikam.com"
    $simpleUrl = New-CsSimpleUrl -Component "meet" -Domain "fabrikam.com" -SimpleUrlEntry $urlEntry -ActiveUrl "https://meet.fabrikam.com"
    
    Set-CsSimpleUrlConfiguration -Identity "site:Redmond" -SimpleUrl @{Add=$simpleUrl}

## EXAMPLE 3

The commands shown in Example 3 demonstrate how you can delete a single URL from a simple URL collection. Because the **Set-CsSimpleUrlConfiguration** cmdlet needs to work with URL objects, the example starts by creating a new object that contains the exact same property values as the URL to be deleted. To do that, the first command uses the **New-CsSimpleUrlEntry** cmdlet to create a URL entry that points to https://meet.fabrikam.com; this URL entry is stored in a variable named $urlEntry.

After the URL entry has been created, the second command uses the **New-CsSimpleUrl** cmdlet to create an in-memory instance of a simple URL. In this example, the URL Component is set to Meet; the domain is set to fabrikam.com; the ActiveUrl is set to https://meet.fabrikam.com; and the SimpleUrl property is set to $urlEntry, $urlEntry being the URL entry created in the first command. This creates an in-memory URL ($simpleUrl) that has the same property values as the URL to be deleted.

The final command in the example then deletes the URL from the simple URL collection for the Redmond site. This is done by using the **Set-CsSimpleUrlConfiguration** cmdlet, the SimpleUrl parameter, and the parameter value @{Remove=$simpleUrl}. This syntax simply causes the URL stored in the object reference $simpleUrl to be removed from the SimpleUrl property.

    $urlEntry = New-CsSimpleUrlEntry -Url "https://fabrikam.vdomain.com"
    $simpleUrl = New-CsSimpleUrl -Component "meet" -Domain "fabrikam.com" -SimpleUrlEntry $urlEntry -ActiveUrl "https://meet.fabrikam.com"
    
    Set-CsSimpleUrlConfiguration -Identity "site:Redmond" -SimpleUrl @{Remove=$simpleUrl}

## Detailed Description

In Microsoft Office Communications Server 2007 R2, meetings had URLs similar to this:

https://imdf.litwareinc.com/Join?uri=sip%3Akenmyer%40litwareinc.com%3Bgruu%3Bopaque%3Dapp%3Aconf%3Afocus%3Aid%3A125f95a0b0184dcea706f1a0191202a8\&key=EcznhLh5K5t

However, such URLs are not especially intuitive, and not easy to convey to someone else. The simple URLs introduced in Lync Server help overcome those problems by providing users with URLs that look more like this:

https://meet.litwareinc.com/kenmyer/071200

Simple URLs are an improvement over the URLs used in the previous version of Office Communications Server. However, simple URLs are not automatically created for you; instead, you must configure the URLs yourself. In addition, you must also do such things as create Domain Name System (DNS) records for each URL; configure reverse proxy rules for external access; add the simple URLs to the your 前端服务器 certificates; and so on.

Lync Server enables you to create three different simple URLs:

Meet – Used for meetings. You must have at least one Meet URL for each of your SIP domains.

Admin – Used to point administrators to the Lync Server.

Dialin – Used for the dial-in conferencing webpage.

Simple URLs are stored in simple URL configuration collections. When you install Lync Server, a global collection is created for you; you can also create custom collections at the site scope. This gives you the ability to use different simple URLs at each of your sites.

Simple URL configuration collections are created by using the **New-CsSimpleUrlConfiguration** cmdlet; you can then use additional cmdlets (such as **New-CsSimpleUrl** cmdlet and the **Set-CsSimpleUrlConfiguration** cmdlet) to populate these collections with simple URLs. After the collections have been created, the **Set-CsSimpleUrlConfiguration** cmdlet also gives you the ability to modify the URLs stored in those collections.

Adding a simple URL to a collection is reasonably straightforward. To begin with, you use the **New-CsSimpleUrl** cmdlet and the **New-CsSimpleUrlEntry** cmdlet to create an in-memory-only URL. You then use the Add command to add the new URL to the existing collection. Alternatively, you can use the Replace method to replace all the existing URLs with the new one.

Removing a URL from a collection is a little more difficult because you must first create a new object reference to that URL (one that mimics the existing URL), and then use that object reference and the Remove method to delete the URL.

After updating a simple URL collection, you must then run the **Enable-CsComputer** cmdlet.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsSimpleUrlConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsSimpleUrlConfiguration"}

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
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier for the collection of simple URLs to be modified. To modify the global collection, use this syntax: -Identity global. To modify a collection from the site scope, use syntax similar to this: -Identity &quot;site:Redmond.&quot;</p>
<p>If this parameter is not specified then the global collection will be modified.</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>SimpleUrlConfiguration object</p></td>
<td><p>允许您将对对象的引用传递到 cmdlet，而不是设置单个参数值。</p></td>
</tr>
<tr class="odd">
<td><p><em>SimpleUrl</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>Simple URLs configured for this collection. These URLs must be created by using the <strong>New-SimpleUrl</strong> cmdlet and the <strong>New-SimpleUrlEntry</strong> cmdlet.</p></td>
</tr>
<tr class="even">
<td><p><em>Tenant</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Guid</p></td>
<td><p>Globally unique identifier (GUID) of the Skype for Business Online tenant account whose Simple URL configuration settings are to be modified. For example:</p>
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

Microsoft.Rtc.Management.WritableConfig.Settings.SimpleUrl.SimpleUrlConfiguration object. The **Set-CsSimpleUrlConfiguration** cmdlet accepts pipelined instances of the simple URL configuration object.

## Return Types

None.

## 另请参阅

#### 其他资源

[Get-CsSimpleUrlConfiguration](get-cssimpleurlconfiguration.md)  
[New-CsSimpleUrl](new-cssimpleurl.md)  
[New-CsSimpleUrlConfiguration](new-cssimpleurlconfiguration.md)  
[New-CsSimpleUrlEntry](new-cssimpleurlentry.md)  
[Remove-CsSimpleUrlConfiguration](remove-cssimpleurlconfiguration.md)

