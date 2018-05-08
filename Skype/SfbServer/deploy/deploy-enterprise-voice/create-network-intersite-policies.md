---
title: 在 Skype for Business Server 2015 中创建网络站点间策略
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b0714aae-55dc-4587-b718-34a03f596b22
description: 创建网络站点间策略，使用 Skype 中的企业语音呼叫允许控制业务服务器。
ms.openlocfilehash: f8c09f850a001b634ee63199210733000775fd0a
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="create-network-intersite-policies-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中创建网络站点间策略
 
创建网络站点间策略，使用 Skype 中的企业语音呼叫允许控制业务服务器。 
  
网络站点间策略定义具有直接 WAN 链接它们之间的站点间带宽限制。
  
> [!IMPORTANT]
> 两个网络站点之间没有直接交叉链接时所需*仅*网络站点间策略。
  
在示例拓扑北美区域中，Reno 和 Albuquerque 站点之间具有直接链接。这两个站点需要可应用相应带宽策略配置文件的站点间策略。以下示例将应用 20Mb_Link 配置文件。
  
### <a name="to-create-a-network-inter-site-policy"></a>创建网络站点间策略

1. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
2. 运行 New-CsNetworkInterSitePolicy cmdlet 创建网络站点间策略并为两个具有直接交叉链接的站点应用相应的带宽策略配置文件。例如，运行：
    
   ```
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. 根据需要重复步骤 2，以便为具有直接交叉链接的所有网络站点对创建网络站点间策略。
    
## <a name="see-also"></a>另请参阅

#### 

[新 CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[Get-csnetworkintersitepolicy](https://docs.microsoft.com/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[Set-csnetworkintersitepolicy](https://docs.microsoft.com/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[Remove-csnetworkintersitepolicy](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)

