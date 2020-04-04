---
title: 云语音功能的网络设置
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: 了解您必须为直接路由和增强的紧急服务的基于位置的路由配置的网络设置。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: bc2694760e93579a78cb849cc054d70a65431724
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2020
ms.locfileid: "43139061"
---
# <a name="network-settings-for-cloud-voice-features-in-microsoft-teams"></a>Microsoft 团队中云语音功能的网络设置

了解网络区域、网络站点、网络子网和受信任的 IP 地址。 这些条款和概念在所有云语音文档中用于直接路由和[动态紧急呼叫](configure-dynamic-emergency-calling.md)的[基于位置的路由](location-based-routing-plan.md)。 如果你要在你的组织中部署这些云功能，则必须配置用于 Microsoft 团队中的这些功能的网络设置。

本文简要介绍了基于位置的路由和动态紧急呼叫的常见网络设置。 你可以配置部分或所有这些设置，具体取决于你部署的云语音功能和功能。 有关如何配置这些设置的步骤，请参阅[管理团队中的云功能的网络拓扑](manage-your-network-topology.md)。

> [!NOTE]
> 针对网络设置的任何特定于功能的要求将记录在该功能的配置主题中。

## <a name="network-region"></a>网络区域

网络区域包含网络站点的集合。 它跨多个地理区域互连网络的各个部分。 例如，如果您的组织具有多个位于印度的网站，您可以选择将 "印度" 指定为网络区域。 每个网络站点都必须与一个网络区域相关联。

相同的网络区域由直接路由和增强的紧急服务的基于位置的路由共享。 如果已为一个功能创建了网络区域，则不必为其他功能创建新的网络区域。

## <a name="network-site"></a>网络站点

网络站点表示您的组织有物理场所的位置，如办公室、一组建筑物或校园。 网络站点定义为 IP 子网的集合。 每个网络站点都必须与一个网络区域相关联。

您也可以使用 "网络站点" 启用和配置紧急呼叫。

## <a name="network-subnet"></a>网络子网

每个子网都必须与特定的网络站点相关联。 根据网络子网和关联的网络站点确定客户端的位置。 你可以将多个子网与同一网络站点关联，但不能将多个站点与同一子网相关联。

子网信息用于确定启动新会话时终结点所在的网络站点。 当会话中每个方的位置已知时，云语音功能可以应用该信息来确定如何处理呼叫设置或路由。

对于每个网络站点，请与您的网络管理员协作，确定哪些 IP 子网分配给每个网络站点。 例如，可为北美区域中的纽约站点分配以下 IP 子网：172.29.80.0/23、157.57.216.0/25、172.29.91.0/23、172.29.81.0/24。 如果 Bob 通常在底特律中工作，在中传播到纽约的 office 进行培训，然后在其计算机上连接到网络，他的计算机将在分配给纽约的四个区域之一（例如172.29.80.103）中获取 IP 地址。

## <a name="trusted-ip-address"></a>受信任的 IP 地址

"受信任的 IP 地址" 是企业网络的 internet 外部 IP 地址。 它们确定用户的终结点是否位于企业网络内，然后再检查特定网站匹配项。

如果用户的外部 IP 地址与 "信任的 IP 地址" 列表中的 IP 地址相匹配，则云语音功能将检查以确定用户终结点所在的内部子网。 可以针对 IPv4 或 IPv6 IP 地址进行匹配，取决于发送到网络设置的 IP 数据包的格式。 （如果公共 IP 地址同时具有 IPv4 和 IPv6，则必须将两者都添加为受信任的 IP 地址。）

如果用户的外部 IP 地址与 "受信任的 IP 地址" 列表中的 IP 地址不匹配，则终结点将被分类为未知位置。
