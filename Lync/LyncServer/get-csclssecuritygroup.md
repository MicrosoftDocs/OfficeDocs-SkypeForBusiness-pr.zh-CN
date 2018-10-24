---
title: Get-CsClsSecurityGroup
TOCTitle: Get-CsClsSecurityGroup
ms:assetid: ce7aa87a-2355-4025-bba8-d4debf2137d2
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205285(v=OCS.15)
ms:contentKeyID: 49314283
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsClsSecurityGroup

 

_**上一次修改主题：** 2015-03-09_

Returns information about the centralized logging configuration security groups in use in the organization. Centralized logging provides a way for administrators to simultaneously enable or disable event tracing on multiple computers. Security groups are intended for use with Skype for Business Online.

此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Get-CsClsSecurityGroup [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsClsSecurityGroup [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Examples

## Example 1

The command shown in Example 1 returns information about all the centralized logging security groups configured for use in the organization.

    Get-CsClsSecurityGroup

## Example 2

In Example 2, information is returned for a single centralized logging security group: the group with the Identity global/helpdesk.

    Get-CsClsSecurityGroup -Identity "global/HelpDesk"

## Example 3

Example 3 returns information for all the centralized logging security groups configured at the global scope. To do this, the Filter parameter is included along with the filter value "global/\*"; that filter value limits the returned data to groups configured at the global scope.

    Get-CsClsSecurityGroup -Filter "global/*"

## Example 4

The command shown in Example 4 returns all the centralized logging security groups where the access level has been set to RedmondSupport. To carry out this task, the command first calls the **Get-CsClsSecurityGroup** cmdlet without any parameters; that returns a collection of all the available centralized logging security groups. That collection is then piped to the **Where-Object** cmdlet, which picks out only those groups where the AccessLevel property is equal to RedmondSupport.

    Get-CsClsSecurityGroup | Where-Object {$_.AccessLevel -eq "RedmondSupport"}

## Detailed Description

The centralized logging service (which replaces the OCSLogger and OCSTracer tools used in Microsoft Lync Server 2010) provides a way for administrators to manage logging and tracing for all computers and pools running Lync Server 2013. Centralized logging enables administrators to stop, start, and configure logging for one or more pools and computers by using a single command; for example, you can use one command to enable Address Book service logging on all your Address Book servers. This differs from the OCSLogger and OCSTracer tools, which had to be individually managed (including individually stopped and started) on each server. In addition, the centralized logging service also provides a way for administrators to search trace logs from the command, using Windows PowerShell 命令行接口 and the [Search-CsClsLogging](search-csclslogging.md) cmdlet.

With Skype for Business Online, security groups are used to determine which users have access to the personally-identifiable information that is written to the log files. Security groups are created by using the [New-CsClsSecurityGroup](new-csclssecuritygroup.md) cmdlet and then are added to a collection of centralized logging configuration settings. You can return information about your centralized logging security groups by using the **Get-CsClsSecurityGroup** cmdlet.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsClsSecurityGroup"}

**Lync Server 控制面板:** The functions carried out by the **Get-CsClsSecurityGroup** cmdlet are not available in the Lync Server 控制面板.

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
<td><p>Enables you to use wildcard characters in order to return a centralized logging security group (or groups). For example, to return a collection of all the groups configured at the global scope, use this syntax:</p>
<p>-Filter &quot;global/*&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier for the centralized logging security group to be returned. A security group identity consists of the scope where the group was created followed by the group name. For example, to return a group named HelpDesk created at the global scope, use the following syntax:</p>
<p>-Identity &quot;global/HelpDesk&quot;</p>
<p>If this parameter is not specified then the <strong>Get-CsClsSecurityGroup</strong> cmdlet returns information about all your centralized logging security groups.</p></td>
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

None. The **Get-CsClsSecurityGroup** cmdlet does not accept pipelined input.

## Return Types

The **Get-CsClsSecurityGroup** cmdlet returns instances of the Microsoft.Rtc.Management.WritableConfig.Settings.CentralizedLogging.SecurityGroup\#Decorated object.

## 另请参阅

#### 其他资源

[New-CsClsSecurityGroup](new-csclssecuritygroup.md)  
[Remove-CsClsSecurityGroup](remove-csclssecuritygroup.md)  
[Set-CsClsSecurityGroup](set-csclssecuritygroup.md)

