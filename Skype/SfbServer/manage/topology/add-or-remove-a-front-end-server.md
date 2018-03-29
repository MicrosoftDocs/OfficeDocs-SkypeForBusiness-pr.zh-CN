---
title: 在 Skype for Business Server 2015 中添加或删除前端服务器
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/12/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 摘要： 了解如何添加或删除在 Skype 业务服务器的前端服务器。
ms.openlocfilehash: aed52becf5d4cc97307f9788a81f8d6563d1d25d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="add-or-remove-a-front-end-server-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中添加或删除前端服务器
 
**摘要：**了解如何添加或删除在 Skype 业务服务器的前端服务器。
  
当您将前端服务器添加到库中，或从池中删除前端服务器时，然后需要重新启动该池。 
  
> [!IMPORTANT]
> 当你向拓扑中的池添加服务器或从中删除服务器时，会导致池中的所有服务器同时重新启动。当服务器重新启动时，池处于脱机状态，这样会为连接到该池的用户中断服务。为防止用户服务中断，请计划于非工作时间在池中发布采用新服务器的拓扑。 
  
您可以使用以下过程添加或删除前端服务器时。
  
> [!NOTE]
> 如果将新服务器添加到池，请将您的新池服务器更新为与池中的现有服务器相同的累积更新级别。 
  
### <a name="to-add-or-remove-front-end-servers"></a>若要添加或删除前端服务器

1. 如果要删除所有前端服务器，请首先停止与这些服务器的新连接。 为此，您可以使用以下 cmdlet：
    
   ```
   Stop-CsWindowsService -Graceful
   ```

2. 打开拓扑生成器以及添加或移除所需的服务器。 
    
3. 发布拓扑。
    
    > [!IMPORTANT]
    > 当你向拓扑中的池添加服务器或从中删除服务器时，会导致池中的所有服务器同时重新启动。当服务器重新启动时，池处于脱机状态，这样会为连接到该池的用户中断服务。为防止用户服务中断，请计划于非工作时间在池中发布采用新服务器的拓扑。 
  
4. 如果您更改了服务器的数量在前端池中任一下列方式，然后通过键入以下 cmdlet 复位与池： 重置-CsPoolRegistrarState-ResetType FullReset-PoolFqdn 
    
   ```
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - 2 到任意
    
     - 任意到 2
    
     - 3 到任意
    
     - 任意到 3
    
5. 键入以下 cmdlet 以重新启动该池
    
   ```
   Start-CsPool
   ```


