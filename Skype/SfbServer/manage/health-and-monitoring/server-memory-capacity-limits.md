---
title: 监控服务器内存容量限制 Skype 业务服务器
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
description: 摘要： 了解如何针对业务服务器监视的 Skype 中的服务器内存容量限制。
ms.openlocfilehash: 249145e0e76377c356082965a76ce8bf3d11af42
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884447"
---
# <a name="monitor-for-server-memory-capacity-limits-in-skype-for-business-server"></a>监控服务器内存容量限制 Skype 业务服务器
 
**摘要：** 了解如何针对业务服务器监视的 Skype 中的服务器内存容量限制。
  
> [!CAUTION]
> 容量规划是指本主题中的信息仅适用于 Lync 2010 移动客户端和 Mobility Service (Mcx)。 由 Lync Server 2013 规划工具提供容量规划的统一通信 Web API (UCWA)，Lync 2013 移动客户端，使用。 

> [!NOTE]
> MCX (Mobility Service) 支持旧的移动客户端的不再可用的业务服务器 2019 Skype 中。 业务移动客户端的所有当前 Skype 已使用统一通信 Web API (UCWA) 来支持即时消息 (IM)、 状态和联系人。 与使用 MCX 的旧客户端的用户需要升级到当前客户端。
  
两个移动性能计数器可以帮助您确定当前使用情况并帮助您规划业务服务器 Mobility Service (Mcx)，以及为 UCWA，监视内存使用量 Skype 的容量。 UCWA，对于计数器类别是**LS:WEB-UCWA**。 对于 Mobility Service (Mcx)，计数器类别为“**LS:WEB - 移动通信服务**”。 要监控的计数器包括：
  
- **Currently Active Session Count with Active Presence Subscriptions**，它是当前通过 UCWA 或 Mobility Service (Mcx) 注册的终结点的数目，这些终结点具有活动状态订阅（始终连接的移动用户的数目）
    
- **Currently Active Session Count**，它是当前通过 UCWA 或 Mobility Service 注册的终结点的数目
    
如果**当前 with Active Presence Subscriptions 的 Active Session Count**和**当前 Active Session Count**之间的差异随着时间的推移小，这意味着大多数移动设备用户具有的始终连接的设备，例如 Android 或Nokia 移动设备 （对于仅 Mcx)。 UCWA 始终连接的设备包括运行 Lync 2013 移动客户端的 Apple 和 Android 设备）。 如果**当前 Active Session Count**是远大于**当前 with Active Presence Subscriptions 的 Active Session Count**，这表明更多用户正在使用背景终结点设备，如 Apple iOS 设备或下的 Windows PhoneMcx。 （Windows Phone 是将注册为此的唯一 Lync 2013 移动客户端）。
  
您应根据您的预期的用法、 容量规划结果和实时监控的**当前 with Active Presence Subscriptions 的 Active Session Count**和**当前 Active Session Count**性能计数器设置限制Mobility Service 和其他前端服务器计数器。 您设置的限制应允许您计算服务器容量并在超出容量时发出警报。
  
若要确定适当的限制，您需要先确定多少内存有 Mobility Service 的前端服务器上可用。 请监控计数器以根据以下公式确定您需要何时规划额外的容量：
  
总内存使用情况 Mcx Mobility Service (MB) = 164 + (400 + 134) / 1024年 ***当前 with Active Presence Subscriptions 的 Active Session Count** + 400 / 1024年 * (**当前 Active Session Count** - **与当前活动会话的计数活动状态订阅**)
  
> [!IMPORTANT]
> Microsoft Lync Server 2010 容量计算器是使用所有启用计划程序，以确定要求将哪些业务服务器，其中包括 CPU、 内存和硬盘驱动器上的 Skype 的公式进行预填充电子表格。 您可以[下载电子表格和关联的文档](https://go.microsoft.com/fwlink/p/?LinkID=212657)。 
  
前端服务器所需内存不足，无法在故障转移的情况下支持 Mobility Service。 通过使用**Memory\Available Mbytes**计数器，或通过使用前面提到的来规划您预期 Mobility Service 若要使用的内存量的计算公式，您可以监视前端服务器上的当前可用内存。
  
如果在前端服务器上的可用内存量低于 1,500 MB 规划预期数量的移动用户时，您需要添加更多的硬件支持 Mobility Service。 有关详细信息，请参阅操作文档中的[Skype 业务服务器中的性能监视器移动](monitor-mobility-performance.md)。
  
## <a name="see-also"></a>另请参阅

[监视移动性的 Skype 业务服务器的性能](monitor-mobility-performance.md)
