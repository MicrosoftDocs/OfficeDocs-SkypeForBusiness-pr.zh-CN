---
title: 在 Skype for Business Server 中创建网络区域间路由
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
ms.assetid: 5555262a-a502-4b01-9593-836dd30064f5
description: 创建或修改网络区域间路由，这些路由企业语音 Skype for Business Server 中的呼叫允许控制。
ms.openlocfilehash: d9ea8def930a075c93effede73ddb3f12d999334
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093120"
---
# <a name="create-network-interregional-routes-in-skype-for-business-server"></a>在 Skype for Business Server 中创建网络区域间路由
 
创建或修改网络区域间路由，这些路由企业语音 Skype for Business Server 中的呼叫允许控制。 
  
网络区域间路由定义一对网络区域之间的路由。 呼叫允许控制部署中的每对网络区域都需要网络区域间路由。 这样部署中的每个网络区域便能够访问任何其他区域。
  
虽然区域链接对区域之间的连接设置了带宽限制，但区域间路由可确定连接从一个区域到另一个区域将遍历的链接路径。
  
在示例拓扑中，必须为三个区域对分别定义网络区域间路由：北美/EMEA、EMEA/APAC 和北美/APAC。 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-management-shell"></a>使用 Skype for Business Server 命令行管理程序创建网络区域间路由

1. 启动 Skype for Business Server命令行管理程序：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**
    
2. 运行 **New-CsNetworkInterRegionRoute** cmdlet 来定义所需路由。 例如，运行：
    
   ```powershell
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
   ```

   ```powershell
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
   ```

   ```powershell
   New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
   ```

    > [!NOTE]
    > 北美/APAC 网络区域间路由需要两个网络区域链接，因为它们之间没有直接网络区域链接。 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-control-panel"></a>使用 Skype for Business Server 控制面板创建网络区域间路由

1. 打开 Skype for Business Server 控制面板。
    
2. 在左侧导航栏中，单击“网络配置”。
    
3. 单击“区域路由”导航按钮。
    
4. 单击“新建”。
    
5. 在"**新建区域路由"** 页上，单击"名称"，然后键入网络区域间路由的名称。
    
6. 单击“网络区域 #1”，然后在列表中单击要路由到网络区域 #2 的网络区域。
    
7. 单击“网络区域 #2”，然后在列表中单击要路由到网络区域 #1 的网络区域。
    
8. 单击 **"** 网络区域 **链接** "字段旁边的"添加"，然后添加将用于网络区域间路由的网络区域链接。
    
    > [!NOTE]
    > 如果要为彼此之间没有直接网络区域链接的两个网络区域创建路由，则必须添加所有必要的链接来完成路由。 例如，北美/APAC 网络区域间路由需要两个网络区域链接，因为它们之间没有直接网络区域链接。 
  
9. 单击“提交”。
    
10. 要完成为拓扑创建网络区域间路由，请通过其他网络区域间路由的设置重复步骤 4 到步骤 9。
    
## <a name="see-also"></a>另请参阅

[New-CsNetworkInterRegionRoute](/powershell/module/skype/new-csnetworkinterregionroute?view=skype-ps)
  
[Get-CsNetworkInterRegionRoute](/powershell/module/skype/get-csnetworkinterregionroute?view=skype-ps)
  
[Set-CsNetworkInterRegionRoute](/powershell/module/skype/set-csnetworkinterregionroute?view=skype-ps)
  
[Remove-CsNetworkInterRegionRoute](/powershell/module/skype/remove-csnetworkinterregionroute?view=skype-ps)