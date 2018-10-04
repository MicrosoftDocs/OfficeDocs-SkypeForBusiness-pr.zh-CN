---
title: 设置要在压力和性能的情况下运行负载的拓扑
ms.author: heidip
author: microsoftheidi
ms.date: 12/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: 若要允许用户成功运行压力和性能工具业务服务器 2015年拓扑更改或资源调配 Skype。
ms.openlocfilehash: 6ff08a3b99f4dc1f05b56c2a1fa86733ccf4f852
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373776"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a>设置要在压力和性能的情况下运行负载的拓扑
 
若要允许用户成功运行压力和性能工具业务服务器 2015年拓扑更改或资源调配 Skype。
  
根据您现有的设置和配置的业务服务器 2015 Skype 的部署，您可能需要在您的环境中进行某些更改。 以下是这些更改的列表：
  
1. 设置为无限制的 Windows PowerShell 执行策略。 如果您不确定它是什么设置为当前，您可以打开 Skype 的业务 Server 命令行管理程序，并运行此命令：
    
   ```
   Get-ExecutionPolicy
   ```

   如果不返回的值不受限制，您将需要运行此下一步：
    
   ```
   Set-ExecutionPolicy -Unrestricted
   ```

2. 若要有效地配置 Skype 业务服务器，您将需要：
    
    - 熟悉您 Skype （如计算机名称、 服务实例、 站点名称和策略） 的业务服务器 2015年拓扑。
    
    - 分配到组中，创建的用户的一些如响应组智能寻线 (例如，SIP Uri)。
    
3. 若要从命令行运行脚本，您可以使用：
    
   ```
   PowerShell.exe -file <path to the file>
   ```

4. 通常情况下，已从此数据包中运行的脚本后，生成跟踪将存储在文件中的相同路径中运行该脚本。 没有也命名格式\<scriptname\>$h$m$s.txt。 因此，如果您在下午 12:15 运行 ArchivingPolicy.ps1，您将获取名为 ArchivingPolicy121500.txt 的日志文件。
    
5. 虽然我们为您提供了服务器配置这些示例，这取决于您同时修改您的配置和还原或已完成运行负载测试后滚动它。
    

