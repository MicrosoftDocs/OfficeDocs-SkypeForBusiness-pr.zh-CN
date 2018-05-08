---
title: 在 Skype for Business Server 2015 中向网络站点添加位置策略
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: 为业务 Server 企业语音给 Skype 中的网络站点分配 E9-1-1 位置策略。
ms.openlocfilehash: 5d6b343db63a309661720a8379d204a0abcac1f5
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中向网络站点添加位置策略
 
为业务 Server 企业语音给 Skype 中的网络站点分配 E9-1-1 位置策略。 
  
下面的示例演示如何添加到现有网络站点[中的业务服务器 2015 Skype 的创建位置策略](create-location-policies.md)中定义的**Redmond**位置策略以及如何创建新的网络站点使用**雷德蒙德**位置策略。
  
有关使用网络站点的详细信息，请参阅 Lync Server 命令行管理程序文档中以下 cmdlet:
  
- **新可**
    
- **Get-csnetworksite**
    
- **Set-csnetworksite**
    
- **删除可**
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a>为现有网络站点分配位置策略

1. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
2. 运行以下 cmdlet 以修改现有网络站点。
    
    将带 **Redmond** 标记的位置策略分配给名为 **Redmond** 的现有网络站点。
    
  ```
  Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

  ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a>为新的网络站点分配位置策略

1. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
2. 运行以下 cmdlet 以创建新的网络站点。
    
    在网络区域中创建新的网络站点，并分配带 **Redmond** 标记的位置策略。
    
   ```
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


