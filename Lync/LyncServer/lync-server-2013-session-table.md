---
title: Lync Server 2013：Session 表
TOCTitle: Session 表
ms:assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398635(v=OCS.15)
ms:contentKeyID: 49313390
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 Session 表

 

_**上一次修改主题：** 2015-03-09_

每条记录分别表示一个包含音频或音频和视频的会话。它包含有关会话的总体信息。会话定义为两个终结点之间的音频或视频会话初始协议 (SIP) 对话。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>列</strong></th>
<th><strong>数据类型</strong></th>
<th><strong>键/索引</strong></th>
<th><strong>详细信息</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>主</p></td>
<td><p>引用自 <a href="lync-server-2013-dialog-table.md">Lync Server 2013 中的 Dialog 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>引用自 <a href="lync-server-2013-dialog-table.md">Lync Server 2013 中的 Dialog 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceKey</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>会议密钥。引用自 <a href="lync-server-2013-conference-table.md">Lync Server 2013 中的 Conference 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>CorrelationKey</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>相关密钥。引用自 <a href="lync-server-2013-sessioncorrelation-table.md">Lync Server 2013 中的 SessionCorrelation 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogCategory</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>对话类别；0 是 Lync Server 到中介服务器线路；1 是中介服务器到 PSTN 网关线路。</p></td>
</tr>
<tr class="even">
<td><p><strong>MediationServerBypassFlag</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>指示是否绕过了呼叫的标记。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaBypassWarningFlag</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>如果存在，此字段指示即使绕过 ID 相匹配也没有绕过呼叫的原因。对于 Lync Server，只定义了一个值。</p>
<p>0x0001 – 默认网络适配器的未知绕过 ID。</p></td>
</tr>
<tr class="even">
<td><p><strong>StartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>呼叫开始时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>呼叫结束时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPool</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>呼叫者的池。引用自 <a href="lync-server-2013-pool-table.md">Lync Server 2013 中的 Pool 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleePool</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>呼叫接收者的池。引用自 <a href="lync-server-2013-pool-table.md">Lync Server 2013 中的 Pool 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleePAI</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>接收终结点的 SIP p 已断言标识 (PAI) 中的 SIP URI。引用自 <a href="lync-server-2013-user-table.md">Lync Server 2013 中的 User 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerURI</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>呼叫者的 URI。引用自 <a href="lync-server-2013-user-table.md">Lync Server 2013 中的 User 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerEndpoint</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>呼叫者的终结点。引用自 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013 中的 Endpoint 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerUserAgent</strong></p></td>
<td><p>bit</p></td>
<td><p>外</p></td>
<td><p>呼叫者的用户代理。引用自 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallPriority</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>此呼叫的优先级。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClassifiedPoorCall</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>此列已被弃用且在 Microsoft Lync Server 2013 中没有使用。相反，此信息是逐媒体行报告的。有关详细信息，请参阅 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPAI</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>发起呼叫的用户的 P-Asserted-Identity。P-Asserted-Identity (PAI) 用于传达发起呼叫的用户的真实身份。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeEndpoint</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>收到呼叫的终结点。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeUserAgent</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>收到呼叫的用户使用的用户代理。用户代理表示客户端终结点设备。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeUri</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>收到呼叫的用户的 SIP URI。</p></td>
</tr>
</tbody>
</table>

