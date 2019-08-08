---
title: 在 Skype for Business 服务器中创建网络站点间策略
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
ms.assetid: b0714aae-55dc-4587-b718-34a03f596b22
description: 创建网络间策略, 这些策略由 Skype for Business 服务器中的 "企业语音呼叫许可控制" 使用。
ms.openlocfilehash: ac03057de5b6e25e2b9de812f0d53ae02811d456
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233480"
---
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a>在 Skype for Business 服务器中创建网络站点间策略
 
创建网络间策略, 这些策略由 Skype for Business 服务器中的 "企业语音呼叫许可控制" 使用。 
  
网络站点间策略定义其间具有直接 WAN 链路的站点间的带宽限制。
  
> [!IMPORTANT]
> 只有当两个网络站点之间有直接交叉链接时,*才*需要网络间策略。
  
在示例拓扑北美区域中，Reno 和 Albuquerque 站点之间具有直接链接。这两个站点需要可应用相应带宽策略配置文件的站点间策略。以下示例将应用 20Mb_Link 配置文件。
  
### <a name="to-create-a-network-inter-site-policy"></a>创建网络站点间策略

1. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。
    
2. 运行 New-CsNetworkInterSitePolicy cmdlet 创建网络站点间策略并为两个具有直接交叉链接的站点应用相应的带宽策略配置文件。例如，运行：
    
   ```
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. 根据需要重复步骤 2，以便为具有直接交叉链接的所有网络站点对创建网络站点间策略。
    
## <a name="see-also"></a>另请参阅

[New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)
