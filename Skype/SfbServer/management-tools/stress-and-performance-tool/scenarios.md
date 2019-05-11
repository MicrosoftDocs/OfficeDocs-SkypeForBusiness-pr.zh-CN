---
title: 为业务服务器 2015年压力和性能工具 Skype 的性能方案
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/17/2015
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: 您需要执行的操作配置的业务服务器 2015 执行性能和负载测试的 Skype 使用压力和性能工具的任务。
ms.openlocfilehash: 06ca34717080421129fc03475103b34804ef280a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901695"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>为业务服务器 2015年压力和性能工具 Skype 的性能方案
 
您需要执行的操作配置的业务服务器 2015 执行性能和负载测试的 Skype 使用压力和性能工具的任务。
  
若要运行的业务 Server 2015 压力和性能工具 (LyncPerfTool) Skype，必须首先配置方案与您相关业务服务器 2015年拓扑的 Skype。 如果业务服务器 2015年的 Skype 未配置，或配置不正确，负载模拟为很有可能会失败。 与业务 Server 2015 压力和性能工具 Skype，我们提供示例 Skype 的业务 Server 命令行管理程序脚本和基本资源文件作为[工具下载](https://www.microsoft.com/download/details.aspx?id=50367)的一部分。 这些可作为起点用于配置您 Skype 业务服务器部署。 本文介绍提供的 Windows PowerShell 示例。
  
> [!NOTE]
> 本主题不能帮助您介绍如何配置 Business Server 2015 通常 Skype，我们，必须规划和部署的其他主题。 有关使用的业务服务器 2015 Skype 中的 Windows PowerShell 的详细信息，请参阅在此处插入简介业务 Server Management Shell 文档 Skype。 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a>有关运行 Skype 业务服务器管理命令行管理程序脚本

我们提供您可用来准备负载模拟的示例 PowerShell 脚本。 因为这些脚本供负载模拟，您会发现他们能够简单和宽松。 这可能不适合您的生产环境。 再次我们压力，这些脚本示例，您需要其进行复查并在许多情况下进行更改与环境相关能够实际利用这些之前。 至少，我们期望需要修改与您的拓扑记住 （用于指定代理分配到代理组） 的响应组服务 (RSG) 脚本。 但是，您无需运行，如果您不需要。
  
> [!CAUTION]
> 请注意中查看和了解这些示例。 脚本将覆盖运行时的拓扑中的任何现有的设置。 
  
## <a name="stress-and-performance-tool-client-version-names"></a>压力和性能工具客户端版本名称

您可能需要配置客户端版本检查策略，如果您先前已更改设置的默认值。 如果您不确定有关此，检查[客户端版本检查的文档](https://msdn.microsoft.com/en-us/vsto/jj923060)。
  
压力和性能工具默认情况下使用以下的用户代理版本与 Skype 的业务服务器 2015年通信时：
  
- LSPT/15.0.0.0 (Skype 的业务服务器 2015年压力和性能工具)
    
- OCPHONE/.0.522
    
LyncPerfTool 中移动 (UCWA) 客户端：
  
- UCWA 性能工具/Web 会议
    
- UCWA 性能工具/移动
    

