---
title: Skype for Business Server 2015 压力和性能工具的性能方案
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 使用压力和性能工具配置 Skype for Business Server 2015 以执行性能和负载测试需要执行的任务。
ms.openlocfilehash: e0a3cc3767cf7652bda9bfacb14ced6632e32d87
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105368"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Skype for Business Server 2015 压力和性能工具的性能方案
 
使用压力和性能工具配置 Skype for Business Server 2015 以执行性能和负载测试需要执行的任务。
  
若要运行 Skype for Business Server 2015 压力和性能工具 (LyncPerfTool) ，必须先针对与您相关的方案配置 Skype for Business Server 2015 拓扑。 如果未配置 Skype for Business Server 2015 或配置不正确，则你的负载模拟很可能失败。 使用 Skype for Business Server 2015 压力和性能工具，我们提供了示例 Skype for Business Server 命令行管理程序脚本和基本资源文件作为工具下载的一 [部分](https://www.microsoft.com/download/details.aspx?id=50367)。 它们可用作配置 Skype for Business Server 部署的起点。 本文介绍Windows PowerShell的示例。
  
> [!NOTE]
> 本主题通常不会帮助你介绍如何配置 Skype for Business Server 2015，我们还有其他有关规划和部署的主题。 有关在 Skype for Business Server 2015 中使用 Windows PowerShell 的详细信息，请参阅插入简介 HERE 中的 Skype for Business Server 命令行管理程序文档。 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a>关于运行 Skype for Business Server 命令行管理程序脚本

我们提供了可用于准备负载模拟的示例 PowerShell 脚本。 由于这些脚本旨在进行负载模拟，因此你会发现它们简单和宽松。 这可能不适合您的生产环境。 我们再次强调，这些脚本是示例，你需要查看它们，并且在许多情况下，需要先对环境进行更改，然后才能实际使用它们。 我们预计您至少需要修改响应服务组 (RSG) 脚本，同时记住拓扑 (以指定分配给代理组) 的代理。 但是，如果不需要，则无需运行它。
  
> [!CAUTION]
> 请谨慎查看和了解这些示例。 脚本将在运行时覆盖拓扑中任何现有设置。 
  
## <a name="stress-and-performance-tool-client-version-names"></a>压力和性能工具客户端版本名称

如果之前更改了默认值的设置，可能需要配置客户端版本检查策略。 如果你不确定这一点，请查看客户端 [版本检查文档](/previous-versions/office/lync-server-2013/lync-server-2013-view-client-version-policy-rules)。
  
与 Skype for Business Server 2015 通信时，压力和性能工具默认使用下列用户代理版本：
  
- LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool) 
    
- OCPHONE/.0.522
    
对于 LyncPerfTool (移动) UCWA 客户端：
  
- UCWA Perf 工具/Web 会议
    
- UCWA Perf 工具/移动
