---
title: Move-CsLegacyUser
TOCTitle: Move-CsLegacyUser
ms:assetid: f4b36fc8-17a7-490d-a147-6d77abab0f92
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg413025(v=OCS.15)
ms:contentKeyID: 49314750
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Move-CsLegacyUser

 

_**上一次修改主题：** 2015-03-09_

Migrates one or more user accounts from Microsoft Office Communications Server 2007 R2 to Lync Server 2013. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Move-CsLegacyUser -Identity <UserIdParameter> -Target <Fqdn> [-Confirm [<SwitchParameter>]] [-Credential <PSCredential>] [-DomainController <Fqdn>] [-ExcludeArchivingPolicy <SwitchParameter>] [-ExcludeConferencingPolicy <SwitchParameter>] [-ExcludeDialPlan <SwitchParameter>] [-ExcludeExternalAccessPolicy <SwitchParameter>] [-ExcludePresencePolicy <SwitchParameter>] [-ExcludeVoicePolicy <SwitchParameter>] [-Force <SwitchParameter>] [-HostedMigrationOverrideUrl <String>] [-IgnoreBackendStoreException <SwitchParameter>] [-PassThru <SwitchParameter>] [-ProxyPool <Fqdn>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

In Example 1, the **Move-CsLegacyUser** cmdlet is used to migrate the user account with the Identity Pilar Ackerman to the Registrar pool atl-cs-001.litwareinc. Because no additional parameters are included, any policies or settings previously assigned to this account will be migrated as well. That means that, if a legacy policy (such as a dial plan) was assigned to Pilar Ackerman, she will be assigned the Lync Server 2013 equivalent when her account is moved.

    Move-CsLegacyUser -Identity "Pilar Ackerman" -Target "atl-cs-001.litwareinc.com"

## EXAMPLE 2

The command shown in Example 2 migrates Pilar Ackerman’s user account, but does not migrate any dial plans previously assigned to her account. After the account is migrated, Pilar will not have an assigned dial plan.

    Move-CsLegacyUser -Identity "Pilar Ackerman" -Target "atl-cs-001.litwareinc.com" -ExcludeDialPlan 

## EXAMPLE 3

In Example 3, all the user accounts in the Finance OU are moved to the Registrar pool atl-cs-001.litwareinc.com. To carry out this task, the command first uses the **Get-CsUser** cmdlet and the OU parameter to retrieve a collection of all the user accounts in the Finance OU. After the accounts have been retrieved, the collection is piped to the **Move-CsLegacyUser** cmdlet, which moves each account to the new Registrar pool. This command assumes that all the users in the Finance OU are legacy users.

    Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Move-CsLegacyUser -Target "atl-cs-001.litwareinc.com"

## EXAMPLE 4

In Example 4, Move-CsLegacyUser is used to assign a Registrar pool to all of the users that have enabled for Lync Server but are not currently assigned to a Registrar pool. In this command, the **Get-CsUser** cmdlet is first called, along with the UnassignedUser parameter, to return a collection of all the users not currently assigned to a Registrar pool. This collection is then piped to the **Move-CsLegacyUser** cmdlet, which assigns each user to the pool atl-cs-001.litwareinc.com. This example assumes that all of the unassigned users are legacy users.

    Get-CsUser -UnassignedUser | Move-CsLegacyUser -Target "atl-cs-001.litwareinc.com"

## Detailed Description

Many organizations that install Lync Server 2013 are also running an earlier version of the software. Fortunately, this does not present a problem: you can run both the latest version of the software and an earlier version of the software simultaneously. Over time, you can then begin to migrate your configuration settings, your policies, and, finally, your user accounts to Lync Server 2013.

The **Move-CsLegacyUser** cmdlet not only enables you to migrate users to Lync Server 2013, but also gives you considerable control over the migration process. For example, in its simplest form you can give the **Move-CsLegacyUser** cmdlet the identity of the user to be migrated and the fully qualified domain name (FQDN) of the Lync Server Registrar pool where that user account will be homed; in turn, the **Move-CsLegacyUser** cmdlet will move the user account and will maintain any existing policies and settings that have been applied to the account. For example, suppose Ken Myer was assigned a dial plan in Communications Server 2007 R2. By default, when you migrate Ken’s account the dial plan will be migrated as well: that means that the **Move-CsLegacyUser** cmdlet will automatically assign Ken Myer the Lync Server 2013 equivalent of the dial plan he was previousl assigned.

Of course, that will occur only if you have migrated dial plans and if there is a Lync Server 2013 equivalent of the dial plan that Ken Myer was previously assigned. Alternatively, you might have decided not to migrate dial plans. In that case, you can call the **Move-CsLegacyUser** cmdlet along with the ExcludeDialPlan parameter. When you use this parameter, dial plans are not migrated along with the user account: that means that Ken Myer’s user account will be moved but he will not be assigned a dial plan. (This will be also be the case even if you did migrate dial plans; the ExcludeDialPlan parameter prevents the migrated user account from being assigned a dial plan.) Other parameters allow you to exclude voice policies, conferencing policies, archiving policies, external access policies, and/or presence policies when migrating user accounts.

Before you can run the **Merge-CsLegacyTopology**, cmdlet you must first install the Windows Management Instrumentation (WMI) Backward Compatibility interfaces package; this application is installed by running OCSWMIBC.msi. (OCSWMIBC.msi can be found on the installation DVD in the Setup folder.) After installing the Compatibility interfaces package, the **Merge-CsLegacyUser** cmdlet can then be called in order to move one or more user accounts.

Who can run this cmdlet? By default, members of the following groups are authorized to run the **Move-CsLegacyUser** cmdlet locally: RTCUniversalUserAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself) run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Move-CsLegacyUser"}

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
<td><p>Indicates the Identity of the user account to be migrated. User Identities can be specified using one of four formats: 1) the user's SIP address; 2) the user's user principal name (UPN); 3) the user's domain name and logon name, in the form domain\logon (for example, litwareinc\kenmyer); and, 4) the user's Active Directory Domain Services display name (for example, Ken Myer). User Identities can also be reference by using the user’s Active Directory distinguished name.</p>
<p>You can use the asterisk (*) wildcard character when using the Display Name as the user Identity. For example, the Identity &quot;* Smith&quot; returns all the users with a display name that ends with the string value &quot; Smith&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>Target</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>FQDN of the Registrar pool where the user account should be homed. For example: -Target atl-cs-001.litwareinc.com.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>Credential</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSCredential</p></td>
<td><p>Enables you to run the Move-CsLegacyUser cmdlet under alternate credentials. This might be required if the account you used to log on to Windows does not have the necessary privileges required to work with user objects.</p>
<p>To use the Credential parameter you must first create a PSCredential object using the Get-Credential cmdlet. For details, see the Get-Credential cmdlet Help topic.</p></td>
</tr>
<tr class="odd">
<td><p><em>DomainController</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Enables you to connect to the specified domain controller in order to move a user account. To connect to a particular domain controller, include the DomainController parameter followed by the computer name (for example, atl-cs-001) or its FQDN (for example, atl-cs-001.litwareinc.com).</p></td>
</tr>
<tr class="even">
<td><p><em>ExcludeArchivingPolicy</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When present, any archiving policies assigned to the user account are not retained when the account is migrated.</p></td>
</tr>
<tr class="odd">
<td><p><em>ExcludeConferencingPolicy</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When present, any conferencing policies assigned to the user account are not retained when the account is migrated.</p></td>
</tr>
<tr class="even">
<td><p><em>ExcludeDialPlan</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When present, any dial plans assigned to the user account are not retained when the account is migrated.</p></td>
</tr>
<tr class="odd">
<td><p><em>ExcludeExternalAccessPolicy</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When present, any external access policies assigned to the user account are not retained when the account is migrated.</p></td>
</tr>
<tr class="even">
<td><p><em>ExcludePresencePolicy</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When present, any presence policies assigned to the user account are not retained when the account is migrated.</p></td>
</tr>
<tr class="odd">
<td><p><em>ExcludeVoicePolicy</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When present, any voice policies assigned to the user account are not retained when the account is migrated.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might arise when running the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>HostedMigrationOverrideUrl</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>URL for the hosted migration service used when moving a user to the Office 365 version of Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><em>IgnoreBackendStoreException</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When present, instructs the computer to ignore any errors that might occur with the backend database and attempt to move the user despite those errors.</p></td>
</tr>
<tr class="odd">
<td><p><em>PassThru</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Enables you to pass a user object through the pipeline that represents the user account being moved. By default, the <strong>Move-CsLegacyUser</strong> cmdlet does not pass objects through the pipeline.</p></td>
</tr>
<tr class="even">
<td><p><em>ProxyPool</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>This parameter is used only with Communications Server 2007 R2. It should not be used with an on-premises implementation of Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Move-CsLegacyUser** cmdlet does not accept pipelined input.

## Return Types

The **Move-CsLegacyUser** cmdlet does not return any values or objects. Instead, the cmdlet moves instances of the Microsoft.Rtc.Management.ADConnect.Schema.ADUser object.

## 另请参阅

#### 其他资源

[Import-CsLegacyConfiguration](import-cslegacyconfiguration.md)  
[Import-CsLegacyConferenceDirectory](import-cslegacyconferencedirectory.md)  
[Merge-CsLegacyTopology](merge-cslegacytopology.md)  
[Move-CsUser](move-csuser.md)  
[Set-CsUser](set-csuser.md)

