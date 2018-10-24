---
title: Lync Server 2013：Registration 表
TOCTitle: Registration 表
ms:assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398114(v=OCS.15)
ms:contentKeyID: 49311881
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 Registration 表

 

_**上一次修改主题：** 2015-03-09_

每条记录代表一个用户注册事件。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>数据类型</th>
<th>键/索引</th>
<th>详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>主、外</p></td>
<td><p>会话请求的时间。与 <strong>SessionIdSeq</strong> 结合使用来唯一地标识会话。有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的 Dialogs 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主、外</p></td>
<td><p>用于标识会话的 ID 号。与 <strong>SessionIdTime</strong> 结合使用来唯一地标识会话。有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的 Dialogs 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>用户 ID。有关详细信息，请参阅 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>EndpointId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p></p></td>
<td><p>标识注册终结点的 GUID。通常，来自同一用户的同一计算机的注册事件具有相同的终结点 ID。不同计算机具有不同的终结点 ID。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndpointEra</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td><p></p></td>
<td><p>ID 用于区分涉及同一用户和同一终结点的注册。</p>
<p>Microsoft Lync Server 2013 中已引入了此字段。</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>当前用户的客户端版本。有关详细信息，请参阅 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RegistrarId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>用于注册的注册服务器的 ID。有关详细信息，请参阅 <a href="lync-server-2013-servers-table.md">Lync Server 2013 中的 Servers 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>在其中捕获会话的池的 ID。有关详细信息，请参阅 <a href="lync-server-2013-pools-table.md">Lync Server 2013 中的 Pools 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EdgeServerId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>进行注册的边缘服务器。有关详细信息，请参阅 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 中的 EdgeServers 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>IsInternal</strong></p></td>
<td><p>Bit</p></td>
<td><p></p></td>
<td><p>用户是否从内部登录。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsUserServiceAvailable</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>UserService 是否可用。</p></td>
</tr>
<tr class="even">
<td><p><strong>IsPrimaryRegistrar</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>是否注册到主注册器。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsPrimaryRegistrarCentral</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>指示用户是否通过 Survivable Branch Appliance 注册。</p>
<p>Microsoft Lync Server 2013 中已引入了此字段。</p></td>
</tr>
<tr class="even">
<td><p><strong>RegisterTime</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>注册时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeRegisterTime</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>注销时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>注册请求的响应代码。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>注册请求的诊断 ID。此 ID 用于指示诊断信息类型。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>发出注册请求的设备。有关详细信息，请参阅 <a href="lync-server-2013-devices-table.md">Lync Server 2013 中的 Devices 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeRegisterTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>外</p></td>
<td><p>注销原因，例如“用户已启动”、“注册已过期”、“客户端故障”等。有关详细信息，请参阅 <a href="lync-server-2013-deregistertype-table.md">Lync Server 2013 中的 DeRegisterType 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>IPAddress</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p></p></td>
<td><p>用户在其中注册的终结点的 IP 地址。可以是 IPv4 地址或 IPv6 地址。</p>
<p>Microsoft Lync Server 2013 中已引入了此字段。</p></td>
</tr>
</tbody>
</table>

