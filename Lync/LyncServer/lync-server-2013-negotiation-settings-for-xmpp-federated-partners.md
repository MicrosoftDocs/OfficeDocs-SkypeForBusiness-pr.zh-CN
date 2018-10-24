---
title: Lync Server 2013：XMPP 联盟伙伴的协商设置
TOCTitle: XMPP 联盟伙伴的协商设置
ms:assetid: ef773942-ef92-4f71-85a1-738dfebdfa00
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ552456(v=OCS.15)
ms:contentKeyID: 49314681
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中 XMPP 联盟伙伴的协商设置

 

_**上一次修改主题：** 2015-03-09_

XMPP 合作伙伴的配置中协商类型的设置有多种可能的组合。并非所有这些组合都有效。本主题中详述的表将定义有效和无效的设置。常用配置显示在第一个表中，第二个表详细列出了所有可能的组合。请注意，您不得有 *简单身份验证和安全层* (SASL) **，但***传输层安全性* (TLS) 也可用除外。以未加密的（可读）格式发送 SASL，且一定不要传输，但以另一种方式提供保护（例如，TLS）除外。

### 公用 XMPP 联盟协商方法

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>传输层安全协议性 (TLS)</th>
<th>简单身份验证和安全层 (SASL)</th>
<th>回拨身份验证</th>
<th>预期的身份验证方法</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>必需</p></td>
<td><p>必需</p></td>
<td><p>错误</p></td>
<td><p>SASL over TLS</p></td>
<td><p>必需的 TLS 和 SASL 有助于确保 SASL 消息流的安全性。如果 XMPP 联盟伙伴未将 TLS 设置为必需或可选，则回拨不可用且无法用于回退方法。</p></td>
</tr>
<tr class="even">
<td><p>必需</p></td>
<td><p>可选</p></td>
<td><p>正确</p></td>
<td><p>SASL over TLS、TLS 回拨、TCP 回拨</p></td>
<td><p>通过要求 TLS，如果 XMPP 联盟伙伴已将 SASL 设置为可选或必需，则使用 SASL。如果 SASL 不可用，则使用 TLS 上的回拨。</p></td>
</tr>
<tr class="odd">
<td><p>可选</p></td>
<td><p>可选</p></td>
<td><p>正确</p></td>
<td><p>SASL over TLS、TLS 回拨、TCP 回拨</p></td>
<td><p>尽管提供的协商方法非常灵活，但这些设置依赖 XMPP 联盟伙伴的设置。如果伙伴将 TLS 设置为可选或必需，但不支持 SASL，则 TLS 回拨将可用。如果合作伙伴将 TLS 和 SASL 设置为可选或必需，则使用 TLS over SASL 的可选选项。</p></td>
</tr>
<tr class="even">
<td><p>不支持</p></td>
<td><p>不支持</p></td>
<td><p>正确</p></td>
<td><p>TCP 回拨</p></td>
<td><p>在多数情况下，TCP 回拨是仅有的可能解决方案。尽管与其他选项相比不太重要，但它确实提供了某些可信级别。</p></td>
</tr>
</tbody>
</table>


### XMPP 联盟协商方法矩阵 - 完成

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>传输层安全协议性 (TLS)</th>
<th>简单身份验证和安全层 (SASL)</th>
<th>回拨身份验证</th>
<th>预期的身份验证方法</th>
<th>注，无效配置的警告或错误</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>必需</p></td>
<td><p>必需</p></td>
<td><p>正确</p></td>
<td><p>SASL over TLS</p></td>
<td><div>

> [!WARNING]
> 如果 SASL 和 TLS 都为必需，回拨将不可操作。

</div></td>
</tr>
<tr class="even">
<td><p>必需</p></td>
<td><p>必需</p></td>
<td><p>错误</p></td>
<td><p>SASL over TLS</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>可选</p></td>
<td><p>必需</p></td>
<td><p>正确</p></td>
<td><p>SASL over TLS、TLS 回拨、TCP 回拨</p></td>
<td><div>

> [!WARNING]
> SASL 需要 TLS。允许 TLS 为可选项可能会导致会话协商失败。

</div></td>
</tr>
<tr class="even">
<td><p>可选</p></td>
<td><p>必需</p></td>
<td><p>错误</p></td>
<td><p>SASL over TLS</p></td>
<td><div>

> [!WARNING]
> SASL 需要 TLS。允许 TLS 为可选项可能会导致会话协商失败。

</div></td>
</tr>
<tr class="odd">
<td><p>不支持</p></td>
<td><p>必需</p></td>
<td><p>正确</p></td>
<td><p>TCP 回拨</p></td>
<td><div>

> [!WARNING]
> SASL 需要 TLS。允许 TLS 为可选项可能会导致会话协商失败。

</div></td>
</tr>
<tr class="even">
<td><p>不支持</p></td>
<td><p>必需</p></td>
<td><p>错误</p></td>
<td><div>

> [!WARNING]
> 不是有效的配置

</div></td>
<td><div>

> [!WARNING]
> 因为 SASL 需要 TLS，而 TLS 不可用，则 SASL/TLS 无法成功。将 TCP 回拨设置为 false，但无法使用。

</div></td>
</tr>
<tr class="odd">
<td><p>必需</p></td>
<td><p>可选</p></td>
<td><p>正确</p></td>
<td><p>SASL over TLS，TLS 回拨</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>必需</p></td>
<td><p>可选</p></td>
<td><p>错误</p></td>
<td><p>SASL over TLS</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>可选</p></td>
<td><p>可选</p></td>
<td><p>正确</p></td>
<td><p>SASL over TLS、TLS 回拨、TCP 回拨</p></td>
<td><div>

> [!WARNING]
> SASL 需要 TLS。允许 TLS 为可选项可能会导致会话协商失败。

</div></td>
</tr>
<tr class="even">
<td><p>可选</p></td>
<td><p>可选</p></td>
<td><p>错误</p></td>
<td><p>SASL over TLS</p></td>
<td><div>

> [!WARNING]
> SASL 需要 TLS。允许 TLS 为可选项可能会导致会话协商失败。

</div></td>
</tr>
<tr class="odd">
<td><p>不支持</p></td>
<td><p>可选</p></td>
<td><p>正确</p></td>
<td><p>TCP 回拨</p></td>
<td><div>

> [!WARNING]
> SASL 需要 TLS。允许 TLS 为可选项可能会导致会话协商失败。

</div></td>
</tr>
<tr class="even">
<td><p>不支持</p></td>
<td><p>可选</p></td>
<td><p>错误</p></td>
<td><div>

> [!WARNING]
> 不是有效的配置

</div></td>
<td><div>

> [!WARNING]
> SASL 需要 TLS。允许 TLS 为可选项可能会导致会话协商失败。

</div></td>
</tr>
<tr class="odd">
<td><p>必需</p></td>
<td><p>不支持</p></td>
<td><p>正确</p></td>
<td><p>TLS 回拨</p></td>
<td><p>允许用于 TLS 回拨的配置。</p></td>
</tr>
<tr class="even">
<td><p>必需</p></td>
<td><p>不支持</p></td>
<td><p>错误</p></td>
<td><p>不是有效的配置</p></td>
<td><div>

> [!WARNING]
> 必须启用 SASL 或回拨。

</div></td>
</tr>
<tr class="odd">
<td><p>可选</p></td>
<td><p>不支持</p></td>
<td><p>正确</p></td>
<td><p>TLS 回拨，TCP 回拨</p></td>
<td><p>根据其他终结点的协商选项，将接受 TCP 或 TLS 回拨。</p></td>
</tr>
<tr class="even">
<td><p>可选</p></td>
<td><p>不支持</p></td>
<td><p>错误</p></td>
<td><p>不是有效的配置</p></td>
<td><div>

> [!WARNING]
> 必须启用 SASL 或回拨。

</div></td>
</tr>
<tr class="odd">
<td><p>不支持</p></td>
<td><p>不支持</p></td>
<td><p>正确</p></td>
<td><p>TCP 回拨</p></td>
<td><p>TCP 回拨是仅可用的协商方法</p></td>
</tr>
<tr class="even">
<td><p>不支持</p></td>
<td><p>不支持</p></td>
<td><p>错误</p></td>
<td><p>不是有效的配置</p></td>
<td><div>

> [!WARNING]
> 必须启用 SASL 或回拨。

</div></td>
</tr>
</tbody>
</table>

