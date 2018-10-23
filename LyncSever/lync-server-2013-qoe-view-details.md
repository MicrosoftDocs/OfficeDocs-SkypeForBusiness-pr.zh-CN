---
title: Lync Server 2013 中的 QoE 视图详细信息
TOCTitle: Lync Server 2013 中的 QoE 视图详细信息
ms:assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688081(v=OCS.15)
ms:contentKeyID: 49888451
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 QoE 视图详细信息

 

_**上一次修改主题：** 2015-03-09_

视图涉及有关从 QoE SQL 数据库返回数据的最常见方案。建议将视图用于生成自定义报告而不是直接访问数据库表；这是因为视图很有可能保留与将来版本的向后兼容性。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>视图名称</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-audiostreamdetail-view.md">AudioStreamDetail 视图</a></p></td>
<td><p>存储数据库中每个音频流的相关信息。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-medialine-view.md">MediaLine 视图</a></p></td>
<td><p>存储有关数据库中每个媒体行的信息。一个音频会话通常包含一个音频媒体行。一个音频与视频 (A/V) 会话通常包含一个音频媒体行和一个视频媒体行；但是，如果使用了会议设备或库视图，则会话可能包含两个视频媒体行。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-networkconfigurationsettings-view.md">NetworkConfigurationSettings 视图</a></p></td>
<td><p>存储有关网络配置的信息。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-session-view.md">Session 视图</a></p></td>
<td><p>存储有关数据库中包含记录的会话的信息。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragent-view.md">UserAgent 视图</a></p></td>
<td><p>存储有关数据库中包含记录的会话中涉及的用户代理的信息。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videostreamdetail-view.md">VideoStreamDetail 视图</a></p></td>
<td><p>存储有关数据库中每个视频流的信息。</p></td>
</tr>
</tbody>
</table>

