---
title: Import-CsUserData
TOCTitle: Import-CsUserData
ms:assetid: f39ef951-ee5b-4200-b6fb-68a4d4d6e86f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205373(v=OCS.15)
ms:contentKeyID: 49314724
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Import-CsUserData

 

_**上一次修改主题：** 2015-03-09_

Imports user data previously exported by using the Export-CsUserData cmdlet. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Import-CsUserData -PoolFqdn <Fqdn> <COMMON PARAMETERS>

    Import-CsUserData -Identity <String> <COMMON PARAMETERS>

    COMMON PARAMETERS: -FileName <String> [-ConfDirectoryFilter <String>] [-DomainController <Fqdn>] [-Force <SwitchParameter>] [-LegacyFormat <SwitchParameter>] [-RoutingGroupFilter <String>] [-UserFilter <String>]

## Examples

## Example 1

The command shown in Example 1 imports user data from a file named C:\\Logs\\ExportedUserData.zip to the pool atl-cs-001.litwareinc.com.

    Import-CsUserData -PoolFqdn "atl-cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserData.zip"

## Detailed Description

The Import-CsUserData cmdlet is used to import previously-saved user data and/or conference directory data to Lync Server. Note that this data must have been exported by using the [Export-CsUserData](export-csuserdata.md) cmdlet.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Import-CsUserData"}

**Lync Server 控制面板:** The functions carried out by the **Import-CsUserData** cmdlet are not available in the Lync Server 控制面板.

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
<td><p><em>FileName</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Full path to the input file containing the exported user data. For example:</p>
<p>-InputFile &quot;C:\Data\ExportedUsers.xml&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Service Identity of the user database where the data should be imported. For example:</p>
<p>-Identity &quot;UserDatabase:atl-sql-001.litwareinc.com&quot;</p>
<p>You cannot use both the Identity and the PoolFqdn parameters in the same command.</p></td>
</tr>
<tr class="odd">
<td><p><em>PoolFqdn</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Fully qualified domain name of the Registrar pool for the user data being imported. For example:</p>
<p>–PoolFqdn &quot;atl-cs-001.litwareinc.com&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>ConfDirectoryFilter</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>When specified, allows you to import conference directory information for the specified conference directory. For example, to import data from the conference directory with the ID 13 use this syntax:</p>
<p>-ConfDirectoryFilter 13</p>
<p>You can return conference directory IDs by using this command:</p>
<p>Get-CsConferenceDirectory</p></td>
</tr>
<tr class="odd">
<td><p><em>DomainController</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Enables administrators to specify the FQDN of the domain controller to be used when running the <strong>Import-CsUserData</strong> cmdlet. If not specified, the cmdlet will use the first available domain controller.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might arise when running the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>LegacyFormat</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Indicates that the data to be imported was exported from a previous version of Lync Server or Office Communications Server.</p></td>
</tr>
<tr class="even">
<td><p><em>RoutingGroupFilter</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to limit the imported data to users who belong to the same routing group. Routing groups are used by Lync Server to determine the Front End server that users register with.</p></td>
</tr>
<tr class="odd">
<td><p><em>UserFilter</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to import user data for a single user. To convert data for a specified user (and only for that user), set the UserFilter parameter to the SIP address of that user, being sure to omit the sip: prefix. For example:</p>
<p>-UserFilter &quot;kenmyer@litwareinc.com&quot;</p>
<p>This parameter allows you to import data one user at a time.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Import-CsUserData** cmdlet does not accept pipelined input.

## Return Types

None.

## 另请参阅

#### 其他资源

[Convert-CsUserData](convert-csuserdata.md)  
[Export-CsUserData](export-csuserdata.md)  
[Sync-CsUserData](sync-csuserdata.md)  
[Update-CsUserData](update-csuserdata.md)

