---
title: 管理网络区域路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 网络区域路由定义一对网络区域之间的路由。 每对网络区域中您的呼叫允许控制部署需要网络区域路由。
ms.openlocfilehash: 53b6383e08196fb22784f3fcd1e8d797c9b138de
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888847"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a>在 Skype for Business Server 中管理网络区域路由

*网络区域路由*定义一对网络区域之间的路由。 每对网络区域中您的呼叫允许控制部署需要网络区域路由。 这样部署中的每个网络区域便能够访问任何其他区域。 使用本节中此 artilce 以查看、 创建、 修改或删除网络区域路由。

## <a name="view-network-region-route-information"></a>查看网络区域路由信息 

呼叫允许控制 (CAC) 配置中的每个区域都必须具有一种方式访问每个其他区域。 虽然区域链接区域之间的连接设置带宽限制，并且还表示物理链路，路由可确定连接从一个区域将遍历到另一个的链接的路径。 使用以下过程可以查看现有网络区域路由中 Skype 业务 Server Control Panel 或 Skype 的业务 Server Management Shell。 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a>若要查看网络区域路由信息 Skype 中的业务 Server Control Panel

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 

3.  在左侧的导航栏中，单击**网络配置**，然后单击**区域路由**。

4.  在**区域路由**页上，单击您想要查看的区域路由。


    > [!NOTE]  
    > 一次只能查看一个区域路由。


5.  在“编辑”**** 菜单上，单击“显示详细信息”****。


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 查看网络区域路由信息

可以通过使用 Windows PowerShell 和 Get-csnetworkinterregionroute cmdlet 查看网络区域路由信息。 从业务 Server 命令行管理程序 Skype 或 Windows PowerShell 远程会话，则可以运行此 cmdlet。 

### <a name="to-view-network-region-route-information"></a>若要查看网络区域路由信息

  - 若要查看有关所有网络区域路由信息，业务 Server Management Shell，Skype 中键入以下命令，然后按 ENTER:
    
        Get-CsNetworkInterRegionRoute
    
    这将返回与以下类似的信息：
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

有关详细信息，请参阅[Get-csnetworkinterregionroute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet 的帮助主题。


## <a name="create-or-modify-network-region-routes"></a>创建或修改网络区域路由

呼叫允许控制 (CAC) 配置中的每个区域都必须具有一种方式访问每个其他区域。 虽然区域链接区域之间的连接设置带宽限制，并且还表示物理链路，路由可确定连接从一个区域将遍历到另一个的链接的路径。 您可以使用业务 Server Control Panel 的 Skype 配置网络区域路由。 从业务 Server 控制面板的 Skype，您可以创建、 修改或删除网络区域路由。 使用本主题可创建或修改网络区域路由。 

### <a name="to-create-a-network-region-route"></a>创建网络区域路由

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 

3.  在左侧的导航栏中，单击**网络配置**，然后单击**区域路由**。

4.  在**区域路由**页上，单击**新建**。

5.  在**新建区域路由**中，键入**名称**字段中的值。
   
    > [!NOTE]  
    > 此值必须是唯一您 Skype 业务服务器部署中。

6.  从**网络区域\#1**下拉列表中，选择要通过此路由进行连接的两个区域之一。

7.  从**网络区域\#2**下拉列表中，选择该路由的其他区域。 此区域必须不同于网络区域选择的区域\#1。

8.  使用**网络区域链接**列表框添加到路由的区域链接。 单击**添加**按钮以显示**区域链接**页。 单击要添加到该路由，区域链接，然后单击**确定**。
    
    > [!NOTE]  
    > 继续单击**添加**按钮添加更多链接，或选择一个链接并单击**删除**以删除链接。

9.  单击“**提交**”。


### <a name="to-modify-a-network-region-route"></a>修改网络区域路由

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 

3.  在左侧的导航栏中，单击**网络配置**，然后单击**区域路由**。

4.  在**区域路由**页上，单击要修改的区域路由。

5.  在“编辑”**** 菜单上，单击“显示详细信息”****。

6.  在**编辑区域路由**，可以修改此路由连接的区域以及与此路由关联的区域链接。

7.  单击“**提交**”。


## <a name="delete-existing-network-region-routes"></a>删除现有网络区域路由

呼叫允许控制 (CAC) 配置中的每个区域都必须具有一种方式访问每个其他区域。 虽然区域链接区域之间的连接设置带宽限制，并且还表示物理链路，路由可确定连接从一个区域将遍历到另一个的链接的路径。 您可以使用业务 Server Control Panel 的 Skype 配置网络区域路由。 从业务 Server 控制面板的 Skype，您可以创建、 修改或删除网络区域路由。 使用本主题可删除现有网络区域路由。 

### <a name="to-delete-a-network-region-route"></a>删除网络区域路由

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 

3.  在左侧的导航栏中，单击**网络配置**，然后单击**区域路由**。

4.  在**区域路由**页上，单击您想要删除的区域路由。

    > [!NOTE]  
    > 您可以一次删除多个区域路由。 若要执行此操作，请按住 CTRL 并按住 CTRL 键选择多个区域路由。 或者，若要选择所有区域路由，**都选择全部**上单击**编辑**菜单。

5.  在**编辑**菜单上，单击**删除**。

6.  单击“**确定**”。



## <a name="see-also"></a>另请参阅

[在 Skype for Business Server 中管理网络区域](managing-network-regions.md)

[New-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
