---
title: Skype for Business Server 2015 压力和性能工具
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 4/6/2016
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: Skype for Business Server 2015 Stress and Performance Tool is used during capacity planning and performance tuning in non-production or test environments.
ms.openlocfilehash: 0ce2c4f4a608f6ecba980d7f8fe77fbc2863d81d
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2021
ms.locfileid: "60012366"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a>Skype for Business Server 2015 压力和性能工具
 
Skype for Business Server 2015 Stress and Performance Tool is used during capacity planning and performance tuning in non-production or test environments.
  
Skype for Business Server 2015 压力和性能工具包括可简化 Skype for Business Server 2015 容量规划的工具。 Skype for Business Server 2015 压力和性能工具将帮助你：
  
- 简化 Skype for Business Server 的硬件规划
    
- 为性能调整提供增强的知识和最佳做法
    
- 测量 Skype for Business Server 部署的性能
    
通常，使用 [Skype for Business Server 2015](../../management-tools/planning-tool/planning-tool.md) 规划工具设计拓扑，并使用 Skype for Business Server [2015](../../management-tools/capacity-planning-calculator.md)容量规划计算器精简拓扑后，通常使用此工具。 

> [!NOTE]
> 此工具不会针对 Skype for Business Server 2019 进行更新。
  
## <a name="tests"></a>测试

压力和性能工具可以模拟以下类型的用户负载：
  
|&nbsp;|&nbsp;|
|:-----|:-----|
|即时消息 (IM) 和状态   |音频会议   |
|应用程序共享   |IP 语音 (VoIP) ，包括公用电话交换网 (PTSN) 模拟   |
|Web Access 客户端会议   |会议自动助理   |
|响应组   |通讯组列表扩展   |
|通讯簿下载和通讯簿查询   |增强型 911 (E911) 呼叫和位置配置文件 (拨号计划)    |
|MultiView   |数据协作   |
|移动性   ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Skype for Business Server 2015 Stress and Performance Tool 中包含的应用程序和文件

这些应用程序是 Skype for Business Server 压力和性能工具的一部分：
  
|工具|说明|
|:-----|:-----|
|UserProvisioningTool.exe   |此工具用于创建用户和联系人。   |
|UserProfileGenerator.exe   |用于配置要模拟的用户负载的特征。   |
|LyncPerfTool.exe   |模拟用户加载的工具。   |
|Default.tmx   |需要使用 Skype for Business Server 2015 日志记录工具。   |
|预配脚本示例   |用于根据特定方案配置用于运行负载测试的拓扑。 你可能需要修改它们，使其与特定环境相关。   |
   
## <a name="topics-in-this-section"></a>本节中的主题

如果需要了解更多信息，应查看以下文章：
  
- [Skype for Busines 压力和性能工具的先决条件和设置](prerequisites-and-setup.md)
    
- [Skype for Business Server 2015 压力和性能工具的性能方案](scenarios.md)
    
  - [设置拓扑以在压力和性能方案中运行负载](provisioning-the-topology-to-run-load.md)
    
  - [为 Skype for Business Server 2015 压力和性能工具配置策略](configuring-policies.md)
    
- [使用 Skype for Business Server 2015 压力和性能工具](using-the-tool.md)
    
- [Skype for Business Server 2015 压力和性能工具常见问题解答](faq.md)
    

