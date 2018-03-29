---
title: 资源调配压力和性能的情况下运行负载的拓扑
ms.author: heidip
author: microsoftheidi
ms.date: 12/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: 若要允许用户成功地运行压力和性能工具的业务服务器 2015年拓扑的更改或设置 Skype。
ms.openlocfilehash: 825dd56a7f2cb343eddd8cbed7e811cdc5154b9c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a>资源调配压力和性能的情况下运行负载的拓扑
 
若要允许用户成功地运行压力和性能工具的业务服务器 2015年拓扑的更改或设置 Skype。
  
这取决于您的现有设置和部署的 Skype 业务服务器 2015年的配置，可能需要在您的环境中进行一些更改。 下面是列出的那些更改：
  
1. Windows PowerShell 执行策略设置为无限制。 如果你不知道它是什么设置为当前，您可以为业务服务器管理外壳程序打开 Skype 和运行此命令：
    
  ```
  Get-ExecutionPolicy
  ```

  如果未返回的值不受限制，您需要运行这下一步：
    
  ```
  Set-ExecutionPolicy -Unrestricted
  ```

2. 有效地配置 Skype 业务服务器，您需要：
    
    - 熟悉您 Skype 业务服务器 2015年拓扑 （例如计算机名称，服务实例、 站点名称和策略）。
    
    - 分配的部分创建组，用户如响应组查寻组 (例如，SIP Uri)。
    
3. 若要从命令行运行脚本，您可以使用：
    
  ```
  PowerShell.exe -file <path to the file>
  ```

4. 通常情况下，已经从该包中运行脚本后，生成跟踪都存储在一个文件的同一路径中运行该脚本的位置。 没有命名的格式以及\<scriptname\>$h$m$s.txt。 因此如果您运行 ArchivingPolicy.ps1 在下午 12:15 时，您将获得名为 ArchivingPolicy121500.txt 日志文件。
    
5. 同时我们为您的服务器配置中提供了这些示例，这取决于您要同时修改您的配置和恢复，或者将其滑运行负载测试完后。
    

