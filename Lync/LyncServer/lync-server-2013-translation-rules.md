---
title: 'Lync Server 2013: 翻译规则'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Translation rules
ms:assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398520(v=OCS.15)
ms:contentKeyID: 48184460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22b6fbacf068f6a1a388a968989259afec81d17a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845538"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="translation-rules-in-lync-server-2013"></a>Lync Server 2013 中的翻译规则

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-05_

Lync Server 2013 企业版语音要求将所有拨号字符串正常化为格式, 以便执行反向数字查找 (RNL)。 在 Microsoft Lync Server 2010 中, 仅支持被呼叫号码的翻译规则。 Microsoft Lync Server 2013 中的新增, 翻译规则也支持呼叫号码。 *中继对等方*（即，关联网关、专用交换机 (PBX) 或 SIP 中继）可能要求号码采用本地拨号格式。 要将 E.164 格式的号码转换为本地拨号格式，可以在将其路由至中继对等方之前，定义一个或多个转换规则以处理请求 URI。 例如，可以编写用于删除拨号串开头的 +44 并将其替换为 0144 的转换规则。

通过在服务器上执行出站路由转换，可以降低每个单独中继对等方上的配置要求，以便将电话号码转换为本地拨号格式。 在规划要与特定中介服务器群集关联的网关和多少个网关时, 使用类似的本地拨号要求对干线对等进行分组可能非常有用。 这可减少所需的转换规则数和编写转换规则所需的时间。

<div>


> [!IMPORTANT]  
> 将一个或多个翻译规则与企业语音中继配置相关联应用作在中继对等上配置翻译规则的替代方法。 如果你已在中继对等上配置了转换规则, 请不要将翻译规则与企业语音中继配置相关联, 因为这两个规则可能会发生冲突。



</div>

<div>

## <a name="example-translation-rules"></a>示例转换规则

以下示例转换规则说明了如何在服务器上开发将号码由 E.164 格式转换为适用于中继对等方的本地格式的规则。

有关如何实现翻译规则的详细信息, 请参阅部署文档中[Lync Server 2013 中的 "定义翻译规则](lync-server-2013-defining-translation-rules.md)"。


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
<th>描述</th>
<th>起始数字</th>
<th>长度</th>
<th>要删除的数字</th>
<th>要添加的数字</th>
<th>匹配模式</th>
<th>转换</th>
<th>示例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>美国常规长途拨号</p>
<p>（去掉“+”）</p></td>
<td><p>+1</p></td>
<td><p>正好 12 位</p></td>
<td><p>1</p></td>
<td><p>0</p></td>
<td><p>^\+(1 \ d{10}) $</p></td>
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
<td><p>^\+(\d{9}\d +) $</p></td>
<td><p>011$1</p></td>
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

