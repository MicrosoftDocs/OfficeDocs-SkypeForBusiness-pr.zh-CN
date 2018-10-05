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
ms.openlocfilehash: c87081ccd40765b10929a0d2762d834ce6a1b2ab
ms.sourcegitcommit: 2e11749734ff26b18709a1442b2c417f33430144
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/05/2018
ms.locfileid: "25429450"
---
# <a name="migrate-lync-room-system-lrs-devices-to-skype-room-system-v2"></a>将 Lync 会议室系统 (LRS) 设备迁移到 Skype 会议室系统 v2 
Skype 会议室系统版本 1 (SR v1) 软件 Lync 会议室系统 (LRS) 设备将到达[2018 年 10 月 9，支持的结束](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018)。 这意味着所有产品更新或此日期之后的修补程序，也不会都收到 Skype 会议室系统 v1 软件。 建议使用 Skype 会议室系统 v1 软件的 Lync 会议室系统设备的客户升级其设备到 Skype 会议室系统版本 2 (SR v2)。

Skype 会议室系统版本 2 (SR v2) 软件与除了 Skype 的 Microsoft 团队适用于会议和呼叫所有 SR v2 支持设备上的业务服务器和联机服务。

您现有设备**可能会**继续工作 Skype 会议室系统 v1 软件支持的结束后，直至此软件命中软件 bug 程序需要 Microsoft 释放修复或可能使用情况下，现有的通信协议 Skype 会议室系统v1 软件更改或不再受支持。 此类的一个已知的更改已否决的 TLS 1.0 / 1.1 Microsoft Office 365 中。 您可以了解有关[TLS 1.0/1.1 否决准备](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608)的详细信息。  

## <a name="which-devices-are-affected"></a>哪些设备会受到影响？
下面是此更改影响的设备的列表：
- [智能会议室系统](https://smartkapp.com/products/smart-room-systems)
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
对于智能 LRS 客户，除了 Crestron 硬件折旧计划，Microsoft 和智能还提供解决方案升级到 Skype 会议室系统 v2 工作。 将由智能向所有现有智能 LRS 客户提供此升级。 将年 10 月 2018年在此页上提供此程序的更多详细信息。 请确保更新后的检查。

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
我们建议您打算到之前使用上面提到的升级选项的 TLS 1.0/1.1 否决的 Skype 会议室系统 v2 更新 Lync 会议室系统的设备。 此外，也可以考虑将新设备认证 SR v2 替换为现有的设备。 有关详细信息，请参阅[聊天室设备](https://aka.ms/roomdevices)和也看看[Skype 会议室系统 v2 要求](https://docs.microsoft.com/en-us/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements)。  

> [!NOTE]
> Skype 会议室系统 v2 中尚不支持触摸和白板功能。 触摸和白板支持的 Skype 会议室系统 v2 积压工作中，将被添加到 H1 CY2019。
