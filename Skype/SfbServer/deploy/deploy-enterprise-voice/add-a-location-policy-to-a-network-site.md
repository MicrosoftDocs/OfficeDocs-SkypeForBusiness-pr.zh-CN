---
title: 在 Skype for Business 服务器中将位置策略添加到网络网站
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: 在 Skype for business Server Enterprise Voice 中向网络站点分配 E9-1-1 位置策略。
ms.openlocfilehash: 4a74b1ee44d1e2f34a51d7859235e10649d0e2ee
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233865"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server"></a>在 Skype for Business 服务器中将位置策略添加到网络网站
 
在 Skype for business Server Enterprise Voice 中向网络站点分配 E9-1-1 位置策略。 
  
以下示例显示了如何将在[Skype For Business Server 的 "创建位置策略" 中](create-location-policies.md)定义的**Redmond**位置策略添加到现有网络网站, 以及如何创建使用**Redmond**位置策略的新网络网站。
  
有关使用网络站点的详细信息, 请参阅以下 cmdlet 的 Lync Server Management Shell 文档:
  
- **New-CsNetworkSite**
    
- **Get-CsNetworkSite**
    
- **Set-CsNetworkSite**
    
- **Remove-CsNetworkSite**
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a>为现有网络站点分配位置策略

1. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。
    
2. 运行以下 cmdlet 以修改现有网络站点。
    
    将带 **Redmond** 标记的位置策略分配给名为 **Redmond** 的现有网络站点。
    
   ```
   Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a>为新的网络站点分配位置策略

1. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。
    
2. 运行以下 cmdlet 以创建新的网络站点。
    
    在网络区域中创建新的网络站点，并分配带 **Redmond** 标记的位置策略。
    
   ```
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


