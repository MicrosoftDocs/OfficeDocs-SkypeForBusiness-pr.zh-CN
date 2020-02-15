---
title: Lync Server 2013：从另一个应用程序启动 Lync
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Starting Lync from another application
ms:assetid: 573b30b1-6590-4b24-8e96-a41be57cb0ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398376(v=OCS.15)
ms:contentKeyID: 48184184
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c22f5e365e47ae7b6a41cd6e917b87718e07ac9e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038754"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="starting-lync-from-another-application"></a>从另一个应用程序启动 Lync

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-20_

您可以使用命令行参数快速启动 Lync 2013。 例如，如果用户在另一个应用程序中单击某个电话号码，则应用程序可以启动 Lync 2013 的一个实例，并启动对该号码的呼叫。

Lync 2013 还可以识别以分号分隔的多方会议联系人姓名列表。

如果 Lync 2013 配置为在启动时自动登录，则使用命令行参数启动 Lync 2013 将打开 Lync 主窗口。 如果 Lync 没有配置为启动时自动登录，将打开登录窗口。

下表显示了可用的参数。

### <a name="lync-2013-command-line-parameters"></a>Lync 2013 命令行参数

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>扩展名</th>
<th>数据格式</th>
<th>Action</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>电话</p></td>
<td><p>tel URI</p></td>
<td><p>打开音频呼叫的“对话”窗口，但不拨打指定号码。</p></td>
</tr>
<tr class="even">
<td><p>callto</p></td>
<td><p>tel:、sip: 或可键入的 tel URI</p></td>
<td><p>打开音频呼叫的“对话”窗口，但不拨打指定号码。</p></td>
</tr>
<tr class="odd">
<td><p>sip</p></td>
<td><p>SIP URI</p></td>
<td><p>使用参与者列表中指定的 SIP 统一资源标识符 (URI) 打开“对话”窗口。</p></td>
</tr>
<tr class="even">
<td><p>那些</p></td>
<td><p>SIP URI</p></td>
<td><p>如果将 Lync 2013 配置为使用传输层安全性（TLS）协议，则功能与 sip 完全一样：。 如果没有使用 TLS，将显示一个对话框，通知用户需要更高级别的安全性。</p></td>
</tr>
<tr class="odd">
<td><p>会议</p></td>
<td><p>要加入的会议的 SIP URI</p></td>
<td><p>如果 URI 是自身，则将实例化会议状态中心，并打开仅显示名单的视图。否则，将打开名单视图，但不会发送 INVITE。</p></td>
</tr>
<tr class="even">
<td><p>im</p></td>
<td><p>SIP URI</p></td>
<td><p>使用 SIP URI 打开仅显示即时消息 (IM) 的“对话”窗口。 接受不带任何分隔符的尖括号（&lt;&gt;）内指定的多个 SIP uri。</p>
<pre><code>im:&lt;sip:user1@host&gt;&lt;sip:user2@host&gt;</code></pre></td>
</tr>
</tbody>
</table>


下表提供了这些命令行参数的示例。

### <a name="command-line-parameter-examples"></a>命令行参数示例

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
<td><p>电话： + 14255550101</p></td>
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
<td><p>会议： sip：https://meet.contoso.com/kazuto/7322994</p></td>
<td><p>打开对话窗口并显示会议音频加入选项。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

