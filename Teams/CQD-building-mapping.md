---
title: " (CQD) 创建通话质量仪表板的构建地图"
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: 了解如何创建可用于在通话质量仪表板 (CQD) 中上载租户和生成数据的构建地图。
ms.openlocfilehash: 890e5e9b394cf8b600e635014c90ebb9053a1e07
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "46584031"
---
# <a name="create-a-building-map-for-call-quality-dashboard-cqd"></a> (CQD) 创建通话质量仪表板的构建地图

在 Microsoft 团队或 Skype for business Online 部署中，所有客户端都是外部客户端。 因此，默认情况下，所有客户在呼叫质量仪表板 (CQD) 中报告为外部，无论客户是否连接到内部公司网络。

使用 CQD 时，你需要知道终结点的位置以及它是否已连接到你可以管理的网络或无法管理的网络，假定你只能改进你可以管理的网络。 通过将子网和生成信息上载到 CQD，你可以启用 CQD 以确定终结点是连接到内部 (托管) 网络还是外部 (非托管) 网络。 这就是为您的组织创建建筑地图并[将其上传到 CQD](CQD-upload-tenant-building-data.md)非常重要的原因。

## <a name="building-mapping-tools"></a>构建地图工具

可通过多种方式来映射组织的子网。 如果需要帮助，您可以使用此[博客文章](https://aka.ms/cqdtools)中介绍的 CQDTools PowerShell 模块。 这些工具基于 PowerShell，并使用 Active Directory (AD) 网站和服务以及 Microsoft DHCP 服务来帮助预填充你的构建文件。 这些工具将帮助你执行以下任务：

1. 查询广告网站和服务，并基于其中包含的信息创建构建文件。
1. 查询 Microsoft DHCP 服务器或服务器以提取子网信息并自动创建构建文件。
1. 验证现有生成文件、检查重复项和重叠。
1. 在 CQD 中查找未映射的子网。

## <a name="related-topics"></a>相关主题

[在 CQD 中上载租户和构建数据](CQD-upload-tenant-building-data.md)