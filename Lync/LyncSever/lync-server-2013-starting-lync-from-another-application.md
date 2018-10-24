---
title: 通过其他应用程序启动 Lync
TOCTitle: 通过其他应用程序启动 Lync
ms:assetid: 573b30b1-6590-4b24-8e96-a41be57cb0ef
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398376(v=OCS.15)
ms:contentKeyID: 52061033
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 通过其他应用程序启动 Lync

 

_**上一次修改主题：** 2015-03-09_

可以使用命令行参数快速启动 Lync 2013。例如，如果用户在另一应用程序中单击某个电话号码，该应用程序可以启动一个 Lync 2013 实例，并向该号码发起呼叫。

Lync 2013 还能识别由多方会议的联系人姓名（以分号分隔）构成的列表。

如果 Lync 2013 配置为启动时自动登录，则使用命令行参数启动 Lync 2013 时将打开 Lync 主窗口。如果 Lync 没有配置为启动时自动登录，将打开登录窗口。

下表显示了可用的参数。

### Lync 2013 命令行参数

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>扩展</th>
<th>数据格式</th>
<th>操作</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>tel:</p></td>
<td><p>tel URI</p></td>
<td><p>打开音频呼叫的“对话”窗口，但不拨打指定号码。</p></td>
</tr>
<tr class="even">
<td><p>callto:</p></td>
<td><p>tel:、sip: 或可键入的 tel URI</p></td>
<td><p>打开音频呼叫的“对话”窗口，但不拨打指定号码。</p></td>
</tr>
<tr class="odd">
<td><p>sip:</p></td>
<td><p>SIP URI</p></td>
<td><p>使用参与者列表中指定的 SIP 统一资源标识符 (URI) 打开“对话”窗口。</p></td>
</tr>
<tr class="even">
<td><p>Sips:</p></td>
<td><p>SIP URI</p></td>
<td><p>如果 Lync 2013 配置为使用传输层安全性 (TLS) 协议，则其功能与 sip: 完全相同。如果没有使用 TLS，将显示一个对话框，通知用户需要更高级别的安全性。</p></td>
</tr>
<tr class="odd">
<td><p>conf:</p></td>
<td><p>要加入的会议的 SIP URI</p></td>
<td><p>如果 URI 是自身，则将实例化会议状态中心，并打开仅显示名单的视图。否则，将打开名单视图，但不会发送 INVITE。</p>
<p></p></td>
</tr>
<tr class="even">
<td><p>im:</p></td>
<td><p>SIP URI</p></td>
<td><p>使用 SIP URI 打开仅显示即时消息 (IM) 的“对话”窗口。接受尖括号 (&lt;&gt;) 中指定的多个 SIP URI（不带任何分隔符）。</p>
<pre><code>im:&lt;sip:user1@host&gt;&lt;sip:user2@host&gt;</code></pre></td>
</tr>
</tbody>
</table>


下表提供了这些命令行参数的示例。

### 命令行参数示例

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>实例</th>
<th>结果</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tel:+14255550101</p></td>
<td><p>使用 +14255550101 打开仅显示电话的视图。</p></td>
</tr>
<tr class="even">
<td><p>Callto:tel:+ 14255550101</p></td>
<td><p>使用 +14255550101 打开仅显示电话的视图。</p></td>
</tr>
<tr class="odd">
<td><p>Callto:sip:kazuto@litwareinc.com</p></td>
<td><p>使用 kazuto@litwareinc.com 打开仅显示电话的视图。</p></td>
</tr>
<tr class="even">
<td><p>sip:kazuto@litwareinc.com</p></td>
<td><p>使用 kazuto@litwareinc.com 打开“对话”窗口。</p></td>
</tr>
<tr class="odd">
<td><p>conf:sip:https://meet.contoso.com/kazuto/7322994</p></td>
<td><p>打开“对话”窗口并显示会议音频加入选项。</p></td>
</tr>
</tbody>
</table>

