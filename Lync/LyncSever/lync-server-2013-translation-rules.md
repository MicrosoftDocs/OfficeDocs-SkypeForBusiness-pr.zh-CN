---
title: Lync Server 2013：转换规则
TOCTitle: 转换规则
ms:assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398520(v=OCS.15)
ms:contentKeyID: 49313184
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的转换规则

 

_**上一次修改主题：** 2015-03-09_

为了执行反向号码查找 (RNL)， Lync Server 2013企业语音要求将所有拨号串规范化为 E.164 格式。在 Microsoft Lync Server 2010 中，转换规则仅适用于被叫号码。作为 Microsoft Lync Server 2013 中的新增功能，转换规则还适用于主叫号码。“中继对等方”（即，关联网关、专用交换机 (PBX) 或 SIP 中继）可能要求号码采用本地拨号格式。要将 E.164 格式的号码转换为本地拨号格式，可以在将其路由至中继对等方之前，定义一个或多个转换规则以处理请求 URI。例如，可以编写用于删除拨号串开头的 +44 并将其替换为 0144 的转换规则。

通过在服务器上执行出站路由转换，可以降低每个单独中继对等方上的配置要求，以便将电话号码转换为本地拨号格式。在规划要与特定的 中介服务器群集关联的网关和网关数时，将具有类似本地拨号要求的中继对等方归为一组可能会很有用。这可减少所需的转换规则数和编写转换规则所需的时间。

> [!IMPORTANT]
> 将一个或多个转换规则与 企业语音中继配置进行关联的操作应用作在中继对等方上配置转换规则的备选方法。如果已在中继对等方上配置转换规则，则不要将任何转换规则与 企业语音中继配置相关联，因为这两个规则可能会发生冲突。


## 示例转换规则

以下示例转换规则说明了如何在服务器上开发将号码由 E.164 格式转换为适用于中继对等方的本地格式的规则。

有关如何实施转换规则的详细信息，请参阅部署文档中的 [在 Lync Server 2013 中定义转换规则](lync-server-2013-defining-translation-rules.md)。


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
<td><p>^\+(1\d{10})$</p></td>
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
<td><p>^\+(\d{9}\d+)$</p></td>
<td><p>011$1</p></td>
<td><p>+441235551010 变为 011441235551010</p></td>
</tr>
</tbody>
</table>

