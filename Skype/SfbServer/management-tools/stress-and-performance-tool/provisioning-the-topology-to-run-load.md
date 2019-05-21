---
title: 预配拓扑以在压力和性能方案中运行负载
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
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: Skype for Business Server 2015 拓扑更改或设置, 以允许用户成功运行压力和性能工具。
ms.openlocfilehash: c7cdc10b3667ac99376904c81309df739e49844a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299700"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a>预配拓扑以在压力和性能方案中运行负载
 
Skype for Business Server 2015 拓扑更改或设置, 以允许用户成功运行压力和性能工具。
  
你可能需要在你的环境中进行一些更改, 具体取决于你的 Skype for business Server 2015 部署的现有设置和配置。 下面列出了这些更改:
  
1. 将 Windows PowerShell 执行策略设置为 "无限制"。 如果您不确定当前设置的内容, 您可以打开 Skype for Business 服务器命令行管理程序并运行以下命令:
    
   ```
   Get-ExecutionPolicy
   ```

   如果未返回值 "不受限制", 则需要运行以下下一步:
    
   ```
   Set-ExecutionPolicy -Unrestricted
   ```

2. 若要有效配置 Skype for Business 服务器, 您需要:
    
    - 熟悉 Skype for Business Server 2015 拓扑 (如计算机名、服务实例、站点名称和策略)。
    
    - 将某些创建的用户分配给组, 如 "响应组查寻组" (例如, SIP Uri)。
    
3. 若要从命令行运行脚本, 可以使用:
    
   ```
   PowerShell.exe -file <path to the file>
   ```

4. 通常, 从该程序包运行脚本后, 生成的跟踪将存储在文件中, 该文件位于运行脚本的位置所在的同一路径中。 还存在命名格式, \<scriptname\>$h $ m $ s。 因此, 如果你在 12:15 PM 运行 ArchivingPolicy, 你将获得一个名为 ArchivingPolicy121500 的日志文件。
    
5. 虽然我们为服务器配置提供了这些示例, 但你可以在完成负载测试后修改配置并还原或回退它们。
    

