---
title: Remove-CsClsScenario
TOCTitle: Remove-CsClsScenario
ms:assetid: 747bd4d6-797e-4088-9303-6ceb65f66183
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205010(v=OCS.15)
ms:contentKeyID: 49313261
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsClsScenario

 

_**上一次修改主题：** 2015-03-09_

Removes the specified centralized logging configuration scenario. A scenario represents a particular Lync Server 2013 component or situation (such as IM and presence) that administrators can enable or disable for tracing. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Remove-CsClsScenario -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in Example 1 removes the WAC scenario from the global collection of centralized logging configuration settings.

    Remove-CsClsScenario -Identity "site:Redmond/WAC"

## Example 2

In Example 2, the HybridVoice scenario is removed from all the centralized logging configuration settings in use in the organization. To do this, the **Get-CsClsScenario** cmdlet is first called without any parameters in order to return a collection of all the available scenarios. That collection is then piped to the Where-Object cmdlet, which picks out all the scenarios where the Name property is equal to (-eq) HybridVoice. The HybridVoice scenarios are then piped to, and deleted by, the **Remove-CsClsScenario** cmdlet.

    Get-CsClsScenario | Where-Object {$_.Name -eq "HybridVoice" | Remove-CsClsScenario

## Detailed Description

The centralized logging service (which replaces the OCSLogger and OCSTracer tools used in Microsoft Lync Server 2010) provides a way for administrators to manage logging and tracing for all computers and pools running Lync Server 2013. Centralized logging enables administrators to stop, start, and configure logging for one or more pools and computers by using a single command; for example, you can use one command to enable Address Book service logging on all your Address Book servers. This differs from the OCSLogger and OCSTracer tools, which had to be individually managed (including individually stopped and started) on each server. In addition, the centralized logging service also provides a way for administrators to search trace logs from the command, using the Windows PowerShell 命令行接口 and the [Search-CsClsLogging](search-csclslogging.md) cmdlet.

Centralized logging is built around a series of predefined scenarios that offer a more finely-targeted approach to logging than offered in previous versions of Lync Server. These scenarios predetermine the server components and logging for you; as a result, an administrator enabling the RGS scenario can be confident that he or she will only log information relevant to the Response Group service and not to, say, the audio conferencing provider service.

The **Remove-CsClsScenario** cmdlet provides a way for you to remove scenarios from your centralized logging configuration settings.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsClsScenario"}

Lync Server 控制面板: The functions carried out by the **Remove-CsClsScenario** cmdlet are not available in the Lync Server 控制面板.

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
<td><p>Unique identifier of the scenario to be removed. A scenario consists of two parts: the scope where the scenario is configured (that is, the collection of centralized logging configuration settings where the scenario can be found) and the scenario name. For example:</p>
<p>-Identity &quot;site:Redmond/AddressBook&quot;</p>
<p>You can also specify just the scenario scope; for example:</p>
<p>-Identity &quot;site:Redmond&quot;</p>
<p>If you do that, however, the entire collection of centralized logging configuration settings for the specified scope will be removed, and not just the scenarios.</p></td>
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

The **Remove-CsClsScenario** cmdlet accepts pipelined instances of the Microsoft.Rtc.Management.WritableConfig.Settings.CentralizedLogging.Scenario\#Decorated object.

## Return Types

None. Instead, the **Remove-CsClsScenario** cmdlet deletes existing instances of the Microsoft.Rtc.Management.WritableConfig.Settings.CentralizedLogging.Scenario\#Decorated object.

