---
title: Lync Server 2013 支持公共即时消息连接
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Support for public instant messenger connectivity
ms:assetid: 9c6eb500-647b-4ccd-a00e-2b8dd7c44a76
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn458579(v=OCS.15)
ms:contentKeyID: 59170234
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c89cc911411095034385f7b8ebbe01edddcd20c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845793"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="support-for-public-instant-messenger-connectivity-in-lync-server-2013"></a>Lync Server 2013 中的公共即时消息连接支持

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-10-07_

<div>

## <a name="support-for-public-instant-messenger-connectivity"></a>对公共即时消息连接的支持

本文提供有关公共 IM 连接 (PIC) 的支持信息。 PIC 是 Microsoft Lync 的一项功能, 允许组织使其 Lync 用户能够通过其 Lync 客户端和标识与特定公共即时消息 (IM) 服务的用户进行连接。

最终用户可以通过其条款与客户、合作伙伴和供应商联系, 从而获益。 在保持 Lync 的控制、合规性和存档功能的同时支持单个实时通信客户端的好处。 Lync-Skype 连接 ([可在5月2013公开推出](http://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx)) 依赖于 Lync/Office 通信服务器 (OCS)/Live 通信服务器 (LCS), 该服务器首先在连接到 MSN/Windows LIVE、AOL 和 Yahoo 时与 PIC 建立的通信服务器 (LCS)。有关 Lync-Skype 连接的详细信息, 请参阅[Lync-skype 连接](http://office.microsoft.com/en-us/lync/lync-skype-connectivity-fx103789635.aspx)。 与 Windows Live、AOL 和 Yahoo 的联盟, 每个都在一条路线上的生命周期结束。此页面记录每个服务的状态。

若要使用 PIC, 客户必须为每个公共 IM 服务提供商激活该服务。 如何执行此操作的要求和详细信息取决于 IM 服务提供商和客户的基础许可计划。

<div>

## <a name="windows-live-messenger"></a>Windows Live Messenger

Microsoft 将 Windows Live Messenger 和 Skype 一起引入。 2013年4月, 在登录时, Messenger 用户已迁移到 Skype。 即使在这些联系人更新到 Skype 后, 依赖联盟的 Lync 客户仍然能够与他们的 Messenger 联系人进行通信。 Lync 管理员或 Lync 最终用户无需执行此操作来维护服务的连续性, 并且 Lync 中的此功能的管理与 Messenger 的通信方式相同。 

当 Messenger 用户使用其 Microsoft 帐户 (即 Messenger 使用的相同凭据) 登录到 Skype 时, 其所有 Messenger 联系人 (包括联合 Lync 联系人) 都使用 Skype。 可使用 Skype 和 Lync 之间的联机状态共享和即时消息功能。 

Lync-Skype 连接-联系人在 Lync 和 Skype 用户之间的添加、状态共享、即时消息和音频呼叫现在也可供所有 Lync 客户使用。

</div>

<div>

## <a name="yahoo-and-aol-instant-messenger"></a>Yahoo\! 和 AOL 即时消息

与 Yahoo 的联盟\! AOL (和 Office 通信服务器) 的客户可以通过路径获得 AOL。 Microsoft 提供每项服务的能力已被从 Yahoo 提供支持\! 和 AOL, 并向下缠绕这些协议的基础协议。 对于这两个 Yahoo\! 并且 AOL 的服务将继续至2014年6月。

  - **Yahoo** -服务将在2014年6月后继续, 并且客户将继续使用 Microsoft LYNC 公共 IM 连接用户订阅许可证 ("PIC USL") 获得许可。从2012年9月1日起, PIC USL 不能再购买新的或续订协议。在此日期之前购买许可证的客户将能够继续与 Yahoo 进行联盟\! 直到较早的服务关闭日期或许可证过期。阅读 Lync 团队博客上[的公告](http://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx)。如果客户的许可证在2014年6月30日之前过期, 则将按与年6月30日到2014之间的时间段的付款金额为比例, 获得点数。

  - **AOL** -在2014年6月30日, LYNC 的 IM 连接 ("PIC") 服务将不再可用。为了在服务结束时限制客户中断, 我们已停止设置其他客户域。 在2014年6月30日之前, 客户无需执行任何操作即可继续支持与目标的联盟通信。 除了此日期 (或对于想要在以后预配其他域的客户), 可直接从 AOL 获取替代服务。 有关 AOL 新服务的详细信息, 请参阅[建立与 AIM](http://aimenterprise.aol.com/pic.php)  的直接联盟 (在 AOL.com 上打开新页面)。  

</div>

<div>

## <a name="public-im-provider-summary"></a>公共 IM 提供商摘要

下表提供了公用 IM 服务提供商、与 Lync 的联盟功能以及授权要求的摘要。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>公用 IM 服务提供商</th>
<th>联合功能</th>
<th>许可要求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Skype</p></td>
<td><p>即时消息、状态、音频</p></td>
<td><p>Lync Server 客户端访问许可证, Lync Online 计划1/2/3</p></td>
</tr>
<tr class="even">
<td><p>Windows Live Messenger</p></td>
<td><p>即时消息、状态、音频/视频</p></td>
<td><p>Lync Server 客户端访问许可证 (受支持的时间为 WLM 的市场)</p></td>
</tr>
<tr class="odd">
<td><p>AOL</p></td>
<td><p>即时消息、状态</p></td>
<td><p>Lync Server 客户端访问许可证;支持的现有客户2014年6月。</p></td>
</tr>
<tr class="even">
<td><p>Yahoo!</p></td>
<td><p>即时消息、状态</p></td>
<td><p>除了 Lync Server 客户端访问许可证之外, 还需要其他 Microsoft Lync 公共 IM 连接用户订阅许可证 ("PIC USL")。 从2012年9月的价目表中, PIC USL 不能再购买。 具有活动许可证的客户可以继续与 Yahoo! 进行联盟 Messenger, 直到服务在2014年6月30日的关闭日期。</p></td>
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

