---
title: Remove-CsBackupServiceConfiguration
TOCTitle: Remove-CsBackupServiceConfiguration
ms:assetid: 56bbf0a2-20cf-4f1e-b305-3521659eb909
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204903(v=OCS.15)
ms:contentKeyID: 49312898
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsBackupServiceConfiguration

 

_**上一次修改主题：** 2015-03-09_

Resets the properties in the backup service configuration settings for Lync Server 2013 to their default values. These settings include information about the maximum number of simultaneous Windows Communication Framework calls that can be made to the backup service as well as the backup service synchronization interval. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Remove-CsBackupServiceConfiguration -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

Example 1 resets the backup service configuration settings for Lync Server 2013. Note that even though Lync Server 2013 only uses a single, global collection of backup settings you must still include the Identity parameter: if you do not, the **Remove-CsBackupServiceConfiguration** cmdlet will prompt you for the Identity before continuing.

    Remove-CsBackupServiceConfiguration -Identity "global"

## Detailed Description

The backup service configuration settings are used to manage pool backups in Lync Server 2013. Note that Lync Server allows only for a single, global collection of backup configuration settings. Among other things, that means that all your pools must be backed up using the same synchronization schedule, and that users and groups authorized to backup Pool A are also allowed to backup Pools B, C, D, and E.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsBackupServiceConfiguration"}

**Lync Server 控制面板:** The functions carried out by the **Remove-CsBackupServiceConfiguration** cmdlet are not available in the Lync Server 控制面板.

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
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique Identity of the backup service configuration settings. Although you can only have a single, global instance of these settings, you still need to specify an Identity when calling the <strong>Remove-CsBackupServiceConfiguration</strong> cmdlet:</p>
<p>-Identity global</p></td>
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
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Describes what would happen if you executed the command without actually executing the command.</p></td>
</tr>
</tbody>
</table>


## Input Types

The **Remove-CsBackupServiceConfiguration** cmdlet accepts pipelined instances of the Microsoft.Rtc.Management.WritableConfig.Settings.BackupService.BackupServiceConfiguration object.

## Return Types

None. Instead, the **Remove-CsBackupServiceConfiguration** cmdlet deletes instances of the Microsoft.Rtc.Management.WritableConfig.Settings.BackupService.BackupServiceConfiguration object.

## 另请参阅

#### 其他资源

[Get-CsBackupServiceConfiguration](get-csbackupserviceconfiguration.md)  
[Set-CsBackupServiceConfiguration](set-csbackupserviceconfiguration.md)

