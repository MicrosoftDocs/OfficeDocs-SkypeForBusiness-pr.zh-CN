---
title: Show-CsClsLogging
TOCTitle: Show-CsClsLogging
ms:assetid: 19b2de51-5c14-4a8b-97e5-573c3285b174
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ619173(v=OCS.15)
ms:contentKeyID: 49312147
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Show-CsClsLogging

 

_**上一次修改主题：** 2015-03-09_

Shows the current status of the centralized logging service. (That is, shows which centralized logging scenarios are currently active.) Centralized logging provides a way for administrators to simultaneously enable or disable Lync Server 2013 tracing on multiple computers. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Show-CsClsLogging [-AsXml <SwitchParameter>] [-Computers <String[]>] [-Pools <String[]>]

## Examples

## Example 1

The command shown in Example 1 returns information about the scenarios currently being logged on all the Computers in the topology.

    Show-CsClsLogging

## Example 2

In Example 2, logging information is returned for all the servers in the pool atl-cs-001…litwareinc.com…

    Show-CsClsLogging -Pools "atl-cs-001.litwareinc.com"

## Detailed Description

The centralized logging service (which replaces the OCSLogger and OCSTracer tools used in Microsoft Lync Server 2010) provides a way for administrators to manage logging and tracing for all computers and pools running Lync Server 2013. Centralized logging enables administrators to stop, start, and configure logging for one or more pools and computers by using a single command; for example, you can use one command to enable Address Book service logging on all your Address Book servers. This differs from the OCSLogger and OCSTracer tools, which had to be individually managed (including individually stopped and started) on each server. In addition, the centralized logging service also provides a way for administrators to search trace logs from the command, using the Windows PowerShell 命令行接口 and the [Search-CsClsLogging](search-csclslogging.md) cmdlet.

Centralized logging is built around a series of predefined scenarios that offer a more finely-targeted approach to logging than offered in previous versions of Lync Server. These scenarios predetermine the server components and logging for you; as a result, an administrator enabling the RGS scenario can be confident that he or she will only log information relevant to the Response Group service and not to, say, the audio conferencing provider service.

It is also possible to define custom scenarios by using the [New-CsClsScenario](new-csclsscenario.md) cmdlet.

The **Show-CsClsLogging** cmdlet returns information about all the scenarios currently being logged on a computer or set of computers; this information includes the name and duration of each active scenario, as well as the date and time that logging began.

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
<td><p><em>AsXml</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When specified, information is returned using XML.</p></td>
</tr>
<tr class="even">
<td><p><em>Computers</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String[]</p></td>
<td><p>Enables administrators to return logging information from a specified server or set of servers. To return information from a single server, specify the fully qualified domain name of that server. For example:</p>
<p>-Computers &quot;atl-server-001.litwareinc.com&quot;</p>
<p>Multiple servers can be specified by separating the computer FQDNs using commas:</p>
<p>-Computers &quot;atl-server-001.litwareinc.com&quot;,&quot;red-server-002.litwareinc.com&quot;</p>
<p>If you do not include the Computers parameter or the Pools parameter, the <strong>Show-CsClsLogging</strong> cmdlet will show the status of all Computers in the topology.</p></td>
</tr>
<tr class="odd">
<td><p><em>Pools</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String[]</p></td>
<td><p>Enables administrators to return logging information for each server in a pool. To return information for a pool, specify the fully qualified domain name of that pool. For example:</p>
<p>-Pools &quot;atl-cs-001.litwareinc.com&quot;</p>
<p>Multiple pools can be specified by separating the pool FQDNs using commas:</p>
<p>-Pools &quot;atl-cs-001.litwareinc.com&quot;,&quot;red-cs-002.litwareinc.com&quot;</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Show-CsClsLogging** cmdlet does not accept pipelined input.

## Return Types

String value or XML output. The **Show-CsClsLogging** cmdlet does not return objects.

## 另请参阅

#### 其他资源

[Search-CsClsLogging](search-csclslogging.md)  
[Start-CsClsLogging](start-csclslogging.md)  
[Stop-CsClsLogging](stop-csclslogging.md)  
[Sync-CsClsLogging](sync-csclslogging.md)  
[Update-CsClsLogging](update-csclslogging.md)

