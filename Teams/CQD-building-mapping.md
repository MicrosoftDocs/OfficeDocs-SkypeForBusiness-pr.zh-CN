---
title: 为调用质量仪表板 (CQD) 创建生成映射
author: CarolynRowe
ms.author: crowe
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
description: 了解如何创建可用于在调用质量仪表板 (CQD) 中上传租户和生成数据的生成映射。
ms.openlocfilehash: 71d1872bbd81769f9a49f4ca9f6ac9aae641252f
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789817"
---
# <a name="create-a-building-map-for-call-quality-dashboard-cqd"></a>为调用质量仪表板 (CQD) 创建生成映射

在 Microsoft Teams 或 Skype for Business Online 部署中，所有客户端都是外部客户端。 因此，默认情况下，所有客户端在呼叫质量仪表板 (CQD) 中报告为外部，而不管客户端是否在内部企业网络上连接。

使用 CQD 时，需要知道终结点的位置，以及终结点是连接到可以管理的网络还是无法管理的网络，假设只能改进可管理的网络。 通过将子网和生成信息上传到 CQD，可让 CQD 确定终结点是连接到内部 (托管) 网络还是外部 (非托管) 网络。 因此，请务必为组织创建生成映射并 [将其上传到 CQD](CQD-upload-tenant-building-data.md)。

## <a name="building-mapping-tools"></a>生成映射工具

可通过多种方式映射组织的子网。 如果需要帮助，可以使用此 [博客文章](https://aka.ms/cqdtools)中所述的 CQDTools PowerShell 模块。 这些工具基于 PowerShell，并使用 Active Directory (AD) 站点和服务以及 Microsoft DHCP 服务来帮助预填充生成文件。 这些工具将有助于完成以下任务：

1. 查询 AD 站点和服务，并根据其中包含的信息创建生成文件。
1. 查询 Microsoft DHCP 服务器或服务器以拉取子网信息并自动创建生成文件。
1. 验证现有生成文件，检查重复和重叠。
1. 在 CQD 中查找未映射的子网。

## <a name="related-topics"></a>相关主题

[在 CQD 中上传租户和生成数据](CQD-upload-tenant-building-data.md)