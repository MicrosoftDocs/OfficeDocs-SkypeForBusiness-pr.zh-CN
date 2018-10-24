---
title: New-CsSimpleUrlEntry
TOCTitle: New-CsSimpleUrlEntry
ms:assetid: 3d9dbebf-d23f-40da-9676-19e7906decda
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425902(v=OCS.15)
ms:contentKeyID: 49312586
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsSimpleUrlEntry

 

_**上一次修改主题：** 2015-03-09_

Creates a new simple URL entry, an element needed when creating a simple URL. Simple URLs make it easier for users to join meetings and conferences, and also make it easier for Administrators to log on to the Lync Server 控制面板. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsSimpleUrlEntry -Url <String>

## Examples

## EXAMPLE 1

Example 1 shows how a new URL can be added to an existing collection of simple URLs. To begin with, the first command in the example uses the **New-CsSimpleUrlEntry** cmdlet to create a URL entry that points to https://meet.fabrikam.com; this URL entry is stored in a variable named $urlEntry.

In the second command, the **New-CsSimpleUrl** cmdlet is used to create an in-memory-only instance of a simple URL. In this example, the URL Component is set to Meet; the domain is set to fabrikam.com; the ActiveUrl is set to https://meet.fabrikam.com; and the SimpleUrl property is set to $urlEntry, with $urlEntry being the URL entry created in the first command.

After the URL has been created (and stored in the object reference $simpleUrl) the final command in the example adds the new URL to the simple URL collection for the Redmond site. This is done by using the **Set-CsSimpleUrlConfiguration** cmdlet, the SimpleUrl parameter and the parameter value @{Add=$simpleUrl}. This syntax causes the URL stored in the object reference $simpleUrl to be added to the SimpleUrl property.

    $urlEntry = New-CsSimpleUrlEntry -Url "https://meet.fabrikam.com"
    $simpleUrl = New-CsSimpleUrl -Component "meet" -Domain "fabrikam.com" -SimpleUrlEntry $urlEntry -ActiveUrl "https://meet.fabrikam.com"
    
    Set-CsSimpleUrlConfiguration -Identity "site:Redmond" -SimpleUrl @{Add=$simpleUrl}

## EXAMPLE 2

In Example 2, a pair of URL entries is added to an existing collection of simple URLs. To do this, the first command in the example uses the **New-CsSimpleUrlEntry** cmdlet to create a URL entry that points to https://meet.fabrikam.com; this URL entry is stored in a variable named $urlEntry. The second command then creates a second URL entry, this one stored in the variable $urlEntry2 and pointing to the URL https:// dialin.fabrikam.com.

After the two URL entries have been created, the **New-CsSimpleUrl** cmdlet is used to create two in-memory-only instances of a simple URL. In the first instance, the URL Component is set to Meet; the domain is set to fabrikam.com; and the ActiveUrl is set to https://meet.fabrikam.com. In the second instance, the component is set to Dialin; the domain to an asterisk (\*); and the ActiveURL property is set to https://dialin.fabrikam.com.

After the URLs have been created (and stored in the object references $simpleUrl and $simpleUrl2), the final command in the example adds the new URL to the simple URL collection for the Redmond site. This is done by using the **Set-CsSimpleUrlConfiguration** cmdlet, the SimpleUrl parameter, and the parameter value @{Add=$simpleUrl, $simpleUrl2}. This syntax causes the URLs stored in the object references $simpleUrl and $simpleUrl2 to be added to the SimpleUrl property.

    $urlEntry = New-CsSimpleUrlEntry -Url "https://meet.fabrikam.com"
    $urlEntry2 = New-CsSimpleUrlEntry -Url "https://dialin.fabrikam.com"
    
    $simpleUrl = New-CsSimpleUrl -Component "meet" -Domain "fabrikam.com" -SimpleUrlEntry $urlEntry -ActiveUrl "https://meet.fabrikam.com"
    $simpleUrl2 = New-CsSimpleUrl -Component "dialin" -Domain "*" -SimpleUrlEntry $urlEntry -ActiveUrl "https://dialin.fabrikam.com"
    
    Set-CsSimpleUrlConfiguration -Identity "site:Redmond" -SimpleUrl @{Add=$simpleUrl, $simpleUrl2}

## Detailed Description

In Microsoft Office Communications Server 2007 R2, meetings had URLs similar to this:

https://imdf.litwareinc.com/Join?uri=sip%3Akenmyer%40litwareinc.com%3Bgruu%3Bopaque%3Dapp%3Aconf%3Afocus%3Aid%3A125f95a0b0184dcea706f1a0191202a8\&key=EcznhLh5K5t

However, such URLs are not especially intuitive, and not easy to convey to someone else. The simple URLs introduced in Lync Server 2010 help overcome those problems by providing users with URLs that look more like this:

https://meet.litwareinc.com/kenmyer/071200

Simple URLs are obviously an improvement over the URLs used in Office Communications Server. However, simple URLs are not automatically created for you; instead, you must configure the URLs yourself. In addition, you must also do such things as create Domain Name System (DNS) records for each URL; configure reverse proxy rules for external access; add the simple URLs to the your 前端服务器 certificates; and so on.

Lync Server enables you to create three different simple URLs:

Meet – Used for meetings. You must have at least one Meet URL for each of your SIP domains.

Admin – Used to point administrators toward the Lync Server 控制面板.

Dialin – Used for the dial-in conferencing webpage.

Simple URLs are stored in simple URL configuration collections. When you install Lync Server, a global collection is created for you; you can also create custom collections at the site scope. This gives you the ability to use different simple URLs at each of your sites.

To add an actual URL to a simple URL collection, you must first create the URL by using the **New-CsSimpleUrl** cmdlet and the **New-CsSimpleUrlEntry** cmdlet. The **New-CsSimpleUrlEntry** cmdlet creates a URL entry; this is nothing more than a URL (such as https://meet.litwareinc.com) that can be used as a simple URL (for meeting, administration, or dial-in conferencing purposes). The object created by the **New-CsSimpleUrlEntry** cmdlet is then added to the SimpleUrlEntry property of a new simple URL. You must use a separate cmdlet to create the object; that’s because the SimpleUrlEntry property can hold multiple URLs. (However, only one such URL can be designated as the active URL. The active URL represents the actual URL used for meetings, administration, or dial-in conferencing.)

After creating a simple URL entry, you then use the **New-CsSimpleUrl** cmdlet to create an in-memory-only instance of a simple URL, defining such things as the component (the type of simple URL); the domain; the active URL; and all of the simple URL entries. After you have created an object representing the simple URL, that object can then be added to a new or existing simple URL collection. After updating a simple URL collection, you must then run the **Enable-CsComputer** cmdlet.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsSimpleUrlEntry** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsSimpleUrlEntry"}

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
<td><p><em>Url</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>URL to be added to the SimpleUrlEntry property of a simple URL. For example: -Url &quot;https://meet.litwareinc.com&quot;. URLs must start with the &quot;https:&quot; prefix.</p></td>
</tr>
</tbody>
</table>


## Input Types

None.

## Return Types

The **New-CsSimpleUrlEntry** cmdlet creates new instances of the Microsoft.Rtc.Management.WritableConfig.SimpleUtl.SimpleUrlEntry object.

## 另请参阅

#### 其他资源

[New-CsSimpleUrl](new-cssimpleurl.md)  
[New-CsSimpleUrlConfiguration](new-cssimpleurlconfiguration.md)

