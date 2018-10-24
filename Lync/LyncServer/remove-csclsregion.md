---
title: Remove-CsClsRegion
TOCTitle: Remove-CsClsRegion
ms:assetid: 6ab1596e-0e27-44e7-8cbc-efd4064ba58b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204971(v=OCS.15)
ms:contentKeyID: 49313138
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsClsRegion

 

_**上一次修改主题：** 2015-03-09_

Removes one or more centralized logging configuration regions. Centralized logging provides a way for administrators to simultaneously enable or disable event tracing on multiple computers. Centralized logging regions are intended for use with Skype for Business Online.

此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Remove-CsClsRegion -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in Example 1 removes the centralized logging region that has the Identity global/US.

    Remove-CsClsRegion -Identity "global/US"

## Example 2

In Example 2, all the centralized logging regions configured at the global scope are removed. To do this, the command first calls the **Get-CsClsRegion** cmdlet along with the Filter parameter; the filter value "global/\*" limits the returned data to regions configured at the global scope. These regions are then piped to, and deleted by, the **Remove-CsClsRegion** cmdlet.

    Get-CsClsRegion -Filter "global/*" | Remove-CsClsRegion 

## Example 3

Example 3 deletes all the centralized logging regions that have the security group suffix EMEA. To carry out this task, the command first calls the **Get-CsClsRegion** cmdlet without any parameters; this returns a collection of all the centralized logging regions configured for use in the organization. This collection is then piped to the Where-Object cmdlet, which picks out only those regions where the SecurityGroupSuffix property is equal to (-eq) EMEA. That subcollection of regions is then piped to the **Remove-CsClsRegion** cmdlet, which deletes each region in the subcollection.

    Get-CsClsRegion | Where-Object {$_.SecurityGroupSuffix -eq "EMEA" | Remove-CsClsRegion

## Detailed Description

The centralized logging service (which replaces the OCSLogger and OCSTracer tools used in Microsoft Lync Server 2010) provides a way for administrators to manage logging and tracing for all computers and pools running Skype for Business Online. Centralized logging enables administrators to stop, start, and configure logging for one or more pools and computers by using a single command; for example, you can use one command to enable Address Book service logging on all your Address Book servers. This differs from the OCSLogger and OCSTracer tools, which had to be individually managed (including individually stopped and started) on each server. In addition, the centralized logging service also provides a way for administrators to search trace logs from the command, using the Windows PowerShell 命令行接口 and the [Search-CsClsLogging](search-csclslogging.md) cmdlet.

With Skype for Business Online, regions are used to determine which users have access to the personally-identifiable information that is written to the log files. Regions are created by using the [New-CsClsRegion](new-csclsregion.md) cmdlet and then are added to a collection of centralized logging configuration settings. Regions added to one of these collections can later be removed by using the **Remove-CsClsRegion** cmdlet.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsClsRegion"}

**Lync Server 控制面板:** The functions carried out by the **Remove-CsClsRegion** cmdlet are not available in the Lync Server 控制面板.

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
<td><p>Unique identifier for the centralized logging region to be removed. A region identity consists of the scope where the region was created followed by the region name. For example, to delete a region named US created at the global scope, use the following syntax:</p>
<p>-Identity &quot;global/US&quot;</p></td>
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

The **Remove-CsClsRegion** cmdlet accepts pipelined instances of the Microsoft.Rtc.Management.WritableConfig.Settings.CentralizedLogging.Region\#Decorated object.

## Return Types

None. Instead, the **Remove-CsClsRegion** cmdlet deletes existing instances of the Microsoft.Rtc.Management.WritableConfig.Settings.CentralizedLogging.Region\#Decorated object.

## 另请参阅

#### 其他资源

[Get-CsClsRegion](get-csclsregion.md)  
[New-CsClsRegion](new-csclsregion.md)  
[Set-CsClsRegion](set-csclsregion.md)

