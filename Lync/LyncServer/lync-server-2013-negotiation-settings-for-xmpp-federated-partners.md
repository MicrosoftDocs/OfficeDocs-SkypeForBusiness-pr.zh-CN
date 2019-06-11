---
title: Lync Server 2013：XMPP 联盟伙伴的协商设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Negotiation settings for XMPP federated partners
ms:assetid: ef773942-ef92-4f71-85a1-738dfebdfa00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552456(v=OCS.15)
ms:contentKeyID: 48679567
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02d72870e4060be6aa4ec428159af7ab19cb68b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826708"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a>Lync Server 2013 中 XMPP 联盟伙伴的协商设置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-21_

XMPP 合作伙伴配置中的协商类型的设置有多种可能的组合。 并非所有这些组合都有效。 本主题中所述的表将定义有效和无效的设置。 常见配置显示在第一个表中, 第二个表介绍了所有可能的组合。 请注意, 除非也提供了 "*传输层安全性*(TLS)",**否则**不能具有*简单的身份验证和安全层*(SASL)。 使用不加密的 (可读) 格式发送 SASL, 除非受到另一种方式 (如 TLS) 保护, 否则切勿传输。

### <a name="common-xmpp-federation-negotiation-methods"></a>常见的 XMPP 联盟协商方法

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
<th>简单身份验证和安全层 (SASL)</th>
<th>回拨身份验证</th>
<th>预期的身份验证方法</th>
<th>注释</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>必需</p></td>
<td><p>必需</p></td>
<td><p>False</p></td>
<td><p>TLS 上的 SASL</p></td>
<td><p>TLS 和 SASL 所需有助于确保 SASL 消息流的安全。 如果 XMPP 联盟合作伙伴未将 TLS 设置为必需或可选, 则回拨不可用, 也不能用于回退方法。</p></td>
</tr>
<tr class="even">
<td><p>必需</p></td>
<td><p>可选</p></td>
<td><p>True</p></td>
<td><p>TLS 上的 SASL, TLS 回拨, TCP 回拨</p></td>
<td><p>如果 XMPP 联盟合作伙伴已将 SASL 设置为 "可选" 或 "所需的 SASL", 则需要使用 TLS。 如果 SASL 不可用, 将使用通过 TLS 的回拨。</p></td>
</tr>
<tr class="odd">
<td><p>可选</p></td>
<td><p>可选</p></td>
<td><p>True</p></td>
<td><p>TLS 上的 SASL, TLS 回拨, TCP 回拨</p></td>
<td><p>在提供的协商方法中非常灵活, 这些设置依赖于 XMPP 联盟伙伴的设置。 如果合作伙伴具有 TLS 可选或必需, 但不支持 SASL, TLS 回拨将可用。 如果合作伙伴将 TLS 和 SASL 设置为 "可选" 或 "所需", 则使用通过 SASL 的最佳选择。</p></td>
</tr>
<tr class="even">
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>True</p></td>
<td><p>TCP 回拨</p></td>
<td><p>在许多情况下, TCP 回拨是唯一可行的解决方案。 比其他选项更少, 它提供一定级别的信任。</p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a>XMPP 联盟协商方法矩阵-完成

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
<th>简单身份验证和安全层 (SASL)</th>
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
<td><p>TLS 上的 SASL</p></td>
<td><div>

> [!WARNING]  
> 如果需要 SASL 和 TLS, 则回拨不会运行。


</div></td>
</tr>
<tr class="even">
<td><p>必需</p></td>
<td><p>必需</p></td>
<td><p>False</p></td>
<td><p>TLS 上的 SASL</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>可选</p></td>
<td><p>必需</p></td>
<td><p>True</p></td>
<td><p>TLS 上的 SASL, TLS 回拨, TCP 回拨</p></td>
<td><div>

> [!WARNING]  
> SASL 需要 TLS。 允许 TLS 是可选的可能会导致会话协商失败。


</div></td>
</tr>
<tr class="even">
<td><p>可选</p></td>
<td><p>必需</p></td>
<td><p>False</p></td>
<td><p>TLS 上的 SASL</p></td>
<td><div>

> [!WARNING]  
> SASL 需要 TLS。 允许 TLS 是可选的可能会导致会话协商失败。


</div></td>
</tr>
<tr class="odd">
<td><p>否</p></td>
<td><p>必需</p></td>
<td><p>True</p></td>
<td><p>TCP 回拨</p></td>
<td><div>

> [!WARNING]  
> SASL 需要 TLS。 允许 TLS 是可选的可能会导致会话协商失败。


</div></td>
</tr>
<tr class="even">
<td><p>否</p></td>
<td><p>必需</p></td>
<td><p>False</p></td>
<td><div>

> [!WARNING]  
> 配置无效


</div></td>
<td><div>

> [!WARNING]  
> 由于 SASL 需要 TLS, 并且 TLS 不可用, 因此不能成功使用 SASL/TLS。 TCP 回拨已设置为 false, 无法使用。


</div></td>
</tr>
<tr class="odd">
<td><p>必需</p></td>
<td><p>可选</p></td>
<td><p>True</p></td>
<td><p>TLS 上的 SASL, TLS 回拨</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>必需</p></td>
<td><p>可选</p></td>
<td><p>False</p></td>
<td><p>TLS 上的 SASL</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>可选</p></td>
<td><p>可选</p></td>
<td><p>True</p></td>
<td><p>TLS 上的 SASL, TLS 回拨, TCP 回拨</p></td>
<td><div>

> [!WARNING]  
> SASL 需要 TLS。 允许 TLS 是可选的可能会导致会话协商失败。


</div></td>
</tr>
<tr class="even">
<td><p>可选</p></td>
<td><p>可选</p></td>
<td><p>False</p></td>
<td><p>TLS 上的 SASL</p></td>
<td><div>

> [!WARNING]  
> SASL 需要 TLS。 允许 TLS 是可选的可能会导致会话协商失败。


</div></td>
</tr>
<tr class="odd">
<td><p>否</p></td>
<td><p>可选</p></td>
<td><p>True</p></td>
<td><p>TCP 回拨</p></td>
<td><div>

> [!WARNING]  
> SASL 需要 TLS。 允许 TLS 是可选的可能会导致会话协商失败。


</div></td>
</tr>
<tr class="even">
<td><p>否</p></td>
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
<td><p>否</p></td>
<td><p>True</p></td>
<td><p>TLS 回拨</p></td>
<td><p>配置允许 TLS 回拨。</p></td>
</tr>
<tr class="even">
<td><p>必需</p></td>
<td><p>否</p></td>
<td><p>False</p></td>
<td><p>配置无效</p></td>
<td><div>

> [!WARNING]  
> 必须启用 SASL 或回拨。


</div></td>
</tr>
<tr class="odd">
<td><p>可选</p></td>
<td><p>否</p></td>
<td><p>True</p></td>
<td><p>TLS 回拨, TCP 回拨</p></td>
<td><p>根据其他终结点的协商选项, 将接受 TCP 或 TLS 回拨。</p></td>
</tr>
<tr class="even">
<td><p>可选</p></td>
<td><p>否</p></td>
<td><p>False</p></td>
<td><p>配置无效</p></td>
<td><div>

> [!WARNING]  
> 必须启用 SASL 或回拨。


</div></td>
</tr>
<tr class="odd">
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>True</p></td>
<td><p>TCP 回拨</p></td>
<td><p>TCP 回拨是唯一可用的协商方法</p></td>
</tr>
<tr class="even">
<td><p>否</p></td>
<td><p>否</p></td>
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

