---
title: 监视服务器内存容量限制Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
description: 摘要：了解如何监视 Skype for Business Server 中的服务器内存容量Skype for Business Server。
ms.openlocfilehash: df24f96c8fca1927c1222e2bf42981f5cebf7aac
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768700"
---
# <a name="monitor-for-server-memory-capacity-limits-in-skype-for-business-server"></a>监视服务器内存容量限制Skype for Business Server
 
**摘要：** 了解如何监视服务器内存容量限制Skype for Business Server。
  
> [!CAUTION]
> 本主题中有关容量规划的信息仅适用于 Lync 2010 移动客户端和 Mobility Service (Mcx) 。 Lync 2013 移动客户端使用的统一通信 Web API (UCWA) 的容量规划由 Lync Server 2013 规划工具提供。 

> [!NOTE]
> MCX (Mobility Service) 2019 年不再提供对旧版移动客户端Skype for Business Server支持。 所有当前Skype for Business客户端已使用统一通信 Web API (UCWA) 支持即时消息 (IM) 、状态和联系人。 使用 MCX 的旧客户端的用户将需要升级到当前客户端。
  
两个移动性能计数器可帮助您确定当前使用情况，并帮助您规划 Skype for Business Server Mobility Service (Mcx) 的容量，以及监视 UCWA 的内存使用情况。 对于 UCWA，计数器类别为 **LS：WEB - UCWA**。 对于 Mobility Service (Mcx) ，计数器在 **类别 LS：WEB - Mobile Communication Service 下**。 要监视的计数器包括：
  
- **Currently Active Session Count with Active Presence Subscriptions**， which is the current number of endpoints registered through UCWA or the Mobility Service (Mcx) that have active presence subscriptions (number of always-connected mobile users) 
    
- **Currently Active Session Count**， which is the current number of endpoints registered through UCWA or the Mobility Service
    
如果"Currently **Active Session Count with Active Presence Subscriptions"** 和 **"Currently Active Session Count"** 的区别随着时间的推移较小，这意味着大多数移动设备用户都有一个始终连接的设备，例如 Android 或 Nokia 移动设备 (for Mcx) 。 UCWA 始终连接的设备包括运行 Lync 2013 移动客户端的 Apple 和 Android) 。 如果当前 **活动会话计数** 比 Currently **Active Session Count with Active Presence Subscriptions** 要高很多，这表示使用后台终结点设备的用户更多，如 Apple iOS 设备或 mcx Windows Phone设备。  (Windows Phone是注册为此客户端的唯一 Lync 2013 移动) 。
  
您应该根据预期使用情况、容量规划结果以及持续监视 Mobility Service 和其他前端服务器计数器，对 Currently **Active Session Count with Active Presence Subscriptions** 和 Currently Active Session **Count** 性能计数器设置限制。 您设置的限制应使您能够评估服务器容量，在超出容量时发出警报。
  
若要确定适当的限制，您需要首先确定前端服务器上可用于 Mobility Service 的内存量。 根据以下公式，监视计数器以确定何时需要规划额外容量：
  
Mcx Mobility Service (MB) = 164 + (400 + 134) / 1024 * **Currently Active Session Count with Active Presence Subscriptions** + 400 / 1024 * ( **Currently Active Session Count Currently** Active Session Count with Active Presence  -  **Subscriptions**) 
  
> [!IMPORTANT]
> Microsoft Lync Server 2010 容量计算器是一个电子表格，其中预填充了所有公式，使规划器可以确定 Skype for Business 服务器（包括 CPU、内存和硬盘驱动器）的要求。 可以 [下载电子表格和相关文档](https://go.microsoft.com/fwlink/p/?LinkID=212657)。 
  
前端服务器需要足够的可用内存来支持故障转移情况下的移动服务。 您可以使用 **Memory\Available Mbytes** 计数器或使用前面提到的公式来规划预计 Mobility Service 将使用的内存量，以监视前端服务器上当前的可用内存。
  
如果规划预计的移动用户数时，前端服务器上可用的内存量小于 1，500 MB，则需要添加更多硬件以支持 Mobility Service。 有关详细信息，请参阅操作文档中的 Monitor [mobility for performance Skype for Business Server](monitor-mobility-performance.md) in the operations documentation。
  
## <a name="see-also"></a>另请参阅

[监视移动性能以Skype for Business Server](monitor-mobility-performance.md)
