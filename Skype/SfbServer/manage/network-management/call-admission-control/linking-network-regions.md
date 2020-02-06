---
title: 链接网络区域
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: '你可以配置两个网络区域之间的链接作为呼叫许可控制（CAC）的一部分。 '
ms.openlocfilehash: 4a643f34b9525b53168b9015b77a7f8292abd417
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817521"
---
# <a name="linking-network-regions-in-skype-for-business-server"></a>在 Skype for Business Server 中链接网络区域

你可以配置两个网络区域之间的链接作为呼叫许可控制（CAC）的一部分。 使用本文中的部分可查看 newtwork 区域链接信息，或配置或删除 netwrok 区域链接。 

## <a name="view-network-region-link-information"></a>查看网络区域链接信息 

您可以查看两个网络区域之间的链接，作为呼叫许可控制（CAC）的一部分。 网络中的区域通过物理广域网络（WAN）连接进行链接。 您可以使用 Skype for Business 服务器控制面板查看两个网络区域之间的现有链接。 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a>在 "Skype for Business 服务器" 控制面板中查看网络区域链接

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 

3.  在左侧导航栏中，单击 "**网络配置**"，然后单击 "**区域链接**"。

4.  在 "**区域链接**" 页面上，单击要查看的区域链接。
    
    > [!NOTE]  
    > 一次只能查看有关一个区域链接的信息。

5.  从 "**编辑**" 菜单中，选择 "**显示详细信息**"。

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell cmdlet 查看网络区域链接信息

你可以使用 Windows PowerShell 和**CsNetworkRegionLink** cmdlet 查看网络区域链接。 你可以从 Skype for Business Server Management Shell 或从 Windows PowerShell 的远程会话运行此 cmdlet。 


### <a name="to-view-network-region-link-information"></a>查看网络区域链接信息

  - 若要查看有关所有网络区域链接的信息，请在 Skype for Business Server 命令行管理器中键入以下命令，然后按 ENTER：
    
        Get-CsNetworkRegionLink
    
    此命令会返回类似下列信息：
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California


有关详细信息，请参阅[CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)。


## <a name="configure-network-region-links"></a>配置网络区域链接 

你可以配置两个网络区域之间的链接作为呼叫许可控制（CAC）的一部分。 网络中的区域通过物理广域网络（WAN）连接进行链接。 您可以使用 Skype for Business 服务器控制面板定义两个网络区域之间的链接，并设置这些区域之间的音频和视频连接的带宽限制。

### <a name="to-create-a-network-region-link"></a>创建网络区域链接

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 

3.  在左侧导航栏中，单击 "**网络配置**"，然后单击 "**区域链接**"。

4.  在 "**区域链接**" 页面上，单击 "**新建**"。

5.  在 "**新区域链接**" 中，在 "**名称**" 字段中键入值。
 
    > [!NOTE]  
    > 此值在 Skype for Business 服务器部署中必须是唯一的。

6.  从 "**网络区域\#1** " 下拉列表中，选择要链接的两个区域之一。

7.  从 "**网络区域\#2** " 下拉列表中，选择要链接的其他区域。 此区域必须与为 "网络区域\#1" 选择的区域不同。

8.  可选如果您想要对这些区域之间的音频或视频通话设置带宽限制，请从 "**带宽策略**" 下拉列表中选择一个带宽策略配置文件。

9.  单击“**提交**”。

### <a name="to-modify-a-network-region-link"></a>修改网络区域链接

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 

3.  在左侧导航栏中，单击 "**网络配置**"，然后单击 "**区域链接**"。

4.  在 "**区域链接**" 页面上，单击要修改的区域链接。

5.  在“编辑”**** 菜单上，单击“显示详细信息”****。

6.  在 "**编辑区域" 链接**中，可以修改链接的区域或此链接的 "带宽策略" 配置文件。

7.  单击“**提交**”。


## <a name="delete-network-region-links"></a>删除网络区域链接

你可以配置两个网络区域之间的链接作为呼叫许可控制（CAC）的一部分。 网络中的区域通过物理广域网络（WAN）连接进行链接。 您可以使用 Skype for Business 服务器控制面板删除两个网络区域之间的现有链接。 

### <a name="to-delete-a-network-region-link"></a>删除网络区域链接

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 

3.  在左侧导航栏中，单击 "**网络配置**"，然后单击 "**区域链接**"。

4.  在 "**区域链接**" 页面上，单击要删除的区域链接。
 
    > [!NOTE]  
    > 您可以一次删除多个区域链接。 若要执行此操作，请在按住 CTRL 键的同时按 CTRL 并选择多个区域链接。 或者，若要选择所有区域链接，请单击 "<STRONG>编辑</STRONG>" 菜单上的 "<STRONG>全选</STRONG>"。

5.  从 "**编辑**" 菜单中，选择 "**删除**"。

6.  单击“**确定**”。


## <a name="see-also"></a>另请参阅

[New-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  

[Set-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  

[Remove-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  

[Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
