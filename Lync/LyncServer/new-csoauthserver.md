---
title: New-CsOAuthServer
TOCTitle: New-CsOAuthServer
ms:assetid: b9d10216-a743-4e62-9cf0-6d5fb55dd64e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205206(v=OCS.15)
ms:contentKeyID: 49314065
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsOAuthServer

 

_**上一次修改主题：** 2015-03-09_

Creates a new Open Authorization (OAuth) server for use by the organization. OAuth servers, also known as security token servers, issue security tokens used in server-to-server authentication and authorization. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    New-CsOAuthServer -MetadataUrl <String> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-Identity <XdsGlobalRelativeIdentity>] [-InMemory <SwitchParameter>] [-Realm <String>] [-Tenant <Guid>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

Example 1 creates a new OAuth Server named "Office 365". The new server uses the metadata URL https://sts.office365.microsoft.com/metadata/json/1.

    New-CsOAuthServer -Identity "Office 365" -MetadataUrl "https://sts.office365.microsoft.com/metadata/json/1"

## Detailed Description

In Lync Server 2013, server-to-server authentication (for example, the authentication that enables Lync Server 2013 and Microsoft Exchange Server 2013 to share information) is carried out using the OAuth security protocol. This type of authentication typically requires three servers: the two servers that need to communicate with one another (Server A and B) and a third-party security token server. If Servers A and B need to communicate with one another, the two servers contact the token server (also known as an OAuth server) and obtain mutually-trusted security tokens that the two servers can exchange in order to prove their identities.

If you are using an on-premises version of Lync Server 2013 and you need to communicate with another server product that fully supports the OAuth protocol (for example, Exchange 2013 or Microsoft SharePoint 2013) then you typically do not need to use a token server; that's because these server products are able to issue their own security tokens. However, if you need to communicate with another server product (including server products found on Office 365) then you will need to use a token servers. These token servers can be managed by using the **CsOAuthServer** cmdlets.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsOAuthServer"}

**Lync Server 控制面板:** The functions carried out by the New-CsOAuthServer cmdlet are not available in the Lync Server 控制面板.

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
<td><p><em>MetadataUrl</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>URL where the WS-FederationMetadata for the server is published. Servers use the metadata to agree on the types of tokens that will be exchanged as well the keys that will be used to sign these tokens. Note that the specified URL must be available when you run the <strong>New-CsOAuthServer</strong> cmdlet or else the command will fail.</p></td>
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
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Friendly (and unique) name used to identify the OAuth server.</p></td>
</tr>
<tr class="odd">
<td><p><em>InMemory</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Creates an object reference without actually committing the object as a permanent change. If you assign the output of this cmdlet called with this parameter to a variable, you can make changes to the properties of the object reference and then commit those changes by calling this cmdlet’s matching Set- cmdlet.</p></td>
</tr>
<tr class="even">
<td><p><em>Realm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Server-to-server security container. By default, Lync Server 2013 uses your default SIP domain as its OAuth realm.</p></td>
</tr>
<tr class="odd">
<td><p><em>Tenant</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Guid</p></td>
<td><p>Globally unique identifier (GUID) of the Skype for Business Online tenant account for which the new OAuth server is being created. For example:</p>
<p>–Tenant &quot;38aad667-af54-4397-aaa7-e94c79ec2308&quot;</p>
<p>You can return the tenant ID for each of your tenants by running this command:</p>
<p>Get-CsTenant | Select-Object DisplayName, TenantID</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Describes what would happen if you executed the command without actually executing the command.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **New-CsOAuthServer** cmdlet does not accept pipelined input.

## Return Types

The **New-CsOAuthServer** cmdlet creates new instances of the Microsoft.Rtc.Management.WritableConfig.Settings.SSAuth.OAuthServer\#Decorated object.

## 另请参阅

#### 其他资源

[Get-CsOAuthServer](get-csoauthserver.md)  
[Remove-CsOAuthServer](remove-csoauthserver.md)  
[Set-CsOAuthServer](set-csoauthserver.md)

