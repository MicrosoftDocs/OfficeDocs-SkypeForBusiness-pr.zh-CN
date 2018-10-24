---
title: Get-CsOAuthServer
TOCTitle: Get-CsOAuthServer
ms:assetid: c2a61eb0-cdff-4069-99e4-2bdf42812f47
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205238(v=OCS.15)
ms:contentKeyID: 49314162
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsOAuthServer

 

_**上一次修改主题：** 2015-03-09_

Returns information about the Open Authorization (OAuth) servers configured for use by the organization. OAuth servers, also known as security token servers, issue security tokens used in server-to-server authentication and authorization. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Get-CsOAuthServer [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Get-CsOAuthServer [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>] [-Tenant <Guid>]

## Examples

## Example 1

Example 1 returns information about all the OAuth servers configured for use in the organization.

    Get-CsOAuthServer

## Example 2

In Example 2, information is returned for the OAuth server that has the Identity "Office 365".

    Get-CsOAuthServer -Identity "Office 365"

## Detailed Description

In Lync Server 2013, server-to-server authentication (for example, the authentication that enables Lync Server 2013 and Microsoft Exchange Server 2013 to share information) is carried out using the OAuth security protocol. This type of authentication typically requires three servers: the two servers that need to communicate with one another (Server A and B) and a third-party security token server. If Servers A and B need to communicate with one another, the two servers contact the token server (also known as an OAuth server) and obtain mutually-trusted security tokens that the two servers can exchange in order to prove their identities.

If you are using an on-premises version of Lync Server 2013 and you need to communicate with another server product that fully supports the OAuth protocol (for example, Exchange 2013 or Microsoft SharePoint 2013) then you typically do not need to use a token server; that's because these server products are able to issue their own security tokens. However, if you need to communicate with another server product (including server products found on Office 365) then you will need to use a token servers. These token servers can be managed by using the **CsOAuthServer** cmdlets.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsOAuthServer"}

**Lync Server 控制面板:** The functions carried out by the **Get-CsOAuthServer** cmdlet are not available in the Lync Server 控制面板.

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
<td><p>Enables you to use wildcard characters in order to return one or more OAuth servers. For example, to return all of the OAuth servers that have an Identity that includes the string value &quot;Microsoft&quot; use this syntax:</p>
<p>-Filter &quot;*Microsoft*&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Unique identifier for the OAuth server to be returned. For example:</p>
<p>-Identity &quot;Office 365&quot;</p>
<p>If neither the Identity parameter nor the Filter parameter is included in the command then the <strong>Get-CsOAuthServer</strong> cmdlet will return information about all your OAuth servers.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the OAuth service data from the local replica of the Central Management store rather than from the Central Management store itself.</p></td>
</tr>
<tr class="even">
<td><p><em>Tenant</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Guid</p></td>
<td><p>Globally unique identifier (GUID) of the Skype for Business Online tenant account whose OAuth server settings are to be retrieved.</p>
<p>For example:</p>
<p>–Tenant &quot;38aad667-af54-4397-aaa7-e94c79ec2308&quot;</p>
<p>You can return the tenant ID for each of your tenants by running this command:</p>
<p>Get-CsTenant | Select-Object DisplayName, TenantID</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Get-CsOAuthServer** cmdlet does not accept pipelined input.

## Return Types

The **Get-CsOAuthServer** cmdlet returns instances of the Microsoft.Rtc.Management.WritableConfig.Settings.SSAuth.OAuthServer\#Decorated object.

## 另请参阅

#### 其他资源

[New-CsOAuthServer](new-csoauthserver.md)  
[Remove-CsOAuthServer](remove-csoauthserver.md)  
[Set-CsOAuthServer](set-csoauthserver.md)

