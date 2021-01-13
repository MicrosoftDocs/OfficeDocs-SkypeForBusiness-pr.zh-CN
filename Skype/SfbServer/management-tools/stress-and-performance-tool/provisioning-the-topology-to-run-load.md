---
title: 设置拓扑以在压力和性能方案中运行负载
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
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: Skype for Business Server 2015 拓扑更改或设置以允许用户成功运行压力和性能工具。
ms.openlocfilehash: 8d422497d11c9e56e4d5b205269a09f96dffc136
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814932"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a>设置拓扑以在压力和性能方案中运行负载
 
Skype for Business Server 2015 拓扑更改或设置以允许用户成功运行压力和性能工具。
  
根据 Skype for Business Server 2015 部署的现有设置和配置，可能需要在你的环境中进行一些更改。 下面是这些更改的列表：
  
1. 将Windows PowerShell策略设置为"无限制"。 如果不确定当前设置什么，可以打开 Skype for Business Server 命令行管理程序 并运行以下命令：
    
   ```PowerShell
   Get-ExecutionPolicy
   ```

   如果未返回 Unrestricted 值，则下一步将需要运行此值：
    
   ```PowerShell
   Set-ExecutionPolicy -Unrestricted
   ```

2. 要有效地配置 Skype for Business Server，你需要：
    
    - 熟悉 Skype for Business Server 2015 拓扑 (例如计算机名称、服务实例、站点名称和策略) 。
    
    - 将创建的一些用户分配给组，例如响应组 (例如 SIP URI) 。
    
3. 若要从命令行运行脚本，可以使用：
    
   ```PowerShell
   PowerShell.exe -file <path to the file>
   ```

4. 通常，在此包中运行脚本后，生成的跟踪将存储在运行该脚本的同一路径的文件中。 还有一种命名格式 \<scriptname\> ，$h$m$s.txt。 因此，如果你在 12ArchivingPolicy.ps1 12：15 运行该日志文件，你将ArchivingPolicy121500.txt。
    
5. 尽管我们已为服务器配置提供了这些示例，但由你负责修改配置，在运行完负载测试后还原或回滚配置。
    

