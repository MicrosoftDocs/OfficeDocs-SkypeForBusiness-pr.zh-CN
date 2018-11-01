---
title: Get-CsClsScenario
TOCTitle: Get-CsClsScenario
ms:assetid: 8f0c5f52-c000-4e27-82a2-534a50b11a98
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205091(v=OCS.15)
ms:contentKeyID: 49313572
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsClsScenario

 

_**上一次修改主题：** 2015-03-09_

Returns information for one or more centralized logging configuration scenarios. A scenario represents a particular Lync Server 2013 component or situation (such as IM and presence) that administrators can enable or disable for tracing. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Get-CsClsScenario [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsClsScenario [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Examples

## Example 1

The command shown in Example 1 returns information about all the centralized logging scenarios currently in use in the organization.

    Get-CsClsScenario

## Example 2

Example 2 returns information about a single centralized logging scenario: the VoiceMail scenario included in the global settings collection.

    Get-CsClsScenario -Identity "global/VoiceMail"

## Example 3

Example 3 returns information about all the default scenarios currently in use. To do this, the command first calls the **Get-CsClsScenario** cmdlet without any parameters; that returns a collection of all the available scenarios. That collection is then piped to the **Where-Object** cmdlet, which picks out only those scenarios that contain (-match) a Provider named "AsMcu".

    Get-CsClsScenario | Where-Object {$_.Provider.Name -match "AsMcu"}

## Example 4

In Example 4, detailed information is returned for the Provider property of the global VoiceMail scenario. To carry out this task the cmdlet first uses the **Get-CsClsScenario** cmdlet to return all the property values for the global VoiceMail scenario. That information is then piped to the Select-Object cmdlet, which uses the ExpandProperty parameter to "expand" the value of the Provider property. In turn, that causes all the data stored in the Provider property to be displayed onscreen in an easy-to-read format.

    Get-CsClsScenario -Identity "global/VoiceMail" | Select-Object -ExpandProperty Provider

## Detailed Description

The centralized logging service (which replaces the OCSLogger and OCSTracer tools used in Microsoft Lync Server 2010) provides a way for administrators to manage logging and tracing for all computers and pools running Lync Server 2013. Centralized logging enables administrators to stop, start, and configure logging for one or more pools and computers by using a single command; for example, you can use one command to enable Address Book service logging on all your Address Book servers. This differs from the OCSLogger and OCSTracer tools, which had to be individually managed (including individually stopped and started) on each server. In addition, the centralized logging service also provides a way for administrators to search trace logs from the command, using the Windows PowerShell 命令行接口 and the [Search-CsClsLogging](search-csclslogging.md) cmdlet.

Centralized logging is built around a series of predefined scenarios that offer a more finely-targeted approach to logging than offered in previous versions of Lync Server. These scenarios predetermine the server components and logging for you; as a result, an administrator enabling the RGS scenario can be confident that he or she will only log information relevant to the Response Group service and not to, say, the audio conferencing provider service.

Information about all the centralized logging scenarios available for use in your organization can be returned by using the **Get-CsClsScenario** cmdlet.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsClsScenario"}

Lync Server 控制面板: The functions carried out by the **Get-CsClsScenario** cmdlet are not available in the Lync Server 控制面板

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
<td><p>Enables you to use wildcards in order to return one or scenarios. For example, to return all the HybridVoice scenarios, regardless of the scope where these scenarios have been configured, use this syntax:</p>
<p>-Filter &quot;*HybridVoice*&quot;</p>
<p>You cannot use both the Identity parameter and the Filter parameter in the same command.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier of the scenario to be returned. A scenario consists of two parts: the scope where the scenario is configured (that is, the collection of centralized logging configuration settings where the scenario can be found) and the scenario name. For example:</p>
<p>-Identity &quot;site:Redmond/AddressBook&quot;</p>
<p>You can also specify just the scenario scope; for example:</p>
<p>-Identity &quot;site:Redmond&quot;</p>
<p>In that case, all the scenarios configured for use on the Redmond site will be returned.</p>
<p>If this parameter is not specified then the <strong>Get-CsClsScenario</strong> cmdlet will return information about all your centralized logging scenarios.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the scenario data from the local replica of the Central Management store rather than from the Central Management store itself.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Get-CsScenario** cmdlet does not accept pipelined input.

## Return Types

The **Get-CsScenario** cmdlet returns instances of the Microsoft.Rtc.Management.WritableConfig.Settings.CentralizedLogging.Scenario\#Decorated object.

