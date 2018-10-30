---
title: Debug-CsIntraPoolReplication
TOCTitle: Debug-CsIntraPoolReplication
ms:assetid: 9882f703-07c7-46fe-b525-7efd1326503c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205103(v=OCS.15)
ms:contentKeyID: 49313683
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Debug-CsIntraPoolReplication

 

_**上一次修改主题：** 2015-03-09_

Verifies the synchronous replication of a pool by comparing the data stored for a specified user on a primary Front End server with data for that same user stored on replica Front End servers. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Debug-CsIntraPoolReplication -UserUri <UserIdParameter> <COMMON PARAMETERS>

    Debug-CsIntraPoolReplication -ConferenceDirectory <XdsGlobalRelativeIdentity> <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Force <SwitchParameter>]

## Examples

## Example 1

The command shown in Example 1 verifies replication on a Front End server by using the user with the SIP address "sip:kenmyer@litwareinc.com".

    Debug-CsIntraPoolReplication -UserUri "sip:kenmyer@litwareinc.com"

## Example 2

In Example 2, replication is verified by using all the users who have user accounts in the Redmond OU. To do this, the command first calls Get-CsUser along with the OU parameter; the parameter value "OU=Redmond,dc=litwareinc,dc=com" limits the returned data to user accounts found in the Redmond OU. Those accounts are then piped to the ForEach-Object cmdlet which, in turn, uses Debug-CsIntraPoolReplication cmdlet to verify the replication status of each account in the OU.

    Get-CsUser -OU "OU=Redmond,dc=litwareinc,dc=com" | ForEach-Object {Debug-CsIntraPoolReplication $_.Identity}

## Example 3

The command shown in Example 3 verifies replication status by using a pair of user SIP addresses. To perform this task, the two SIP addresses (enclosed in quotation marks and separated by using a comma) are piped to the ForEach-Object cmdlet, which then runs the Debug-CsIntraPoolReplication cmdlet against each SIP address..

    "sip:kenmyer@litwareinc.com","sip:pilar@litwareinc.com" | ForEach-Object {Debug-CsIntraPoolReplication -UserUri $_}

## Example 4

In Example 4, replication is verified for the conference directory with the ID 13.

    Debug-CsIntraPoolReplication -ConferenceDirectory 13

## Example 5

Example 5 shows how you can verify replication for all the users homed on a specified Registrar pool. To do this, the command first calls Get-CsUser along with the Filter parameter; the filter value {RegistrarPool –eq "atl-cs-001.litwareinc.com"} limits the returned data to user accounts homed on the Registrar pool atl-cs-001.litwareinc.com. Those accounts are then piped to the Debug-CsIntraPoolReplication cmdlet, which verifies replication for each user in the pool.

    Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Debug-CsIntraPoolReplication UserUri {$_.Identity}

## Detailed Description

The Debug-CsIntraPoolReplication cmdlet provides a way for administrators to verify that replication is taking place between a primary Front End server and its replica Front End servers. This can be done in one of two ways: 1) by verifying that the data for a specified user is identical on the Front End server and all its replica servers; or, 2) by verifying that the data for a conference directory is identical on the Front End server and all its replica servers. To perform either of these two tasks, Debug-CsIntraPoolReplication first connects to the primary Front End server and constructs an XML file containing user or conference directory data. The cmdlet then connects to the replica servers, constructs similar XML files, then verifies that selected content in the XML files is identical.

The Debug-CsIntraPoolReplication cmdlet verifies replication for a pool by taking one or more user accounts (or one conference directory) and querying a primary Front End server and all its replica Front End servers for data about that account (or conference directory). The information retrieved from the primary Front End server and the replica servers is then compared: if the data matches, then it is assumed that intrapool replication is working as expected.

Note that this cmdlet can only be called using users or conference directories homed on Lync Server 2013.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Debug-CsIntraPoolReplication"}

**Lync Server 控制面板:** The functions carried out by the Debug-CsIntraPoolReplication cmdlet are not available in the Lync Server 控制面板.

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
<td><p><em>ConferenceDirectory</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Enables you to verify the replication of a conference directory. Conference directories should be specified using the directory Identity; conference directory Identities can be retrieved by using this command:</p>
<p>Get-CsConferenceDirectory | Select-Object Identity, ServiceId</p>
<p>You cannot use the ConferenceDirectory parameter and the UserUri parameter in the same command.</p></td>
</tr>
<tr class="even">
<td><p><em>UserUri</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.AD.UserIdParameter</p></td>
<td><p>SIP address of the user account employed in testing intra-pool replication. For example:</p>
<p>-UserUri &quot;sip:kenmyer@litwareinc.com&quot;</p>
<p>You cannot use the ConferenceDirectory parameter and the UserUri parameter in the same command.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
</tbody>
</table>


## Input Types

String or Microsoft.Rtc.Management.ADConnect.Schema.ADUser object. Debug-CsIntraPoolReplication accepts a pipelined string value representing the SIP address or Active Directory display name of a user account that has been enabled for Lync Server. The cmdlet also accepts pipelined instances of the Active Directory user object for a Lync Server-enabled user.

## Return Types

Debug-CsIntraPoolReplication returns instances of the Microsoft.Rtc.Management.UserPinservice.Data.syncReplicationDetails object.

## 另请参阅

#### 其他资源

[Get-CsManagementStoreReplicationStatus](get-csmanagementstorereplicationstatus.md)  
[Test-CsReplica](test-csreplica.md)

