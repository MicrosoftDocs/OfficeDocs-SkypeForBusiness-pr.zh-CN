---
title: 将 Lync 会议室系统设备迁移到 Microsoft 团队聊天室
ms.author: jambirk
author: jambirk
ms.reviewer: sohailta
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: 阅读本主题可了解如何迁移 Lync 会议室系统设备要使用的 Microsoft 团队聊天室软件。
ms.openlocfilehash: 2d9187643d8ffa72a843cbd72a47f4fd4a564f6e
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2019
ms.locfileid: "31013013"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a>将 Lync 会议室系统 (LRS) 设备迁移到 Microsoft 团队聊天室

Skype 会议室系统版本 1 (SR v1) 软件 Lync 会议室系统 (LRS) 设备已达到[2018 年 10 月 9，支持的结束](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018)。 这意味着 Skype 会议室系统 v1 软件将不再能够获取所有产品更新或修补程序不再。 建议使用 Skype 会议室系统 v1 软件的 Lync 会议室系统设备的客户以将其设备升级到 Microsoft 团队聊天室。

Microsoft 团队聊天室软件适用于 Microsoft 团队除了 Skype 业务服务器和联机会议和电话上所有的 Microsoft 团队会议室的服务支持的设备。

您现有设备**可能会**继续工作后的末尾 Skype 会议室系统 v1 软件支持。 但是，如果此软件命中需要释放修复的 Microsoft 软件 bug，它将不支持。 SR v1 使用 TLS 1.0 / 1.1 其 Microsoft 将来将弃用。 您可以了解有关[TLS 1.0/1.1 否决准备](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608)的详细信息。 Microsoft 团队会议室正在添加支持 TLS 1.2，并将继续过 2018 年 10 月 31，工作。 Skype for Business 的本地客户不应禁用 TLS 1.0/1.1，直到 Microsoft 团队聊天室宣布支持 TLS 1.2 无论 TLS 1.0/1.1 否决的一般准则。

## <a name="which-devices-are-affected"></a>哪些设备会受到影响？

下面是此更改影响的设备的列表：

- Crestron RL
- [Crestron RL2](https://www.crestron.com/en-US/Products/Featured-Solutions/Crestron-RL-2)
- [智能会议室系统](https://support.smarttech.com/en/hardware/room-systems-skype)
- [Polycom CX8000](http://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a>升级选项

有多种升级到下一代 Microsoft 团队聊天室 Lync 会议室系统。

### <a name="crestron-hardware-trade-in-program"></a>Crestron 硬件折旧计划

Crestron 将提供升级到[Crestron SR 系统](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr)或等效的所有非 Crestron Lync 会议室系统客户 （例如智能或 Polycom LRS）。 此程序的详细信息，请参阅[此处](https://support.crestron.com/app/answers/answer_view/a_id/1000220)或 <!-- For details, -->[电子邮件](mailto:lrsupgrade@crestron.com)Crestron LRS 支持。  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a>Crestron RL2 升级到 Microsoft 团队聊天室

现有 Crestron RL2 （也称为 Crestron RL200） 客户可以获取升级到 RL3 使用当前 RL2 的升级工具包的每个设备的最小成本。 此程序的详细信息，请参阅[此处](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT)。

### <a name="smart-room-systems-upgrade"></a>智能会议室系统升级

对于智能 LRS 客户，除了 Crestron 硬件折旧计划，智能也正在提供的解决方案升级到 Microsoft 团队聊天室。 向下产品支持的客户，将通过智能技术 Inc.提供此升级。 请参阅有关此[此处](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml)的详细信息。


## <a name="what-should-you-do"></a>怎么办？

我们建议您打算使用上面提到的升级选项的 TLS 1.0/1.1 否决之前 Microsoft 团队 room 更新 Lync 会议室系统设备。 此外，也可以考虑为 Microsoft 团队房间认证的新设备替换现有的设备。 有关详细信息，请参阅[聊天室设备](https://aka.ms/roomdevices)和也看看[Microsoft 团队聊天室要求](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements)。  

> [!NOTE]
> 在 Microsoft 团队聊天室中尚不支持触摸和白板功能。 触摸和白板支持当前计划的 Microsoft 团队聊天室，并将添加到 2019年。

> [!NOTE]
> Microsoft 团队聊天室软件支持与应用程序版本 4.0.64.0 截止 2018 年 12 月 14，TLS 1.2 协议。 对于本地客户为 Microsoft 团队房间 over TLS 1.2 启用通信需要 Skype 业务 Server 2015 累积更新 9 (CU9) 或 Skype 业务 Server 2019 累积更新 1 (CU1)。 更改应不会影响 Skype 的业务联机客户客户端的更改一样向前和向后兼容。
