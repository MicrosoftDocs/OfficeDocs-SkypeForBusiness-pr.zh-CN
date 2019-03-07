---
title: 基于位置的路由术语
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
search.appverid: MET150
description: 了解术语和概念的直接路由与基于位置的路由相关联。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 34ec6558873da0db3537f6c5ae82b6624a3af369
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/07/2019
ms.locfileid: "30462393"
---
# <a name="location-based-routing-terminology"></a>基于位置的路由术语

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

下面是一些术语和概念用于整个基于位置的路由文档的。 最好之前插入文档获取更深入地介绍要熟悉这些术语和概念。

|术语  |说明  |
|---------|---------|
|网络区域     | 网络区域包含网络站点的集合。 例如，如果您的组织具有位于印度的多个网站，您可以选择将"印度"指定为网络区域。        |
|网络站点    | 网络站点表示您的组织其中有物理定义位置，如 office、 一组建筑或一所高校的位置。 网络站点定义为 IP 子网的集合。 基于位置的路由的最佳做法是创建单独的网站的每个具有唯一的 PSTN 连接的位置。  每个网络站点必须与网络区域相关联。 您可以创建基于位置的路由启用网站或网站的未启用基于位置的路由。 例如，您可能想要创建基于位置的路由，以便为基于位置的路由，以便 PSTN 呼叫，它们漫游到该网站时启用的用户未启用网站。 请注意，网络站点可能还使用启用和配置紧急呼叫。        |
|网络子网     |其中团队终结点可以连接到网络位置的 IP 子网必须定义，并定义网络强制实施收费绕过关联。 多个子网可能的相同的网络站点相关联，但可能不与同一子网关联多个站点。 此关联的子网启用基于位置的路由来查找地理位置以确定是否应允许给定的 PSTN 呼叫的终结点。 支持 IPv6 和 IPv4 子网。 在确定是否团队终结点所处的网站时，基于位置的路由首先检查匹配的 IPv6 地址。 如果 IPv6 地址不存在，基于位置的路由检查 IPv4 地址。 <br><br>IPv6 支持正在进行，可通过常规可用性 (GA) 的基于位置的路由。          |
|受信任的外部 IP 地址    |受信任的外部 IP 地址是企业网络的 Internet 外部 IP 地址。 决定是否用户的终结点位于企业网络内部之前检查的特定网站匹配项。 如果用户的外部 IP 与受信任列表中定义的 IP 地址相匹配，基于位置的路由检查以确定用户的终结点所在的内部子网。 如果用户的外部 IP 地址不匹配的受信任列表中定义的任意 IP 地址，终结点分类为未知位置，或从基于位置的路由启用的用户的所有 PSTN 呼叫被都阻止。          |

### <a name="related-topics"></a>相关主题
- [为直接路由计划基于位置的路由](location-based-routing-plan.md)
- [为基于位置的路由配置网络设置](location-based-routing-configure-network-settings.md)
- [为直接路由启用基于位置的路由](location-based-routing-enable.md)
