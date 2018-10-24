---
title: Unpublish-CsLisConfiguration
TOCTitle: Unpublish-CsLisConfiguration
ms:assetid: 7fcba482-e1cc-46fa-8b39-fba549eb0fec
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398639(v=OCS.15)
ms:contentKeyID: 49313403
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Unpublish-CsLisConfiguration

 

_**上一次修改主题：** 2015-03-09_

Removes the Location Information Server (LIS) configuration from the 中央管理存储. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Unpublish-CsLisConfiguration [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

This command removes the LIS configuration from the 中央管理存储.

    Unpublish-CsLisConfiguration

## Detailed Description

In order to implement Enhanced 9-1-1 (E9-1-1) in Lync Server, you must create a location mapping (called a wiremap). This mapping includes matching physical addresses to ports, subnets, switches, and wireless access points so emergency calls made over an Enterprise Voice connection will reach the nearest emergency operator and provide that operator with the correct location of the caller. This mapping configuration, created by calling cmdlets such as the **Set-CsLisPort** cmdlet and the **Set-CsLisSubnet** cmdlet, is stored in the location configuration database. A configuration can be committed from the location configuration database to the 中央管理存储 by calling the **Publish-CsLisConfiguration** cmdlet, which allows for replication of the data to the Location Information Server. The **Unpublish-CsLisConfiguration** cmdlet removes the LIS configuration from the 中央管理存储.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Unpublish-CsLisConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Unpublish-CsLisConfiguration"}

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
<td><p>Suppresses any confirmation prompts that would otherwise be displayed before making changes.</p></td>
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

None.

## Return Types

This cmdlet does not return a value.

## 另请参阅

#### 其他资源

[Debug-CsLisConfiguration](debug-cslisconfiguration.md)  
[Publish-CsLisConfiguration](publish-cslisconfiguration.md)  
[Import-CsLisConfiguration](import-cslisconfiguration.md)  
[Export-CsLisConfiguration](export-cslisconfiguration.md)  
[Test-CsLisConfiguration](test-cslisconfiguration.md)

