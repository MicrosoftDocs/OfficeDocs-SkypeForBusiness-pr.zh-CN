---
title: 将 Lync Room System 设备迁移到 Microsoft Teams 会议室
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: ''
description: 阅读本主题，了解如何迁移 Lync Room System 设备以使用 Microsoft Teams 会议室软件。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d8da14f2d5f3ec75c6a9fb9c03a33d7e83cd1aed
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662617"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a>将 Lync Room System (LRS) 迁移到 Microsoft Teams 会议室

具有 Skype Room System 版本 1 (SRS v1) 软件的 Lync Room System (LRS) 设备于 [2018 年 10](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018)月 9 日终止支持。 这意味着 Skype Room Systems v1 软件将不再获得任何产品更新或修补程序。 建议安装有 Skype Room System v1 软件的 Lync Room System 设备的用户将其设备升级到 Microsoft Teams 会议室。

除了 Skype for Business Server 和 Online 服务外，Microsoft Teams 会议室软件还适用于 Microsoft Teams，用于会议和呼叫所有 Microsoft Teams 会议室支持的设备。

在 Skype会议室系统 v1 软件支持结束后，你的现有设备可能会继续工作。 但是，如果此软件命中需要 Microsoft 发布修补程序的软件 bug，则它将不受支持。 SRS v1 使用 TLS 1.0/ 1.1，将来 Microsoft 将弃用它。 可以详细了解如何准备弃用[TLS 1.0/1.1。](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608) 

## <a name="which-devices-are-affected"></a>哪些设备受影响？

下面是受此更改影响的设备列表：

- Crestron RL
- [Crestron RL2](https://www.crestron.com/Products/Featured-Solutions/Crestron-RL-2)
- [SMART Room 系统](https://support.smarttech.com/en/hardware/room-systems-skype)
- [Polycom CX8000](https://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a>升级选项

有多种选项用于将 Lync Room Systems 升级到下一代 Microsoft Teams 会议室。

### <a name="crestron-hardware-trade-in-program"></a>Crestron 硬件折中程序

对于 Smart 或 Polycom LRS 等所有非 (Lync Room System 客户 [，Crestron 将提供到 Crestron SR](https://www.crestron.com/products/featured-solutions/crestron-sr) 系统的升级或等效) 。 在此处查看此计划 [的详细信息，](https://support.crestron.com/app/answers/answer_view/a_id/1000220) 或 <!-- For details, -->[电子邮件](mailto:lrsupgrade@crestron.com) Crestron LRS 支持。  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a>将 Crestron RL2 升级到 Microsoft Teams 会议室

现有 Crestron RL2 (也称为 Crestron RL200) 客户可以获取升级工具包，以使用每个设备的最低成本将当前 RL2 升级到 RL3。 请在此处查看此计划 [的详细信息](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT)。

### <a name="smart-room-systems-upgrade"></a>SMART Room Systems 升级

对于 SMART LRS 客户，除了使用 Crestron 硬件折中计划外，SMART 还致力于提供升级到 Microsoft Teams 会议室的解决方案。 此升级由 SMART Technologies Inc. 在产品支持下提供给客户。 请在此处查看有关 [此方面更多信息](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml)。


## <a name="what-should-you-do"></a>应该怎么办？

我们建议您计划使用上述升级选项在 TLS 1.0/1.1 弃用之前将 Lync Room System 设备更新到 Microsoft Teams 会议室。 此外，还可以考虑将现有设备替换为通过 Microsoft Teams 会议室认证的新设备。 有关详细信息 [，请参阅](https://aka.ms/roomdevices) 会议室设备，并查看 [Microsoft Teams 会议室要求](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements)。  


> [!NOTE]
> 自 2018 年 12 月 14 日起，Microsoft Teams 会议室软件支持应用版本 4.0.64.0 的 TLS 1.2 协议。 对于本地客户，通过 TLS 1.2 为 Microsoft Teams 会议室启用通信需要 Skype for Business Server 2015 累积更新 9 (CU9) 或 Skype for Business Server 2019 累积更新 1 (CU1) 。 更改不会影响 Skype for Business Online 客户，因为客户端更改是向前和向后兼容的。
