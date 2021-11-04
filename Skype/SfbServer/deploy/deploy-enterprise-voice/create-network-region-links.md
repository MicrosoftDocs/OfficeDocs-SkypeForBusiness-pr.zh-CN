---
title: 在站点内创建网络Skype for Business Server
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
ms.assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
description: 创建或修改网络区域链接，企业语音呼叫允许控制Skype for Business Server。
ms.openlocfilehash: dd46e7d7043d7d1814b7a23ac755624af0af4c69
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60775792"
---
# <a name="create-network-region-links-in-skype-for-business-server"></a>在站点内创建网络Skype for Business Server
 
创建或修改网络区域链接，企业语音呼叫允许控制Skype for Business Server。 
  
网络内的区域通过物理 WAN 连接进行链接。 网络区域链接在为呼叫允许控制 (CAC) 配置的两个区域之间创建链接，并设置这些区域之间的音频和视频流量的带宽限制。
  
示例拓扑具有一条 North America 和 APAC 区域之间的链接，以及一条 EMEA 和 APAC 区域之间的链接。 其中每个区域链接都受 WAN 带宽限制，如示例：收集呼叫允许控制要求中的区域链接带宽信息表[Skype for Business Server。](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)
  
### <a name="to-create-network-region-links-by-using-skype-for-business-server-management-shell"></a>使用命令行管理程序创建Skype for Business Server链接

1. 启动命令行Skype for Business Server：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击"Skype for Business Server **命令行管理程序"。**
    
2. 运行 New-CsNetworkRegionLink cmdlet 创建区域链接并应用相应的带宽策略配置文件。例如，运行：
    
   ```powershell
   New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
   ```

   ```powershell
   New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
   ```

### <a name="to-create-network-region-links-by-using-skype-for-business-server-control-panel"></a>使用控制面板创建网络Skype for Business Server链接

1. 打开Skype for Business Server控制面板"。
    
2. 在左侧导航栏中，单击“网络配置”。
    
3. 单击“区域链接”导航按钮。
    
4. 单击“新建”。
    
5. 在“新建区域链接”页上，单击“名称”，然后键入网络区域链接的名称。
    
6. 单击“网络区域 #1”，然后在列表中单击要链接到“网络区域 #2”的网络区域。
    
7. 单击“网络区域 #2”，然后在列表中单击要链接到“网络区域 #1”的网络区域。
    
8. 也可以选择单击“带宽策略”，然后选择要应用于网络区域链接的带宽策略配置文件。
    
    > [!NOTE]
    > 仅在网络区域链接受带宽限制，并且您希望使用 CAC 控制该链接上的媒体流量时，应用带宽策略。 
  
9. 单击“提交”。
    
10. 要为拓扑完成网络区域链接的创建，请使用其他区域的设置重复步骤 4 至 9。
    
## <a name="see-also"></a>另请参阅

[New-CsNetworkRegionLink](/powershell/module/skype/new-csnetworkregionlink?view=skype-ps)
  
[Get-CsNetworkRegionLink](/powershell/module/skype/get-csnetworkregionlink?view=skype-ps)
  
[Set-CsNetworkRegionLink](/powershell/module/skype/set-csnetworkregionlink?view=skype-ps)
  
[Remove-CsNetworkRegionLink](/powershell/module/skype/remove-csnetworkregionlink?view=skype-ps)