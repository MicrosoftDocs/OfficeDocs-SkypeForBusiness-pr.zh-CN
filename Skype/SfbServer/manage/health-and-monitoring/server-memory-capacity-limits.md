---
title: 监视 Skype for Business 服务器中的服务器内存容量限制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
description: 摘要：了解如何在 Skype for Business 服务器中监视服务器内存容量限制。
ms.openlocfilehash: 4f56fec8f3ed6900f4c4f1a97286dc14b66bb7c8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817701"
---
# <a name="monitor-for-server-memory-capacity-limits-in-skype-for-business-server"></a>监视 Skype for Business 服务器中的服务器内存容量限制
 
**摘要：** 了解如何在 Skype for Business 服务器中监视服务器内存容量限制。
  
> [!CAUTION]
> 本主题中涉及容量规划的信息仅适用于 Lync 2010 移动客户端和移动服务（Mcx）。 Lync 2013 移动客户端使用的统一通信 Web API （UCWA）的容量规划由 Lync Server 2013、计划工具提供。 

> [!NOTE]
> 在 Skype for Business Server 2019 中，MCX （移动服务）对旧式移动客户端的支持不再可用。 所有当前 Skype for business 移动客户端都已使用统一通信 Web API （UCWA）来支持即时消息（IM）、状态和联系人。 具有使用 MCX 的旧客户端的用户将需要升级到当前客户端。
  
两个移动性能计数器可帮助你确定当前使用情况并帮助你规划 Skype for Business Server 移动服务（Mcx）的容量，以及监视 UCWA 的内存使用情况。 对于 UCWA，计数器类别为**LS： WEB-UCWA**。 对于 Mobility Service (Mcx)，计数器类别为“**LS:WEB - 移动通信服务**”。 要监控的计数器包括：
  
- **Currently Active Session Count with Active Presence Subscriptions**，它是当前通过 UCWA 或 Mobility Service (Mcx) 注册的终结点的数目，这些终结点具有活动状态订阅（始终连接的移动用户的数目）
    
- **Currently Active Session Count**，它是当前通过 UCWA 或 Mobility Service 注册的终结点的数目
    
如果**当前活动的会话计数与活动状态订阅**和**当前活动会话计数**之间的差异在一段时间内较小，这意味着大多数移动设备用户都有一个一直连接的设备，例如 Android 或 Nokia 移动设备（仅限 Mcx）。 UCWA 始终连接的设备包括运行 Lync 2013 移动客户端的 Apple 和 Android 设备。 如果**当前处于活动状态的会话计数**比**当前处于活动状态订阅的当前活动会话计数**高得多，这表示更多用户正在使用后台终结点设备，如 Apple iOS 设备或 Mcx 下的 Windows Phone。 （Windows Phone 是唯一将注册为此的 Lync 2013 移动客户端）。
  
你应根据预期使用情况、容量计划结果和持续监视移动服务和其他前端服务器计数器，对**当前处于活动状态的会话计数**和**当前活动的会话计数**性能计数器设置限制。 您设置的限制应允许您计算服务器容量并在超出容量时发出警报。
  
若要确定相应的限制，需要首先确定移动服务前端服务器上的可用内存量。 请监控计数器以根据以下公式确定您需要何时规划额外的容量：
  
Mcx 移动服务（MB）使用的总内存 = 164 + （400 + 134）/1024 ***当前处于活动状态订阅的活动会话计数**+ 400/1024 * （**当前处于活动** - 状态订阅的活动会话计数当前处于活动**状态的订阅**）
  
> [!IMPORTANT]
> Microsoft Lync Server 2010 容量计算器是预填充了所有公式的电子表格，它使 planner 能够确定 Skype for business 服务器（包括 CPU、内存和硬盘）的要求。 您可以[下载电子表格和关联的文档](https://go.microsoft.com/fwlink/p/?LinkID=212657)。 
  
前端服务器需要足够的可用内存才能在故障转移情况下支持移动服务。 你可以通过使用**Memory\Available mb**计数器来监视前端服务器上的当前可用内存，也可以使用前面提到的公式来规划你希望移动服务使用的内存量。
  
如果在针对预期的移动用户数进行规划时前端服务器上可用的内存量小于 1500 MB，则需要添加更多硬件来支持移动服务。 有关更多详细信息，请参阅操作文档中的 Skype for business 服务器中的[监视器性能移动](monitor-mobility-performance.md)。
  
## <a name="see-also"></a>另请参阅

[监视移动版 Skype for business 服务器的性能](monitor-mobility-performance.md)
