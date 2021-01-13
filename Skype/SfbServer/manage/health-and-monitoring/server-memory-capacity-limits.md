---
title: 监视 Skype for Business Server 中的服务器内存容量限制
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
description: 摘要：了解如何监视 Skype for Business Server 中的服务器内存容量限制。
ms.openlocfilehash: f1423d840fdf690332081a8083617c3a072b373c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814292"
---
# <a name="monitor-for-server-memory-capacity-limits-in-skype-for-business-server"></a>监视 Skype for Business Server 中的服务器内存容量限制
 
**摘要：** 了解如何监视 Skype for Business Server 中的服务器内存容量限制。
  
> [!CAUTION]
> 本主题中有关容量规划的信息仅适用于 Lync 2010 移动客户端和 Mobility Service (Mcx) 。 Lync 2013 移动客户端使用的统一通信 Web API (UCWA) 的容量规划由 Lync Server 2013 规划工具提供。 

> [!NOTE]
> SKYPE (Server 2019 中不再提供对) 移动客户端的 MCX 移动服务支持。 所有当前的 Skype for Business 移动客户端已使用统一通信 Web API (UCWA) 来支持即时消息 (IM) 、状态和联系人。 使用 MCX 的旧客户端的用户将需要升级到当前客户端。
  
两个移动性能计数器可以帮助您确定当前使用情况，并帮助您规划 Skype for Business Server Mobility Service (Mcx) 的容量，以及监视 UCWA 的内存使用情况。 对于 UCWA，计数器类别为 **LS：WEB - UCWA。** 对于 Mobility Service (Mcx) ，计数器在 **类别 LS：WEB - Mobile Communication Service 下**。 要监视的计数器包括：
  
- **Currently Active Session Count with Active Presence Subscriptions，** which is the current number of endpoints registered through UCWA or the Mobility Service (Mcx) that have active presence subscriptions (number of always-connected mobile users) 
    
- **Currently Active Session Count**， which is the current number of endpoints registered through UCWA or the Mobility Service
    
如果当前 Active **Session Count with Active Presence Subscriptions** 和 Currently Active Session **Count** 的差值随着时间的推移较小，这意味着大多数移动设备用户都有始终连接的设备，例如 Android 或 Nokia 移动设备 (for Mcx) 。 UCWA 始终连接的设备包括运行 Lync 2013 移动客户端的 Apple 和 Android) 。 如果当前 **活动会话计数** 比具有 **活动** 状态订阅的"当前活动会话计数"要高很多，则表明使用后台终结点设备（如 Apple iOS 设备或 Mcx 下的 Windows Phone）的用户更多。  (Windows Phone 是唯一一个将注册为此客户端的 Lync 2013 移动) 。
  
应基于预期使用情况、容量规划结果以及持续监控 Mobility Service 和其他前端服务器计数器，对具有 **活动** 状态订阅的"当前活动会话计数"和"当前 **活动** 会话计数"性能计数器设置限制。 您设置的限制应使您能够评估服务器容量，并当超出容量时发出警报。
  
若要确定适当的限制，您需要首先确定 Mobility Service 的前端服务器上可用的内存量。 根据以下公式，监视计数器以确定何时需要规划额外容量：
  
Mcx Mobility Service (MB) = 164 + (400 + 134) / 1024 * **Currently Active Session Count with Active Presence Subscriptions** + 400 / 1024 * ( Currently Active Session **Count** Currently Active Session Count with Active  -  **Presence Subscriptions**) 
  
> [!IMPORTANT]
> Microsoft Lync Server 2010 容量计算器是一个电子表格，它预填充了所有公式，使规划器可以确定 Skype for Business 服务器（包括 CPU、内存和硬盘驱动器）的要求。 您可以 [下载电子表格和关联的文档](https://go.microsoft.com/fwlink/p/?LinkID=212657)。 
  
前端服务器需要足够的可用内存来支持故障转移情况下的移动服务。 您可以使用 **Memory\Available Mbytes** 计数器或使用前面提到的公式来规划预计 Mobility Service 使用的内存量，以监视前端服务器上当前的可用内存。
  
如果规划预计的移动用户数时，前端服务器上可用的内存量小于 1，500 MB，则需要添加更多硬件以支持 Mobility Service。 有关详细信息，请参阅操作文档中的 ["监视 Skype for Business Server](monitor-mobility-performance.md) 中的移动性能"。
  
## <a name="see-also"></a>另请参阅

[监视 Skype for Business Server 中的移动性能](monitor-mobility-performance.md)
