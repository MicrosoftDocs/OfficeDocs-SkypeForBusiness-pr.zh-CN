---
title: 设置拓扑以在压力和性能方案中运行负载
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: Skype for Business Server 2015 拓扑更改或设置，以允许用户成功运行压力和性能工具。
ms.openlocfilehash: 50bd77dd7b3531a150e1e62f6192d32666fa5ba7
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60854256"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a>设置拓扑以在压力和性能方案中运行负载
 
Skype for Business Server 2015 拓扑更改或设置，以允许用户成功运行压力和性能工具。
  
根据您的 2015 年 Skype for Business Server部署的现有设置和配置，您可能需要在环境中进行一些更改。 下面是这些更改的列表：
  
1. 将Windows PowerShell策略设置为 Unrestricted。 如果不确定当前设置为什么，可以打开命令行管理程序，Skype for Business Server运行以下命令：
    
   ```PowerShell
   Get-ExecutionPolicy
   ```

   如果未返回值 Unrestricted，则接下来将需要运行以下代码：
    
   ```PowerShell
   Set-ExecutionPolicy -Unrestricted
   ```

2. 若要有效地Skype for Business Server配置配置，您需要：
    
    - 熟悉 Skype for Business Server 2015 拓扑结构 (例如计算机名称、服务实例、站点名称和策略) 。
    
    - 为组分配一些创建的用户，例如响应组 (，例如 SIP URI) 。
    
3. 若要从命令行运行脚本，可以使用：
    
   ```PowerShell
   PowerShell.exe -file <path to the file>
   ```

4. 通常，在此包中运行脚本后，生成的跟踪将存储在运行脚本的同一路径的文件中。 还有一种命名格式 \<scriptname\> ，$h$m$s.txt。 因此，如果你在 12ArchivingPolicy.ps1 12：15 运行该日志文件，你将看到一个名为 ArchivingPolicy121500.txt。
    
5. 虽然我们已为服务器配置提供了这些示例，但由你负责修改配置和还原配置，或在运行完负载测试后将其回滚。
    

