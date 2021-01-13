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
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: Skype for Business Server 2015 Stress and Performance Tool is used during capacity planning and performance tuning in non-production or test environments.
ms.openlocfilehash: 551e4e5f985fc18439a4f277685034e86c7cdfb6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814922"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a>Skype for Business Server 2015 压力和性能工具
 
Skype for Business Server 2015 Stress and Performance Tool is used during capacity planning and performance tuning in non-production or test environments.
  
Skype for Business Server 2015 压力和性能工具包括可简化 Skype for Business Server 2015 容量规划的工具。 Skype for Business Server 2015 压力和性能工具将帮助你：
  
- 简化 Skype for Business Server 的硬件规划
    
- 为性能调整提供增强的知识和最佳做法
    
- 测量 Skype for Business Server 部署的性能
    
通常，使用 [Skype for Business Server 2015](../../management-tools/planning-tool/planning-tool.md) 规划工具设计拓扑，并使用 Skype for Business Server [2015](../../management-tools/capacity-planning-calculator.md)容量规划计算器优化拓扑后，通常使用此工具。 

> [!NOTE]
> 此工具不会针对 Skype for Business Server 2019 进行更新。
  
## <a name="tests"></a>测试

压力和性能工具可以模拟以下类型的用户负载：
  
|||
|:-----|:-----|
|即时消息 (IM) 和状态  <br/> |音频会议  <br/> |
|应用程序共享  <br/> |IP 语音 (VoIP) ，包括公用电话交换网 (PTSN) 模拟  <br/> |
|Web Access 客户端会议  <br/> |会议自动助理  <br/> |
|响应组  <br/> |通讯组列表扩展  <br/> |
|通讯簿下载和通讯簿查询  <br/> |增强型 911 (E911) 呼叫和位置配置文件 (拨号计划)   <br/> |
|MultiView  <br/> |数据协作  <br/> |
|移动性  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Skype for Business Server 2015 压力和性能工具中包含的应用程序和文件

这些应用程序是 Skype for Business Server 压力和性能工具的一部分：
  
|**工具**|**说明**|
|:-----|:-----|
|UserProvisioningTool.exe  <br/> |此工具用于创建用户和联系人。  <br/> |
|UserProfileGenerator.exe  <br/> |用于配置要模拟的用户负载的特征。  <br/> |
|LyncPerfTool.exe  <br/> |模拟用户负载的工具。  <br/> |
|Default.tmx  <br/> |需要使用 Skype for Business Server 2015 日志记录工具。  <br/> |
|预配脚本示例  <br/> |用于根据特定方案配置用于运行负载测试的拓扑。 你可能需要修改它们，使其与特定环境相关。  <br/> |
   
## <a name="topics-in-this-section"></a>本节中的主题

如果需要了解更多信息，应查看以下文章：
  
- [Skype for Busines 压力和性能工具的先决条件和设置](prerequisites-and-setup.md)
    
- [Skype for Business Server 2015 压力和性能工具的性能方案](scenarios.md)
    
  - [设置拓扑以在压力和性能方案中运行负载](provisioning-the-topology-to-run-load.md)
    
  - [为 Skype for Business Server 2015 压力和性能工具配置策略](configuring-policies.md)
    
- [使用 Skype for Business Server 2015 压力和性能工具](using-the-tool.md)
    
- [Skype for Business Server 2015 压力和性能工具常见问题解答](faq.md)
    

