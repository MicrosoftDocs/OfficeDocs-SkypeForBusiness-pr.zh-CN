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
description: 在Skype for Business Server或测试环境中进行容量规划和性能调整期间，使用 2015 压力和性能工具。
ms.openlocfilehash: 381e6178994ce8d4ce2f3558bd075cf6fc3b6d43
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58611891"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a>Skype for Business Server 2015 压力和性能工具
 
在Skype for Business Server或测试环境中进行容量规划和性能调整期间，使用 2015 压力和性能工具。
  
The Skype for Business Server 2015 Stress and Performance Tool includes tools that will simplify your capacity planning for Skype for Business Server 2015. The Skype for Business Server 2015 Stress and Performance Tool will help you to：
  
- 简化硬件规划Skype for Business Server
    
- 为性能调整提供增强的知识和最佳做法
    
- 测量部署Skype for Business Server性能
    
通常，使用[Skype for Business Server 2015 规划](../../management-tools/planning-tool/planning-tool.md)工具设计拓扑，并使用[Skype for Business Server 2015](../../management-tools/capacity-planning-calculator.md)容量规划计算器精简拓扑之后，通常使用此工具。 

> [!NOTE]
> 此工具不会在 2019 Skype for Business Server更新。
  
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

这些应用程序是"压力和性能Skype for Business Server的一部分：
  
|**工具**|**描述**|
|:-----|:-----|
|UserProvisioningTool.exe  <br/> |此工具用于创建用户和联系人。  <br/> |
|UserProfileGenerator.exe  <br/> |用于配置要模拟的用户负载的特征。  <br/> |
|LyncPerfTool.exe  <br/> |模拟用户加载的工具。  <br/> |
|Default.tmx  <br/> |使用 Skype for Business Server 2015 日志记录工具是必需的。  <br/> |
|预配脚本示例  <br/> |用于根据特定方案配置用于运行负载测试的拓扑。 你可能需要修改它们，使其与特定环境相关。  <br/> |
   
## <a name="topics-in-this-section"></a>本节中的主题

如果需要了解更多信息，应查看以下文章：
  
- [总线压力和性能Skype组件的先决条件和设置](prerequisites-and-setup.md)
    
- [Skype for Business Server 2015 压力和性能工具的性能方案](scenarios.md)
    
  - [设置拓扑以在压力和性能方案中运行负载](provisioning-the-topology-to-run-load.md)
    
  - [Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool](configuring-policies.md)
    
- [使用 Skype for Business Server 2015 压力和性能工具](using-the-tool.md)
    
- [Skype for Business Server 2015 压力和性能工具的常见问题解答](faq.md)
    

