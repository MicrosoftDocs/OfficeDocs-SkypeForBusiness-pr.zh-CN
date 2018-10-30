---
title: Get-CsBackupServiceConfiguration
TOCTitle: Get-CsBackupServiceConfiguration
ms:assetid: 8e81a76c-4019-490d-9cd5-895cc2cc0863
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205087(v=OCS.15)
ms:contentKeyID: 49313554
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsBackupServiceConfiguration

 

_**上一次修改主题：** 2015-03-09_

Retrieves the backup service configuration settings for Lync Server 2013. These settings include information about the maximum number of simultaneous Windows Communication Framework calls that can be made to the backup service, as well as the backup service synchronization interval. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Get-CsBackupServiceConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsBackupServiceConfiguration [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Examples

## Example 1

The command shown in Example 1 retrieves the backup service configuration information for Lync Server 2013. Because there is only a single, global set of backup service configuration settings you do not need to include the Identity parameter when running this command.

    Get-CsBackupServiceConfiguration

## Detailed Description

The backup service configuration settings are used to manage pool backups in Lync Server 2013. Note that Lync Server allows only for a single, global collection of backup configuration settings. Among other things, that means that all your pools must be backed up using the same synchronization schedule, and that users and groups authorized to backup Pool A are also allowed to backup Pools B, C, D, and E.

Get-CsBackupServiceConfiguration can be run from any computer running a Lync Server 2013 server role or from a remote instance of Windows PowerShell.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsBackupServiceConfiguration"}

**Lync Server 控制面板:** The functions carried out by the **Get-CsBackupServiceConfiguration** cmdlet are not available in the Lync Server 控制面板.

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
<td><p><em>Filter</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to use wildcard values when referencing a collection of backup service configuration settings. Because you can only have a single, global instance of these settings there is no reason to use the Filter parameter. However, if you prefer you can use the following syntax to reference the global settings:</p>
<p>-Filter &quot;g*&quot;</p>
<p>The preceding syntax returns all the conference backup service configuration settings that have an Identity that begins with the letter &quot;g&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique Identity of the backup service configuration settings. Because you can only have a single, global instance of these settings, you do not need to specify an Identity when calling the <strong>Get-CsBackupServiceConfiguration</strong> cmdlet. You can, however, use the following syntax to reference the global settings:</p>
<p>-Identity global</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the backup service configuration data from the local replica of the Central Management store rather than from the Central Management store itself.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Get-CsBackupServiceConfiguration** cmdlet does not accept pipelined input.

## Return Types

The **Get-CsBackupServiceConfiguration** cmdlet returns instances of the Microsoft.Rtc.Management.WritableConfig.Settings.BackupService.BackupServiceConfiguration object.

## 另请参阅

#### 其他资源

[Remove-CsBackupServiceConfiguration](remove-csbackupserviceconfiguration.md)  
[Set-CsBackupServiceConfiguration](set-csbackupserviceconfiguration.md)

