---
title: 链接网络区域
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: '您可以配置呼叫允许控制 (CAC) 的一部分的两个网络区域之间的链接。 '
ms.openlocfilehash: 4ea6ddcc72d2cadea32608288d1db93ba8505aee
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884682"
---
# <a name="linking-network-regions-in-skype-for-business-server"></a>在 Skype for Business Server 中链接网络区域

您可以配置呼叫允许控制 (CAC) 的一部分的两个网络区域之间的链接。 使用本文中的部分以查看 newtwork 区域链接信息或者配置或删除网络区域链接。 

## <a name="view-network-region-link-information"></a>查看网络区域链接信息 

您可以查看作为呼叫允许控制 (CAC) 的一部分的两个网络区域之间的链接。 在网络中的区域链接通过物理广域网 (wan) 连接。 您可以使用业务 Server Control Panel 的 Skype 查看两个网络区域之间的现有链接。 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a>若要查看网络区域链接 Skype 中的业务 Server Control Panel

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 

3.  在左侧的导航栏中，单击**网络配置**，然后单击**区域链接**。

4.  在**区域链接**页上，单击您想要查看的区域链接。
    
    > [!NOTE]  
    > 您只能查看一个区域链接信息一次。

5.  从**编辑**菜单上，选择**显示详细信息**。

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell cmdlet 查看网络区域链接信息

您可以使用 Windows PowerShell 和**Get-csnetworkregionlink** cmdlet 查看网络区域链接。 从业务 Server 命令行管理程序 Skype 或 Windows PowerShell 远程会话，您可以运行此 cmdlet。 


### <a name="to-view-network-region-link-information"></a>若要查看网络区域链接信息

  - 若要查看有关所有网络区域链接的信息，业务 Server Management Shell，Skype 中键入以下命令，然后按 ENTER:
    
        Get-CsNetworkRegionLink
    
    此命令会返回类似下列信息：
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California


有关详细信息，请参阅[Get-csnetworkregionlink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)。


## <a name="configure-network-region-links"></a>配置网络区域链接 

您可以配置呼叫允许控制 (CAC) 的一部分的两个网络区域之间的链接。 在网络中的区域链接通过物理广域网 (wan) 连接。 可以使用业务 Server Control Panel 的 Skype 定义两个网络区域之间的链接和这些区域之间的音频和视频连接设置带宽限制。

### <a name="to-create-a-network-region-link"></a>创建网络区域链接

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 

3.  在左侧的导航栏中，单击**网络配置**，然后单击**区域链接**。

4.  在**区域链接**页上，单击**新建**。

5.  在**新建区域链接**中，键入**名称**字段中的值。
 
    > [!NOTE]  
    > 此值必须是唯一您 Skype 业务服务器部署中。

6.  从**网络区域\#1**下拉列表中，选择要链接的两个区域之一。

7.  从**网络区域\#2**下拉列表中，选择要链接的其他区域。 此区域必须不同于网络区域选择的区域\#1。

8.  （可选）如果您想要在这些区域之间的音频或视频呼叫设置带宽限制，请从**带宽策略**下拉列表中选择带宽策略配置文件。

9.  单击“**提交**”。

### <a name="to-modify-a-network-region-link"></a>修改网络区域链接

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 

3.  在左侧的导航栏中，单击**网络配置**，然后单击**区域链接**。

4.  在**区域链接**页上，单击要修改的区域链接。

5.  在“编辑”**** 菜单上，单击“显示详细信息”****。

6.  在**编辑区域链接**，您可以修改链接的区域或此链接的带宽策略配置文件。

7.  单击“**提交**”。


## <a name="delete-network-region-links"></a>删除网络区域链接

您可以配置呼叫允许控制 (CAC) 的一部分的两个网络区域之间的链接。 在网络中的区域链接通过物理广域网 (wan) 连接。 您可以使用业务 Server Control Panel 的 Skype 删除现有两个网络区域之间的链接。 

### <a name="to-delete-a-network-region-link"></a>删除网络区域链接

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 

3.  在左侧的导航栏中，单击**网络配置**，然后单击**区域链接**。

4.  在**区域链接**页上，单击您想要删除的区域链接。
 
    > [!NOTE]  
    > 您可以一次删除多个区域链接。 若要执行此操作，请按住 CTRL 并按住 CTRL 键选择多个区域链接。 或者，若要选择所有区域链接，<STRONG>都选择全部</STRONG>上单击<STRONG>编辑</STRONG>菜单。

5.  从**编辑**菜单上，选择**删除**。

6.  单击“**确定**”。


## <a name="see-also"></a>另请参阅

[New-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  

[Set-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  

[Remove-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  

[Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
