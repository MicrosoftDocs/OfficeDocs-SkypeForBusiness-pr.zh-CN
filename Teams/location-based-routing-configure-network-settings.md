---
title: 配置网络设置 - 基于位置的路由
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何为直接路由的路由创建和设置Location-Based、站点和子网。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 06bccad77991aa4e9d11160bfd7b7b3e6759189f1160100ebd064e3c133e965d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54306364"
---
# <a name="configure-network-settings-for-location-based-routing"></a>为基于位置的路由配置网络设置

如果尚未这样做，请阅读规划直接路由Location-Based路由[](location-based-routing-plan.md)，查看为直接路由配置网络设置之前需要执行的其他Location-Based设置。

本文介绍如何为网络路由配置Location-Based设置。 在组织中电话系统直接路由后，接下来的步骤是创建和设置网络区域、网络站点和网络子网。

## <a name="define-network-regions"></a>定义网络区域

网络区域包含一组网络站点，跨多个地理区域互连网络的各个部分。 有关配置网络区域的步骤，请转到管理云功能的网络拓扑[Teams。](manage-your-network-topology.md)

## <a name="define-network-sites"></a>定义网络站点

网络网站表示组织具有物理场所的位置，例如办公室、一组建筑物或校园。 必须将拓扑中的每个网络站点与网络区域关联。 有关配置网络站点的步骤，请参阅[管理](manage-your-network-topology.md)云功能的网络拓扑Teams。

路由路由Location-Based为每个具有唯一 PSTN 连接的位置创建单独的网站。 可以创建为路由启用的站点Location-Based未启用路由路由Location-Based站点。 例如，你可能想要创建未为 Location-Based 路由启用的网站，以允许启用了 Location-Based 路由的用户在漫游到该网站时进行 PSTN 呼叫。

## <a name="define-network-subnets"></a>定义网络子网

每个子网必须与特定的网络站点相关联。 可以将多个子网与同一网络站点关联，但不能将多个站点与同一子网关联。 有关配置网络子网的步骤，请转到管理云功能的网络拓扑[，Teams。](manage-your-network-topology.md)

对于Location-Based路由，必须定义终结点Teams位置的 IP 子网，并关联到定义的网络，以强制绕过收费。 子网的这种关联Location-Based路由在地理上查找终结点，确定是否应允许给定的 PSTN 呼叫。 支持 IPv6 和 IPv4 子网。 确定终结点是否Teams站点时，Location-Based路由首先检查匹配的 IPv6 地址。 如果不存在 IPv6 地址，Location-Based路由检查 IPv4 地址。

## <a name="define-trusted-ip-addresses-external-subnets"></a>定义外部子网 (受信任的 IP) 

受信任的 IP 地址是企业网络的 Internet 外部 IP 地址，用于确定用户的终结点是否在企业网络中。 若要了解如何配置受信任的 IP 地址，请转到管理云功能的网络[](manage-your-network-topology.md)拓扑，Teams。

如果用户的外部 IP 地址与受信任的 IP 地址列表中的 IP 地址匹配，Location-Based路由检查以确定用户终结点所在的内部子网。 如果用户的外部 IP 地址与受信任的 IP 地址列表中定义的任何 IP 地址不匹配，则终结点被分类为位于未知位置，并且阻止与启用了 Location-Based 路由的用户之间的任何 PSTN 呼叫。

## <a name="next-steps"></a>下一步

转到"[为直接Location-Based启用路由"。](location-based-routing-enable.md)

## <a name="related-topics"></a>相关主题

- [云语音功能的网络设置Teams](cloud-voice-network-settings.md)
