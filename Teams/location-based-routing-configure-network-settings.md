---
title: 配置网络设置-基于位置的路由
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何创建和设置用于直接路由的基于位置的路由的网络区域、站点和子网。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 8025467a0581c95a40551244948a8e6b7c0ecbc8
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372052"
---
# <a name="configure-network-settings-for-location-based-routing"></a>为基于位置的路由配置网络设置

如果尚未执行此操作，请阅读[基于计划位置的路由，直接路由](location-based-routing-plan.md)以查看在为基于位置的路由配置网络设置之前需要执行的其他步骤。

本文介绍如何为基于位置的路由配置网络设置。 在组织中部署手机系统直接路由后，下一步是创建和设置网络区域、网络网站和网络子网。

## <a name="define-network-regions"></a>定义网络区域

网络区域包含网络站点集合，并跨多个地理区域互连网络的各个部分。 有关如何配置网络区域的步骤，请转到[管理团队中的云功能的网络拓扑](manage-your-network-topology.md)。

## <a name="define-network-sites"></a>定义网络站点

网络站点表示您的组织有物理场所的位置，如办公室、一组建筑物或校园。 您必须将拓扑中的每个网络站点与网络区域相关联。 有关如何配置网络网站的步骤，请参阅[管理团队中的云功能的网络拓扑](manage-your-network-topology.md)。

基于位置的路由的最佳做法是为每个具有唯一 PSTN 连接的位置创建单独的网站。 你可以创建为基于位置的路由或未启用基于位置的路由的网站启用的网站。 例如，你可能希望创建一个未启用基于位置的路由的网站，以便允许启用了基于位置的路由的用户在漫游到该站点时进行 PSTN 呼叫。

## <a name="define-network-subnets"></a>定义网络子网

每个子网都必须与特定的网络站点相关联。 你可以将多个子网与同一网络站点关联，但不能将多个站点与同一子网相关联。 有关如何配置网络子网的步骤，请转到[管理团队中的云功能的网络拓扑](manage-your-network-topology.md)。

对于基于位置的路由，团队终结点可以连接到网络的位置上的 IP 子网必须定义并关联到已定义的网络，才能强制使用收费旁路。 这种子网的关联使基于位置的路由能够在地理位置找到终结点，以确定是否应允许给定的 PSTN 呼叫。 IPv6 和 IPv4 子网均受支持。 确定团队终结点是否位于某个网站时，基于位置的路由首先检查匹配的 IPv6 地址。 如果不存在 IPv6 地址，则基于位置的路由检查 IPv4 地址。

## <a name="define-trusted-ip-addresses-external-subnets"></a>定义受信任的 IP 地址（外部子网）

"受信任的 IP 地址" 是企业网络的 internet 外部 IP 地址，用于确定用户的终结点是否位于企业网络内。 有关如何配置受信任 IP 地址的步骤，请转到[管理团队中的云功能的网络拓扑](manage-your-network-topology.md)。

如果用户的外部 IP 地址与 "受信任的 IP 地址" 列表中的 IP 地址匹配，则基于位置的路由检查以确定用户终结点所在的内部子网。 如果用户的外部 IP 地址不匹配在 "信任的 IP 地址" 列表中定义的任何 IP 地址，终结点将被归类为处于未知位置，并且对启用了基于位置的路由的用户的任何 PSTN 呼叫都将被阻止。

## <a name="next-steps"></a>后续步骤

转到 "为[直接路由启用基于位置的路由](location-based-routing-enable.md)"。

## <a name="related-topics"></a>相关主题

- [团队中云语音功能的网络设置](cloud-voice-network-settings.md)
