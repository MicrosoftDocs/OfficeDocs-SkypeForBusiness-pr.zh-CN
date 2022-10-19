---
title: 云语音功能的网络设置
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: 了解必须为直接路由和增强的紧急服务Location-Based路由配置的网络设置。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 327dbcef98e62d86f814f8e1fadc1c26673d0928
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2022
ms.locfileid: "68584003"
---
# <a name="network-settings-for-cloud-voice-features-in-microsoft-teams"></a>Microsoft Teams 中云语音功能的网络设置

了解网络区域、网络站点、网络子网和受信任的 IP 地址。 这些术语和概念在云语音文档中用于直接路由和[动态紧急呼叫](configure-dynamic-emergency-calling.md)[的基于位置的路由](location-based-routing-plan.md)。 如果要在组织中部署这些云功能，则必须在 Microsoft Teams 中配置用于这些功能的网络设置。

本文概述了Location-Based路由和动态紧急呼叫常见的网络设置。 根据要部署的云语音功能和功能，可以配置某些或所有这些设置。 有关如何配置这些设置的步骤，请参阅 [管理 Teams 中云功能的网络拓扑](manage-your-network-topology.md)。

> [!NOTE]
> 网络设置的任何特定于功能的要求都记录在该功能的配置主题中。

## <a name="network-region"></a>网络区域

网络区域包含网络站点的集合。 它跨多个地理区域连接网络的各个部分。 例如，如果你的组织在印度有许多站点，则可以选择将“印度”指定为网络区域。 每个网络站点必须与网络区域相关联。

同一网络区域由直接路由的Location-Based路由和增强的紧急服务共享。 如果已为一项功能创建了网络区域，则无需为另一项功能创建新的网络区域。

## <a name="network-site"></a>网络站点

网络站点表示组织有物理场地的位置，例如办公室、一组建筑物或校园。 网络站点定义为 IP 子网的集合。 每个网络站点必须与网络区域相关联。

还可以使用网络站点启用和配置紧急呼叫。

## <a name="network-subnet"></a>网络子网

每个子网必须与特定的网络站点相关联。 客户端的位置基于网络子网和关联的网络站点确定。 可以将多个子网与同一网络站点相关联，但不能将多个站点与同一子网相关联。

子网信息用于确定启动新会话时终结点所在的网络站点。 当会话中每个方的位置已知时，云语音功能可以应用该信息来确定如何处理呼叫设置或路由。

对于每个网络站点，请与网络管理员协作，确定分配给每个网络站点的 IP 子网。 例如，可为北美区域中的纽约站点分配以下 IP 子网：172.29.80.0/23、157.57.216.0/25、172.29.91.0/23、172.29.81.0/24。 如果通常在底特律工作的 Bob 前往纽约办公室接受培训，打开计算机并连接到网络，他的计算机将获得分配给纽约的四个范围之一的 IP 地址，例如 172.29.80.103。

## <a name="trusted-ip-address"></a>受信任的 IP 地址

受信任的 IP 地址是企业网络的 Internet 外部 IP 地址。 在检查特定网站匹配之前，他们确定用户的终结点是否在公司网络内。

如果用户的外部 IP 地址与受信任 IP 地址列表中的 IP 地址匹配，云语音功能将检查以确定用户终结点所在的内部子网。 可以对 IPv4 或 IPv6 IP 地址进行匹配，并依赖于发送到网络设置的 IP 数据包的格式。  (如果公共 IP 地址同时包含 IPv4 和 IPv6，则必须同时添加两者作为受信任的 IP 地址。) 

如果用户的外部 IP 地址与受信任 IP 地址列表中的 IP 地址不匹配，则将终结点分类为位于未知位置。

> [!Important]
> 修改 Teams 客户端的源 IP 地址的云代理服务部署不支持网络配置设置查找。
