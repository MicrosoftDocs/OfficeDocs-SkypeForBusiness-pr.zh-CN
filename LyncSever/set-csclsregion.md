---
title: Set-CsClsRegion
TOCTitle: Set-CsClsRegion
ms:assetid: 2599cae9-edef-408f-8987-313c67bfe763
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204746(v=OCS.15)
ms:contentKeyID: 49312278
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsClsRegion

 

_**上一次修改主题：** 2015-03-09_

Modifies an existing centralized logging configuration region. Centralized logging provides a way for administrators to simultaneously enable or disable event tracing on multiple computers. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Set-CsClsRegion [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsClsRegion [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-OtherRegionAccess <String>] [-SecurityGroupSuffix <String>] [-Sites <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in Example 1 changes the security group suffix for the region global/US to USSupport.

    Set-CsClsRegion -Identity "global/US" -SecurityGroupSuffix "USSupport"

## Detailed Description

The centralized logging service (which replaces the OCSLogger and OCSTracer tools used in Microsoft Lync Server 2010) provides a way for administrators to manage logging and tracing for all computers and pools running Lync Server 2013. Centralized logging enables administrators to stop, start, and configure logging for one or more pools and computers by using a single command; for example, you can use one command to enable Address Book service logging on all your Address Book servers. This differs from the OCSLogger and OCSTracer tools, which had to be individually managed (including individually stopped and started) on each server. In addition, the centralized logging service also provides a way for administrators to search trace logs from the command, using the Windows PowerShell 命令行接口 and the [Search-CsClsLogging](search-csclslogging.md) cmdlet.

With Skype for Business Online, regions are used to determine which users have access to the personally-identifiable information that is written to the log files. Regions are created by using the [New-CsClsRegion](new-csclsregion.md) cmdlet and then are added to a collection of centralized logging configuration settings. After they have been created, you can modify the properties of these regions by using the **Set-CsClsRegion** cmdlet.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsClsRegion"}

**Lync Server 控制面板:** The functions carried out by the **Set-CsClsRegion** cmdlet are not available in the Lync Server 控制面板.

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
<td><p>Unique identifier for the region. Region Identities consist of the centralized logging configuration scope where the region was created plus a unique region name. For example, to refer to a global region named Redmond use this syntax:</p>
<p>-Identity &quot;global/Redmond&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSObject</p></td>
<td><p>Allows you to pass a reference to an object rather than set individual parameter values.</p></td>
</tr>
<tr class="odd">
<td><p><em>OtherRegionAccess</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Name of an additional region that can be accessed by authorized users for this region.</p></td>
</tr>
<tr class="even">
<td><p><em>SecurityGroupSuffix</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Suffix to be added to the end of the name of any security group that will be authorized for this region.</p></td>
</tr>
<tr class="odd">
<td><p><em>Sites</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Sites contained within this region. These correspond to the SideId attribute values in the topology document.</p></td>
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

The **Set-CsClsRegion** cmdlet accepts pipelined instances of the Microsoft.Rtc.Management.WritableConfig.Settings.CentralizedLogging.Region\#Decorated object.

## Return Types

None. Instead, the **Set-CsClsRegion** cmdlet modifies existing instances of the Microsoft.Rtc.Management.WritableConfig.Settings.CentralizedLogging.Region\#Decorated object.

## 另请参阅

#### 其他资源

[Get-CsClsRegion](get-csclsregion.md)  
[New-CsClsRegion](new-csclsregion.md)  
[Remove-CsClsRegion](remove-csclsregion.md)

