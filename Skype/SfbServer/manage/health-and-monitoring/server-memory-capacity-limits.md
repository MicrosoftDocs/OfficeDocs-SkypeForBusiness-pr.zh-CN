---
title: 在 Skype for Business Server 2015 中针对服务器内存容量限制进行监视
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
description: 摘要： 了解如何监视的服务器内存容量限制在 Skype 业务服务器 2015年。
ms.openlocfilehash: df05cdf43a7f09f49760f9671c900d6a9ea992b1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="monitor-for-server-memory-capacity-limits-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中针对服务器内存容量限制进行监视
 
**摘要：**了解如何监视的服务器内存容量限制在 Skype 业务服务器 2015年。
  
> [!CAUTION]
> 容量规划是指此主题中的信息仅适用于 Lync 2010 移动客户端和移动服务 (Mcx)。 容量规划的统一通信 Web API (UCWA)，使用 Lync 2013 移动客户端，可通过 Lync Server 2013，规划工具。 
  
两个移动性能计数器可帮助您确定当前的使用情况，并帮助您规划产能为 Skype 业务服务器 2015年移动服务 (Mcx) 也为 UCWA，监视内存使用情况。 对于 UCWA，该计数器类别为**LS:WEB-UCWA**。 对于 Mobility Service (Mcx)，计数器类别为“**LS:WEB - 移动通信服务**”。 要监控的计数器包括：
  
- **Currently Active Session Count with Active Presence Subscriptions**，它是当前通过 UCWA 或 Mobility Service (Mcx) 注册的终结点的数目，这些终结点具有活动状态订阅（始终连接的移动用户的数目）
    
- **Currently Active Session Count**，它是当前通过 UCWA 或 Mobility Service 注册的终结点的数目
    
如果随着时间的推移，**当前活动状态订阅使用的活动会话数**和**当前活动会话数**之间的差异很小，这意味着大多数移动设备用户可以始终连接的设备，如 Android 或诺基亚移动设备 （仅 Mcx)。 UCWA 总是连接设备包括苹果和 Android 设备运行 Lync 2013 移动客户端）。 如果**当前活动会话数**要远远高于**当前活动状态订阅使用的活动会话计数**，这表示更多的用户正在使用背景终结点设备，如苹果 iOS 设备或在 Windows PhoneMcx。 （Windows Phone 是将注册为这只 Lync 2013 移动客户端）。
  
您应该根据您预期的用途、 容量规划的结果，并持续监视**当前活动状态订阅使用的活动会话数**和**当前活动会话计数**性能计数器上设置限制移动服务，前端服务器的其他计数器。 您设置的限制应允许您计算服务器容量并在超出容量时发出警报。
  
若要确定适当的限制，您需要首先确定是移动服务的前端服务器上的可用内存量。 请监控计数器以根据以下公式确定您需要何时规划额外的容量：
  
使用通过 Mcx 移动服务 (MB) 的内存总量 = 164 + (400 + 134) / 1024年 ***当前活动状态订阅使用的活动会话数**+ 400 / 1024年 * (**当前活动会话数** - **当前处于活动状态的会话数的活动状态订阅**)
  
> [!IMPORTANT]
> Microsoft Lync 服务器 2010年容量计算器是填入所有的公式，使规划者确定要求将有关业务服务器，包括 CPU、 内存和硬盘的 Skype 是一个电子表格。 您可以[下载该电子表格和相关联的文档](https://go.microsoft.com/fwlink/p/?LinkID=212657)。 
  
前端服务器需要内存不足，无法在故障转移情况下支持移动服务。 通过使用该**Memory\Available 兆字节数**计数器，或通过使用前面提到的计划希望移动服务使用的内存量的计算公式，您可以监视在前端服务器上当前可用的内存。
  
如果在前端服务器上可用的内存量低于 1500 MB 在规划预期的移动用户数量时，您需要添加更多硬件以支持移动服务。 有关详细信息，请参阅[有关业务服务器 2015年的 Skype 的性能监视器移动](monitor-mobility-performance.md)运营文档资料。
  
## <a name="see-also"></a>另请参阅

#### 

[监视业务服务器 2015年的性能在 Skype 的移动性](monitor-mobility-performance.md)

