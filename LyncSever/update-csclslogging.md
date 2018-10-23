---
title: Update-CsClsLogging
TOCTitle: Update-CsClsLogging
ms:assetid: 104ecc02-789d-4538-8203-0451448d4301
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ619170(v=OCS.15)
ms:contentKeyID: 49312025
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Update-CsClsLogging

 

_**上一次修改主题：** 2015-03-09_

Updates the duration time for all active centralized logging scenarios. Centralized logging provides a way for administrators to simultaneously enable or disable Lync Server 2013 tracing on multiple computers. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Update-CsClsLogging -Duration <String> [-AsXml <SwitchParameter>] [-Computers <String[]>] [-Pools <String[]>]

## Examples

## Example 1

The command shown in Example 1 modifies the logging duration time for servers in the topology. In this example, the duration time is set to 1 hour (60 minutes).

    Update-CsClsLogging -Duration 60

## Example 2

In Example 2, the duration time is modified for all the servers in the pool atl-cs-001.litwareinc.com.

    Update-CsClsLogging -Duration 60 -Pools "atl-cs-001.litwareinc.com"

## Detailed Description

The centralized logging service (which replaces the OCSLogger and OCSTracer tools used in Microsoft Lync Server 2010) provides a way for administrators to manage logging and tracing for all computers and pools running Lync Server 2013. Centralized logging enables administrators to stop, start, and configure logging for one or more pools and computers by using a single command; for example, you can use one command to enable Address Book service logging on all your Address Book servers. This differs from the OCSLogger and OCSTracer tools, which had to be individually managed (including individually stopped and started) on each server. In addition, the centralized logging service also provides a way for administrators to search trace logs from the command, using the Windows PowerShell 命令行接口 and the [Search-CsClsLogging](search-csclslogging.md) cmdlet.

Centralized logging is built around a series of predefined scenarios that offer a more finely-targeted approach to logging than offered in previous versions of Lync Server. These scenarios predetermine the server components and logging for you; as a result, an administrator enabling the RGS scenario can be confident that he or she will only log information relevant to the Response Group service and not to, say, the audio conferencing provider service.

It is also possible to define custom scenarios by using the [New-CsClsScenario](new-csclsscenario.md) cmdlet.

By default, logging operations run for 4 hours (240 minutes) before automatically stopping; however, administrators have the option of specifying a different duration time when they begin logging. In addition, administrators can also use the **Update-CsClsLogging** cmdlet to change the duration time for all the scenarios currently being logged.

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
<td><p><em>Duration</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Amount of time that the logging operation should run. For example, this syntax causes the logging operation to run for 2 hours (120 minutes) and then stop:</p>
<p>-Duration 120</p>
<p>This following syntax would specify a duration of 3 hours and 14 minutes:</p>
<p>-Duration 3:15</p>
<p>The following syntax would specify a duration of 6 days, 5 hours and 12 minutes:</p>
<p>-Duration 6.5:12</p>
<p>The default value is 30 minites.</p></td>
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
<td><p>Enables administrators to updates the centralized logging service on a specified server or set of servers. To update a single server, specify the fully qualified domain name of that server. For example:</p>
<p>-Computers &quot;atl-server-001.litwareinc.com&quot;</p>
<p>Multiple servers can be specified by separating the computer FQDNs using commas:</p>
<p>-Computers &quot;atl-server-001.litwareinc.com&quot;,&quot;red-server-002.litwareinc.com&quot;</p>
<p>If you do not the Computers parameter or the Pools parameter, Update-CsClsLogging will automatically run against all the computers in the topology.</p></td>
</tr>
<tr class="even">
<td><p><em>Pools</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String[]</p></td>
<td><p>Enables administrators to update the centralized logging service on each server in a pool. To update the servers in a pool, specify the fully qualified domain name of that pool. For example:</p>
<p>-Pools &quot;atl-cs-001.litwareinc.com&quot;</p>
<p>Multiple pools can be specified by separating the pool FQDNs using commas:</p>
<p>-Pools &quot;atl-cs-001.litwareinc.com&quot;,&quot;red-cs-002.litwareinc.com&quot;</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Update-CsClsLogging** cmdlet does not accept pipelined input.

## Return Types

String value.

## 另请参阅

#### 其他资源

[Search-CsClsLogging](search-csclslogging.md)  
[Show-CsClsLogging](show-csclslogging.md)  
[Start-CsClsLogging](start-csclslogging.md)  
[Stop-CsClsLogging](stop-csclslogging.md)  
[Sync-CsClsLogging](sync-csclslogging.md)

