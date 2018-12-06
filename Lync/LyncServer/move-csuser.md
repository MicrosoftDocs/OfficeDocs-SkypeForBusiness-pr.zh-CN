---
title: Move-CsUser
TOCTitle: Move-CsUser
ms:assetid: 6fbdbab6-8a8c-421c-b16c-2319be4b8915
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398528(v=OCS.15)
ms:contentKeyID: 49313200
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Move-CsUser

 

_**上一次修改主题：** 2015-03-09_

Moves one or more user accounts enabled for Lync Server to a new Registrar pool. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Move-CsUser -Identity <UserIdParameter> -Target <Fqdn> [-Confirm [<SwitchParameter>]] [-Credential <PSCredential>] [-DomainController <Fqdn>] [-Force <SwitchParameter>] [-HostedMigrationOverrideUrl <String>] [-IgnoreBackendStoreException <SwitchParameter>] [-MoveConferenceData <SwitchParameter>] [-PassThru <SwitchParameter>] [-ProxyPool <Fqdn>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

In Example 1, the **Move-CsUser** cmdlet is used to move the user account with the Identity Pilar Ackerman to the Registrar pool atl-cs-001.litwareinc.com.

    Move-CsUser -Identity "Pilar Ackerman" -Target "atl-cs-001.litwareinc.com"

## EXAMPLE 2

In Example 2 all the user accounts in the Finance organizational unit (OU) are moved to the Registrar pool atl-cs-001.litwareinc.com. To carry out this task, the command first uses the **Get-CsUser** cmdlet and the OU parameter to retrieve a collection of all the user accounts in the Finance OU. After the data has been retrieved, the information is piped to the **Move-CsUser** cmdlet, which moves each account in the collection to the Registrar pool atl-cs-001.litwareinc.com.

    Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Move-CsUser -Target "atl-cs-001.litwareinc.com"

## EXAMPLE 3

In Example 3, the **Move-CsUser** cmdlet is used to move the user account with the Identity Pilar Ackerman to the Registrar pool atl-cs-001.litwareinc.com. In addition, the Force parameter is used to ensure that only the account itself is moved; user data associated with that account (such conferences that Pilar has scheduled) will not be moved but will, instead, be discarded. The Force parameter should only be used if you have tried calling the **Move-CsUser** cmdlet without the parameter and that move failed.

    Move-CsUser -Identity "Pilar Ackerman" -Target "atl-cs-001.litwareinc.com" -Force

## Detailed Description

The **Move-CsUser** cmdlet enables you to move a user account enabled for Lync Server from one Registrar pool to another. The **Move-CsUser** cmdlet affects only the user’s Lync Server account location; it does not move the user's Active Directory account to a new organizational unit (OU) or other new location.

If Lync Server is coexisting with Office Communications Server 2007 R2 or Office Communications Server 2007, then the **Move-CsUser** cmdlet can used to move a user back from Lync Server to the legacy installation of Office Communications Server. To move a user back to Office Communications Server, assign the fully qualified domain name (FQDN) of the legacy pool to the Target parameter. If you do this, keep in mind that users moved back to Office Communications Server will likely experience functionality and data loss; that’s because Lync Server has many more capabilities than either Office Communications Server 2007 or Office Communications Server 2007 R2. Users moved back might also need to install previous versions of their client software, and may be required to reschedule meetings that were created when their user accounts were homed on Lync Server.

To move users from Communications Server 2007 or Communications Server 2007 R2 to Lync Server, use the **Move-CsLegacyUser** cmdlet. The **Move-CsUser** cmdlet is designed to move users from one Lync Server to another Lync Server pool, or to move a user from a Lync Server pool to an Office Communications Server pool. Move-CsLegacyUser moves users from Office Communications Server to Lync Server.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Move-CsUser** cmdlet locally: RTCUniversalUserAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Move-CsUser"}

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
<td><p>Microsoft.Rtc.Management.AD.UserIdParameter</p></td>
<td><p>Indicates the Identity of the user account to be moved. User Identities can be specified using one of four formats: 1) the user's SIP address; 2) the user's user principal name (UPN); 3) the user's domain name and logon name, in the form domain\logon (for example, litwareinc\kenmyer); and, 4) the user's Active Directory display name (for example, Ken Myer). User Identities can also be referenced by using the user’s Active Directory distinguished name.</p>
<p>You can use the asterisk (*) wildcard character when using the Display Name as the user Identity. For example, the Identity &quot;* Smith&quot; returns all the users with who have a display name that ends with the string value &quot; Smith&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>Target</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>The FQDN (for example, atl-cs-001.litwareinc.com) of the Registrar pool where the user account should be moved. In addition to a Registrar pool, the Target can also be the FQDN of a legacy Office Communications Server 前端服务器 or a hosting provider. Any accounts moved to a hosting provider (for example, Microsoft Lync Online 2010) will lose all their associated user data. For example, any conferences the user has scheduled will be deleted and will not be available in Lync Online 2010.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Enables you to bypass the confirmation prompt that would otherwise appear when you attempt to move a user. To bypass the confirmation prompt, include the Confirm parameter using this syntax:</p>
<p>-Confirm:$False</p>
<p>If you would prefer to have the confirmation prompt then use this syntax:</p>
<p>-Confirm</p></td>
</tr>
<tr class="even">
<td><p><em>Credential</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSCredential</p></td>
<td><p>Enables you to run the Move-CsUser cmdlet under alternate credentials. This might be required if the account you used to log on to Windows does not have the necessary privileges required to work with user objects.</p>
<p>To use the Credential parameter you must first create a PSCredential object using the <strong>Get-Credential</strong> cmdlet. For details, see the <strong>Get-Credential</strong> cmdlet help topic.</p></td>
</tr>
<tr class="odd">
<td><p><em>DomainController</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Enables you to connect to the specified domain controller in order to retrieve contact information. To connect to a particular domain controller, include the DomainController parameter followed by the computer name (for example, atl-cs-001) or its FQDN (for example, atl-cs-001.litwareinc.com).</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>If present, moves the user account but deletes any associated user data (such as conferences that the user has scheduled). If not present, both the account and the associated data are moved.</p></td>
</tr>
<tr class="odd">
<td><p><em>HostedMigrationOverrideUrl</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>URL for the hosted migration service used when moving a user to Skype for Business Online.</p></td>
</tr>
<tr class="even">
<td><p><em>IgnoreBackendStoreException</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When present, instructs the computer to ignore any errors that might occur with the backend database and attempt to move the user despite those errors.</p></td>
</tr>
<tr class="odd">
<td><p><em>MoveConferenceData</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When present, moves meeting and conference data for users being transferred to a different Registrar pool. Note that you should not use the MoveConferenceData parameter if you are moving users as part of a disaster recovery procedure. Instead, you should rely on the backup service for moving conference data as part of a disaster recovery procedure.</p></td>
</tr>
<tr class="even">
<td><p><em>PassThru</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Enables you to pass a user object through the pipeline that represents the user account being moved. By default, the <strong>Move-CsUser</strong> cmdlet does not pass objects through the pipeline.</p></td>
</tr>
<tr class="odd">
<td><p><em>ProxyPool</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>This parameter is used only for Lync Online. It should not be used with an on-premises implementation of Lync Server.</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## Input Types

String or Microsoft.Rtc.Management.ADConnect.Schema.ADUser object. The **Move-CsUser** cmdlet accepts a pipelined string value representing the Identity of a user account that has been enabled for Lync Server. The cmdlet also accepts pipelined instances of the Active Directory user object.

## Return Types

The **Move-CsUser** cmdlet does not return a value or object. Instead, the cmdlet modifies instances of the Microsoft.Rtc.Management.ADConnect.Schema.ADUser object.

## 另请参阅

#### 其他资源

[Get-CsUser](get-csuser.md)  
[Move-CsLegacyUser](move-cslegacyuser.md)

