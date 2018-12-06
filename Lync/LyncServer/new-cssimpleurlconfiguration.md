---
title: New-CsSimpleUrlConfiguration
TOCTitle: New-CsSimpleUrlConfiguration
ms:assetid: 3140f15a-e448-42fe-b494-bf9caba32b35
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425813(v=OCS.15)
ms:contentKeyID: 49312415
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsSimpleUrlConfiguration

 

_**上一次修改主题：** 2015-03-09_

Creates a new simple URL configuration collection. Simple URLs make it easier for users to join meetings and conferences. They also make it easier for Administrators to sign in to the Lync Server 控制面板. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsSimpleUrlConfiguration -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-SimpleUrl <PSListModifier>] [-Tenant <Guid>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 creates a new simple URL collection for the Redmond site. Because no parameters other than Identity are included with this command, the new collection will not contain any simple URLs. This command will fail if the Redmond site already hosts a simple URL collection.

    New-CsSimpleUrlConfiguration -Identity "site:Redmond"

## EXAMPLE 2

Example 2 shows how you can create a new collection of simple URLs that includes two simple URLs (one for meeting management and one for dial-in conferencing). To do this, the first command in the example uses the **New-CsSimpleUrlEntry** cmdlet to create a URL entry that points to https://dialin.litwareinc.com; this URL entry is stored in a variable named $urlEntry. The second command then creates another URL entry, this one pointing to https://meet.fabrikam.com.

Next, the **New-CsSimpleUrl** cmdlet is used to create an in-memory-only instance of a simple URL. In this example, the URL Component is set to dialin; the domain is set to an asterisk (\*); the ActiveUrl is set to https://dialin.fabrikam.com; and the SimpleUrl property is set to $urlEntry. (The variable $urlEntry represents the URL entry created in the first command.) A similar command is then used to create a simple URL for meet.fabrikam.com.

After the URLs have been created (and stored in the object references $simpleUrl and $simpleUrl2) the final command in the example creates a new simple URL collection for the Redmond site, adding the two new in-memory-only URLs to that collection. The new URLs are added to the collection by using the **New-CsSimpleUrlConfiguration** cmdlet, the SimpleUrl parameter, and the parameter value @{Add=$simpleUrl, $simpleUrl2}. That syntax causes the URLs stored in the object references $simpleUrl and $simpleUrl2 to be added to the SimpleUrl property.

    $urlEntry = New-CsSimpleUrlEntry -Url "https://dialin.fabrikam.com"
    $simpleUrl = New-CsSimpleUrl -Component "dialin" -Domain "*" -SimpleUrlEntry $urlEntry -ActiveUrl "https://dialin.fabrikam.com"
    
    $urlEntry2 = New-CsSimpleUrlEntry -Url "https://meet.fabrikam.com"
    $simpleUrl2 = New-CsSimpleUrl -Component "meet" -Domain "fabrikam.com" -SimpleUrlEntry $urlEntry2 
    
    New-CsSimpleUrlConfiguration -Identity "site:Redmond" -SimpleUrl @{Add=$simpleUrl,$simpleUrl2}

## Detailed Description

In Microsoft Office Communications Server 2007 R2, meetings had URLs similar to this:

https://imdf.litwareinc.com/Join?uri=sip%3Akenmyer%40litwareinc.com%3Bgruu%3Bopaque%3Dapp%3Aconf%3Afocus%3Aid%3A125f95a0b0184dcea706f1a0191202a8\&key=EcznhLh5K5t

However, such URLs are not especially intuitive, and not easy to convey to someone else. The simple URLs introduced in Lync Server 2010 help overcome those problems by providing users with URLs that look more like this:

https://meet.litwareinc.com/kenmyer/071200

Simple URLs are an improvement over the URLs used in Office Communications Server. However, simple URLs are not automatically created for you; instead, you must configure the URLs yourself. In addition, you must also do such things as create Domain Name System (DNS) records for each URL; configure reverse proxy rules for external access; add the simple URLs to the your 前端服务器 certificates; and so on.

Lync Server enables you to create three different simple URLs:

Meet – Used for meetings. You must have at least one Meet URL for each of your SIP domains.

Admin – Used to point administrators toward the Lync Server 控制面板.

Dialin – Used for the dial-in conferencing webpage.

Simple URLs are stored in simple URL configuration collections. When you install Lync Server, a global collection is created for you; you can also create custom collections at the site scope. This gives you the ability to use different simple URLs at each of your sites.

Simple URL configuration collections are created by using the **New-CsSimpleUrlConfiguration** cmdlet; you can then use additional cmdlets (such as the **New-CsSimpleUrl** cmdlet and the **Set-CsSimpleUrlConfiguration** cmdlet) to populate these collections with simple URLs. After updating a simple URL collection you must then run the **Enable-CsComputer** cmdlet.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsSimpleUrlConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsSimpleUrlConfiguration"}

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
<td><p>Unique identifier for the new simple URL configuration collection. Because new collections can only be created at the site scope, the Identity must be the prefix &quot;site:&quot; followed by the name of the site. For example, this syntax creates a new collection for the Redmond site: -Identity &quot;site:Redmond&quot;.</p></td>
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
<td><p><em>InMemory</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>创建对象引用，但并不作为永久性更改实际提交对象。如果将使用此参数调用的 cmdlet 的输出分配给一个变量，您可以更改对象引用的属性，然后通过调用与此 cmdlet 匹配的 Set- cmdlet 提交这些更改。</p></td>
</tr>
<tr class="odd">
<td><p><em>SimpleUrl</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>Simple URLs that have been configured for this collection. These URLs must be created by using the <strong>New-SimpleUrl</strong> cmdlet and the <strong>New-SimpleUrlEntry</strong> cmdlet.</p></td>
</tr>
<tr class="even">
<td><p><em>Tenant</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Guid</p></td>
<td><p>Globally unique identifier (GUID) of the Skype for Business Online tenant account for which the new Simple URL configuration settings are being created. For example:</p>
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

None.

## Return Types

The **New-CsSimpleUrlConfiguration** cmdlet creates new instances of the Microsoft.Rtc.Management.WritableConfig.Settings.SimpleUrl.SimpleUrlConfiguration object.

## 另请参阅

#### 其他资源

[Get-CsSimpleUrlConfiguration](get-cssimpleurlconfiguration.md)  
[New-CsSimpleUrl](new-cssimpleurl.md)  
[New-CsSimpleUrlEntry](new-cssimpleurlentry.md)  
[Remove-CsSimpleUrlConfiguration](remove-cssimpleurlconfiguration.md)  
[Set-CsSimpleUrlConfiguration](set-cssimpleurlconfiguration.md)

