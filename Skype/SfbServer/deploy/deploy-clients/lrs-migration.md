---
title: 将 Lync 会议室系统设备迁移到 Skype 会议室系统版本 2
ms.author: jambirk
author: jambirk
ms.reviewer: sohailta
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ''
description: 阅读本主题可了解如何迁移 Lync 会议室系统设备使用 Skype 会议室系统 v2 软件。
ms.openlocfilehash: 9436c5a843f21b9913c0dbcbed6e62df8ef62ce2
ms.sourcegitcommit: e53749714dcde9f7b184d5ef554bffbc77f54267
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2019
ms.locfileid: "28729405"
---
# <a name="migrate-lync-room-system-lrs-devices-to-skype-room-system-v2"></a>将 Lync 会议室系统 (LRS) 设备迁移到 Skype 会议室系统 v2 
Skype 会议室系统版本 1 (SR v1) 软件 Lync 会议室系统 (LRS) 设备已达到[2018 年 10 月 9，支持的结束](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018)。 这意味着 Skype 会议室系统 v1 软件将不再能够获取所有产品更新或修补程序不再。 建议使用 Skype 会议室系统 v1 软件的 Lync 会议室系统设备的客户升级其设备到 Skype 会议室系统版本 2 (SR v2)。

Skype 会议室系统版本 2 (SR v2) 软件与除了 Skype 的 Microsoft 团队适用于会议和呼叫所有 SR v2 支持设备上的业务服务器和联机服务。

您现有设备**可能会**继续工作后的末尾 Skype 会议室系统 v1 软件支持。 但是，如果此软件命中需要释放修复的 Microsoft 软件 bug，它将不支持。 SR v1 使用 TLS 1.0 / 1.1 其 Microsoft 在将来将弃用。 您可以了解有关[TLS 1.0/1.1 否决准备](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608)的详细信息。 Skype 会议室系统 V2 正在添加支持 TLS 1.2 和将继续过 2018 年 10 月 31，工作。 在内部部署客户业务的 Skype 不应禁用 TLS 1.0/1.1 Skype 会议室系统 V2 annouces 支持 TLS 1.2 无论 TLS 1.0/1.1 否决的一般准则。

## <a name="which-devices-are-affected"></a>哪些设备会受到影响？
下面是此更改影响的设备的列表：
- [智能会议室系统](https://support.smarttech.com/en/hardware/room-systems-skype)
- [Crestron RL2](https://www.crestron.com/en-US/Products/Featured-Solutions/Crestron-RL-2)
- [Polycom CX8000](http://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)
- Crestron RL

## <a name="upgrade-options"></a>升级选项
有多个选项下一代 Skype 会议室系统 (SR v2) 的升级 Lync 会议室系统。

### <a name="crestron-hardware-trade-in-program"></a>Crestron 硬件折旧计划
Crestron 将为所有非 Crestron Lync 会议室系统客户[Crestron SR 系统](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr)或等效提供升级。 此程序的详细信息，请参阅[此处](https://support.crestron.com/app/answers/answer_view/a_id/1000220)或<!-- For details, -->[电子邮件](mailto:lrsupgrade@crestron.com)Crestron LRS 支持。  


### <a name="crestron-rl2-upgrade-to-srs-v2"></a>Crestron RL2 升级到 SR V2
现有 Crestron RL2 （也称为 Crestron RL200） 客户可以获取升级到 RL3 使用当前 RL2 的升级工具包的每个设备的最小成本。 此程序的详细信息，请参阅[此处](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT)。 


### <a name="smart-room-systems-upgrade"></a>智能会议室系统升级 
对于智能 LRS 客户，除了 Crestron 硬件折旧计划，Microsoft 和智能还提供解决方案升级到 Skype 会议室系统 v2 工作。 将通过智能技术 Inc.提供此升级请参阅有关此[此处](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml)的详细信息。

  
若要使用此选项，但是所示，客户必须另外购买[Logitech 屏幕共享](https://www.logitech.com/en-us/product/screen-share)适配器。 Microsoft 将提供有关如何与 Skype 会议室系统 v2 软件一起使用此适配器的说明。 


查找有关此页上的升级说明回来。 
  
### <a name="summary-of-upgrade-options"></a>升级选项摘要
下表列出的所有可用选项的现有 LRS 设备的摘要：

## <a name="what-should-you-do"></a>怎么办？
我们建议您打算到之前使用上面提到的升级选项的 TLS 1.0/1.1 否决的 Skype 会议室系统 v2 更新 Lync 会议室系统的设备。 此外，也可以考虑将新设备认证 SR v2 替换为现有的设备。 有关详细信息，请参阅[聊天室设备](https://aka.ms/roomdevices)和也看看[Skype 会议室系统 v2 要求](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements)。  

> [!NOTE]
> Skype 会议室系统 v2 中尚不支持触摸和白板功能。 触摸和白板支持的 Skype 会议室系统 v2 积压工作中，将被添加到 H1 CY2019。

> [!NOTE]
> Skype 会议室系统 V2 软件应用程序版本 4.0.64.0 以来 2018 年 12 月 14，支持 TLS 1.2 协议。 对于在内部部署客户通讯 over TLS 1.2 启用 Skype 会议室系统 V2 需要 Skype 业务 2015 Cummulative 更新 9 (CU9) 或 Skype Buisness 2019 Cummulative 更新 1 (CU1)。 更改应不可知到 Skype 业务联机客户的客户端的更改一样向前和向后兼容。 
