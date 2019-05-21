---
title: Skype for Business Server 2015 的性能方案应力和性能工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: 使用压力和性能工具配置 Skype for Business Server 2015 以执行性能和负载测试时需要执行的任务。
ms.openlocfilehash: 2aedb43a6b7214aaf582e1dfd4754e626a602508
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299381"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Skype for Business Server 2015 的性能方案应力和性能工具
 
使用压力和性能工具配置 Skype for Business Server 2015 以执行性能和负载测试时需要执行的任务。
  
若要运行 Skype for Business Server 2015 应力和性能工具 (LyncPerfTool), 必须首先针对与你相关的方案配置 Skype for business Server 2015 拓扑。 如果未配置 Skype for Business 服务器 2015, 或者配置不正确, 则你的负载模拟很可能会失败。 通过 Skype for Business Server 2015 应力和性能工具, 我们将提供示例 Skype for business Server Management Shell 脚本和基本资源文件, 作为[工具下载](https://www.microsoft.com/download/details.aspx?id=50367)的一部分。 这些可用作配置 Skype for Business 服务器部署的起始点。 本文介绍所提供的 Windows PowerShell 示例。
  
> [!NOTE]
> 本主题不能帮助你介绍如何配置 Skype for Business Server 2015。通常, 我们有其他规划和部署主题。 有关在 Skype for Business Server 2015 中使用 Windows PowerShell 的详细信息, 请参阅此处的插入简介中的 Skype for business 服务器管理外壳文档。 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a>关于运行 Skype for Business Server management shell 脚本

我们正在提供可用于准备负载模拟的示例 PowerShell 脚本。 由于这些脚本适用于负载模拟, 因此你将发现它们是简单且容许的。 这可能不适合你的生产环境。 我们再次强调这些脚本是示例, 你需要检查这些脚本, 并且在许多情况下, 在能够实际使用你的环境之前, 你需要对其进行更改。 至少, 我们希望你需要修改 "响应服务组" (RSG) 脚本, 注意你的拓扑 (用于指定分配给代理组的代理)。 但是, 如果不需要, 您不必运行该程序。
  
> [!CAUTION]
> 请注意查看和理解这些示例。 运行时, 脚本将覆盖拓扑中的任何现有设置。 
  
## <a name="stress-and-performance-tool-client-version-names"></a>应力和性能工具客户端版本名称

如果以前已更改默认值的设置, 则可能需要配置客户端版本检查策略。 如果不确定此内容, 请查看[客户端版本检查文档](https://msdn.microsoft.com/en-us/vsto/jj923060)。
  
在与 Skype for Business Server 2015 通信时, "压力" 和 "性能" 工具默认使用以下用户代理版本:
  
- LSPT/15.0.0.0 (Skype for Business Server 2015 应力和性能工具)
    
- OCPHONE/.0.522
    
对于 LyncPerfTool 中的移动 (UCWA) 客户端:
  
- UCWA Perf 工具/Web 会议
    
- UCWA Perf 工具/移动版
    

