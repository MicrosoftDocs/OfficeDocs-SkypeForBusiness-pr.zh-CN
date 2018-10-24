---
title: Import-CsLegacyConferenceDirectory
TOCTitle: Import-CsLegacyConferenceDirectory
ms:assetid: 5ecb9bf9-cbce-48a6-966c-ecbdac59cb3a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398418(v=OCS.15)
ms:contentKeyID: 49312990
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Import-CsLegacyConferenceDirectory

 

_**上一次修改主题：** 2015-03-09_

The **Import-CsLegacyConferenceDirectory** cmdlet enables you to import conference directories from Microsoft Office Communications Server 2007 R2 to Lync Server. This helps provide interoperability between Lync Server and Office Communications Server 2007 R2. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Import-CsLegacyConferenceDirectory [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-Report <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 imports conferencing directories from Communications Server 2007 R2 to Lync Server.

    Import-CsLegacyConferenceDirectory

## Detailed Description

The **Import-CsLegacyConferenceDirectory** cmdlet is used in conjunction with the **Merge-CsLegacyTopology** cmdlet to enable organizations to migrate from Office Communications Server 2007 R2 to Lync Server. The **Import-CsLegacyConfiguration** cmdlet imports conferencing directories from Communications Server 2007 R2 to Lync Server.

Before you can run the **Import-CsLegacyConferenceDirectory** cmdlet, you must first install the Windows Management Instrumentation (WMI) Backward Compatibility interfaces package; this application is installed by running OCSWMIBC.msi. (OCSWMIBC.msi can be found on the Lync Server installation DVD in the Setup folder.) After installing the Backward Compatibility interfaces package, you should next run the **Merge-CsLegacyTopology** cmdlet.

When the **Merge-CsLegacyTopology** cmdlet finishes running, you can call the **Import-CsLegacyConferenceDirectory** cmdlet. The **Import-CsLegacyConferenceDirectory** cmdlet first uses WMI to read legacy data from Communications Server 2007 R2, then takes the retrieved data and creates corresponding objects in Lync Server: for each conferencing directory found in your installation of Communications Server 2007 R2, a corresponding directory will be created in your new installation of Lync Server.

The **Import-CsLegacyConferenceDirectory** cmdlet should be rerun anytime conferences directories are added, deleted, or moved in the Communications Server 2007 R2 environment. The **Import-CsLegacyConferenceDirectory** cmdlet should also be run anytime the **Merge-CsLegacyTopology** cmdlet is run; this helps to ensure the conference directories and the topology remain in sync.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Import-CsLegacyConferenceDirectory** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Import-CsLegacyConferenceDirectory"}

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
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>Report</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to specify a file path for the log file created when the cmdlet runs. For example: -Report &quot;C:\Logs\ImportDirectories.html&quot;</p></td>
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

None. The **Import-CsLegacyConferenceDirectory** cmdlet does not accept pipelined input.

## Return Types

The **Import-CsLegacyConferenceDirectory** cmdlet does not return any objects or values.

## 另请参阅

#### 其他资源

[Import-CsLegacyConfiguration](import-cslegacyconfiguration.md)  
[Merge-CsLegacyTopology](merge-cslegacytopology.md)  
[Move-CsLegacyUser](move-cslegacyuser.md)

