---
title: 在 Skype for Business Server 2015 中创建网络区域间路由
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
ms.assetid: 5555262a-a502-4b01-9593-836dd30064f5
description: 创建或修改网络 interregional 路由，使用 Skype 中的企业语音呼叫允许控制业务服务器。
ms.openlocfilehash: 22e7872c6faa989779a93b6524c1740386f32d7d
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="create-network-interregional-routes-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中创建网络区域间路由
 
创建或修改网络 interregional 路由，使用 Skype 中的企业语音呼叫允许控制业务服务器。 
  
网络 interregional 路由定义一对网络区域之间的路由。 呼叫允许控制部署中的每对网络区域均需要网络区域间路由。 这样部署中的每个网络区域便能够访问任何其他区域。
  
虽然区域链接会对区域之间的连接设置带宽限制，但是区域间路由可确定连接从一个区域到另一个区域将遍历的链接路径。
  
在示例拓扑中，必须为三个区域对中的每一对定义网络区域间路由：北美/EMEA、EMEA/APAC 以及北美/APAC。 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-management-shell"></a>使用 Skype 业务 Server 命令行管理程序创建网络 interregional 路由

1. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
2. 运行**新建 CsNetworkInterRegionRoute** cmdlet 可以定义所需的路由。 例如，运行：
    
   ```
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
   ```

   ```
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
   ```

   ```
   New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
   ```

    > [!NOTE]
    > 北美/APAC 的网络区域间路由需要两个网络区域链接，因为它们之间没有直接网络区域链接。 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-control-panel"></a>使用 Skype 业务 Server 控制面板创建网络 interregional 路由

1. 打开 Skype 业务 Server Control Panel。
    
2. 在左侧导航栏中，单击“网络配置”****。
    
3. 单击“区域路由”**** 导航按钮。
    
4. 单击“新建”****。
    
5. 在“**新建区域路由**”页上，单击“**名称**”，然后键入网络区域间路由的名称。
    
6. 单击“网络区域 #1”****，然后在列表中单击要路由到网络区域 #2 的网络区域。
    
7. 单击“网络区域 #2”****，然后在列表中单击要路由到网络区域 #1 的网络区域。
    
8. 单击“**网络区域链接**”字段旁边的“**添加**”，然后添加将用于网络区域间路由的网络区域链接。
    
    > [!NOTE]
    > 如果要为彼此之间没有直接网络区域链接的两个网络区域创建路由，则必须添加所有必要的链接来完成路由。例如，北美/APAC 网络区域间路由需要两个网络区域链接，因为它们之间没有直接网络区域链接。 
  
9. 单击“**提交**”。
    
10. 要为拓扑完成网络区域间路由的创建，请为其他网络区域间路由重复步骤 4 至 步骤 9 的设置。
    
## <a name="see-also"></a>另请参阅

#### 

[新 CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/new-csnetworkinterregionroute?view=skype-ps)
  
[Get-csnetworkinterregionroute](https://docs.microsoft.com/powershell/module/skype/get-csnetworkinterregionroute?view=skype-ps)
  
[设置 CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/set-csnetworkinterregionroute?view=skype-ps)
  
[删除 CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkinterregionroute?view=skype-ps)

