---
title: Set-CsOAuthServer
TOCTitle: Set-CsOAuthServer
ms:assetid: 52825ca3-d287-4e09-9aec-b8b2d7bafc06
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204896(v=OCS.15)
ms:contentKeyID: 49312851
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsOAuthServer

 

_**上一次修改主题：** 2015-03-09_

Modifies an existing Open Authorization (OAuth) server. OAuth servers, also known as security token servers, issue security tokens used in server-to-server authentication and authorization. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Set-CsOAuthServer <COMMON PARAMETERS>

    Set-CsOAuthServer [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: -Identity <XdsGlobalRelativeIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-MetadataUrl <String>] [-Tenant <Guid>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in Example 1 updates the metadata URL for the OAuth Server Office 365.

    Set-CsOAuthServer -Identity "Office 365" -MetadataUrl "https://sts.office365.microsoft.com/metadata/json/1"

## Detailed Description

In Lync Server 2013, server-to-server authentication (for example, the authentication that enables Lync Server 2013 and Microsoft Exchange Server 2013 to share information) is carried out using the OAuth security protocol. This type of authentication typically requires three servers: the two servers that need to communicate with one another (Server A and B) and a third-party security token server. If Servers A and B need to communicate with one another, the two servers contact the token server (also known as an OAuth server) and obtain mutually-trusted security tokens that the two servers can exchange in order to prove their identities.

If you are using an on-premises version of Lync Server 2013 and you need to communicate with another server product that fully supports the OAuth protocol (for example, Exchange 2013 or Microsoft SharePoint 2013) then you typically do not need to use a token server; that's because these server products are able to issue their own security tokens. However, if you need to communicate with another server product (including server products found on Office 365) then you will need to use a token servers. These token servers can be managed by using the CsOAuthServer cmdlets.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsOAuthServer"}

**Lync Server 控制面板:** The functions carried out by the **Set-CsOAuthServer** cmdlet are not available in the Lync Server 控制面板.

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
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Friendly (and unique) name used to identify the OAuth server.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSObject</p></td>
<td><p>Allows you to pass a reference to an object to the cmdlet rather than set individual parameter values.</p></td>
</tr>
<tr class="odd">
<td><p><em>MetadataUrl</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>URL where the WS-FederationMetadata for the server is published. Servers use the metadata to agree on the types of tokens that will be exchanged as well the keys that will be used to sign these tokens.</p></td>
</tr>
<tr class="even">
<td><p><em>Tenant</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Guid</p></td>
<td><p>Globally unique identifier (GUID) of the Skype for Business Online tenant account for the OAuth server being modified. For example:</p>
<p>–Tenant &quot;38aad667-af54-4397-aaa7-e94c79ec2308&quot;</p>
<p>You can return the tenant ID for each of your tenants by running this command:</p>
<p>Get-CsTenant | Select-Object DisplayName, TenantID</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Describes what would happen if you executed the command without actually executing the command.</p></td>
</tr>
</tbody>
</table>


## Input Types

The **Set-CsOAuthServer** cmdlet accepts pipelined instances of the Microsoft.Rtc.Management.WritableConfig.Settings.SSAuth.OAuthServer\#Decorated object.

## Return Types

None. Instead, the **Set-CsOAuthServer** cmdlet modifies existing instances of the Microsoft.Rtc.Management.WritableConfig.Settings.SSAuth.OAuthServer\#Decorated object.

## 另请参阅

#### 其他资源

[Get-CsOAuthServer](get-csoauthserver.md)  
[New-CsOAuthServer](new-csoauthserver.md)  
[Remove-CsOAuthServer](remove-csoauthserver.md)

