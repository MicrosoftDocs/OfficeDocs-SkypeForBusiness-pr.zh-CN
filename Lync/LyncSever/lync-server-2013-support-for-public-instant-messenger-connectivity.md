---
title: Lync Server 2013 中的公共即时消息连接支持
TOCTitle: Lync Server 2013 中的公共即时消息连接支持
ms:assetid: 9c6eb500-647b-4ccd-a00e-2b8dd7c44a76
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn458579(v=OCS.15)
ms:contentKeyID: 59602822
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的公共即时消息连接支持

 

_**上一次修改主题：** 2016-12-08_

## 公共即时消息连接支持

本文提供有关公共 IM 连接 (PIC) 支持的信息。PIC 是 Microsoft Lync 的一种功能，使组织的 Lync 用户能够通过其 Lync 客户端和标识与特定公共即时消息 (IM) 服务的用户保持联系。

最终用户将因能够根据自己的情况与客户、合作伙伴和供应商保持联系而受益。IT 用户将因支持单个实时通信客户端同时保持 Lync 的控制、合规性和存档功能而受益。Lync-Skype 连接（[2013 年 5 月公开可用](http://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx)）依赖于以下旧功能：Lync/Office Communications Server (OCS)/Live Communications Server (LCS) 连接到 MSN/Windows Live、AOL 和 Yahoo 时首先与 PIC 建立连接。有关 Lync-Skype 连接的详细信息，请参阅 [Lync-Skype 连接](http://office.microsoft.com/zh-cn/lync/lync-skype-connectivity-fx103789635.aspx)。 与 Windows Live、AOL 和 Yahoo 的联盟即将结束。此页面介绍了各项服务的状态。

要使用 PIC，客户需要激活各个公共 IM 服务提供商的服务。如何执行此操作的要求和详细信息因 IM 服务提供商和客户的基础许可计划而异。

## Windows Live Messenger

Microsoft 将 Windows Live Messenger 和 Skype 融为一体。2013 年 4 月，Messenger 用户登录时已迁移到 Skype。依赖与 Messenger 的联盟的 Lync 客户继续能够与其 Messenger 联系人进行通信，即使在这些联系人更新到 Skype 之后也是如此。Lync 管理员或 Lync 最终用户无需执行任何操作来保持服务的连续性，Lync 中此功能的管理与 Messenger 通信相同。

当 Messenger 用户使用其 Microsoft 帐户（如，用于 Messenger 的相同凭据）登录 Skype 时，其所有 Messenger 联系人（包括联盟的 Lync 联系人）都将载入 Skype 中。这些联系人在 Skype 和 Lync 之间进行的状态共享和即时消息可用。

Lync-Skype 连接（Lync 和 Skype 用户之间的联系人添加、状态共享、即时消息和音频呼叫）现在对所有 Lync 客户可用。

## Yahoo\! 和 AOL Instant Messenger

对于 Lync（和 Office Communications Server）的用户，与 Yahoo\! 和 AOL 的联盟即将结束。Microsoft 之所以能够提供这些服务离不开 Yahoo\! 和 AOL 的支持，但这些支持的基础协议正在逐步终止。对于 Yahoo\! 和 AOL，服务将在 2014 年 6 月截止。

  - **Yahoo** - 服务将在 2014 年 6 月截止，客户继续需要通过 Microsoft Lync 公共 IM 连接用户订阅许可证 (“PIC USL”) 获得许可。自 2012 年 9 月 1 日起，新订或续订合同不能再购买 PIC USL。在此日期之前购买了许可证的客户能够继续与 Yahoo\! 联盟直至服务关闭日期或许可证到期（以较早者为准）。请阅读 Lync 团队博客上的[公告](http://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx)。协议上的 PIC 许可证日期超过 2014 年 6 月 30 日的客户将按照付款金额的比例享受折扣优惠（涵盖 2014 年 6 月 30 日之后的时间段）。

  - **AOL** - 2014 年 6 月 30 日，Lync 的 IM 连接 ("PIC") 不再可用。为了限制服务结束时出现的客户中断，我们已停止设置其他客户域。在 2014 年 6 月 30 日之前，客户无需执行任何操作来继续支持与 AIM 的联盟通信。如果超出此日期（或者对于同时想要设置其他域的客户），替换服务可直接从 AOL 使用。有关 AOL 的新服务的详细信息，请参阅 [Establishing Direct Federation with AIM](http://aimenterprise.aol.com/pic.php)（在 AOL.com 上打开新页）。

## 公共 IM 提供商摘要

下表提供了公共 IM 服务提供商、与 Lync 的联盟功能和许可要求的摘要。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>公共 IM 服务提供商</th>
<th>联盟功能</th>
<th>许可要求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Skype</p></td>
<td><p>IM、状态和音频</p></td>
<td><p>Lync Server 客户端访问许可证、Lync Online 计划 1/2/3</p></td>
</tr>
<tr class="even">
<td><p>Windows Live Messenger</p></td>
<td><p>IM、状态和音频/视频</p></td>
<td><p>Lync Server 客户端访问许可证（只要 WLM 仍在市场中使用就会支持）</p></td>
</tr>
<tr class="odd">
<td><p>AOL</p></td>
<td><p>IM 和状态</p></td>
<td><p>Lync Server 客户端访问许可证；在 2014 年 6 月之前支持现有客户。</p></td>
</tr>
<tr class="even">
<td><p>Yahoo!</p></td>
<td><p>IM 和状态</p></td>
<td><p>除了 Lync Server 客户端访问许可证之外，需要其他 Microsoft Lync 公共 IM 连接用户订阅许可证（“PIC USL”）。自 2012 年 9 月价目单起，不能再购买 PIC USL。具有活动许可证的客户将能继续与 Yahoo! Messenger 联盟，直到服务关闭日期 2014 年 6 月 30 日。</p></td>
</tr>
</tbody>
</table>

