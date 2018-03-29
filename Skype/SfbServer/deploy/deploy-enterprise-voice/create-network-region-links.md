---
title: 在 Skype for Business Server 2015 中创建网络区域链接
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
description: 创建或修改用于业务服务器通过企业语音调用许可控制在 Skype 的网络区域链接。
ms.openlocfilehash: f2b9ba5d6ccf2c2648bf755306001350f82c2931
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="create-network-region-links-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中创建网络区域链接
 
创建或修改用于业务服务器通过企业语音调用许可控制在 Skype 的网络区域链接。 
  
网络内的区域通过物理 WAN 连接进行链接。 网络区域链接配置调用许可控制 (CAC) 的两个区域之间创建链接，设置带宽限制在这些区域之间的音频和视频通信。
  
示例拓扑具有一条 North America 和 APAC 区域之间的链接，以及一条 EMEA 和 APAC 区域之间的链接。 每一个这些区域链接受 WAN 带宽，地区链路带宽信息表中所述[示例： 收集业务服务器 2015年在 Skype 呼叫许可控制要求](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)。
  
### <a name="to-create-network-region-links-by-using-skype-for-business-server-management-shell"></a>通过 Skype 业务服务器管理外壳程序创建的区域网络链接

1. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
2. 运行 New-CsNetworkRegionLink cmdlet 创建区域链接并应用相应的带宽策略配置文件。例如，运行：
    
   ```
   New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
   ```

   ```
   New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
   ```

### <a name="to-create-network-region-links-by-using-skype-for-business-server-control-panel"></a>通过 Skype 业务服务器控件面板中创建网络区域链接

1. 打开 Skype 业务服务器的控制面板。
    
2. 在左侧导航栏中，单击“网络配置”****。
    
3. 单击“区域链接”****导航按钮。
    
4. 单击“新建”****。
    
5. 在“新建区域链接”****页上，单击“名称”****，然后键入网络区域链接的名称。
    
6. 单击“网络区域 #1”****，然后在列表中单击要链接到“网络区域 #2”的网络区域。
    
7. 单击“网络区域 #2”****，然后在列表中单击要链接到“网络区域 #1”的网络区域。
    
8. 也可以选择单击“带宽策略”****，然后选择要应用于网络区域链接的带宽策略配置文件。
    
    > [!NOTE]
    > 仅在网络区域链接受带宽限制，并且您希望使用 CAC 控制该链接上的媒体流量时，应用带宽策略。 
  
9. 单击“**提交**”。
    
10. 要为拓扑完成网络区域链接的创建，请使用其他区域的设置重复步骤 4 至 9。
    
## <a name="see-also"></a>另请参阅

#### 

[新 CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregionlink?view=skype-ps)
  
[获得 CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregionlink?view=skype-ps)
  
[一组 CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregionlink?view=skype-ps)
  
[删除 CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregionlink?view=skype-ps)

