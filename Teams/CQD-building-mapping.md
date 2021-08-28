---
title: '为 CQD 呼叫质量仪表板创建 (地图) '
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: 了解如何在 CQD 仪表板的呼叫质量仪表板中创建可用于上传租户和 (建筑物) 。
ms.openlocfilehash: a119324090d05b593eb1ed66f41efbb7a5bd7a0a
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58634096"
---
# <a name="create-a-building-map-for-call-quality-dashboard-cqd"></a>为 CQD 呼叫质量仪表板创建 (地图) 

在 Microsoft Teams 或 Skype for Business Online 部署中，所有客户端都是外部客户端。 因此，默认情况下，在呼叫质量仪表板 (CQD) 中，所有客户端都报告为外部，而不考虑客户端是否已在内部公司网络上连接。

使用 CQD 时，需要知道终结点的位置以及终结点是否已连接到可以管理的网络或无法管理的网络，前提是只能改进可以管理的网络。 将子网和生成信息上传到 CQD 后，可让 CQD 确定终结点是连接到内部 (托管) 网络还是外部 (非托管) 网络。 正因如此，为组织创建建筑地图并将其上传到 [CQD 非常重要](CQD-upload-tenant-building-data.md)。

## <a name="building-mapping-tools"></a>构建地图工具

有许多方法可以映射组织的子网。 如果需要帮助，可以使用此博客文章 中所述的 CQDTools PowerShell [模块](https://aka.ms/cqdtools)。 这些工具基于 PowerShell，使用 Active Directory (AD) 站点和服务以及 Microsoft DHCP 服务来帮助预填充生成文件。 这些工具可帮助完成以下任务：

1. 查询 AD 站点和服务，并基于其中包含的信息创建一个建筑物文件。
1. 查询 Microsoft DHCP 服务器以拉取子网信息并自动创建一个建筑物文件。
1. 验证现有建筑物文件，检查重复项和重叠。
1. 在 CQD 中查找未映射的子网。

## <a name="related-topics"></a>相关主题

[Upload CQD 中构建租户和建筑物数据](CQD-upload-tenant-building-data.md)