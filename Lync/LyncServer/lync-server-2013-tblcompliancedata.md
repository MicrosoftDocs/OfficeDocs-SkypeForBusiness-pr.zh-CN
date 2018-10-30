---
title: Lync Server 2013：tblComplianceData
TOCTitle: tblComplianceData
ms:assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg558606(v=OCS.15)
ms:contentKeyID: 49311874
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 tblComplianceData

 

_**上一次修改主题：** 2015-03-09_

tblComplianceData 包含合规适配器尚未处理的合规事件。

### 列

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>类型</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>cmplEventID</p></td>
<td><p>bigint，不为 null</p></td>
<td><p>事件 ID。</p></td>
</tr>
<tr class="even">
<td><p>entryDate</p></td>
<td><p>smalldatetime，不为 null</p></td>
<td><p>插入时间（将来对于 cmplType=9，可能比较遥远，因为该条目在那种情况下只是一个占位符）。</p></td>
</tr>
<tr class="odd">
<td><p>cmplType</p></td>
<td><p>int，不为 null</p></td>
<td><p>合规事件的类型：</p>
<ul>
<li><p>1：聊天</p></li>
<li><p>2：聊天记录</p></li>
<li><p>3：文件下载</p></li>
<li><p>4：文件上载</p></li>
<li><p>9：临时文件传输</p></li>
<li><p>10：删除聊天（通过替换）</p></li>
<li><p>11：清除聊天</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>cmplTime</p></td>
<td><p>bigint，不为 null</p></td>
<td><p>事件的时间戳。</p></td>
</tr>
<tr class="odd">
<td><p>cmplChannelUri</p></td>
<td><p>nvarchar (255)，不为 null</p></td>
<td><p>通道统一资源标识符 (URI)。</p></td>
</tr>
<tr class="even">
<td><p>cmplChatID</p></td>
<td><p>bigint</p></td>
<td><p>聊天 ID（与 tblChat.chatId 表对应）。</p></td>
</tr>
<tr class="odd">
<td><p>cmplUserID</p></td>
<td><p>int，不为 null</p></td>
<td><p>发布人的主体 ID（与 tblPrincipal.prinID 表对应）。</p></td>
</tr>
<tr class="even">
<td><p>cmplUserUri</p></td>
<td><p>nvarchar (255)，不为 null</p></td>
<td><p>用户 URI。</p></td>
</tr>
<tr class="odd">
<td><p>cmplMessage</p></td>
<td><p>nvarchar (max)</p></td>
<td><p>消息（编码方式取决于 cmplType）。</p></td>
</tr>
</tbody>
</table>


### 按键

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>cmplEventID</p></td>
<td><p>主键。</p></td>
</tr>
</tbody>
</table>

