---
title: Start-CsClsLogging
TOCTitle: Start-CsClsLogging
ms:assetid: cac15f5a-5a0c-4b3c-9bef-bb4fd44005b2
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ619190(v=OCS.15)
ms:contentKeyID: 49314242
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Start-CsClsLogging

 

_**上一次修改主题：** 2015-03-09_

Starts the specified scenario centralized logging service scenario. Centralized logging provides a way for administrators to simultaneously enable or disable Lync Server 2013 tracing on multiple computers. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Start-CsClsLogging -Scenario <String> [-AsXml <SwitchParameter>] [-Computers <String[]>] [-Duration <String>] [-Pools <String[]>]

## Examples

## Example 1

Example 1 starts logging the AlwaysOn scenario on all the computers in the current topology.

    Start-CsClsLogging -Scenario "AlwaysOn"

## Example 2

The command shown in Example 2 starts CPS logging on all the computers in the pool atl-cs-001.litwareinc.com with duration of 12 hours.

    Start-CsClsLogging -Scenario "cps" -Pools "atl-cs-001.litwareinc.com" -Duration 12:0

## Detailed Description

The centralized logging service (which replaces the OCSLogger and OCSTracer tools used in Microsoft Lync Server 2010) provides a way for administrators to manage logging and tracing for all computers and pools running Lync Server 2013. Centralized logging enables administrators to stop, start, and configure logging for one or more pools and computers by using a single command; for example, you can use one command to enable Address Book service logging on all your Address Book servers. This differs from the OCSLogger and OCSTracer tools, which had to be individually managed (including individually stopped and started) on each server. In addition, the centralized logging service also provides a way for administrators to search trace logs from the command, using the Windows PowerShell 命令行接口 and the [Search-CsClsLogging](search-csclslogging.md) cmdlet.

Centralized logging is built around a series of predefined scenarios that offer a more finely-targeted approach to logging than offered in previous versions of Lync Server. These scenarios predetermine the server components and logging for you; as a result, an administrator enabling the RGS scenario can be confident that he or she will only log information relevant to the Response Group service and not to, say, the audio conferencing provider service.

It is also possible to define custom scenarios by using the [New-CsClsScenario](new-csclsscenario.md) cmdlet.

The **Start-CsClsLogging** cmdlet provides a way for administrators to begin logging a specified scenario on a computer or set of computers. By default, that logging operation will continue to run until the Duration time limit has expired. However, administrators can manually stop a logging operation at any time by using the [Stop-CsClsLogging](stop-csclslogging.md) cmdlet.

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
<td><p><em>Scenario</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Name of the centralized logging scenario to be started. Available scenarios (and their names) names can be returned by using this command:</p>
<p>Get-CsClsScenario | Select-Object Name</p>
<p>Note that you can only specify one scenario per call to the <strong>Start-CsClsLogging</strong> cmdlet. . Also only one scenario other than the “AlwaysOn” scenario can be started on a computer at any one time.</p></td>
</tr>
<tr class="even">
<td><p><em>AsXml</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When specified, information is returned using XML.</p></td>
</tr>
<tr class="odd">
<td><p><em>Computers</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String[]</p></td>
<td><p>Enables administrators to start logging on a specified server or set of servers. To start logging on a single server, specify the fully qualified domain name of that server. For example:</p>
<p>-Computers &quot;atl-server-001.litwareinc.com&quot;</p>
<p>Multiple servers can be specified by separating the computer FQDNs using commas:</p>
<p>-Computers &quot;atl-server-001.litwareinc.com&quot;,&quot;red-server-002.litwareinc.com&quot;</p>
<p>If you do not include the Computers parameter or the Pools parameter, the <strong>Start-CsClsLogging</strong> cmdlet will automatically run against all the computers in the topology.</p></td>
</tr>
<tr class="even">
<td><p><em>Duration</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Amount of time that the logging operation should run. For example, this syntax causes the logging operation to run for 2 hours (0 days.02 hours:00 minutes) and then stop:</p>
<p>-Duration 0.02:00</p>
<p>This following syntax would specify a duration of 3 hours and 15 minutes:</p>
<p>-Duration 0.03:15</p>
<p>The following syntax would specify a duration of 6 days, 5 hours and 12 minutes:</p>
<p>-Duration 6.05:12</p>
<p>The default value is 4 hours (04:00).</p></td>
</tr>
<tr class="odd">
<td><p><em>Pools</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String[]</p></td>
<td><p>Enables administrators to start logging a scenario on each server in a pool. To start logging in a pool, specify the fully qualified domain name of that pool. For example:</p>
<p>-Pools &quot;atl-cs-001.litwareinc.com&quot;</p>
<p>Multiple pools can be specified by separating the pool FQDNs using commas:</p>
<p>-Pools &quot;atl-cs-001.litwareinc.com&quot;,&quot;red-cs-002.litwareinc.com&quot;</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Start-CsClsLogging** cmdlet does not accept pipelined input.

## Return Types

String value or XML output. The **Start-CsClsLogging** cmdlet does not return objects.

## 另请参阅

#### 其他资源

[Search-CsClsLogging](search-csclslogging.md)  
[Show-CsClsLogging](show-csclslogging.md)  
[Stop-CsClsLogging](stop-csclslogging.md)  
[Sync-CsClsLogging](sync-csclslogging.md)  
[Update-CsClsLogging](update-csclslogging.md)

