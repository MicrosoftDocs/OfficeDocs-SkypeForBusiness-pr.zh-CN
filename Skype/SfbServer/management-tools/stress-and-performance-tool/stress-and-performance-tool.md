---
title: Skype for Business Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 在非生产环境或测试环境中进行容量规划和性能优化期间，使用 Skype for Business Server 2015 应力和性能工具。
ms.openlocfilehash: efc3ed6cc7f24acc5fda7a7ae2ae818df5b43393
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816151"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a>Skype for Business Server 2015 Stress and Performance Tool
 
在非生产环境或测试环境中进行容量规划和性能优化期间，使用 Skype for Business Server 2015 应力和性能工具。
  
Skype for Business Server 2015 应力和性能工具包括可简化 Skype for business Server 2015 的容量规划的工具。 Skype for Business Server 2015 应力和性能工具将帮助你：
  
- 简化 Skype for business 服务器的硬件规划
    
- 为您提供改进的性能优化知识和最佳做法
    
- 衡量 Skype for business 服务器部署的性能
    
在使用[skype For Business server 2015 规划工具](../../management-tools/planning-tool/planning-tool.md)设计拓扑并使用[Skype for Business Server 2015 容量规划计算器](../../management-tools/capacity-planning-calculator.md)优化拓扑时，通常使用此工具。 

> [!NOTE]
> 此工具将不会针对 Skype for Business Server 2019 进行更新。
  
## <a name="tests"></a>测试

压力和性能工具可以模拟以下类型的用户负载：
  
|||
|:-----|:-----|
|即时消息（IM）和状态  <br/> |音频会议  <br/> |
|应用程序共享  <br/> |IP 语音（VoIP），包括公共交换电话网络（PTSN）模拟  <br/> |
|Web Access 客户端会议  <br/> |会议自动助理  <br/> |
|响应组  <br/> |通讯组列表扩展  <br/> |
|通讯簿下载和通讯簿查询  <br/> |增强的911（E911）通话和位置配置文件（拨号计划）  <br/> |
|重视  <br/> |数据协作  <br/> |
|移动性  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Skype for Business Server 2015 中附带的应用程序和文件应力和性能工具

这些应用程序是 Skype for Business Server 压力和性能工具的一部分：
  
|**工具**|**说明**|
|:-----|:-----|
|UserProvisioningTool  <br/> |此工具用于创建用户和联系人。  <br/> |
|UserProfileGenerator  <br/> |用于配置要模拟的用户负载的特征。  <br/> |
|LyncPerfTool  <br/> |模拟用户负载的工具。  <br/> |
|默认的 tmx  <br/> |需要使用 Skype for Business Server 2015 日志记录工具。  <br/> |
|预配脚本示例  <br/> |用于根据特定方案配置用于运行负载测试的拓扑。 你可能需要对其进行修改以使其与你的特定环境相关。  <br/> |
   
## <a name="topics-in-this-section"></a>本部分中的主题

如果需要了解详细信息，请查看以下文章：
  
- [Skype for Business Stress and Performance Tool 的先决条件和设置](prerequisites-and-setup.md)
    
- [Skype for Business Server 2015 的性能方案应力和性能工具](scenarios.md)
    
  - [预配拓扑以在压力和性能方案中运行负载](provisioning-the-topology-to-run-load.md)
    
  - [为 Skype for Business Server 2015 配置策略应力和性能工具](configuring-policies.md)
    
- [使用 Skype for Business Server 2015 应力和性能工具](using-the-tool.md)
    
- [Skype for Business Server 2015 的常见问题应力和性能工具](faq.md)
    

