---
title: Skype for Business Server 容量计划计算器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/1/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bc4d93b1-0c38-4bf8-8b65-692ff3e2446d
description: 摘要：如何使用容量计算器工具。
ms.openlocfilehash: 24e268c6ecc3cc48fbfb4405f1e5e6b008639944
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274455"
---
# <a name="skype-for-business-server-capacity-planning-calculator"></a>Skype for Business Server 容量计划计算器
 
**摘要：** 如何使用容量计算器工具。

> [!NOTE]
> 本文引用 Skype for Business Server 2015 下载, 但它适用于:
> - Skype for Business 服务器2019。
> - Skype for Business 服务器2015。
  
[Skype For Business server 2015 容量计算器](https://www.microsoft.com/en-us/download/details.aspx?id=51196)和[Skype for Business Server 2019 容量计算器](https://www.microsoft.com/en-us/download/details.aspx?id=57509)增强了[skype for business 计划工具](https://www.microsoft.com/en-us/download/details.aspx?id=50357)和你的部署文档 ([适用于 skype for business 的计划服务器 2015](../plan-your-deployment/plan-your-deployment.md)分别部署和[规划 Skype For business Server 2019 部署](../../SfBServer2019/plan/plan-your-deployment-2019.md)。 请在阅读指南并使用规划工具创建建议的拓扑之后使用计算器。
  
Skype for Business 服务器容量计算器可帮助你根据你的组织使用的用户数和通信工具来确定服务器要求。 在确定你的配置文件和你想要为用户启用的功能之后，请使用计算器确定所需的服务器数、内存和带宽。 此版本的计算器不针对磁盘 I/O 要求提供指导。
  
如果您拥有有关您的特定用户概况的准确、详细的信息，则可以充分享受计算器带来的好处。例如，启用语音的用户的百分比、每个用户每小时的平均呼叫、呼叫持续时间以及会议中的并发用户百分比可能会对服务器要求造成巨大差异。计算器创建的建议的准确性取决于您提供的信息的准确性。
  
使用计划工具和容量计划计算器后, 您应模拟建议的和计划的负载, 以确保 Skype for business 服务器将获得适当的设置。 若要在模拟的负载下执行压力测试, 请使用 Skype for business server 压力和[性能工具](https://technet.microsoft.com/en-us/library/mt631400.aspx)中记录的[Skype For business 服务器压力和性能工具](https://www.microsoft.com/en-us/download/details.aspx?id=50367)。
  
## <a name="using-the-capacity-calculator"></a>使用容量计算器

计算器是一个 Microsoft Excel 电子表格。 橙色单元格供你输入内容。 在单元格中输入默认值 (对于 Skype for business Server 2015, 在一个池中有十二个前端服务器的80000用户), 而对于 Skype for Business Server 2019, 则在一个池中有十六个前端服务器的106000用户, 但应将这些值更改为满足组织的需求。
  
使用模型包含以下部分。要计算你的容量要求，请按照所述从工作表顶部开始并向下逐行输入数据： 
  
 **即时消息和状态**
  
- 在“**用户数**”下，键入将一次登录的用户数。 此数目通常是已设置的用户总数的 80%。 在大多数情况下，将对所有并发用户启用 IM 和状态。 默认值为 80000 for Skype for business Server 2015, 并106000用户的 Skype for business Server 2019。
    
- **联系人列表中的平均联系人数**表示我们用于验证你的系统要求的联系人数。此数字是固定的，不可更改。
    
  **企业语音**
  
- 在“**启用企业语音的用户**”中，键入启用企业语音的用户的百分比。默认值为 60%。 
    
- 在“**每个用户每小时的平均呼叫数（峰值）**”中，键入你预计峰值负载时段内每小时参与用户的平均呼叫数。默认值为 4。 
    
- 在“**使用媒体旁路的呼叫百分比**”中，键入由你的用户拨打的、将绕过中介服务器的呼叫百分比。默认值为 65%，但是如果你的用户所在地理位置较为宽广或者在家工作的用户较多，则该值可能较低。
    
- 在**uc-pstn 呼叫所涉及的语音用户的百分比**中, 键入您的组织的呼叫的百分比, 即 "UC-pstn 电话呼叫"。 默认值为 60%。
    
- 在“**UC-UC 呼叫中涉及的语音用户百分比**”中，显示启用了企业语音并且只将启用 UC-UC 呼叫的用户百分比。此数目基于你对“**启用 UC-PSTN 呼叫的语音用户百分比**”输入的内容进行计算。 
    
  **会议**
  
- 在“**并发会议中的用户百分比**”中，键入将同时参与会议的用户百分比。默认值为 5%。 
    
- 在“**仅使用组 IM（无语音）的会议百分比**”中，键入会议仅涉及即时消息而不包括音频的会议百分比。默认值为 10%。
    
- 在“**使用电话拨入式会议的用户百分比**”中，键入会议中一次使用电话拨入式会议的参与者的百分比。默认值为 15%。
    
- 在“**使用语音的会议百分比**”中，键入将包括音频的会议百分比。 
    
  - 如果 20% 的语音会议也将包括普通视频，请选择“**包括视频（无多视图）**”复选框。
    
  - 如果 20% 的会议也将包括多视图视频，请选择“**包括多视图**”复选框。
    
  - 如果 50% 的语音会议还将包含应用程序共享, 请选中 "**包括应用程序共享**" 复选框。
    
  - 如果 20% 的语音会议包括数据上载（如 PowerPoint 演示文稿），请选择“**包括 Web 会议**”复选框。
    
  **移动性**
  
- 在 "**为移动启用的用户百分比**" 中, 键入将启用其使用移动设备连接到 Skype For business 服务器的用户的百分比。 默认值为 40%。 
    
在你输入所有必要信息之后，容量计算器将估计你的要求。 黄色单元格根据 Skype for Business Server 性能实验室中执行的测试显示 CPU、内存和带宽要求的计算值。 这些数字仅供参考，并没有针对所有单个变体进行测试和验证。 将计算以下值： 
  
- **前端 CPU**：当与测试中使用的服务器规格相同的一个前端服务器处理整个负载时的 CPU 使用百分比（请参阅本文末尾的说明）。
    
- **网络 (Mbps)**：对应工作负载的带宽要求 (Mbps)。
    
- **内存 (GB)**：对应工作负载所需的内存 (GB)。
    
绿色单元格显示为您输入的使用模型提供的建议。 
  
- **前端服务器总数**: 所需的物理服务器数基于运行 Skype For business server 2015 的专用服务器 (具有双处理器、hex、2260兆周期) 或 skype For business server 2019 与英特尔至强 2673 v3 (双处理器、十六进制-核心。
    
    请注意，建议启用超线程，它经过证明可改进支持音频/视频的服务器的性能。
    
- **边缘服务器**：所需的边缘服务器数目基于通过边缘服务器进行通信的所有并发用户的 30% 确定。此百分比不可在计算器中更改。 
    
- **存档/呼叫详细记录/用户体验质量服务存储**：存档或监视功能（如果你的组织已启用）所需的存储数。
    
- **所需的后端数据库服务器（需要池）**：支持所选工作负载所需的后端数据库服务器数目。
    
此外，在“前端服务器总数”旁边的行中，针对综合的所有计划工作负载提供了有关您的服务器和网络上的负载的更多信息。
  
- **平均 CPU 负载**：每个前端服务器的平均 CPU 使用。
    
- **网络 (Mbps)**：支持你输入的使用模型所需的带宽分配。
    
- **内存 (GB)**：每个前端服务器所需的内存 (GB)。
    
### <a name="adjusting-for-your-processors"></a>针对处理器进行调整

电子表格中的所有 CPU 使用图假设每个 Skype for business server 2015 服务器都具有双处理器、16 GHz 的 2.26 16 GHz、至少 32 GB 的内存以及8个或更多的 10000 RPM 硬盘, 至少有 72 gb 的可用磁盘空间。 对于每个 Skype for Business 服务器2019服务器, 电子表格中的所有 CPU 使用图都假定每台服务器都有一个双处理器、16进制和 Intel 至强的 2673 v3、至少 64 GB 的内存以及8个或更多 10000 RPM 的硬盘 (至少有 72 GB 的可用磁盘)领先.
  
如果您的服务器具有不同的处理器，您可以根据您的硬件调整数字。
  
