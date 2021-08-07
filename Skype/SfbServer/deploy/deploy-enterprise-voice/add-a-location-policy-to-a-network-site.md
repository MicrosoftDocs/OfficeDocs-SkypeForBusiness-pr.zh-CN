---
title: 将位置策略添加到网络站点Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: 将 E9-1-1 位置策略分配给 Skype for Business Server 企业语音。
ms.openlocfilehash: bdb34209a164375b1e21f9e896ec53d7d242c006ec4df4053634918857f8ea4e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54305934"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server"></a>将位置策略添加到网络站点Skype for Business Server
 
将 E9-1-1 位置策略分配给 Skype for Business Server 企业语音。 
  
以下示例显示如何将 [Skype for Business Server](create-location-policies.md)中的创建位置策略中定义的 **Redmond** 位置策略添加到现有网络站点，以及如何创建使用 **Redmond** 位置策略的新网络站点。
  
有关使用网络站点的详细信息，请参阅以下 cmdlet 的 Lync Server 命令行管理程序文档：
  
- **New-CsNetworkSite**
    
- **Get-CsNetworkSite**
    
- **Set-CsNetworkSite**
    
- **Remove-CsNetworkSite**
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a>为现有网络站点分配位置策略

1. 启动命令行Skype for Business Server：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击"Skype for Business Server **命令行管理程序"。**
    
2. 运行以下 cmdlet 以修改现有网络站点。
    
    将 **Redmond** 标记的位置策略分配给名为 **Redmond 的现有网络站点**。
    
   ```powershell
   Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a>为新的网络站点分配位置策略

1. 启动命令行Skype for Business Server：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击"Skype for Business Server **命令行管理程序"。**
    
2. 运行以下 cmdlet 以创建新的网络站点。
    
    在网络区域中创建新的网络站点，并分配 **Redmond** 带标记的位置策略。
    
   ```powershell
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


