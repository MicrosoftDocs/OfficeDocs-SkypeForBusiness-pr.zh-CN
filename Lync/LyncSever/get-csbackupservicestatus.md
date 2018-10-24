---
title: Get-CsBackupServiceStatus
TOCTitle: Get-CsBackupServiceStatus
ms:assetid: 7f56cc81-534c-48e8-9f74-5741d4534a83
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205032(v=OCS.15)
ms:contentKeyID: 49313396
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsBackupServiceStatus

 

_**上一次修改主题：** 2015-03-09_

Returns information about the current state of the backup service for a specified pool. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Get-CsBackupServiceStatus -PoolFqdn <Fqdn> [-Category <UserData | CMS>] [-Force <SwitchParameter>]

## Examples

## Example 1

The preceding command returns the backup service status for the pool atl-cs-001.litwareinc.com.

    Get-CsBackupServiceStatus -PoolFqdn "atl-cs-001.litwareinc.com"

## Detailed Description

The **Get-CsBackupServiceStatus** cmdlet enables administrators to verify that the backup service for a specified Registrar pool has been configured and is working properly. Note that, by default, only users who belong to the RTCUniversalServerAdmins group are allowed to run this cmdlet and check the backup status for a pool. To provide additional groups with permission to run the cmdlet, use the **Set-CsBackupServiceConfiguration** cmdlet to add those groups to the AuthorizedUniversalGroups property.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsBackupServiceStatus"}

**Lync Server 控制面板:** The functions carried out by the **Get-CsBackupServiceStatus** cmdlet are not available in the Lync Server 控制面板.

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
<td><p><em>PoolFqdn</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Fully qualified domain name of the pool whose backup service status is being checked. For example:</p>
<p>-PoolFqdn &quot;atl-cs-001.litwareinc.com&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Category</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Hadr.BackupService.BackupCategory</p></td>
<td><p>Type of backup whose status is being checked. Allowed values are:</p>
<p>* CMS</p>
<p>* UserData</p>
<p>If this parameter is not specified then both backup types will be checked.</p></td>
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

None. The **Get-CsBackupServiceStatus** cmdlet does not accept pipelined input.

## Return Types

Returns information about the backup service.

## 另请参阅

#### 其他资源

[Get-CsBackupServiceConfiguration](get-csbackupserviceconfiguration.md)

