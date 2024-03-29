---
title: 链接网络区域
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
description: '您可以配置两个网络区域之间的链接，以作为呼叫允许控制 (CAC) 的一部分。 '
---


# <a name="linking-network-regions-in-skype-for-business-server"></a>在 Skype for Business Server 中链接网络区域

您可以配置两个网络区域之间的链接，以作为呼叫允许控制 (CAC) 的一部分。 使用本文中的各节查看 newtwork 区域链接信息，或者配置或删除 netwrok 区域链接。 

## <a name="view-network-region-link-information"></a>查看网络区域链接信息 

您可以查看两个网络区域之间作为呼叫允许控制 (CAC) 的一部分的链接。 网络内的区域通过物理广域网 (WAN) 连接进行链接。 可以使用"Skype for Business Server控制面板"查看两个网络区域之间的现有链接。 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a>在控制面板中查看Skype for Business Server区域链接

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 

3.  在左侧导航栏中，单击" **网络配置"**，然后单击"区域 **链接"**。

4.  在“区域链接”页上，单击要查看的区域链接。
    
    > [!NOTE]
    > 您一次只能查看一个区域链接的相关信息。

5.  从“编辑”菜单中选择“显示详细信息”。

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a>使用 cmdlet 查看网络区域Windows PowerShell信息

可以使用 **Get-CsNetworkRegionLink** cmdlet 和 Windows PowerShell查看网络区域链接。 还可从 Skype for Business Server Management Shell 或 Windows PowerShell 远程会话运行此 cmdlet。 


### <a name="to-view-network-region-link-information"></a>查看网络区域链接信息

  - 若要查看有关所有网络区域链接的信息，请在命令行管理程序中键入Skype for Business Server命令，然后按 Enter：
    
    **Get-CsNetworkRegionLink**
    
    此命令会返回类似下列信息：
    
       标识 ：NorthwestToCalifor pacific BWPolicyProfileID ： NetworkRegionLinkID ： NorthwestToCalifor进行 NetworkRegionID1 ： Pacific Northwest NetworkRegionID2 ： 加利福尼亚


有关详细信息，请参阅[Get-CsNetworkRegionLink](/powershell/module/skype/Get-CsNetworkRegionLink)。


## <a name="configure-network-region-links"></a>配置网络区域链接 

您可以配置两个网络区域之间的链接，以作为呼叫允许控制 (CAC) 的一部分。 网络内的区域通过物理广域网 (WAN) 连接进行链接。 可以使用"Skype for Business Server控制面板"定义两个网络区域之间的链接，并设置这些区域之间的音频和视频连接的带宽限制。

### <a name="to-create-a-network-region-link"></a>创建网络区域链接

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 

3.  在左侧导航栏中，单击" **网络配置"**，然后单击"区域 **链接"**。

4.  在"区域 **链接"** 页上，单击" **新建"**。

5.  在 **"新建区域链接**"的"名称"字段中 **键入** 值。
 
    > [!NOTE]  
    > 此值在部署中必须Skype for Business Server唯一。

6.  从" **网络区域 \#1** "下拉列表中，选择要链接的两个区域之一。

7.  从 **"网络区域 \#2** "下拉列表中，选择要链接的其他区域。 此区域必须与为网络区域 1 所选的区域 \#不同。

8.   (可选) 如果要在这些区域之间的音频或视频呼叫上设置带宽限制，请从"带宽策略"下拉列表中选择带宽策略配置文件。

9.  单击“提交”。

### <a name="to-modify-a-network-region-link"></a>修改网络区域链接

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 

3.  在左侧导航栏中，单击" **网络配置"**，然后单击"区域 **链接"**。

4.  在" **区域链接"** 页上，单击要修改的区域链接。

5.  在“编辑”菜单上，单击“显示详细信息”。

6.  在 **"编辑区域链接**"中，可以修改链接的区域或此链接的带宽策略配置文件。

7.  单击“提交”。


## <a name="delete-network-region-links"></a>删除网络区域链接

您可以配置两个网络区域之间的链接，以作为呼叫允许控制 (CAC) 的一部分。 网络内的区域通过物理广域网 (WAN) 连接进行链接。 可以使用"Skype for Business Server控制面板"删除两个网络区域之间的现有链接。 

### <a name="to-delete-a-network-region-link"></a>删除网络区域链接

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 

3.  在左侧导航栏中，单击" **网络配置"**，然后单击"区域 **链接"**。

4.  在“区域链接”页上，单击要删除的区域链接。
 
    > [!NOTE]  
    > 可一次性删除多个区域链接。要执行此操作，请按住 Ctrl 键，同时选择多个区域链接。或者，要选择全部区域链接，请单击“编辑”<STRONG></STRONG>菜单中的“全选”<STRONG></STRONG>。

5.  从“编辑”菜单中选择“删除”。

6.  单击“确定”。


## <a name="see-also"></a>另请参阅

[New-CsNetworkRegionLink](/powershell/module/skype/New-CsNetworkRegionLink)  

[Set-CsNetworkRegionLink](/powershell/module/skype/Set-CsNetworkRegionLink)  

[Remove-CsNetworkRegionLink](/powershell/module/skype/Remove-CsNetworkRegionLink)  

[Get-CsNetworkRegionLink](/powershell/module/skype/Get-CsNetworkRegionLink)