---
title: Set-CsBackupServiceConfiguration
TOCTitle: Set-CsBackupServiceConfiguration
ms:assetid: 72ed064e-5f67-481f-802a-74846cecb189
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205006(v=OCS.15)
ms:contentKeyID: 49313235
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsBackupServiceConfiguration

 

_**上一次修改主题：** 2015-03-09_

Retrieves the backup service configuration settings for Lync Server 2013. These settings include information about the maximum number of simultaneous Windows Communication Framework calls that can be made to the backup service as well as the backup service synchronization interval. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Set-CsBackupServiceConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsBackupServiceConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-AuthorizedLocalAccounts <String>] [-AuthorizedUniversalGroups <String>] [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-MaxBatchesPerCmsSync <Int32>] [-MaxBatchesPerUserStoreSync <Int32>] [-MaxConcurrentCalls <Int32>] [-MaxDataConfPackageSizeKB <Int32>] [-SyncInterval <TimeSpan>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in Example 1 assigns the Active Directory security group Schema Admins to the AuthorizedUniversalGroup property for the global collection of backup service settings.

    Set-CsBackupServiceConfiguration -Identity "global" -AuthorizedUniversalGroup "Schema Admins"

## Example 2

In Example 2, the MaxConcurrentCalls property of the global collection of backup service settings is set to 12.

    Set-CsBackupServiceConfiguration -Identity "global" -MaxConcurrentCalls 12

## Example 3

Example 3 modifies the SyncInterval property of the global collection of backup service settings. In this example, SyncInterval is set to 10 minutes: 00 hours : 10 minutes : 00 seconds.

    Set-CsBackupServiceConfiguration -Identity "global" -SyncInterval "00:10:00"

## Detailed Description

The backup service configuration settings are used to manage pool backups in Lync Server 2013. Note that Lync Server allows only for a single, global collection of backup configuration settings. Among other things, that means that all your pools must be backed up using the same synchronization schedule, and that users and groups authorized to backup Pool A are also allowed to backup Pools B, C, D, and E.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsBackupServiceConfiguration"}

**Lync Server 控制面板:** The functions carried out by the **Set-CsBackupServiceConfiguration** cmdlet are not available in the Lync Server 控制面板.

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
<td><p><em>AuthorizedLocalAccounts</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Names of the local users/local groups that are authorized to run the backup service. The default value is Network Service.</p></td>
</tr>
<tr class="even">
<td><p><em>AuthorizedUniversalGroups</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Names of the universal groups authorized to run the backup service. The default value is Schema admins.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command.</p></td>
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
<td><p>Unique identifier for the backup service configuration settings. Because you can only have a single, global instance of these settings, you do not need to specify an Identity when calling the <strong>Set-CsBackupServiceConfiguration</strong> cmdlet. If you prefer, however, you can use the following syntax to reference the global settings:</p>
<p>-Identity global</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSObject</p></td>
<td><p>Allows you to pass a reference to an object to the cmdlet rather than set individual parameter values.</p></td>
</tr>
<tr class="odd">
<td><p><em>MaxBatchesPerCmsSync</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Int32</p></td>
<td><p>Maximum number of batches that the CMS backup module will export during each export cycle. The default value is 500.</p></td>
</tr>
<tr class="even">
<td><p><em>MaxBatchesPerUserStoreSync</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Int32</p></td>
<td><p>Maximum number of batches that the User Store backup module will export during each export cycle. The default value is 500.</p></td>
</tr>
<tr class="odd">
<td><p><em>MaxConcurrentCalls</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Int32</p></td>
<td><p>The maximum number of Windows Communication Foundation (WCF) calls that can be made to the backup service at the same time. The default value is 10.</p></td>
</tr>
<tr class="even">
<td><p><em>MaxDataConfPackageSizeKB</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Int32</p></td>
<td><p>Maximum size of the data package (in kilobytes) that the Data Conference module will export during each export cycle. The default value is 102400.</p></td>
</tr>
<tr class="odd">
<td><p><em>SyncInterval</em></p></td>
<td><p>Optional</p></td>
<td><p>System.TimeSpan</p></td>
<td><p>Specifies the amount of time that the service waits before synchronizing a pool with its backup pool. The default value is 2 minutes (00:02:00, or 00 hours, 02 minutes, 00 seconds). The SyncInterval can be configured to any value between 5 seconds (00:00:05) and 3 hours (03:00:00), inclusive.</p></td>
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

The **Set-CsBackupServiceConfiguration** cmdlet accepts piped instances of the Microsoft.Rtc.Management.WritableConfig.Settings.BackupService.BackupServiceConfiguration object.

## Return Types

None. Instead, the **Set-CsBackupServiceConfiguration** cmdlet modifies existing instances of the Microsoft.Rtc.Management.WritableConfig.Settings.BackupService.BackupServiceConfiguration object.

## 另请参阅

#### 其他资源

[Get-CsBackupServiceConfiguration](get-csbackupserviceconfiguration.md)  
[Remove-CsBackupServiceConfiguration](remove-csbackupserviceconfiguration.md)

