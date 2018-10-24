---
title: Export-CsUserData
TOCTitle: Export-CsUserData
ms:assetid: 52c411e1-76da-48b8-b1e3-ddc7c7f86e3d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204897(v=OCS.15)
ms:contentKeyID: 49312852
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Export-CsUserData

 

_**上一次修改主题：** 2015-03-09_

Exports user data in a format that can be imported into Lync Server. The data will be exported as a .ZIP file containing a pair of XML documents. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Export-CsUserData -PoolFqdn <Fqdn> <COMMON PARAMETERS>

    Export-CsUserData -Identity <String> <COMMON PARAMETERS>

    COMMON PARAMETERS: -FileName <String> [-ConfDirectoryFilter <String>] [-DomainController <Fqdn>] [-Force <SwitchParameter>] [-LegacyFormat <SwitchParameter>] [-UserFilter <String>]

## Examples

## Example 1

The command shown in Example 1 exports user data from the pool atl-cs-001.litwareinc.com to a file named C:\\Logs\\ExportedUserData.zip.

    Export-CsUserData -PoolFqdn "atl-cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserData.zip"

## Detailed Description

The **Export-CsUserData** cmdlet provides a way for administrators to export user data and/or conference directory for a Lync Server pool. That data, which can be saved in the user data format used by either Lync Server 2013 or Microsoft Lync Server 2010 can then be imported by using the [Import-CsUserData](import-csuserdata.md) cmdlet.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Export-CsUserData"}

**Lync Server 控制面板:** The functions carried out by the **Export-CsUserData** cmdlet are not available in the Lync Server 控制面板.

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
<td><p>Full path to the .ZIP file that the <strong>Export-CsUserData</strong> cmdlet will create; this file will contain the exported user data. For example:</p>
<p>-FileName &quot;C:\Logs\ExportedData.zip&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Fully qualified domain name of the pool where the User database containing the user data to be exported is installed. For example:</p>
<p>-Identity &quot;atl-sql-001.litwareinc.com&quot;</p>
<p>Note that you can retrieve fully qualified domain names for your User database pools by running this command:</p>
<p>Get-CsService –UserDatabase</p></td>
</tr>
<tr class="odd">
<td><p><em>PoolFqdn</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Fully qualified domain name of the Registrar pool containing the user data to be exported. For example:</p>
<p>-PoolFqdn &quot;atl-cs-001.litwareinc.com&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>ConfDirectoryFilter</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>When specified, allows you to export conference directory information for the specified conference directory. For example, to export data from the conference directory with the ID 13 use this syntax:</p>
<p>-ConfDirectoryFilter 13</p>
<p>You can return conference directory IDs by using this command:</p>
<p>Get-CsConferenceDirectory</p></td>
</tr>
<tr class="odd">
<td><p><em>DomainController</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Enables administrators to specify the FQDN of the domain controller to be used when running the <strong>Export-CsUserData</strong> cmdlet. If not specified, the cmdlet will use the first available domain controller.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>LegacyFormat</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When specified, data is saved in the format used by Microsoft Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p><em>UserFilter</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to export data for a single user. That user is in dictated by specifying his or her SIP address, minus the sip: prefix. For example:</p>
<p>-UserFilter &quot;kenmyer@litwareinc.com&quot;</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Export-CsUserData** cmdlet does not accept pipelined input.

## Return Types

The **Export-CsUserData** cmdlet creates new .ZIP files.

## 另请参阅

#### 其他资源

[Convert-CsUserData](convert-csuserdata.md)  
[Import-CsUserData](import-csuserdata.md)  
[Sync-CsUserData](sync-csuserdata.md)  
[Update-CsUserData](update-csuserdata.md)

