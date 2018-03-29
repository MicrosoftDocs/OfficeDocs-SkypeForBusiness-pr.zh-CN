---
title: 为业务服务器 2015年的压力和性能工具 Skype 的性能情况
ms.author: heidip
author: microsoftheidi
ms.date: 12/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: 您将需要执行配置 Skype 的业务服务器 2015 做性能和负载测试使用的压力和性能工具的任务。
ms.openlocfilehash: 6b60d403e0a440e544874a8ed877a0b98e3e92ae
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>为业务服务器 2015年的压力和性能工具 Skype 的性能情况
 
您将需要执行配置 Skype 的业务服务器 2015 做性能和负载测试使用的压力和性能工具的任务。
  
若要运行 Skype 业务服务器 2015年的压力和性能工具 (LyncPerfTool)，必须首先配置方案与您相关业务服务器 2015年拓扑 Skype。 如果业务服务器 2015年的 Skype 不配置，或配置不正确，负载模拟是非常失败的可能性。 具有的业务服务器 2015年压力和性能工具 Skype，我们提供的示例 Skype 业务服务器管理 Shell 脚本和基本资源文件作为[工具下载](https://www.microsoft.com/download/details.aspx?id=50367)的一部分。 这些可作为起始点来配置您的 Skype 业务服务器部署。 本文介绍了提供的 Windows PowerShell 示例。
  
> [!NOTE]
> 本主题不能帮助您介绍了如何配置 Skype 业务服务器 2015年通常，我们该有的规划和部署的其他主题。 有关使用 Windows PowerShell 在 Skype 的业务服务器 2015年的详细信息，请参阅在此处插入介绍业务服务器管理外壳程序文档用于 Skype。 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a>有关运行 Skype 业务服务器管理外壳脚本

我们提供的示例 PowerShell 脚本可用来准备您的负载模拟。 因为这些脚本适用于负载模拟，您会发现它们是简单和宽松。 这可能不适合您的生产环境。 我们再次强调，这些脚本示例，您将需要查看它们并在许多情况下进行的更改与您的环境相关后才能实际使用。 至少我们希望如此需要修改带有一点 （可以指定分配给代理组的代理） 拓扑结构的响应服务组 (RSG) 脚本。 但是，您不需要运行的如果不需要。
  
> [!CAUTION]
> 请小心地查看并理解这些示例。 脚本将覆盖任何现有设置运行时拓扑中。 
  
## <a name="stress-and-performance-tool-client-version-names"></a>压力和性能工具的客户端版本名称

您可能需要配置客户端版本检查策略，如果您以前已从默认值更改设置。 如果您不确定有关此，检查[客户端版本检查文档](https://msdn.microsoft.com/en-us/vsto/jj923060)。
  
压力和性能工具默认使用以下用户代理版本与 Skype 通信的业务服务器 2015年时：
  
- LSPT/15.0.0.0 (Skype 业务服务器 2015年的压力和性能工具)
    
- OCPHONE/.0.522
    
在 LyncPerfTool 行动 (UCWA) 客户端：
  
- UCWA 性能工具/网络会议
    
- UCWA 性能工具/移动
    

