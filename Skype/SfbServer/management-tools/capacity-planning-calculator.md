---
title: Skype for Business Server 容量规划计算器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/1/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bc4d93b1-0c38-4bf8-8b65-692ff3e2446d
description: 摘要：如何使用容量计算器工具。
ms.openlocfilehash: 1bb1c9cde82c1f2d6e487c3bc28520b630d59210
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031076"
---
# <a name="skype-for-business-server-capacity-planning-calculator"></a>Skype for Business Server 容量规划计算器
 
**摘要：** 如何使用容量计算器工具。

> [!NOTE]
> 本文引用 Skype for business Server 2015 下载，但它适用于：
> - Skype for Business Server 2019。
> - Skype for Business Server 2015。
  
[Skype For Business server 2015 容量计算器](https://www.microsoft.com/download/details.aspx?id=51196)和[Skype for Business Server 2019 容量计算器](https://www.microsoft.com/download/details.aspx?id=57509)增强了[skype for business 规划工具](https://www.microsoft.com/download/details.aspx?id=50357)和部署文档（[规划 Skype For business server 2015 部署](../plan-your-deployment/plan-your-deployment.md)并[规划 skype for business server 2019 部署](../../SfBServer2019/plan/plan-your-deployment-2019.md)）。 在您查看指南并使用规划工具创建推荐的拓扑之后，使用计算器。
  
Skype for Business Server 容量计算器可帮助您根据您的组织使用的用户数和通信工具来确定服务器要求。 确定您的用户配置文件和要为用户启用的功能之后，请使用计算器确定所需的服务器、内存和带宽的数量。 此版本的计算器不会提供磁盘 i/o 要求指南。
  
如果您具有有关特定用户配置文件的准确、详细信息，则可以从计算器中获益最多。 例如，启用了语音的用户的百分比、每个用户每小时平均呼叫数、呼叫持续时间以及会议中并发用户的百分比可能会对服务器的要求产生巨大的影响。 计算器所创建的建议的准确性取决于您提供的信息的准确性。
  
在使用规划工具和容量规划计算器后，应模拟建议和计划的负载，以确保已充分设置 Skype for business Server。 若要在模拟负载下执行压力测试，请使用 Skype for business [Server 压力和性能工具](https://technet.microsoft.com/library/mt631400.aspx)中记录的[Skype For business Server 压力和性能工具](https://www.microsoft.com/download/details.aspx?id=50367)。
  
## <a name="using-the-capacity-calculator"></a>使用容量计算器

计算器是 Microsoft Excel 电子表格。 您的输入单元格的颜色为橙色。 默认值在单元格中输入（对于在具有十二台前端服务器的一个池中的 Skype for Business Server 2015、80000用户），而对于 Skype for Business Server 2019，则使用一个池中的106000用户进行16台前端服务器，但应将这些值更改为满足组织的需求。
  
使用模型包含以下部分。 若要计算您的容量要求，请按照工作表顶部的说明输入数据，并逐行工作： 
  
 **即时消息和状态**
  
- 在 "**用户数**" 下，键入将一次性登录的用户数。 此数字通常为已设置的用户总数的80%。 在大多数情况下，将对100% 的并发用户启用 IM 和状态。 默认值为80000（适用于 Skype for business Server 2015）和106000适用于 Skype for business Server 2019 的用户。
    
- **联系人列表中的平均联系人数**表示用于验证您的系统要求的联系人数量。 此号码是固定的，不是应该更改的内容。
    
  **企业语音**
  
- 在 "**启用企业语音的用户**" 中，键入启用了企业语音的用户的百分比。 默认值为60%。 
    
- 在 "每个**用户每小时的平均呼叫数（峰值）**" 中，键入预计在高峰负载期间平均用户参与的每小时的呼叫数。 默认值为 4。 
    
- 在 "**使用媒体旁路的呼叫百分比**" 中，键入用户发出的将绕过中介服务器的呼叫百分比。 默认值为65%，但如果分散在不同地理位置或拥有在家工作的大量用户，则可能会降低。
    
- 在**与 uc-pstn 呼叫相关的语音用户的百分比**中，键入组织的呼叫的百分比，即 UC-pstn 电话呼叫。 默认值为60%。
    
- **Uc-uc 呼叫中涉及的语音用户所占的百分比**显示为企业语音启用的、仅对 uc uc 呼叫启用的用户的百分比。 根据**为 UC-PSTN 呼叫启用的语音用户百分比**输入的内容计算此数字。 
    
  **会议**
  
- 在 "**并发会议的用户百分比**" 中，键入将同时参与会议的用户的百分比。 默认值为5%。 
    
- 在 "**仅限组 IM （无语音）的会议百分比**" 中，键入将仅涉及即时消息且不包含音频的会议所占的百分比。 默认值为10%
    
- 在**使用电话拨入式会议的用户百分比**中，键入会议中一次使用电话拨入式会议的参与者的百分比。 默认值为15%。
    
- 在 "**使用语音的会议百分比**" 中，键入将包含音频的会议所占的百分比。 
    
  - 如果20% 的语音会议也将包含常规视频，请选中 "**包含视频（无多视图）** " 复选框。
    
  - 如果20% 的会议也将包含多视图视频，请选中 "**包含多个视图**" 复选框。
    
  - 如果50% 的语音会议也将包含应用程序共享，请选中 "**包括应用程序共享**" 复选框。
    
  - 如果20% 的语音会议包括数据上载（如 PowerPoint 演示文稿），请选中 "**包括 web 会议**" 复选框。
    
  **移动性**
  
- 在 "**已启用移动性的用户百分比**" 中，键入将启用使用移动设备连接到 Skype For business Server 的用户的百分比。 默认值为40%。 
    
输入所有必要的信息后，容量计算器估计您的要求。 黄色单元格根据在 Skype for Business Server 性能实验室中执行的测试，显示 CPU、内存和带宽要求的计算值。 这些数字作为指南提供，并不是每个单独的变体都经过测试和验证。 将计算以下值： 
  
- **前端 cpu**：如果整个负载与测试中使用的服务器具有相同规范的一台前端服务器的处理，则 cpu 使用率的百分比（请参阅本文末尾的说明）。
    
- **网络（以 mbps**为单位）：带宽要求对应工作负载的带宽要求为每秒兆位（Mbps）。
    
- **内存（gb**）：针对相应工作负荷的内存，以千兆字节（GB）为单位。
    
绿色单元格显示有关您输入的使用情况模型的建议。 
  
- **前端服务器总数**：所需的物理服务器数基于运行 Skype For business server 2015 的专用服务器，使用双处理器、hex-core、2260兆周期或 Skype For business server 2019 与 Intel 2673 v3、双处理器、hex-core。
    
    请注意，建议启用超线程，并已证明可提高支持音频/视频的服务器的性能。
    
- **边缘服务器**：根据所有并发用户通过边缘服务器通信时所需的边缘服务器的数量。 计算器中不能更改此百分比。 
    
- **存档/呼叫详细记录/高级服务存储**：存档或监控功能所需的存储数量（如果在组织中已启用）。
    
- **必需的后端数据库服务器（需要池）**：支持所选工作负荷所需的后端数据库服务器的数量。
    
此外，在前端服务器总数的第一行中，提供了有关服务器和网络上的负载的更多信息，用于组合所有计划的工作负载。
  
- **平均 Cpu 负载**：每个前端服务器的平均 cpu 使用率。
    
- **网络（以 Mbps 为单位**）：支持所需的带宽分配以支持您输入的使用模式。
    
- **内存（gb**）：每个前端服务器所需的内存（以 gb 为单位）。
    
### <a name="adjusting-for-your-processors"></a>针对处理器进行调整

电子表格中的所有 CPU 使用情况图假定每个 Skype for Business Server 2015 服务器都具有双处理器、16 GHz 16 2.26 进制的内存、至少有 32 GB 的内存以及8个或更多个至少具有 72 GB 可用磁盘空间的 10000 RPM 硬盘。 对于每个 Skype for Business Server 2019 服务器，电子表格中的所有 CPU 使用情况图都会假定每台服务器都有双处理器、hex-core 和英特尔至强 2673 v3、至少 64 GB 的内存以及至少有 72 GB 可用磁盘的8个或更多 10000 RPM 的硬盘驱动器复杂.
  
如果你的服务器具有不同的处理器，则可以调整这些数字以匹配你的硬件。
  
