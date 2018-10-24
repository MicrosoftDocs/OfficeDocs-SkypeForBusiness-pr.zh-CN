---
title: Get-CsPresenceProvider
TOCTitle: Get-CsPresenceProvider
ms:assetid: 15f7a7d0-d6d6-491e-a2e3-04fd2d6528d5
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204705(v=OCS.15)
ms:contentKeyID: 49312109
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsPresenceProvider

 

_**上一次修改主题：** 2015-03-09_

Returns information about the presence providers configured for use in the organization. Presence providers represent the PresenceProviders property of a collection of user services configuration settings. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Get-CsPresenceProvider [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsPresenceProvider [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Examples

## Example 1

The command shown in Example 1 returns information about all the presence providers configured for use in your organization.

    Get-CsPresenceProvider

## Example 2

Example 2 returns information about a single presence provider: the provider with the Identity global/fabrikam.com.

    Get-CsPresenceProvider -Identity "global/fabrikam.com"

## Example 3

In Example 3, information is returned for all the presence providers configured at the site scope. To do this, the Filter parameter is used along with the filter value "site:\*". That filter value limits returned data to presence providers that have an Identity that begins with the string value "site:".

    Get-CsPresenceProvider -Filter "site:*"

## Example 4

Example 4 returns all the presence providers that have the string value "fabrikam.com" somewhere in their Fqdn property. To carry out this task, the command first uses the **Get-CsPresenceProvider** cmdlet to return a collection of all the presence providers configured for use in the organization. That collection is then piped to the **Where-Object** cmdlet, which picks out only those providers where the Fqdn property includes (-match) the string value "fabrikam.com".

    Get-CsPresenceProvider | Where-Object {$_.Fqdn -match "fabrikam.com"}

## Detailed Description

The **CsPresenceProvider** cmdlets are used to manage the PresenceProviders property found in the User Services configuration settings. Among other things, these settings are used to maintain presence information, including a collection of authorized presence providers. That collection is stored in the PresenceProviders property. The Get-CsPresenceProvider cmdlet provides a way for you to return information about the presence providers that have been authorized for use in your organization.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsPresenceProvider"}

**Lync Server 控制面板:** The functions carried out by the **Get-CsPresenceProvider** cmdlet are not available in the Lync Server 控制面板.

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
<td><p>Enables you to use wildcards when specifying the Identity of the presence provider (or providers) to be returned. For example, to return all the presence providers configured at the service scope use this filter value:</p>
<p>-Filter &quot;service:*&quot;</p>
<p>You cannot use both the Filter parameter and the Identity parameter in the same command.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier for the presence provider. The Identity of a presence provider is composed of two parts: the scope (Parent) where the provider has been applied (for example, service:UserServer:atl-cs-001.litwareinc.com) and the provider's fully qualified domain name. For example, to retrieve a single presence provider use syntax similar to this:</p>
<p>-Identity &quot;global/fabrikam.com&quot;</p>
<p>To return all the presence providers for a specific parent, simply specify the scope. For example, this syntax returns all the presence providers configured for the global scope:</p>
<p>-Identity &quot;global&quot;</p>
<p>If neither the Identity nor the Filter parameters are included, then the <strong>Get-CsPresenceProvider</strong> cmdlet returns information about all your providers.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the allowed domains from the local replica of the Central Management store rather than from the Central Management store itself.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Get-CsPresenceProvider** cmdlet does not accept pipelined input.

## Return Types

The **Get-CsPresenceProvider** cmdlet returns instances of the Microsoft.Rtc.Management.WritableConfig.Settings.UserServices.PresenceProvider\#Decorated object.

## 另请参阅

#### 其他资源

[Get-CsUserServicesConfiguration](get-csuserservicesconfiguration.md)  
[New-CsPresenceProvider](new-cspresenceprovider.md)  
[Remove-CsPresenceProvider](remove-cspresenceprovider.md)  
[Set-CsPresenceProvider](set-cspresenceprovider.md)

