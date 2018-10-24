---
title: Get-CsClsRegion
TOCTitle: Get-CsClsRegion
ms:assetid: 4f38e966-8e92-4549-8124-097c236c0165
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204879(v=OCS.15)
ms:contentKeyID: 49312814
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsClsRegion

 

_**上一次修改主题：** 2015-03-09_

Returns information about the centralized logging configuration regions in use in the organization. Centralized logging provides a way for administrators to simultaneously enable or disable event tracing on multiple computers. Centralized logging regions are intended for use with Skype for Business Online.

此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Get-CsClsRegion [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsClsRegion [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Examples

## Example 1

The command shown in Example 1 returns information for all the centralized logging regions configured for use in the organization.

    Get-CsClsRegion

## Example 2

In Example 2, information is returned only for the centralized logging region that has the Identity global/US.

    Get-CsClsRegion -Identity "global/US"

## Example 3

Example 3 returns information about all the centralized logging regions configured at the global scope. This is done by calling the **Get-CsClsRegion** cmdlet along with the Filter parameter; the filter value "global/\*" limits the returned data to regions configured at the global scope.

    Get-CsClsRegion -Filter "global/*"

## Example 4

The command shown in Example 4 returns information for all the centralized logging regions that allow access by the Europe region. To carry out this task, the command first uses the **Get-CsClsRegion** cmdlet to return a collection of all the centralized logging regions currently in use. This collection is then piped to the **Where-Object** cmdlet, which selects only those regions where the OtherRegionAccess property includes the string value "Europe".

    Get-CsClsRegion | Where-Object {$_.OtherRegionAccess -match "Europe"}

## Detailed Description

The centralized logging service (which replaces the OCSLogger and OCSTracer tools used in Microsoft Lync Server 2010) provides a way for administrators to manage logging and tracing for all computers and pools running Lync Server 2013. Centralized logging enables administrators to stop, start, and configure logging for one or more pools and computers by using a single command; for example, you can use one command to enable Address Book service logging on all your Address Book servers. This differs from the OCSLogger and OCSTracer tools, which had to be individually managed (including individually stopped and started) on each server. In addition, the centralized logging service also provides a way for administrators to search trace logs from the command, using the Windows PowerShell 命令行接口 and the [Search-CsClsLogging](search-csclslogging.md) cmdlet.

With the Office 365 version of Lync Server, regions are used to determine which users have access to the personally-identifiable information that is written to the log files. Regions are created by using the [New-CsClsRegion](new-csclsregion.md) cmdlet and then are added to a collection of centralized logging configuration settings. You can return information about your centralized logging regions by using the **Get-CsClsRegion** cmdlet.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsClsRegion"}

**Lync Server 控制面板:** The functions carried out by the **Get-CsClsRegion** cmdlet are not available in the Lync Server 控制面板.

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
<td><p>Enables you to use wildcard characters in order to return a centralized logging region (or regions). For example, to return a collection of all the settings configured at the global scope, use this syntax:</p>
<p>-Filter &quot;global/*&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier for the centralized logging region to be returned. A region identity consists of the scope where the region was created followed by the region name. For example, to return a region named US created at the global scope, use the following syntax:</p>
<p>-Identity &quot;global/US&quot;</p>
<p>If this parameter is not specified then the <strong>Get-CsClsRegion</strong> cmdlet returns information about all your centralized logging regions.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the centralized logging configuration data from the local replica of the 中央管理存储, rather than the 中央管理存储 itself.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Get-CsClsRegion** cmdlet does not accept pipelined input.

## Return Types

The **Get-CsClsRegion** cmdlet returns instances of the Microsoft.Rtc.Management.WritableConfig.Settings.CentralizedLogging.Region\#Decorated object.

## 另请参阅

#### 其他资源

[New-CsClsRegion](new-csclsregion.md)  
[Remove-CsClsRegion](remove-csclsregion.md)  
[Set-CsClsRegion](set-csclsregion.md)

