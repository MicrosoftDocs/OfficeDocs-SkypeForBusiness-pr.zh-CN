---
title: Get-CsSipDomain
TOCTitle: Get-CsSipDomain
ms:assetid: 8a8def42-7b14-40c3-be5a-57905069b405
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398701(v=OCS.15)
ms:contentKeyID: 49313529
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsSipDomain

 

_**上一次修改主题：** 2015-03-09_

Returns information about the SIP domains configured for use in your organization. SIP domains are domains authorized to send and receive SIP traffic, and are used when assigning SIP addresses to users. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsSipDomain [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Get-CsSipDomain [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS:

## Examples

## EXAMPLE 1

In Example 1, the **Get-CsSipDomain** cmdlet is called without any parameters; this returns information about all the SIP domains configured for use in your organization.

    Get-CsSipDomain

## EXAMPLE 2

The command shown in Example 2 returns information for any SIP domain that has the Identity fabrikam.com. Because SIP domain Identities must be unique, this command will never return more than a single item.

    Get-CsSipDomain -Identity fabrikam.com

## EXAMPLE 3

Example 3 uses the **Get-CsSipDomain** cmdlet and the Filter parameter to return information about all the SIP domains that have an Identity that begins with the letter "f". For example: fabrikam.com; fabrikam.org; fabrikam-users.com; and so on.

    Get-CsSipDomain -Filter "f*"

## EXAMPLE 4

The command shown in Example 4 returns information about the default SIP domain. To do this, the **Get-CsSipDomain** cmdlet is first called without any parameters in order to return a collection of all the SIP domains configured for use in your organization. This collection is then piped to the **Where-Object** cmdlet, which selects the one domain where the IsDefault property is equal to True.

    Get-CsSipDomain | Where-Object {$_.IsDefault -eq $True}

## Detailed Description

In order to configure SIP addresses for your users (and thus enable them to use SIP-related software such as Lync 2013), you need two pieces of information: a user ID (for example, Ken.Myer) and a SIP domain (for example, litwareinc.com). The SIP domain used to construct a SIP address must be a domain located within your Active Directory forest that is authorized to send and receive SIP traffic. For example, suppose you have domains named litwareinc.com, fabrikam.com, and contoso.com, but only litwareinc.com has been identified as being a SIP domain. In that case, you cannot use a SIP address like sip:Ken.Myer@fabrikam.com or sip:Ken.Myer@contoso.com, at least not until fabrikam.com and contoso.com have been configured as valid SIP domains. This is something you can do by running the **New-CsSipDomain** cmdlet.

The **Get-CsSipDomain** cmdlet provides a way for you to return information about the SIP domains authorized for use in your organization. The **Get-CsSipDomain** cmdlet also identifies the default SIP domain for your organization; this is the domain that Lync Server will use, by default, if a SIP domain is not specified.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsSipDomain** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsSipDomain"}

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
<td><p><em>Filter</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to use wildcards when specifying the Identities of the SIP domain (or domains) to be returned. For example the filter value &quot;*.org&quot; returns a collection of all the authorized SIP domains that have an Identity that ends with the string value &quot;.org&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Fully qualified domain name (FQDN) of the SIP domain to be returned (for example, fabrikam.com). If neither this parameter nor the Filter parameter is specified, then all the SIP domains authorized for use in your organization are returned.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Get-CsSipDomain** cmdlet does not accept pipelined data.

## Return Types

The **Get-CsSipDomain** cmdlet returns instances of the Microsoft.Rtc.Management.Xds.SipDomain object.

## 另请参阅

#### 其他资源

[New-CsSipDomain](new-cssipdomain.md)  
[Remove-CsSipDomain](remove-cssipdomain.md)  
[Set-CsSipDomain](set-cssipdomain.md)

