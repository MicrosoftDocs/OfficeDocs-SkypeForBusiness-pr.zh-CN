---
title: 基于位置的路由术语
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: conceptual
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: 了解与直接路由的基于位置的路由相关的术语和概念。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9d35b42453ac0eb9d9ae4a3f4c71f4452943a3b0
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245091"
---
# <a name="location-based-routing-terminology"></a>基于位置的路由术语

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

下面是在整个基于位置的路由文档中使用的一些术语和概念。 在深入了解文档之前, 最好先熟悉这些条款和概念。

|术语  |说明  |
|---------|---------|
|网络区域     | 网络区域包含网络站点的集合。 例如, 如果您的组织具有多个位于印度的网站, 您可以选择将 "印度" 指定为网络区域。        |
|网络站点    | 网络站点表示您的组织有物理场所的位置, 如办公室、一组建筑物或校园。 网络站点定义为 IP 子网的集合。 基于位置的路由的最佳做法是为每个具有唯一 PSTN 连接的位置创建单独的网站。  每个网络站点都必须与一个网络区域相关联。 你可以创建为基于位置的路由或未启用基于位置的路由的网站启用的网站。 例如, 你可能希望创建一个未启用基于位置的路由的网站, 以便允许启用了基于位置的路由的用户在漫游到该站点时进行 PSTN 呼叫。 请注意, 网络站点也可以用于启用和配置紧急呼叫。        |
|网络子网     |必须定义团队终结点可以连接到网络的位置的 IP 子网, 并将其关联到已定义的网络以强制使用免费功能。 多个子网可能与同一网络站点相关联, 但是多个站点可能未与同一子网关联。 这种子网的关联使基于位置的路由能够在地理位置找到终结点, 以确定是否应允许给定的 PSTN 呼叫。 IPv6 和 IPv4 子网均受支持。 确定团队终结点是否位于某个网站时, 基于位置的路由首先检查匹配的 IPv6 地址。 如果不存在 IPv6 地址, 则基于位置的路由检查 IPv4 地址。 <br><br>
|受信任的外部 IP 地址    |受信任的外部 IP 地址是企业网络的 Internet 外部 IP 地址。 它们确定用户的终结点是否位于企业网络内, 然后再检查特定网站匹配项。 如果用户的外部 IP 与受信任列表中定义的 IP 地址匹配, 则基于位置的路由检查以确定用户终结点所在的内部子网。 如果用户的外部 IP 地址与受信任列表中定义的任何 IP 地址不匹配, 则终结点将被归为未知位置, 并且对启用了基于位置的路由的用户的任何 PSTN 呼叫都将被阻止。          |

### <a name="related-topics"></a>相关主题
- [为直接路由计划基于位置的路由](location-based-routing-plan.md)
- [为基于位置的路由配置网络设置](location-based-routing-configure-network-settings.md)
- [为直接路由启用基于位置的路由](location-based-routing-enable.md)
