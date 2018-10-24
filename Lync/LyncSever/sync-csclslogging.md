---
title: Sync-CsClsLogging
TOCTitle: Sync-CsClsLogging
ms:assetid: 0df996b7-1834-42f1-84e5-346ba74631e7
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ619169(v=OCS.15)
ms:contentKeyID: 49312001
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Sync-CsClsLogging

 

_**上一次修改主题：** 2015-03-09_

Flushes the centralized logging service cache. Centralized logging provides a way for administrators to simultaneously enable or disable Lync Server 2013 tracing on multiple computers. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Sync-CsClsLogging [-AsXml <SwitchParameter>] [-Computers <String[]>] [-Pools <String[]>]

## Examples

## Example 1

The command shown in Example 1 flushes the centralized logging caches for all the servers in the topology.

    Sync-CsClsLogging 

## Example 2

In Example 2, the centralized logging caches are flushed on all the servers in the pool atl-cs-001.litwareinc.com.

    Sync-CsClsLogging -Pools "atl-cs-001.litwareinc.com"

## Detailed Description

The centralized logging service (which replaces the OCSLogger and OCSTracer tools used in Microsoft Lync Server 2010) provides a way for administrators to manage logging and tracing for all computers and pools running Lync Server 2013. Centralized logging enables administrators to stop, start, and configure logging for one or more pools and computers by using a single command; for example, you can use one command to enable Address Book service logging on all your Address Book servers. This differs from the OCSLogger and OCSTracer tools, which had to be individually managed (including individually stopped and started) on each server. In addition, the centralized logging service also provides a way for administrators to search trace logs from the command, using the Windows PowerShell 命令行接口 and the [Search-CsClsLogging](search-csclslogging.md) cmdlet.

Centralized logging is built around a series of predefined scenarios that offer a more finely-targeted approach to logging than offered in previous versions of Lync Server. These scenarios predetermine the server components and logging for you; as a result, an administrator enabling the RGS scenario can be confident that he or she will only log information relevant to the Response Group service and not to, say, the audio conferencing provider service.

It is also possible to define custom scenarios by using the [New-CsClsScenario](new-csclsscenario.md) cmdlet.

When a scenario is being logged, the service will maintain data in memory and then periodically write that data to disk. However, at any time administrators can run the **Sync-CsClsLogging** cmdlet to "flush" the data cache. When this is done, all the logging data currently in memory will be written to disk, the data caches will be cleared, and the log files will be available for searching.

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
<td><p>Enables administrators to flush the centralized logging service cache on a specified server or set of servers. To flush a single server cache, specify the fully qualified domain name of that server. For example:</p>
<p>-Computers &quot;atl-server-001.litwareinc.com&quot;</p>
<p>Multiple servers can be specified by separating the computer FQDNs using commas:</p>
<p>-Computers &quot;atl-server-001.litwareinc.com&quot;,&quot;red-server-002.litwareinc.com&quot;</p>
<p>If you do not include the Computers parameter or the Pools parameter, the <strong>Sync-CsClsLogging</strong> cmdlet will apply the command against all pools in the topology.</p></td>
</tr>
<tr class="odd">
<td><p><em>Pools</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String[]</p></td>
<td><p>Enables administrators to flush the centralized logging service cache on each server in a pool. To flush the server caches in a pool, specify the fully qualified domain name of that pool. For example:</p>
<p>-Pools &quot;atl-cs-001.litwareinc.com&quot;</p>
<p>Multiple pools can be specified by separating the pool FQDNs using commas:</p>
<p>-Pools &quot;atl-cs-001.litwareinc.com&quot;,&quot;red-cs-002.litwareinc.com&quot;</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Sync-CsClsLogging** cmdlet does not accept pipelined input.

## Return Types

String value. The **Sync-CsClsLogging** cmdlet does not return objects.

## 另请参阅

#### 其他资源

[Search-CsClsLogging](search-csclslogging.md)  
[Show-CsClsLogging](show-csclslogging.md)  
[Start-CsClsLogging](start-csclslogging.md)  
[Stop-CsClsLogging](stop-csclslogging.md)  
[Update-CsClsLogging](update-csclslogging.md)

