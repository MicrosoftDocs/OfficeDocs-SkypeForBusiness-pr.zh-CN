---
title: 管理网络区域路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 网络区域路由定义一对网络区域之间的路线。 呼叫许可控制部署中的每对网络区域都需要网络区域路线。
ms.openlocfilehash: 174fdd021655f3e338001582a1409107b266582e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279506"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a>在 Skype for Business Server 中管理网络区域路由

*网络区域路由*定义一对网络区域之间的路线。 呼叫许可控制部署中的每对网络区域都需要网络区域路线。 这样部署中的每个网络区域便能够访问任何其他区域。 使用此 artilce 中的过程查看、创建、修改或删除网络区域路由。

## <a name="view-network-region-route-information"></a>查看网络区域路线信息 

呼叫许可控制 (CAC) 配置中的每个区域都必须有某种方式才能访问其他每个区域。 虽然区域链接为区域之间的连接设置带宽限制, 同时也表示物理链接, 但路由决定了连接从一个地区到另一个地区的链接路径。 使用以下过程可查看 Skype for business Server 控制面板或 Skype for business Server Management Shell 中的现有网络区域路由。 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a>在 "Skype for Business 服务器" 控制面板中查看网络区域路线信息

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 

3.  在左侧导航栏中, 单击 "**网络配置**", 然后单击 "**区域路由**"。

4.  在 "**区域路线**" 页面上, 单击要查看的地区路线。


    > [!NOTE]  
    > 一次只能查看一个区域路线。


5.  在“编辑”**** 菜单上，单击“显示详细信息”****。


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 查看网络区域路由信息

可以使用 Windows PowerShell 和 CsNetworkInterRegionRoute cmdlet 查看网络区域路线信息。 此 cmdlet 既可以从 Skype for Business 服务器管理外壳运行, 也可以从 Windows PowerShell 的远程会话运行。 

### <a name="to-view-network-region-route-information"></a>查看网络区域路线信息

  - 若要查看有关所有网络区域路由的信息, 请在 Skype for Business Server 命令行管理器中键入以下命令, 然后按 ENTER:
    
        Get-CsNetworkInterRegionRoute
    
    这将返回与以下类似的信息：
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

有关详细信息, 请参阅[CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet 的帮助主题。


## <a name="create-or-modify-network-region-routes"></a>创建或修改网络区域路由

呼叫许可控制 (CAC) 配置中的每个区域都必须有某种方式才能访问其他每个区域。 虽然区域链接为区域之间的连接设置带宽限制, 同时也表示物理链接, 但路由决定了连接从一个地区到另一个地区的链接路径。 您可以使用 Skype for Business 服务器控制面板配置网络区域路由。 从 "Skype for Business 服务器" 控制面板中, 您可以创建、修改或删除网络区域路线。 使用本主题创建或修改网络区域路线。 

### <a name="to-create-a-network-region-route"></a>创建网络区域路由

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 

3.  在左侧导航栏中, 单击 "**网络配置**", 然后单击 "**区域路由**"。

4.  在 "**区域路由**" 页面上, 单击 "**新建**"。

5.  在 "**新区域路由**" 中, 在 "**名称**" 字段中键入值。
   
    > [!NOTE]  
    > 此值在 Skype for Business 服务器部署中必须是唯一的。

6.  从 "**网络区域\#1** " 下拉列表中, 选择两个要通过此路由连接的区域之一。

7.  从 "**网络区域\#2** " 下拉列表中, 选择此路由的其他区域。 此区域必须与为 "网络区域\#1" 选择的区域不同。

8.  使用 "**网络区域链接**" 列表框将区域链接添加到路由。 单击 "**添加**" 按钮以显示 "**区域链接**" 页面。 单击要添加到此路由的区域链接, 然后单击 **"确定"**。
    
    > [!NOTE]  
    > 继续单击 "**添加**" 按钮以添加更多链接, 或选择一个链接, 然后单击 "**删除**" 以删除链接。

9.  单击“**提交**”。


### <a name="to-modify-a-network-region-route"></a>修改网络区域路由

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 

3.  在左侧导航栏中, 单击 "**网络配置**", 然后单击 "**区域路由**"。

4.  在 "**区域路由**" 页面上, 单击要修改的区域路由。

5.  在“编辑”**** 菜单上，单击“显示详细信息”****。

6.  在 "**编辑区域" 路由**中, 可以修改此路由所联接的区域和与该路由关联的区域链接。

7.  单击“**提交**”。


## <a name="delete-existing-network-region-routes"></a>删除现有网络区域路由

呼叫许可控制 (CAC) 配置中的每个区域都必须有某种方式才能访问其他每个区域。 虽然区域链接为区域之间的连接设置带宽限制, 同时也表示物理链接, 但路由决定了连接从一个地区到另一个地区的链接路径。 您可以使用 Skype for Business 服务器控制面板配置网络区域路由。 从 "Skype for Business 服务器" 控制面板中, 您可以创建、修改或删除网络区域路线。 使用本主题删除现有网络区域路由。 

### <a name="to-delete-a-network-region-route"></a>删除网络区域路由

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 

3.  在左侧导航栏中, 单击 "**网络配置**", 然后单击 "**区域路由**"。

4.  在 "**区域路由**" 页面上, 单击要删除的区域路由。

    > [!NOTE]  
    > 您可以一次删除多个区域路线。 若要执行此操作, 请在按住 CTRL 键的同时按 CTRL 并选择多个区域路由。 或者, 若要选择所有区域路由, 请单击 "**编辑**" 菜单上的 "**全选**"。

5.  在 "**编辑**" 菜单上, 单击 "**删除**"。

6.  单击“**确定**”。



## <a name="see-also"></a>另请参阅

[在 Skype for Business Server 中管理网络区域](managing-network-regions.md)

[New-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
