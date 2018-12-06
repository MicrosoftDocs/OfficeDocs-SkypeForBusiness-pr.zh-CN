---
title: Set-CsClsScenario
TOCTitle: Set-CsClsScenario
ms:assetid: 00de6571-a1ad-4f69-a21e-8a9ae115882f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204622(v=OCS.15)
ms:contentKeyID: 49311805
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsClsScenario

 

_**上一次修改主题：** 2015-03-09_

Enables you to modify a centralized logging configuration scenario. A scenario represents a particular Lync Server 2013 component or situation (such as IM and presence) that administrators can enable or disable for tracing. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Set-CsClsScenario [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsClsScenario [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-Provider <PSListModifier>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The commands shown in Example 1 create a new centralized logging scenario provider and then add that provider to the WAC scenario configured for the Redmond site. To do this, the first command in the example uses the **New-CsClsProvider** cmdlet to create a new provider with the name WebInfrastructure; this new provider is stored in a variable named $provider. The second command in the example then adds this new provider to the scenario site:Redmond/WAC. Because the command uses the syntax @{Add=$provider} the new provider will be added to the WAC scenario in addition to any other providers already configured for that

    $provider = New-CsClsProvider -Name "WebInfrastructure" -Type "WPP" -Level "Warning" -Flags "All"
    
    Set-CsClsScenario -Identity "site:Redmond/WAC" -Provider @{Add=$provider}

## Example 2

The command shown in Example 2 is a variation of the command shown in Example 1. In Example 2, however, the new provider will replace any (and all) the existing providers configured for the WAC scenario. This is done by using the syntax @{Replace=$provider}.

    $provider = New-CsClsProvider -Name "WebInfrastructure" -Type "WPP" -Level "Warning" -Flags "All"
    
    Set-CsClsScenario -Identity "site:Redmond/WAC" -Provider @{Replace=$provider}

## Detailed Description

The centralized logging service (which replaces the OCSLogger and OCSTracer tools used in Microsoft Lync Server 2010) provides a way for administrators to manage logging and tracing for all computers and pools running Lync Server 2013. Centralized logging enables administrators to stop, start, and configure logging for one or more pools and computers by using a single command; for example, you can use one command to enable Address Book service logging on all your Address Book servers. This differs from the OCSLogger and OCSTracer tools, which had to be individually managed (including individually stopped and started) on each server. In addition, the centralized logging service also provides a way for administrators to search trace logs from the command, using the Windows PowerShell 命令行接口 and the [Search-CsClsLogging](search-csclslogging.md) cmdlet.

Centralized logging is built around a series of predefined scenarios that offer a more finely-targeted approach to logging than offered in previous versions of Lync Server. These scenarios predetermine the server components and logging for you; as a result, an administrator enabling the RGS scenario can be confident that he or she will only log information relevant to the Response Group service and not to, say, the audio conferencing provider service.

Custom scenarios by using the [New-CsClsScenario](new-csclsscenario.md) cmdlet and then adding the new scenario to a collection of centralized logging configuration settings. Any of your scenarios can then be modified by using the **Set-CsClsScenario** cmdlet.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsClsScenario"}

Lync Server 控制面板: The functions carried out by the **Set-CsClsScenario** cmdlet are not available in the Lync Server 控制面板.

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
<td><p>Unique identifier of the scenario to be modified. A scenario consists of two parts: the scope where the scenario is configured (that is, the collection of centralized logging configuration settings where the scenario can be found) and the scenario name. For example:</p>
<p>-Identity &quot;site:Redmond/AddressBook&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSObject</p></td>
<td><p>Allows you to pass a reference to an object rather than set individual parameter values.</p></td>
</tr>
<tr class="odd">
<td><p><em>Provider</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>Logging provider for the scenario. New providers must be created using the <strong>New-CsClsProvider</strong> cmdlet. For example:</p>
<p>$provider = New-CsClsProvider –Name &quot;UserServices&quot; –Type &quot;WPP&quot; –Level &quot;Info&quot; –Flags &quot;All&quot;</p></td>
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

The **Set-CsClsScenario** cmdlet accepts pipelined instances of the Microsoft.Rtc.Management.WritableConfig.Settings.CentralizedLogging.Scenario\#Decorated object.

## Return Types

None. Instead, the **Set-CsClsScenario** cmdlet modifies existing instances of the Microsoft.Rtc.Management.WritableConfig.Settings.CentralizedLogging.Scenario\#Decorated object.

