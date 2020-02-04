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
ms.openlocfilehash: dafb8295d3070cd9f38e8691e654146978156d45
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764398"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="starting-lync-from-another-application"></a>从另一个应用程序启动 Lync

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-20_

可以使用命令行参数快速启动 Lync 2013。 例如，如果用户单击另一个应用程序中的电话号码，应用程序可以启动 Lync 2013 的一个实例，并启动对该号码的调用。

Lync 2013 还可以识别以分号分隔的多方会议的联系人姓名列表。

如果 Lync 2013 配置为在启动时自动登录，则通过命令行参数启动 Lync 2013 将打开 Lync 主窗口。 如果 Lync 未配置为在启动时自动登录，则登录窗口将打开。

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
<th>线</th>
<th>数据的格式</th>
<th>操作</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>tel</p></td>
<td><p>电话 URI</p></td>
<td><p>为音频呼叫打开对话窗口，但不拨打指定号码。</p></td>
</tr>
<tr class="even">
<td><p>callto</p></td>
<td><p>电话：、sip：或 typeable 电话 URI</p></td>
<td><p>为音频呼叫打开对话窗口，但不拨打指定号码。</p></td>
</tr>
<tr class="odd">
<td><p>sip</p></td>
<td><p>SIP URI</p></td>
<td><p>在参与者列表中打开具有指定 SIP 统一资源标识符（URI）的对话窗口。</p></td>
</tr>
<tr class="even">
<td><p>那些</p></td>
<td><p>SIP URI</p></td>
<td><p>如果将 Lync 2013 配置为使用传输层安全（TLS）协议，功能与 sip 完全一样：。 如果未使用 TLS，则会显示一个对话框，通知用户需要更高的安全级别。</p></td>
</tr>
<tr class="odd">
<td><p>会议</p></td>
<td><p>要加入的会议的 SIP URI</p></td>
<td><p>如果 URI 为 self，则实例化焦点并显示仅限名单的视图。 否则，调出名单视图，但不发送邀请。</p></td>
</tr>
<tr class="even">
<td><p>im</p></td>
<td><p>SIP URI</p></td>
<td><p>显示带有 SIP URI 的即时消息（IM）对话窗口。 接受不带任何分隔符的尖括号（&lt;&gt;）内指定的多个 SIP uri。</p>
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
<th>示例</th>
<th>结果</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>电话： + 14255550101</p></td>
<td><p>打开具有 + 14255550101 的仅手机视图。</p></td>
</tr>
<tr class="even">
<td><p>Callto：电话： + 14255550101</p></td>
<td><p>打开具有 + 14255550101 的仅手机视图。</p></td>
</tr>
<tr class="odd">
<td><p>Callto:sip:kazuto@litwareinc.com</p></td>
<td><p>打开一个仅限手机的视图，kazuto@litwareinc.com。</p></td>
</tr>
<tr class="even">
<td><p>sip:kazuto@litwareinc.com</p></td>
<td><p>打开一个带 kazuto@litwareinc.com 的对话窗口。</p></td>
</tr>
<tr class="odd">
<td><p>会议： sip：https://meet.contoso.com/kazuto/7322994</p></td>
<td><p>打开对话窗口，并显示会议音频联接选项。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

