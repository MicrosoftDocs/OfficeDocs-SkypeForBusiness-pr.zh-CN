---
title: Lync Server 2013 支持公共即时消息连接
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Support for public instant messenger connectivity
ms:assetid: 9c6eb500-647b-4ccd-a00e-2b8dd7c44a76
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn458579(v=OCS.15)
ms:contentKeyID: 59170234
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be14e3dedf39883a81a040ed31ae38d2966ab647
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208278"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="support-for-public-instant-messenger-connectivity-in-lync-server-2013"></a>Lync Server 2013 中的公共即时消息连接支持

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-10-07_

<div>

## <a name="support-for-public-instant-messenger-connectivity"></a>对公共即时消息连接的支持

本文提供有关对公共 IM 连接（PIC）的支持的信息。 PIC 是 Microsoft Lync 的一项功能，它允许组织使其 Lync 用户能够通过 Lync 客户端和标识与特定的公共即时消息（IM）服务的用户进行连接。

最终用户可以在其条款中与客户、合作伙伴和供应商联系，从而获益。 通过支持单个实时通信客户端，同时保持 Lync 的控制、合规性和存档功能，提供了 IT 优势。 Lync-Skype 连接（可[在5月2013公开发布](https://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx)）依赖旧版的 Lync/Office 通信服务器（OCS）/Live 通信服务器（LCS）首先与 PIC 建立与 MSN/Windows LIVE、AOL 和 Yahoo 的连接。有关 Lync-Skype 连接的详细信息，请参阅[lync-skype 连接](https://office.microsoft.com/lync/lync-skype-connectivity-fx103789635.aspx)。 与 Windows Live、AOL 和 Yahoo 的联盟都在路径上朝向生命期结束。此页面记录每个服务的状态。

若要使用 PIC，客户需要为每个公共 IM 服务提供商激活服务。 有关如何执行此操作的要求和详细信息取决于 IM 服务提供商和客户的基础许可计划。

<div>

## <a name="windows-live-messenger"></a>Windows Live Messenger

Microsoft 将 Windows Live Messenger 和 Skype 放在一起。 在4月2013，信使用户在登录时迁移到 Skype。 依赖联盟和 Messenger 的 Lync 客户将继续能够与其 Messenger 联系人通信，即使这些联系人更新到 Skype 也是如此。 Lync 管理员或 Lync 最终用户不需要执行此操作来维护服务的连续性，并且 Lync 中的此功能的管理仍保持不变，与信使通信一样。 

当 Messenger 用户使用其 Microsoft 帐户登录（即，用于 Messenger 的相同凭据）时，他们的所有 Messenger 联系人-包括联合 Lync 联系人-请将其加入 Skype。 这些联系人的 Skype 和 Lync 之间的状态共享和即时消息可用。 

Lync-Skype 连接-联系人在 Lync 和 Skype 用户之间添加、状态共享、即时消息和音频呼叫，现在也适用于所有 Lync 客户。

</div>

<div>

## <a name="yahoo-and-aol-instant-messenger"></a>Yahoo\! 和 AOL 即时信使

与 Yahoo 的联盟\! AOL （和 Office 通信服务器）的客户在使用寿命结束的路径上。 Microsoft 提供每项服务的能力因 Yahoo 的支持而受到\! 和 AOL 以及这些条款的底层协议将向下缠绕。 对于这两个 Yahoo\! 和 AOL，服务将继续到2014年6月。

  - **Yahoo** -服务将持续到2014年6月，客户继续需要使用 Microsoft LYNC 公共 IM 连接用户订阅许可证（"PIC USL"）获得许可。从9月1日起，2012，PIC USL 不再可用于购买新的或续订的协议。在此日期之前购买许可证的客户将能够继续与 Yahoo 进行联盟\! 在之前的服务关闭日期或其许可证过期之前。阅读 Lync 团队博客上[的通知](https://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx)。如果客户的许可证的使用期限在6月30日之前延长的协议，则2014将按与支付30年6月 30 2014 日之后的时间段的付款金额成比例显示积分。

  - **AOL** -在2014年6月30日，LYNC 的 IM 连接（"PIC"）服务将不再可用。为了在服务结束时限制客户的中断，我们已停止对其他客户域的设置。 在2014年6月30日之前，客户无需执行任何操作即可继续支持与 AIM 的联合通信。 除此日期之外（或对于希望同时预配其他域的客户），可直接从 AOL 获取替代服务。 有关 AOL 新服务的详细信息，请  参阅[建立与 AIM 的直接联盟](http://aimenterprise.aol.com/pic.php)（打开 AOL.com 上的新页面）。  

</div>

<div>

## <a name="public-im-provider-summary"></a>公共 IM 提供商摘要

下表提供了公用 IM 服务提供商的摘要、与 Lync 的联合功能以及许可要求。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>公共 IM 服务提供商</th>
<th>联合功能</th>
<th>许可要求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Skype</p></td>
<td><p>即时消息、状态、音频</p></td>
<td><p>Lync Server 客户端访问许可证，Lync Online 计划1/2/3</p></td>
</tr>
<tr class="even">
<td><p>Windows Live Messenger</p></td>
<td><p>即时消息、状态、音频/视频</p></td>
<td><p>Lync Server 客户端访问许可证（只要 WLM 处于市场中，就支持此项）</p></td>
</tr>
<tr class="odd">
<td><p>寻求</p></td>
<td><p>即时消息、状态</p></td>
<td><p>Lync Server 客户端访问许可证;为现有客户提供6月2014的支持。</p></td>
</tr>
<tr class="even">
<td><p>Yahoo！</p></td>
<td><p>即时消息、状态</p></td>
<td><p>除了 Lync Server 客户端访问许可证之外，还需要其他 Microsoft Lync 公共 IM 连接用户订阅许可证（"PIC USL"）。 从2012年9月发布的价目表中，PIC USL 无法再用于购买。 具有有效许可证的客户可以继续与 Yahoo！联合 在2014年6月30日的服务关闭前，一直向信使。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

