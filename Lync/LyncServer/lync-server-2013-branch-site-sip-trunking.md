---
title: Lync Server 2013：分支站点 SIP 中继
TOCTitle: 分支站点 SIP 中继
ms:assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412974(v=OCS.15)
ms:contentKeyID: 49314175
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的分支站点 SIP 中继

 

_**上一次修改主题：** 2012-09-21_

在某些情况下，可能需要在选定的 分支站点实现分布式 SIP 中继。为了确定 分支站点是否需要 SIP 中继，请检查 [如何在 Lync Server 2013 中实施 SIP 中继？](lync-server-2013-how-do-i-implement-sip-trunking.md)中的信息。

有关支持的拓扑选项（用于在 分支站点中部署 SIP 中继）的详细信息，请参阅 [Lync Server 2013 中的分支站点恢复能力解决方案](lync-server-2013-branch-site-resiliency-solutions.md)。

## 示例分支站点 SIP 中继要求分析

决定部署 分支站点 SIP 中继时，您需要执行特定于站点的成本分析。例如， 中央站点位于华盛顿州雷德蒙德、 分支站点位于纽约的企业应通过分析最终确定是否要实现从纽约站点到本地服务提供商的 SIP 中继。

为了确定纽约的分布式 SIP 中继是否经济高效，请标识将使用 SIP 中继的外线直拨分机（DID）号码，并分析纽约向雷德蒙德 (425) 以外的地区发出的呼叫数量。您可以在 中央站点对 分支站点实施 DID 终止。例如，雷德蒙德 中央站点可以为纽约 分支站点承载 DID 号码。如果实现分布式 SIP 中继的成本低于那些呼叫的成本，请考虑在纽约 分支站点实现 SIP 中继。

## 其他分支站点 SIP 中继要求

根据每个选项的公用电话交换网（PSTN）长途电话费的差额，选择部署 SIP 中继，而不是网关。如果部署 分支站点 SIP 中继，则还需要确定恢复能力和带宽要求。如果 分支站点和 中央站点之间的链接可以恢复并具有足够的带宽，则可以部署 SIP 中继或网关。不需要在 分支站点部署 Survivable Branch Appliance。如果 分支站点和 中央站点之间的链接不可恢复，则部署 Survivable Branch Appliance，或者部署 Survivable Branch Server 并在 分支站点设置网关或 SIP 中继。

