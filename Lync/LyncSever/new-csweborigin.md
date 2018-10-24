---
title: New-CsWebOrigin
TOCTitle: New-CsWebOrigin
ms:assetid: 16053a99-b5ff-45e1-be95-b04e3f2fe528
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ950236(v=OCS.15)
ms:contentKeyID: 52060964
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsWebOrigin

 

_**上一次修改主题：** 2015-03-09_

Creates a new domain object that can be added to the collection of domains allowed to send cross-domain scripting requests to the Lync Server 2013 deployment.

This cmdlet was introduced in the Cumulative Updates for Lync Server 2013: February 2013.

## 语法

    New-CsWebOrigin -Url <String>

## Examples

## Example 1

The commands shown in Example 1 add the domain http://fabrikam.com to a new collection of web service configuration settings being created for the Redmond site. To do this, the first command in the example uses the **New-CsWebOrigin** cmdlet to create a domain object for fabrikam.com. The resulting domain object is stored in a variable named $x.

The second command in the example uses the **New-CsWebServiceConfiguration** cmdlet to create the web service configuration settings for the Redmond site. The syntax "–CrossDomainAuthorizationList $x" adds http://fabrikam.com to the collection of domains authorized for cross-domain scripting.

    $x = New-CsWebOrigin -Url "http://fabrikam.com"
    New-CsWebServiceConfiguration -Identity "site:Redmond" - CrossDomainAuthorizationList $x

## Example 2

The commands shown in Example 2 add the domain http://fabrikam.com to an existing collection of web service configuration settings. To carry out this task, the first command in the example uses the **New-CsWebOrigin** cmdlet to create a domain object for fabrikam.com. The resulting domain object is stored in a variable named $x.

The second command in the example uses the **Set-CsWebServiceConfiguration** cmdlet to add http://fabrikam.com to the web service configuration settings applied to the Redmond site. The syntax @{Add=$x} adds the domain to any domains already in the collection of domains authorized for cross-domain scripting. To replace the existing collection with just http://fabrikam.com use the syntax @{Replace=$x}.

    $x = New-CsWebOrigin -Url "http://fabrikam.com"
    Set-CsWebServiceConfiguration -Identity "site:Redmond" - CrossDomainAuthorizationList @{Add=$x}

## Detailed Description

The New-CsWebOrigin cmdlet is used to specify domains that are authorized to host web applications which, in turn, are permitted to send cross-domain scripting requests to your deployment of Lync Server 2013. This cmdlet is primarily used for applications created on top of the Unified Communications Web API.

To add a domain to a collection of web service configuration settings, you must first create a domain object by using the New-CsWebOrigin cmdlet. This domain object, which will exist only in memory, must be stored in a variable. After the object has been created, it can then be added to a collection of web service configuration settings by using either the New-CsWebServiceConfiguration cmdlet or the Set-CsWebServiceConfiguration cmdlet.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsWebOrigin"}

**Lync Server 控制面板:** The functions carried out by the **New-CsWebOrigin** cmdlet are not available in the Lync Server 控制面板.

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
<td><p>URL of the domain authorized to send cross-domain scripting requests. URLs must be prefaced using either the http: or the https: prefix. For example:</p>
<p>-Url &quot;http://contoso.com&quot;</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **New-CsWebOrigin** cmdlet does not accept pipelined input.

## Return Types

The **New-CsWebOrigin** cmdlet creates new instances of the Microsoft.Rtc.Management.WritableConfig.Settings.Web.Origin object.

## 另请参阅

#### 其他资源

[New-CsWebServiceConfiguration](New-CsWebServiceConfiguration.md)  
[Set-CsWebServiceConfiguration](set-cswebserviceconfiguration.md)

