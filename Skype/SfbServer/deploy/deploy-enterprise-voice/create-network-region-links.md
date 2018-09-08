---
title: 为 Business Server Skype 创建网络区域链接
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
description: 创建或修改网络区域链接，使用 Skype 中的企业语音呼叫允许控制业务服务器。
ms.openlocfilehash: fd74960ed2efe9e8e67c5682c5b30aac17c9b2b6
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23886462"
---
# <a name="create-network-region-links-in-skype-for-business-server"></a>为 Business Server Skype 创建网络区域链接
 
创建或修改网络区域链接，使用 Skype 中的企业语音呼叫允许控制业务服务器。 
  
网络内的区域通过物理 WAN 连接进行链接。网络区域链接在为呼叫允许控制 (CAC) 配置的两个区域之间创建链接，并为这两个区域之间的音频和视频流量设置带宽限制。
  
示例拓扑具有一条 North America 和 APAC 区域之间的链接，以及一条 EMEA 和 APAC 区域之间的链接。 每个区域链接受 WAN 带宽区域链路带宽信息表中所述[示例： 收集呼叫允许控制 Skype 中的业务服务器的要求](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)。
  
### <a name="to-create-network-region-links-by-using-skype-for-business-server-management-shell"></a>若要使用 Skype 业务 Server 命令行管理程序创建网络区域链接

1. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
2. 运行 New-CsNetworkRegionLink cmdlet 创建区域链接并应用相应的带宽策略配置文件。例如，运行：
    
   ```
   New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
   ```

   ```
   New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
   ```

### <a name="to-create-network-region-links-by-using-skype-for-business-server-control-panel"></a>若要使用 Skype 业务 Server 控制面板创建网络区域链接

1. 打开 Skype 业务 Server Control Panel。
    
2. 在左侧导航栏中，单击“网络配置”****。
    
3. 单击“区域链接”**** 导航按钮。
    
4. 单击“新建”****。
    
5. 在“新建区域链接”**** 页上，单击“名称”****，然后键入网络区域链接的名称。
    
6. 单击“网络区域 #1”****，然后在列表中单击要链接到“网络区域 #2”的网络区域。
    
7. 单击“网络区域 #2”****，然后在列表中单击要链接到“网络区域 #1”的网络区域。
    
8. 也可以选择单击“带宽策略”****，然后选择要应用于网络区域链接的带宽策略配置文件。
    
    > [!NOTE]
    > 仅在网络区域链接受带宽限制，并且您希望使用 CAC 控制该链接上的媒体流量时，应用带宽策略。 
  
9. 单击“**提交**”。
    
10. 要为拓扑完成网络区域链接的创建，请使用其他区域的设置重复步骤 4 至 9。
    
## <a name="see-also"></a>另请参阅

[新 CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregionlink?view=skype-ps)
  
[Get-csnetworkregionlink](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregionlink?view=skype-ps)
  
[设置 CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregionlink?view=skype-ps)
  
[删除 CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregionlink?view=skype-ps)