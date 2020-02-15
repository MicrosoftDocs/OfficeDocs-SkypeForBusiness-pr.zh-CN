---
title: Skype for business Server 2015 压力和性能工具的性能方案
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: 使用压力和性能工具配置 Skype for Business Server 2015 以执行性能和负载测试时需要执行的任务。
ms.openlocfilehash: 5531627ab7d5072d32dfcf60fed41eac47f5373f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "41983847"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Skype for business Server 2015 压力和性能工具的性能方案
 
使用压力和性能工具配置 Skype for Business Server 2015 以执行性能和负载测试时需要执行的任务。
  
若要运行 Skype for Business Server 2015 压力和性能工具（LyncPerfTool），必须首先为与您相关的方案配置 Skype for business Server 2015 拓扑。 如果未配置 Skype for Business Server 2015 或配置不正确，则负载模拟很可能会失败。 使用 Skype for Business Server 2015 压力和性能工具，我们将提供示例 Skype for business Server 命令行管理程序脚本和基本资源文件（作为[工具下载](https://www.microsoft.com/download/details.aspx?id=50367)的一部分）。 这些可用作配置 Skype for Business Server 部署的起始点。 本文介绍了提供的 Windows PowerShell 示例。
  
> [!NOTE]
> 本主题不会帮助您介绍如何配置 Skype for Business Server 2015。通常，我们还提供了其他规划和部署主题。 有关在 Skype for business Server 2015 中使用 Windows PowerShell 的详细信息，请参阅此处的插入简介中的 Skype for Business Server 命令行管理程序文档。 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a>关于运行 Skype for Business Server 命令行管理程序脚本

我们正在提供可用于准备负载模拟的示例 PowerShell 脚本。 由于这些脚本是为进行负载模拟而设计的，因此您会发现它们非常简单且是可许可的。 这可能不适合您的生产环境。 再次强调，这些脚本是示例，您需要对其进行检查，并且在很多情况下，在能够实用地使用您的环境之前对其进行更改。 至少，我们预计您需要在您的拓扑中修改响应服务组（RSG）脚本（以指定分配给代理组的代理）。 但如果不需要，则无需运行该程序。
  
> [!CAUTION]
> 请注意查看和理解这些示例。 脚本将在运行时覆盖拓扑中的任何现有设置。 
  
## <a name="stress-and-performance-tool-client-version-names"></a>压力和性能工具客户端版本名称

如果以前更改了默认值中的设置，则可能需要配置客户端版本检查策略。 如果你不确定这一点，请查看[客户端版本检查文档](https://msdn.microsoft.com/vsto/jj923060)。
  
与 Skype for Business Server 2015 通信时，压力和性能工具默认使用以下用户代理版本：
  
- LSPT/15.0.0.0 （Skype for Business Server 2015 压力和性能工具）
    
- OCPHONE/.0.522
    
对于 LyncPerfTool 中的移动性（UCWA）客户端：
  
- UCWA Perf 工具/Web 会议
    
- UCWA Perf 工具/移动
    

