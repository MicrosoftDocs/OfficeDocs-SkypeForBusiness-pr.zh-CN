---
title: 修补或更新 Skype for Business Server 2015 中的前端服务器
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 4/4/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
description: 摘要： 了解如何向前端服务器在 Skype 业务服务器应用升级或修补程序。
ms.openlocfilehash: 1f5ccd6531338d1e6b47dd8363b9386bcbeba0fc
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="patch-or-update-front-end-servers-in-skype-for-business-server-2015"></a>修补或更新 Skype for Business Server 2015 中的前端服务器
 
**摘要：**了解如何到前端服务器在 Skype 业务服务器应用升级或修补程序。
  
当修补在前端池中的服务器时，您需要这样一台服务器执行一次。 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>对池中的前端服务器应用升级

1. 键入以下 cmdlet：
    
  ```
  Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
  ```

     如果此 cmdlet 显示存在任何丢失副本，请运行以下 cmdlet 以恢复池，然后才能应用修补程序。
    
  ```
  Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
  ```

2. 在要修补的第一台服务器上，运行以下 cmdlet：
    
  ```
  Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
  ```

    此 cmdlet 将所有服务都移动到其他前端服务器的池中，并将该服务器脱机。
    
3. 为此服务器应用升级或修补。
    
4. 在升级后的服务器上，运行以下 cmdlet：
    
  ```
  Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
  ```

    服务器重新返回服务。
    
5. 对需要升级的每台服务器执行步骤 2-4。
    

