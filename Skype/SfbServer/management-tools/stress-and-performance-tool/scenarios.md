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
description: 使用压力和性能工具配置 Skype for Business Server 2015 以执行性能和负载测试时需要执行的任务。
ms.openlocfilehash: 3edc945f09ef5b2c7c6ecdefcbc66166f0945aec
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814702"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Skype for Business Server 2015 压力和性能工具的性能方案
 
使用压力和性能工具配置 Skype for Business Server 2015 以执行性能和负载测试时需要执行的任务。
  
若要运行 Skype for Business Server 2015 压力和性能工具 (LyncPerfTool) ，必须先为与您相关的方案配置 Skype for Business Server 2015 拓扑。 如果未配置 Skype for Business Server 2015，或配置不正确，则你的负载模拟很可能失败。 使用 Skype for Business Server 2015 压力和性能工具，我们提供示例 Skype for Business Server 命令行管理程序脚本和基本资源文件作为工具下载的一 [部分](https://www.microsoft.com/download/details.aspx?id=50367)。 这些可以用作配置 Skype for Business Server 部署的起点。 本文介绍所提供的Windows PowerShell示例。
  
> [!NOTE]
> 本主题不会帮助你描述如何配置 Skype for Business Server 2015（通常，我们还有其他规划和部署主题）。 有关在 Skype for Business Server 2015 中使用 Windows PowerShell 的详细信息，请参阅此处插入简介中的 Skype for Business Server 命令行管理程序文档。 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a>关于运行 Skype for Business Server 命令行管理程序脚本

我们提供了可用于准备负载模拟的示例 PowerShell 脚本。 由于这些脚本用于负载模拟，因此你会发现它们非常简单和宽松。 这可能不适合您的生产环境。 我们再次强调，这些脚本是示例，你需要查看它们，并且在许多情况下，在能够实际使用这些脚本之前，对环境进行更改。 我们预计您至少需要修改响应服务组 (RSG) 脚本，同时注意拓扑 (以指定分配给代理组) 。 但是，如果不需要，则无需运行它。
  
> [!CAUTION]
> 请谨慎查看和了解这些示例。 脚本将在运行时覆盖拓扑中任何现有设置。 
  
## <a name="stress-and-performance-tool-client-version-names"></a>压力和性能工具客户端版本名称

如果之前更改了默认值的设置，可能需要配置客户端版本检查策略。 如果你不确定这一点，请查看 [客户端版本检查文档](https://msdn.microsoft.com/vsto/jj923060)。
  
与 Skype for Business Server 2015 通信时，压力和性能工具默认使用以下用户代理版本：
  
- LSPT/15.0.0.0 (Skype for Business Server 2015 压力和性能工具) 
    
- OCPHONE/.0.522
    
对于 LyncPerfTool (Mobility) UCWA) 客户端：
  
- UCWA Perf 工具/Web 会议
    
- UCWA Perf 工具/移动
    

