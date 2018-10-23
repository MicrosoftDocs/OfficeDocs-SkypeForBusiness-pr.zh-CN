---
title: Remove-CsOAuthServer
TOCTitle: Remove-CsOAuthServer
ms:assetid: fac7be48-06bb-4572-86a2-b872fe96d199
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205408(v=OCS.15)
ms:contentKeyID: 49314816
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsOAuthServer

 

_**上一次修改主题：** 2015-03-09_

Removes an existing Open Authorization (OAuth) server. OAuth servers, also known as security token servers, issue security tokens used in server-to-server authentication and authorization. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Remove-CsOAuthServer -Identity <XdsGlobalRelativeIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-Tenant <Guid>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in Example 1 deletes a single OAuth server: the server with the identity "Office 365".

    Remove-CsOAuthServer -Identity "Office365"

## Example 2

Example 2 deletes all the OAuth servers configured for use in the organization. To carry out this task, the command first calls the **Get-CsOAuthServer** cmdlet without any parameters in order to return all the OAuth servers. These servers are then piped to, and removed by, the **Remove-CsOAuthServer** cmdlet.

    Get-CsOAuthServer | Remove-CsOAuthServer

## Detailed Description

In Lync Server 2013, server-to-server authentication (for example, the authentication that enables Lync Server 2013 and Microsoft Exchange Server 2013 to share information) is carried out using the OAuth security protocol. This type of authentication typically requires three servers: the two servers that need to communicate with one another (Server A and B) and a third-party security token server. If Servers A and B need to communicate with one another, the two servers contact the token server (also known as an OAuth server) and obtain mutually-trusted security tokens that the two servers can exchange in order to prove their identities.

If you are using an on-premises version of Lync Server 2013 and you need to communicate with another server product that fully supports the OAuth protocol (for example, Exchange 2013 or Microsoft SharePoint 2013) then you typically do not need to use a token server; that's because these server products are able to issue their own security tokens. However, if you need to communicate with another server product (including server products found on Office 365) then you will need to use a token servers. These token servers can be managed by using the **CsOAuthServer** cmdlets.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsOAuthServer"}

**Lync Server 控制面板:** The functions carried out by the **Remove-CsOAuthServer** cmdlet are not available in the Lync Server 控制面板.

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
<td><p>Unique identifier for the OAuth server to be deleted. For example:</p>
<p>-Identity &quot;Office 365&quot;</p></td>
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
<td><p><em>Tenant</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Guid</p></td>
<td><p>Globally unique identifier (GUID) of the Skype for Business Online tenant account for the OAuth server being deleted. For example:</p>
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

The **Remove-CsOAuthServer** cmdlet accepts pipelined instances of the Microsoft.Rtc.Management.WritableConfig.Settings.SSAuth.OAuthServer\#Decorated object.

## Return Types

None. Instead, the **Remove-CsOAuthServer** cmdlet deletes existing instances of the Microsoft.Rtc.Management.WritableConfig.Settings.SSAuth.OAuthServer\#Decorated object.

## 另请参阅

#### 其他资源

[Get-CsOAuthServer](get-csoauthserver.md)  
[New-CsOAuthServer](new-csoauthserver.md)  
[Set-CsOAuthServer](set-csoauthserver.md)

