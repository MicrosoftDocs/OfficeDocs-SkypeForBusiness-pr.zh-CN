---
title: Lync Server 2013：转换规则
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Translation rules
ms:assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398520(v=OCS.15)
ms:contentKeyID: 48184460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 783d2bb8de49fc7660998fcf3cbcb7cdb5c18e8b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530349"
---
# <a name="translation-rules-in-lync-server-2013"></a>Lync Server 2013 中的转换规则

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-05_

Lync Server 2013 企业语音要求将所有拨号字符串正常化为 e.164 格式，以执行反向号码查找 (RNL) 。 在 Microsoft Lync Server 2010 中，仅对被呼叫的号码支持转换规则。 新增在 Microsoft Lync Server 2013 中，呼叫号码也支持转换规则。 “中继对等方”**（即，关联网关、专用交换机 (PBX) 或 SIP 中继）可能要求号码采用本地拨号格式。 要将 E.164 格式的号码转换为本地拨号格式，可以在将其路由至中继对等方之前，定义一个或多个转换规则以处理请求 URI。 例如，可以编写用于删除拨号串开头的 +44 并将其替换为 0144 的转换规则。

通过在服务器上执行出站路由转换，可以降低每个单独中继对等方上的配置要求，以便将电话号码转换为本地拨号格式。 在规划与特定中介服务器群集相关联的网关和多个网关时，使用类似的本地拨号要求对中继对等方进行分组可能非常有用。 这可减少所需的转换规则数和编写转换规则所需的时间。

<div>


> [!IMPORTANT]  
> 将一个或多个转换规则与企业语音中继配置关联应用作在中继对等方上配置转换规则的替代方法。 如果已在中继对等方上配置转换规则，则不要将转换规则与企业语音中继配置相关联，因为这两个规则可能会发生冲突。



</div>

<div>

## <a name="example-translation-rules"></a>示例转换规则

以下示例转换规则说明了如何在服务器上开发将号码由 E.164 格式转换为适用于中继对等方的本地格式的规则。

有关如何实施转换规则的详细信息，请参阅部署文档中的 [在 Lync Server 2013 中定义转换规则](lync-server-2013-defining-translation-rules.md) 。


<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th>说明</th>
<th>起始数字</th>
<th>Length</th>
<th>要删除的数字</th>
<th>要添加的数字</th>
<th>匹配模式</th>
<th>Translation</th>
<th>示例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>美国常规长途拨号</p>
<p>（去掉“+”）</p></td>
<td><p>+ 1</p></td>
<td><p>正好 12 位</p></td>
<td><p>1</p></td>
<td><p>0</p></td>
<td><p>^\+ (1 \ d {10}) $</p></td>
<td><p>$1</p></td>
<td><p>+14255551010 变为 14255551010</p></td>
</tr>
<tr class="even">
<td><p>美国国际长途拨号</p>
<p>（去掉“+”并添加 011）</p></td>
<td><p>+</p></td>
<td><p>至少 11 位</p></td>
<td><p>1</p></td>
<td><p>011</p></td>
<td><p>^\+ ( \d {9} \d +) $</p></td>
<td><p>011 $ 1</p></td>
<td><p>+441235551010 变为 011441235551010</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

