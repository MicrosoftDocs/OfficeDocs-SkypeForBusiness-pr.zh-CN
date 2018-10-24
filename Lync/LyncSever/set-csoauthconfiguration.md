---
title: Set-CsOAuthConfiguration
TOCTitle: Set-CsOAuthConfiguration
ms:assetid: 43193254-acb1-47c8-8e21-143b610c2edc
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204841(v=OCS.15)
ms:contentKeyID: 49312676
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsOAuthConfiguration

 

_**上一次修改主题：** 2015-03-09_

Modifies the Open Authorization (OAuth) configuration settings currently in use in the organization. OAuth is a standard protocol used for server-to-server authentication and authorization. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Set-CsOAuthConfiguration [-ExchangeAutodiscoverAllowedDomains <String>] [-ExchangeAutodiscoverUrl <String>] [-Identity <XdsIdentity>] [-Realm <String>] [-ServiceName <String>] <COMMON PARAMETERS>

    Set-CsOAuthConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-Tenant <Guid>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in Example 1 modifies the global collection of OAuth configuration settings. In this example, the Realm property is set to "contoso.com".

    Set-CsOAuthConfiguration -Identity global -Realm "contoso.com"

## Detailed Description

In Lync Server 2013, server-to-server authentication (for example, the authentication that enables Lync Server and Microsoft Exchange Server 2013 to share information) is carried out using the OAuth security protocol. OAuth is always on in Lync Server 2013; there is no need (or even any way) to enable or disable the protocol. However, if Lync Server needs to communicate with other server products (such as Exchange 2013 or Microsoft SharePoint 2013) you might need to modify your OAuth configuration settings; for example, you might need to specify the autodiscover URL for the Office 365 version of Exchange, and you might need to specify your Realm name. These settings can only be managed by using the **CsOAuthConfiguration** cmdlets; options for managing OAuth settings are not available in the Lync Server 2013 控制面板.

Note that, for the on-premises version of Lync Server 2013, you can have only a single, global collection of OAuth settings: you cannot not create additional collections of OAuth settings nor can you delete the global collection. Each Skype for Business Online tenant is also limited to a single collection of OAuth configuration settings.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsOAuthConfiguration"}

**Lync Server 控制面板:** The functions carried out by the **Set-CsOAuthConfiguration** cmdlet are not available in the Lync Server 控制面板.

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
<td><p>Prompts you for confirmation before executing the command.</p></td>
</tr>
<tr class="even">
<td><p><em>ExchangeAutodiscoverAllowedDomains</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Collection of domains that autodiscover requests can be redirected to. For example:</p>
<p>-ExchangeAutodiscoverAllowedDomains &quot;*.contoso.com&quot;,&quot;*.fabrikam.com&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>ExchangeAutodiscoverUrl</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>URL for the autodiscovery service used by the Office 365 version of Microsoft Exchange Server.</p></td>
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
<td><p>Unique Identity of the OAuth configuration settings. Because you can only have a single, global instance of these settings, you do not need to specify an Identity when calling the <strong>Set-CsOAuthConfiguration</strong> cmdlet. You can, however, use the following syntax to reference the global settings:</p>
<p>-Identity global</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSObject</p></td>
<td><p>Allows you to pass a reference to an object to the cmdlet rather than set individual parameter values.</p></td>
</tr>
<tr class="odd">
<td><p><em>Realm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Server-to-server security container. By default, Lync Server 2013 uses your default SIP domain as its OAuth realm.</p></td>
</tr>
<tr class="even">
<td><p><em>ServiceName</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Globally unique identifier (GUID) assigned to the OAuth service.</p></td>
</tr>
<tr class="odd">
<td><p><em>Tenant</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Guid</p></td>
<td><p>Globally unique identifier (GUID) of the Skype for Business Online tenant account for which the OAuth configuration settings are being modified. For example:</p>
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

The **Set-CsOAuthConfiguration** cmdlet accepts pipelined instances of the Microsoft.Rtc.Management.WritableConfig.Settings.SSAuth.OAuthSettings object.

## Return Types

None. Instead, the **Set-CsOAuthConfiguration** cmdlet modifies existing instances of the Microsoft.Rtc.Management.WritableConfig.Settings.SSAuth.OAuthSettings object.

## 另请参阅

#### 其他资源

[Get-CsOAuthConfiguration](get-csoauthconfiguration.md)

