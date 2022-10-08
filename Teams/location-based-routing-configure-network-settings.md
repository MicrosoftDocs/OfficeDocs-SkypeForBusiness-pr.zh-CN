---
title: 配置网络设置 - 基于位置的路由
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何创建和设置用于直接路由的Location-Based路由的网络区域、站点和子网。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9a7c02a7299029ec267011f962880884d1d9f4d7
ms.sourcegitcommit: 401cee68d4f6f9470d614dda12b9cb023f382ff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2022
ms.locfileid: "67999327"
---
# <a name="configure-network-settings-for-location-based-routing"></a>为基于位置的路由配置网络设置

本文介绍如何为Location-Based路由配置网络设置。 如果尚未执行此操作，请阅读 [计划Location-Based直接路由路由](location-based-routing-plan.md) ，以便在配置网络设置之前查看需要执行的其他步骤。

在组织中部署直接路由后，后续步骤是创建和设置网络区域、网络站点和网络子网。

## <a name="define-network-regions"></a>定义网络区域

网络区域包含网络站点的集合，并在多个地理区域之间互连网络的各个部分。 有关如何配置网络区域的步骤，请转到 [Teams 中管理云功能的网络拓扑](manage-your-network-topology.md)。

## <a name="define-network-sites"></a>定义网络站点

网络站点表示组织有物理场地的位置，例如办公室、一组建筑物或校园。 必须将拓扑中的每个网络站点与网络区域相关联。 有关如何配置网络站点的步骤，请参阅 [在 Teams 中管理云功能的网络拓扑](manage-your-network-topology.md)。

Location-Based路由的最佳做法是为每个具有唯一公用交换电话网络 (PSTN) 连接的位置创建一个单独的站点。 可以创建为Location-Based路由启用的站点或未启用Location-Based路由的站点。 例如，你可能想要创建一个未启用Location-Based路由的站点，以允许启用Location-Based路由的用户在漫游到该站点时进行 PSTN 调用。

## <a name="define-network-subnets"></a>定义网络子网

每个子网必须与特定的网络站点相关联。 可以将多个子网与同一网络站点关联，但不能将多个站点与同一子网相关联。 有关如何配置网络子网的步骤，请参阅  [在 Teams 中管理云功能的网络拓扑](manage-your-network-topology.md)。

对于Location-Based路由，必须定义 Teams 终结点可连接到网络的位置的 IP 子网并将其关联到定义的网络，以强制执行收费旁路。 这种子网关联使Location-Based路由能够在地理位置定位终结点，以确定是否应允许给定的 PSTN 调用。 支持 IPv6 和 IPv4 子网。 确定 Teams 终结点是否位于站点时，Location-Based路由首先检查匹配的 IPv6 地址。 如果不存在 IPv6 地址，Location-Based路由会检查 IPv4 地址。

## <a name="define-trusted-ip-addresses-external-subnets"></a>定义受信任的 IP 地址 (外部子网) 

受信任的 IP 地址是企业网络的 Internet 外部 IP 地址，用于确定用户的终结点是否在公司网络内。 有关如何配置受信任 IP 地址的步骤，请参阅 [在 Teams 中管理云功能的网络拓扑](manage-your-network-topology.md)。

如果用户的外部 IP 地址与受信任 IP 地址列表中的 IP 地址匹配，Location-Based路由检查以确定用户终结点所在的内部子网。 如果用户的外部 IP 地址与受信任 IP 地址列表中定义的任何 IP 地址不匹配，则终结点被归类为位于未知位置，并且会阻止对启用Location-Based路由的用户进行的任何 PSTN 调用。

## <a name="next-steps"></a>后续步骤

转到 [为直接路由启用Location-Based路由](location-based-routing-enable.md)。

## <a name="related-topics"></a>相关主题

- [Teams 中云语音功能的网络设置](cloud-voice-network-settings.md)
