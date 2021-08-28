---
title: 云语音功能的网络设置
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: 了解必须为直接路由和增强型紧急Location-Based路由配置的网络设置。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
- m365initiative-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 425f453e5e1b7f90b1486aa35d09f7919e0c33b4
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580216"
---
# <a name="network-settings-for-cloud-voice-features-in-microsoft-teams"></a>云语音功能的网络设置Microsoft Teams

了解网络区域、网络站点、网络子网和受信任的 IP 地址。 这些术语和概念将在整个云语音文档中用于 [直接](location-based-routing-plan.md) 路由和动态紧急呼叫的基于位置 [的路由](configure-dynamic-emergency-calling.md)。 如果要在组织中部署这些云功能，则必须配置网络设置，以与 Microsoft Teams 中的这些功能一Microsoft Teams。

本文概述了路由和动态紧急呼叫Location-Based网络设置。 根据要部署的云语音功能，可以配置其中一些或所有设置。 有关配置这些设置的步骤，请参阅[管理](manage-your-network-topology.md)云功能的网络拓扑Teams。

> [!NOTE]
> 该功能的配置主题中记录了网络设置的任何特定于功能的要求。

## <a name="network-region"></a>网络区域

网络区域包含网络站点的集合。 它跨多个地理区域互连网络的各个部分。 例如，如果您的组织有许多位于印度的网站，您可以选择将"印度"指定为网络区域。 每个网络站点必须与网络区域相关联。

同一网络区域由直接路由Location-Based增强型紧急服务的路由共享。 如果已针对一项功能创建了网络区域，则不必为另一项功能创建新的网络区域。

## <a name="network-site"></a>网络站点

网络网站表示组织具有物理场所的位置，例如办公室、一组建筑物或校园。 网络站点定义为 IP 子网的集合。 每个网络站点必须与网络区域相关联。

您也可以使用网络站点来启用和配置紧急呼叫。

## <a name="network-subnet"></a>网络子网

每个子网必须与特定的网络站点相关联。 根据网络子网和关联的网络站点确定客户端的位置。 可以将多个子网与同一网络站点关联，但不能将多个站点与同一子网关联。

子网信息用于确定启动新会话时终结点所在的网络站点。 当知道会话中每一方的位置时，云语音功能可以应用该信息来确定如何处理呼叫设置或路由。

对于每个网络站点，请与网络管理员合作，确定哪些 IP 子网分配给每个网络站点。 例如，可为北美区域中的纽约站点分配以下 IP 子网：172.29.80.0/23、157.57.216.0/25、172.29.91.0/23、172.29.81.0/24。 如果常在 Office 中工作的 Bob 前往纽约办公室接受培训，打开他的计算机并连接到网络，则他的计算机将获取分配给纽约四个范围之一的 IP 地址，例如 172.29.80.103。

## <a name="trusted-ip-address"></a>受信任的 IP 地址

受信任的 IP 地址是企业网络的 Internet 外部 IP 地址。 在检查特定站点匹配之前，确定用户的终结点是否位于企业网络内部。

如果用户的外部 IP 地址与受信任的 IP 地址列表中的 IP 地址匹配，云语音功能会检查以确定用户终结点所在的内部子网。 可以针对 IPv4 或 IPv6 IP 地址进行匹配，并且取决于发送到网络设置的 IP 数据包的格式。  (如果公共 IP 地址同时具有 IPv4 和 IPv6，则必须将两者添加为受信任的 IP 地址.) 

如果用户的外部 IP 地址与受信任的 IP 地址列表中的 IP 地址不匹配，则终结点被分类为位于未知位置。

> [!Important]
> 修改源 IP 地址的云代理服务部署不支持网络配置设置查找Teams客户端。
