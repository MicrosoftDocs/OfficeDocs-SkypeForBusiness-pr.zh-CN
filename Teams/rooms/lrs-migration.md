---
title: 将 Lync 会议室系统设备迁移到 Microsoft 团队聊天室
ms.author: v-lanac
author: lanachin
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
description: 阅读本主题，了解如何将 Lync 会议室系统设备迁移到使用 Microsoft 团队聊天室软件。
ms.openlocfilehash: 4aad70c0a91824f0b1eff892aa1940760fc39d39
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41826000"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a>将 Lync 会议室系统（LRS）设备迁移到 Microsoft 团队聊天室

[在2018年10月9日，](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018)具有 Skype 会议室系统版本1（SRS v1）软件的 Lync 会议室系统（LRS）设备已达到支持的结束。 这意味着 Skype Room Systems v1 软件将不再获得任何产品更新或修补程序。 建议安装有 Skype Room System v1 软件的 Lync Room System 设备的用户将其设备升级到 Microsoft Teams 会议室。

Microsoft 团队会议室软件除了适用于 office 的 Skype for business 服务器和在线服务，还可与 Microsoft 团队一起使用，并可在所有 Microsoft 团队会议室支持的设备上通话。

在 Skype 会议室系统 v1 软件支持结束后，您的现有设备**可能会**继续正常工作。 但是，如果此软件点击了需要 Microsoft 发布修补程序的软件 bug，则不受支持。 SRS v1 使用 TLS 1.0/1.1，将来将被 Microsoft 弃用。 你可以了解有关[为 TLS 1.0/1.1 弃用做准备的](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608)详细信息。 

## <a name="which-devices-are-affected"></a>哪些设备受到影响？

下面是受此更改影响的设备的列表：

- Crestron RL
- [Crestron RL2](https://www.crestron.com/Products/Featured-Solutions/Crestron-RL-2)
- [智能房间系统](https://support.smarttech.com/en/hardware/room-systems-skype)
- [Polycom CX8000](http://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a>升级选项

有多个选项可用于将 Lync 聊天室系统升级到下一代 Microsoft 团队聊天室。

### <a name="crestron-hardware-trade-in-program"></a>Crestron 硬件贸易计划

Crestron 将为所有非 Crestron Lync 会议室系统客户（如 Smart 或 Polycom LRS）提供对[CRESTRON SR 系统](https://www.crestron.com/products/featured-solutions/crestron-sr)或等效项的升级。 [在此处](https://support.crestron.com/app/answers/answer_view/a_id/1000220)查看此程序的详细信息或 <!-- For details, -->[电子邮件](mailto:lrsupgrade@crestron.com)Crestron LRS 支持。  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a>Crestron RL2 升级到 Microsoft 团队聊天室

现有的 Crestron RL2 （也称为 Crestron RL200）客户可以获取升级工具包，以便使用每个设备的最低成本将当前 RL2 升级到 RL3。 请[在此处](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT)查看该程序的详细信息。

### <a name="smart-room-systems-upgrade"></a>智能房间系统升级

对于 SMART LRS 客户，除了 Crestron 硬件的使用计划外，还提供了一种解决方案来升级到 Microsoft 团队的会议室。 此升级将由智能技术公司提供给产品支持部门的客户。 请参阅[此处](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml)的详细信息。


## <a name="what-should-you-do"></a>应该怎么办？

我们建议你计划在 TLS 1.0/1.1 弃用之前使用上述升级选项将 Lync 会议室系统设备更新到 Microsoft 团队聊天室。 此外，你还可以考虑将现有设备替换为针对 Microsoft 团队聊天室认证的新设备。 有关详细信息，请参阅[房间设备](https://aka.ms/roomdevices)，还可查看[Microsoft 团队会议室的要求](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements)。  


> [!NOTE]
> Microsoft 团队会议室软件支持的 TLS 1.2 协议，4.0.64.0 应用版本为2018。 对于本地客户，为 Microsoft 团队聊天室启用通过 TLS 1.2 进行通信需要 Skype for business Server 2015 累积更新9（CU9）或 Skype for business 服务器2019累积更新1（CU1）。 更改不应影响 Skype for Business Online 客户，因为客户端更改是向前和向后兼容的。
