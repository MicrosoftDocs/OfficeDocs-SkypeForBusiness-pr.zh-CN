---
title: Stop-CsClsLogging
TOCTitle: Stop-CsClsLogging
ms:assetid: 63d0f0d6-5eec-4a16-b834-37611c584f52
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ619180(v=OCS.15)
ms:contentKeyID: 49313052
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Stop-CsClsLogging

 

_**上一次修改主题：** 2015-03-09_

Stops the specified scenario centralized logging service scenario. Centralized logging provides a way for administrators to simultaneously enable or disable Lync Server 2013 tracing on multiple computers. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Stop-CsClsLogging -Scenario <String> [-AsXml <SwitchParameter>] [-Computers <String[]>] [-Pools <String[]>]

## Examples

## Example 1

The command shown in Example 1 stops the CPS logging scenario on all the servers in the topology.

    Stop-CsClsLogging -Scenario "cps"

## Example 2

In Example 2, CPS logging scenario is stopped on all the servers in the pool atl-cs-001.litwareinc.com.

    Stop-CsClsLogging -Scenario "cps" -Pools "atl-cs-001.litwareinc.com"

## Detailed Description

The centralized logging service (which replaces the OCSLogger and OCSTracer tools used in Microsoft Lync Server 2010) provides a way for administrators to manage logging and tracing for all computers and pools running Lync Server 2013. Centralized logging enables administrators to stop, start, and configure logging for one or more pools and computers by using a single command; for example, you can use one command to enable Address Book service logging on all your Address Book servers. This differs from the OCSLogger and OCSTracer tools, which had to be individually managed (including individually stopped and started) on each server. In addition, the centralized logging service also provides a way for administrators to search trace logs from the command, using the Windows PowerShell 命令行接口 and the [Search-CsClsLogging](search-csclslogging.md) cmdlet.

Centralized logging is built around a series of predefined scenarios that offer a more finely-targeted approach to logging than offered in previous versions of Lync Server. These scenarios predetermine the server components and logging for you; as a result, an administrator enabling the RGS scenario can be confident that he or she will only log information relevant to the Response Group service and not to, say, the audio conferencing provider service.

It is also possible to define custom scenarios by using the [New-CsClsScenario](new-csclsscenario.md) cmdlet.

The [Start-CsClsLogging](start-csclslogging.md) cmdlet provides a way for administrators to begin logging a specified scenario on a computer or set of computers. By default, that logging operation will continue to run until the Duration time limit has expired. However, administrators can manually stop a logging operation at any time by using the **Stop-CsClsLogging** cmdlet.

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
<td><p>Name of the centralized logging scenario to be stopped. Available scenarios (and their names) names can be returned by using this command:</p>
<p>Get-CsClsScenario | Select-Object Name</p></td>
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
<td><p>Enables administrators to stop logging on a specified server or set of servers. To stop logging on a single server, specify the fully qualified domain name of that server. For example:</p>
<p>-Computers &quot;atl-server-001.litwareinc.com&quot;</p>
<p>Multiple servers can be specified by separating the computer FQDNs using commas:</p>
<p>-Computers &quot;atl-server-001.litwareinc.com&quot;,&quot;red-server-002.litwareinc.com&quot;</p>
<p>If you do not include the Computers parameter or the Pools parameter, the <strong>Stop-CsClsLogging</strong> cmdlet will run the command against all pools in the topology.</p></td>
</tr>
<tr class="even">
<td><p><em>Pools</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String[]</p></td>
<td><p>Enables administrators to stop logging on each server in a pool. To stop logging in a pool, specify the fully qualified domain name of that pool. For example:</p>
<p>-Pools &quot;atl-cs-001.litwareinc.com&quot;</p>
<p>Multiple pools can be specified by separating the pool FQDNs using commas:</p>
<p>-Pools &quot;atl-cs-001.litwareinc.com&quot;,&quot;red-cs-002.litwareinc.com&quot;</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Stop-CsClsLogging** cmdlet does not accept pipelined input.

## Return Types

String value or XML output. The **Stop-CsClsLogging** cmdlet does not return objects.

## 另请参阅

#### 其他资源

[Search-CsClsLogging](search-csclslogging.md)  
[Show-CsClsLogging](show-csclslogging.md)  
[Start-CsClsLogging](start-csclslogging.md)  
[Sync-CsClsLogging](sync-csclslogging.md)  
[Update-CsClsLogging](update-csclslogging.md)

