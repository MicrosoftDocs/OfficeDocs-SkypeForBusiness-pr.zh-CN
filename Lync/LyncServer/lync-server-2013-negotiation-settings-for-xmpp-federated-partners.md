---
title: Lync Server 2013： XMPP 联盟伙伴的协商设置
description: Lync Server 2013： XMPP 联盟伙伴的协商设置。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Negotiation settings for XMPP federated partners
ms:assetid: ef773942-ef92-4f71-85a1-738dfebdfa00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552456(v=OCS.15)
ms:contentKeyID: 48679567
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ac3d9c69d407dc750a1afb35f0a448869a88f09
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578638"
---
# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a>Lync Server 2013 中 XMPP 联盟伙伴的协商设置

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-21_

XMPP 合作伙伴的配置中的协商类型设置有多种可能的组合。 并不是所有这些组合都有效。 本主题中所述的表格将定义有效和无效的设置。 在第一个表中显示了常见配置，第二个表对所有可能的组合进行了详细说明。 请注意，除非还提供了*传输层安全性* (TLS) ，**否则**不能 (SASL) 具有*简单的身份验证和安全层*。 SASL 以未加密的 (可读) 格式发送，除非受到其他方式（如 TLS）的保护，否则永远不应传输。

### <a name="common-xmpp-federation-negotiation-methods"></a>常用 XMPP 联合身份验证协商方法

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
<th>传输层安全性 (TLS)</th>
<th>简单身份验证和安全层 (SASL) </th>
<th>回拨身份验证</th>
<th> (s) 的预期身份验证方法</th>
<th>注释</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>必需</p></td>
<td><p>必需</p></td>
<td><p>False</p></td>
<td><p>通过 TLS 的 SASL</p></td>
<td><p>TLS 和 SASL 必需有助于确保 SASL 邮件流是安全的。 如果 XMPP 联盟伙伴未将 TLS 设置为必需或可选的，则不能使用回拨方法，也不能将其用于回退方法。</p></td>
</tr>
<tr class="even">
<td><p>必需</p></td>
<td><p>可选</p></td>
<td><p>True</p></td>
<td><p>TLS 上的 SASL，TLS 回拨，TCP 回拨</p></td>
<td><p>如果 XMPP 联盟伙伴已将 SASL 设置为 "可选" 或 "必需的 SASL"，则需要使用 TLS。 如果 SASL 不可用，将使用 TLS 的回拨。</p></td>
</tr>
<tr class="odd">
<td><p>可选</p></td>
<td><p>可选</p></td>
<td><p>True</p></td>
<td><p>TLS 上的 SASL，TLS 回拨，TCP 回拨</p></td>
<td><p>在提供的协商方法中非常灵活，这些设置依赖于 XMPP 联盟伙伴的设置。 如果合作伙伴的 TLS 是可选的或必需的，但不支持 SASL，TLS 回拨将可用。 如果合作伙伴将 TLS 和 SASL 设置为 "可选" 或 "必需"，则使用最理想的 TLS over SASL 的选择。</p></td>
</tr>
<tr class="even">
<td><p>不支持</p></td>
<td><p>不支持</p></td>
<td><p>True</p></td>
<td><p>TCP 回拨</p></td>
<td><p>在很多情况下，TCP 回拨是唯一可行的解决方案。 比其他选项更不理想，它提供一定级别的信任。</p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a>XMPP 联合协商方法矩阵-完整

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
<th>传输层安全性 (TLS)</th>
<th>简单身份验证和安全层 (SASL) </th>
<th>回拨身份验证</th>
<th>预期的身份验证方法</th>
<th>无效配置的备注、警告或错误</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>必需</p></td>
<td><p>必需</p></td>
<td><p>True</p></td>
<td><p>通过 TLS 的 SASL</p></td>
<td><div>

> [!WARNING]  
> 如果需要 SASL 和 TLS，回拨将不会运行。


</div></td>
</tr>
<tr class="even">
<td><p>必需</p></td>
<td><p>必需</p></td>
<td><p>False</p></td>
<td><p>通过 TLS 的 SASL</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>可选</p></td>
<td><p>必需</p></td>
<td><p>True</p></td>
<td><p>TLS 上的 SASL，TLS 回拨，TCP 回拨</p></td>
<td><div>

> [!WARNING]  
> SASL 需要 TLS。 允许 TLS 是可选的可能会导致会话协商失败。


</div></td>
</tr>
<tr class="even">
<td><p>可选</p></td>
<td><p>必需</p></td>
<td><p>False</p></td>
<td><p>通过 TLS 的 SASL</p></td>
<td><div>

> [!WARNING]  
> SASL 需要 TLS。 允许 TLS 是可选的可能会导致会话协商失败。


</div></td>
</tr>
<tr class="odd">
<td><p>不支持</p></td>
<td><p>必需</p></td>
<td><p>True</p></td>
<td><p>TCP 回拨</p></td>
<td><div>

> [!WARNING]  
> SASL 需要 TLS。 允许 TLS 是可选的可能会导致会话协商失败。


</div></td>
</tr>
<tr class="even">
<td><p>不支持</p></td>
<td><p>必需</p></td>
<td><p>False</p></td>
<td><div>

> [!WARNING]  
> 配置无效


</div></td>
<td><div>

> [!WARNING]  
> 由于 SASL 需要 TLS，并且 TLS 不可用，因此 SASL/TLS 不能成功。 TCP 回拨被设置为 false，不能使用。


</div></td>
</tr>
<tr class="odd">
<td><p>必需</p></td>
<td><p>可选</p></td>
<td><p>True</p></td>
<td><p>TLS 上的 SASL，TLS 回拨</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>必需</p></td>
<td><p>可选</p></td>
<td><p>False</p></td>
<td><p>通过 TLS 的 SASL</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>可选</p></td>
<td><p>可选</p></td>
<td><p>True</p></td>
<td><p>TLS 上的 SASL，TLS 回拨，TCP 回拨</p></td>
<td><div>

> [!WARNING]  
> SASL 需要 TLS。 允许 TLS 是可选的可能会导致会话协商失败。


</div></td>
</tr>
<tr class="even">
<td><p>可选</p></td>
<td><p>可选</p></td>
<td><p>False</p></td>
<td><p>通过 TLS 的 SASL</p></td>
<td><div>

> [!WARNING]  
> SASL 需要 TLS。 允许 TLS 是可选的可能会导致会话协商失败。


</div></td>
</tr>
<tr class="odd">
<td><p>不支持</p></td>
<td><p>可选</p></td>
<td><p>True</p></td>
<td><p>TCP 回拨</p></td>
<td><div>

> [!WARNING]  
> SASL 需要 TLS。 允许 TLS 是可选的可能会导致会话协商失败。


</div></td>
</tr>
<tr class="even">
<td><p>不支持</p></td>
<td><p>可选</p></td>
<td><p>False</p></td>
<td><div>

> [!WARNING]  
> 配置无效


</div></td>
<td><div>

> [!WARNING]  
> SASL 需要 TLS。 允许 TLS 是可选的可能会导致会话协商失败。


</div></td>
</tr>
<tr class="odd">
<td><p>必需</p></td>
<td><p>不支持</p></td>
<td><p>True</p></td>
<td><p>TLS 回拨</p></td>
<td><p>配置允许 TLS 回拨。</p></td>
</tr>
<tr class="even">
<td><p>必需</p></td>
<td><p>不支持</p></td>
<td><p>False</p></td>
<td><p>配置无效</p></td>
<td><div>

> [!WARNING]  
> 必须启用 SASL 或回拨。


</div></td>
</tr>
<tr class="odd">
<td><p>可选</p></td>
<td><p>不支持</p></td>
<td><p>True</p></td>
<td><p>TLS 回拨，TCP 回拨</p></td>
<td><p>根据其他终结点的协商选择，将接受 TCP 或 TLS 回拨。</p></td>
</tr>
<tr class="even">
<td><p>可选</p></td>
<td><p>不支持</p></td>
<td><p>False</p></td>
<td><p>配置无效</p></td>
<td><div>

> [!WARNING]  
> 必须启用 SASL 或回拨。


</div></td>
</tr>
<tr class="odd">
<td><p>不支持</p></td>
<td><p>不支持</p></td>
<td><p>True</p></td>
<td><p>TCP 回拨</p></td>
<td><p>TCP 回拨是唯一可用的协商方法</p></td>
</tr>
<tr class="even">
<td><p>不支持</p></td>
<td><p>不支持</p></td>
<td><p>False</p></td>
<td><p>配置无效</p></td>
<td><div>

> [!WARNING]  
> 必须启用 SASL 或回拨。


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

