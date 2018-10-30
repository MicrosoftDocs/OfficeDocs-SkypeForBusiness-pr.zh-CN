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
ms.openlocfilehash: 7fa1b9986f16082a7e86390e5c2c94d255076cae
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2018
ms.locfileid: "25839028"
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


### <a name="crestron-rl2-to-rl3"></a>到 RL3 Crestron RL2
现有 Crestron RL2 （也称为 Crestron RL200） 客户可以获取升级到 RL3 使用当前 RL2 升级程序包的每个设备的最小成本。 此程序的详细信息，请参阅[此处](https://support.crestron.com/app/answers/answer_view/a_id/1000220)或<!-- For details, -->[电子邮件](mailto:lrsupgrade@crestron.com)Crestron LRS 支持。  


### <a name="smart-room-systems-upgrade"></a>智能会议室系统升级 
对于智能 LRS 客户，除了 Crestron 硬件折旧计划，Microsoft 和智能还提供解决方案升级到 Skype 会议室系统 v2 工作。 将通过智能技术 Inc.提供此升级请参阅有关此[此处](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml)的详细信息。

<!--  
For later 
### Do-It-Yourself
A Do-It-Yourself option is also available for customers with upgrade to Windows 10 and Skype Room Systems v2 software. Windows 10 Enterprise Licenses are available through [approved resellers](https://www.microsoft.com/en-us/Licensing/how-to-buy/how-to-buy.aspx) and Skype Room System V2 software will be available through this guide. 
 
  
To use this option however, customers must additionaly buy a [Logitech Screen Share](https://www.logitech.com/en-us/product/screen-share) adapter. Microsoft will provide instructions on how to use this adapter with Skype Room System v2 software. 


Look for upgrade instructions on this page shortly. 
  
### Summary of upgrade options
This table lists summary of all available options for existing LRS devices:
<!--  For later 
| Upgrade Option | SMART Room Systems | Crestron RL2 | Polycom CX8000 | Crestron RL |
|:--- |:--- |:--- |:--- |:--- |
|**Crestron hardware </br>Trade-in program**|Available|Available|Available|Available|
|**Crestron RL3**|Not Available|Available|Not Available|Not Available|
|**Do-It-Yourself**|Available|Not Available|Not Available|Not Available|
| | | | | |
-->

## <a name="what-should-you-do"></a>怎么办？
我们建议您打算到之前使用上面提到的升级选项的 TLS 1.0/1.1 否决的 Skype 会议室系统 v2 更新 Lync 会议室系统的设备。 此外，也可以考虑将新设备认证 SR v2 替换为现有的设备。 有关详细信息，请参阅[聊天室设备](https://aka.ms/roomdevices)和也看看[Skype 会议室系统 v2 要求](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements)。  

> [!NOTE]
> Skype 会议室系统 v2 中尚不支持触摸和白板功能。 触摸和白板支持的 Skype 会议室系统 v2 积压工作中，将被添加到 H1 CY2019。

> [!NOTE]
> Skype 会议室系统 V2 软件当前不支持 TLS 1.2 协议。 TLS 1.2 支持正在处理，并且将在 TLS 1.0/1.1 否决之前完成。 客户升级到 SR v2 运行 SR v2 应用程序的最新版本的会议室设备上将不会看到 TLS 1.0/1.1 否决任何的影响。 在内部部署客户业务的 Skype 不应禁用 TLS 1.0/1.1 Skype 会议室系统 V2 annouces 支持 TLS 1.2。 
