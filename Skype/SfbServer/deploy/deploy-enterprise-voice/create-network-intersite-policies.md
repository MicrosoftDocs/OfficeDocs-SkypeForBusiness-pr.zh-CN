---
title: 在站点内创建网络站点间Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b0714aae-55dc-4587-b718-34a03f596b22
description: 创建网络站点间策略，这些策略企业语音呼叫允许控制Skype for Business Server。
ms.openlocfilehash: 634af0c7603ef9f3455933e7ef22ce06fe9f28e4
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741398"
---
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a>在站点内创建网络站点间Skype for Business Server
 
创建网络站点间策略，这些策略企业语音呼叫允许控制Skype for Business Server。 
  
网络站点间策略定义在站点之间具有直接 WAN 链路的站点之间的带宽限制。
  
> [!IMPORTANT]
> 只有在两个网络站点之间具有直接交叉链接时，才需要网络站点间策略。
  
在示例拓扑北美区域中，Reno 和 Albuquerque 站点之间具有直接链接。 这两个站点需要应用相应带宽策略配置文件的站点间策略。 以下示例将应用 20Mb_Link 配置文件。
  
### <a name="to-create-a-network-inter-site-policy"></a>创建网络站点间策略

1. 启动命令行Skype for Business Server：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击"Skype for Business Server **命令行管理程序"。**
    
2. 运行 New-CsNetworkInterSitePolicy cmdlet 创建网络站点间策略，并针对具有直接交叉链接的两个站点应用相应的带宽策略配置文件。 例如，运行：
    
   ```powershell
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. 根据需要重复步骤 2，为具有直接交叉链接的所有网络站点对创建网络站点间策略。
    
## <a name="see-also"></a>另请参阅

[New-CsNetworkInterSitePolicy](/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[Get-CsNetworkInterSitePolicy](/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[Set-CsNetworkInterSitePolicy](/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[Remove-CsNetworkInterSitePolicy](/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)