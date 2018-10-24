---
title: Set-CsUserDatabaseState
TOCTitle: Set-CsUserDatabaseState
ms:assetid: c4d8fe5e-ebc1-443b-943d-fc54649e94fd
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412973(v=OCS.15)
ms:contentKeyID: 49314168
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsUserDatabaseState

 

_**上一次修改主题：** 2015-03-09_

Enables or disables one or more Lync Server user databases. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsUserDatabaseState -RegistrarPool <Fqdn> <COMMON PARAMETERS>

    Set-CsUserDatabaseState -Identity <String> <COMMON PARAMETERS>

    COMMON PARAMETERS: -Online <$true | $false> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 takes the user database UserDatabase:atl-sql-001.litwareinc.com offline. This is done by setting the Online property to $False.

    Set-CsUserDatabaseState -Identity "UserDatabase:atl-sql-001.litwareinc.com" -Online $False

## EXAMPLE 2

In Example 2, all the user databases on the Registrar pool atl-cs-001.litwareinc.com are taken offline.

    Set-CsUserDatabaseState -RegistrarPool atl-cs-001.litwareinc.com -Online $False

## EXAMPLE 3

Example 3 locates all the user databases that are currently offline and then brings them back online. To do this, the command first calls the **Get-CsUserDatabaseState** cmdlet without any parameters in order to return a collection of all the user databases in the organization. This collection is then piped to the **Where-Object** cmdlet, which picks out only those databases where the Online property is equal to False. The filtered collection is then piped to the **ForEach-Object** cmdlet, which takes each database in the collection and sets the Online property to True. Note that the collection of offline databases must be piped to the **ForEach-Object** cmdlet rather than the **Set-CsUserDatabaseState** cmdlet. That is because the latter cmdlet cannot directly accept pipelined information.

    Get-CsUserDatabaseState | Where-Object {$_.Online -eq $False} | ForEach-Object {Set-CsUserDatabaseState -Identity $_.Identity -Online $True}

## Detailed Description

Lync Server employs the user database (also known as the user store) to maintain presence and routing information for Lync Server users. The **Set-CsUserDatabaseState** cmdlet provides a way for you change the state of one or more user databases: you can use the cmdlet to take a database offline or to bring a disabled database back online.

Note that, by default, the firewall exceptions for SQL Server Express are not enabled when you install the Standard Edition of Lync Server. In turn, that means that you will not be able to run the **Set-CsUserDatabaseState** cmdlet from a remote instance of Windows PowerShell. That’s because your command will not be able to traverse the firewall and access the SQL Server Express database. You can still run the cmdlet locally (that is, on the Standard Edition server itself). However, to run the **Set-CsUserDatabaseState** cmdlet remotely you will need to manually enable the firewall exceptions for SQL Server Express.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsUserDatabaseState** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself) run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsUserDatabaseState"}

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
<td><p>System.String</p></td>
<td><p>Unique identifier of the user database whose online status is to be modified. For example: -Identity &quot;UserDatabase:atl-sql-001.litwareinc.com&quot;.</p>
<p>You cannot use both Identity and RegistrarPool in the same command, nor can you use wildcards with either parameter.</p></td>
</tr>
<tr class="even">
<td><p><em>Online</em></p></td>
<td><p>Required</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True ($True), makes a database available online. When set to False ($False), takes a database offline.</p></td>
</tr>
<tr class="odd">
<td><p><em>RegistrarPool</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Fully qualified domain name (FQDN) of the Registrar pool hosting the user databases whose online status is to be modified. For example: -RegistrarPool atl-cs-001.litwareinc.com.</p>
<p>You cannot use both –Identity and –RegistrarPool in the same command, nor can you use wildcards with either parameter.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might arise when running the command.</p></td>
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

String. The **Set-CsUserDatabaseState** cmdlet accepts a string value representing the Identity of the user database to be updated.

## Return Types

None. Instead, the **Set-CsUserDatabaseState** cmdlet modifies existing instances of the Microsoft.Rtc.Management.Xds.UserStoreState object.

## 另请参阅

#### 其他资源

[Get-CsUserDatabaseState](get-csuserdatabasestate.md)  
[Update-CsUserDatabase](update-csuserdatabase.md)

