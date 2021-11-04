---
title: 管理网络区域路由
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 网络区域路由 定义一对网络区域之间的路由。 呼叫允许控制部署中的每对网络区域均需要网络区域路由。
ms.openlocfilehash: 30782564076c5a6bb5961f904fe30b1cfe0d0ef5
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60750191"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a>在 Skype for Business Server 中管理网络区域路由

*网络区域路由* 定义一对网络区域之间的路由。 呼叫允许控制部署中的每对网络区域均需要网络区域路由。 这样部署中的每个网络区域便能够访问其他每个区域。 使用本文中的过程可查看、创建、修改或删除网络区域路由。

## <a name="view-network-region-route-information"></a>查看网络区域路由信息 

呼叫允许控制服务 (CAC) 配置中的每个区域必须采用某种方式才能访问其他每个区域。 虽然区域链接会对区域之间的连接设置带宽限制，并代表物理链接，但路由可确定连接从一个区域到另一个区域将遍历的链接路径。 使用以下过程在控制面板或命令行管理程序Skype for Business Server现有Skype for Business Server路由。 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a>在控制面板中查看Skype for Business Server路由信息

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 

3.  在左侧导航栏中，单击"**网络配置"，** 然后单击"区域 **路由"。**

4.  在“区域路由”页上，单击要查看的区域路由。


    > [!NOTE]
    > 您一次只能查看一个区域路由。


5.  在“编辑”菜单上，单击“显示详细信息”。


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a>使用 Cmdlet 查看网络区域Windows PowerShell信息

网络区域路由信息可以通过使用 Windows PowerShell cmdlet Get-CsNetworkInterRegionRoute查看。 可以从命令行管理程序或 Skype for Business Server远程会话运行此 cmdlet Windows PowerShell。 

### <a name="to-view-network-region-route-information"></a>查看网络区域路由信息

  - 若要查看有关所有网络区域路由的信息，请在命令行管理程序中Skype for Business Server以下命令，然后按 Enter：
    
    **Get-CsNetworkInterRegionRoute**
    
    这将返回与以下类似的信息：
    
    标识 ： TransAmericaRoute<br/>
    NetworkRegionLinks ： {NorthwestToNortheast}<br/>
    InterNetworkRegionRouteID ： TransAmericaRoute<br/>
    NetworkRegionID1： Pacific Northwest<br/>
    NetworkRegionID2：东部<br/>

有关详细信息，请参阅 [Get-CsNetworkInterRegionRoute](/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet 的帮助主题。


## <a name="create-or-modify-network-region-routes"></a>创建或修改网络区域路由

呼叫允许控制服务 (CAC) 配置中的每个区域必须采用某种方式才能访问其他每个区域。 虽然区域链接会对区域之间的连接设置带宽限制，并代表物理链接，但路由可确定连接从一个区域到另一个区域将遍历的链接路径。 可以使用"Skype for Business Server控制面板"配置网络区域路由。 从Skype for Business Server控制面板中，可以创建、修改或删除网络区域路由。 使用本主题创建或修改网络区域路由。 

### <a name="to-create-a-network-region-route"></a>创建网络区域路由

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 

3.  在左侧导航栏中，单击"**网络配置"，** 然后单击"区域 **路由"。**

4.  在“区域路由”页上，单击“新建”。

5.  在“新建区域路由”的“名称”字段中键入值。
   
    > [!NOTE]  
    > 此值在部署中必须Skype for Business Server唯一。

6.  从" **网络区域 \# 1"** 下拉列表中，选择要通过此路由连接的两个区域之一。

7.  从 **"网络区域 \# 2"** 下拉列表中，为此路由选择另一区域。 此区域必须与为网络区域 1 所选的区域 \# 不同。

8.  使用“网络区域链接”列表框向路由添加区域链接。单击“添加”按钮以显示“区域链接”页面。单击某个区域链接将其添加到此路由，然后单击“确定”。
    
    > [!NOTE]  
    > 继续单击“添加”按钮添加更多链接，还可选择某个链接，然后单击“删除”删除该链接。

9.  单击“提交”。


### <a name="to-modify-a-network-region-route"></a>修改网络区域路由

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 

3.  在左侧导航栏中，单击"**网络配置"，** 然后单击"区域 **路由"。**

4.  在“区域路由”页上，单击要修改的区域路由。

5.  在“编辑”菜单上，单击“显示详细信息”。

6.  在“编辑区域路由”中，可以修改此路由连接的区域以及与此路由关联的区域链接。

7.  单击“提交”。


## <a name="delete-existing-network-region-routes"></a>删除现有网络区域路由

呼叫允许控制服务 (CAC) 配置中的每个区域必须采用某种方式才能访问其他每个区域。 虽然区域链接会对区域之间的连接设置带宽限制，并代表物理链接，但路由可确定连接从一个区域到另一个区域将遍历的链接路径。 可以使用"Skype for Business Server控制面板"配置网络区域路由。 从Skype for Business Server控制面板中，可以创建、修改或删除网络区域路由。 使用本主题可删除现有网络区域路由。 

### <a name="to-delete-a-network-region-route"></a>删除网络区域路由

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 

3.  在左侧导航栏中，单击"**网络配置"，** 然后单击"区域 **路由"。**

4.  在“区域路由”页上，单击要删除的区域路由。

    > [!NOTE]  
    > 可一次性删除多个区域路由。要执行此操作，请按住 Ctrl 键，同时选择多个区域路由。或者，要选择全部区域路由，请单击“编辑”菜单中的“全选”。

5.  在“编辑”菜单上，单击“删除”。

6.  单击“确定”。



## <a name="see-also"></a>另请参阅

[在 Skype for Business Server 中管理网络区域](managing-network-regions.md)

[New-CsNetworkInterRegionRoute](/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[Set-CsNetworkInterRegionRoute](/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[Remove-CsNetworkInterRegionRoute](/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[Get-CsNetworkInterRegionRoute](/powershell/module/skype/Get-CsNetworkInterRegionRoute)