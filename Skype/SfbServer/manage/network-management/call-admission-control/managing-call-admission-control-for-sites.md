---
title: 管理网站的呼叫允许控制
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: “网络站点”是指部署了呼叫允许控制 (CAC)、E9-1-1 和媒体旁路的每个网络区域内的办公室或位置。
ms.openlocfilehash: a178839fb87e47dda874d22d13e5da799f80cbff
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62402916"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a>在 Skype for Business Server 中管理站点的呼叫允许控制

“网络站点”是指部署了呼叫允许控制 (CAC)、E9-1-1 和媒体旁路的每个网络区域内的办公室或位置。 使用本文中的过程为网络站点配置呼叫允许控制。

## <a name="configure-network-site-links"></a>配置网络站点链接

在呼叫允许控制 (CAC) 配置中，可以创建定义直接链接的站点之间的带宽限制的网络站点间策略。 当两个网络站点共享一条直接链接时，可定义这两个站点之间的音频和视频连接的带宽限制。 不能使用 Skype for Business Server 控制面板配置网络站点策略，这只能通过使用命令行管理程序中的 cmdlet Skype for Business Server完成。 您可以创建、修改和删除网络站点链接 (命令行管理程序) 网络站点间Skype for Business Server策略。

### <a name="to-create-a-network-site-link"></a>创建网络站点链接

1.  以 RTCUniversalServerAdmins 组的成员或必要的用户权限Skype for Business Server命令行管理程序安装的计算机。

2.  启动命令行Skype for Business Server：单击"开始 **"，单击**"所有程序 **"****，单击**"Skype for Business Server"，然后单击"Skype for Business Server **命令行管理程序"**。

3.  在命令提示符处，键入以下命令，取代有效的配置值：
    
     **New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits**
    
    此示例创建一个名为 RenoPortland\_ 的新网络站点链接，该链接设置 Reno 和 Portland 网络站点之间的带宽限制。 运行此命令之前，必须已存在网络站点和带宽策略配置文件。

有关详细的参数说明，请参阅 [New-CsNetworkInterSitePolicy](/powershell/module/skype/New-CsNetworkInterSitePolicy)。 要检索可应用于网络站点链接的带宽策略配置文件列表，请调用 **Get-CsNetworkBandwidthPolicyProfile** cmdlet。 有关详细信息，请参阅 [Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)。

### <a name="to-modify-a-network-site-link"></a>修改网络站点链接

1.  以 RTCUniversalServerAdmins 组的成员或必要的用户权限Skype for Business Server命令行管理程序安装的计算机。

2.  启动命令行Skype for Business Server：单击"开始 **"，单击**"所有程序 **"****，单击**"Skype for Business Server"，然后单击"Skype for Business Server **命令行管理程序"**。

3.  使用 **Set-CsNetworkInterSitePolicy** cmdlet 修改给定网络站点链接的属性。 可以修改连接站点中的任一个（或两个），也可以修改与链接关联的带宽策略配置文件。 下面是修改名为 RenoPortland\_ 的站点链接的带宽策略配置文件的示例：
    
    **Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits**

有关详细的参数说明，请参阅 [Set-CsNetworkInterSitePolicy](/powershell/module/skype/Set-CsNetworkInterSitePolicy)。


### <a name="to-delete-a-network-site-link"></a>删除网络站点链接

1.  以 RTCUniversalServerAdmins 组的成员或必要的用户权限Skype for Business Server命令行管理程序安装的计算机。

2.  启动命令行Skype for Business Server：单击"开始 **"，单击**"所有程序 **"****，单击**"Skype for Business Server"，然后单击"Skype for Business Server **命令行管理程序"**。

3.  使用 **Remove-CsNetworkInterSitePolicy** cmdlet 删除网络站点链接。 以下示例删除 RenoPortland\_ 网络站点链接：
    
    **Remove-CsNetworkInterSitePolicy -Identity Reno_Portland**

有关详细的参数说明，请参阅 [Remove-CsNetworkInterSitePolicy](/powershell/module/skype/Remove-CsNetworkInterSitePolicy)。


## <a name="view-network-site-information"></a>查看网络站点信息

网络站点是指在部署了呼叫允许控制 (CAC) 或增强型 9-1-1 的每个区域中配置的办公室或位置。 可以在控制面板或命令行管理程序Skype for Business Server网络Skype for Business Server信息。 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a>在控制面板中Skype for Business Server网络站点信息

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 

3.  在左侧导航栏中，单击" **网络配置"**，然后单击"站点 **"**。

4.  在“站点”页上，单击要查看的站点。
 
    > [!NOTE]
    > 一次只能查看一个站点的信息。

5.  在“编辑”菜单上，单击“显示详细信息”。


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a>使用 cmdlet 查看Windows PowerShell站点信息

您可以使用 Windows PowerShell cmdlet 和 Get-CsNetworkSite 查看网络站点信息。 可以从命令行管理程序或 Skype for Business Server远程会话运行此 cmdlet Windows PowerShell。 

### <a name="to-view-network-site-information"></a>查看网络站点信息

  - 若要查看有关所有网络站点的信息，请在命令行管理程序中Skype for Business Server以下命令，然后按 Enter：
    
    **Get-CsNetworkSite**
    
    这将返回与以下类似的信息：
    
    标识 ：Redmond<br/>
    NetworkSiteID ： Redmond<br/>
    说明：<br/>
    NetworkRegionID ： Pacific Northwest<br/>
    BypassID ：3b232b84-2c1d-4da2-8181-e9330bafebe9<br/>
    BWPolicyProfileID ：<br/>
    LocationPolicy ：<br/>

有关详细信息，请参阅 [Get-CsNetworkSite](/powershell/module/skype/Get-CsNetworkSite) cmdlet 的帮助主题。


## <a name="create-or-modify-network-sites"></a>创建或修改网络站点 

网络站点是指在部署了呼叫允许控制 (CAC) 或增强型 9-1-1 的每个区域中配置的办公室或位置。 可以使用"Skype for Business Server控制面板"配置网站并将其与区域关联。 例如，可将北美网络区域与 Chicago、Redmond 和 Vancouver 之类的网络站点关联。 必须为组织中的每个站点创建一个 CAC 网络站点，即使该站点没有带宽限制也应如此。 从Skype for Business Server控制面板中，可以创建、修改和删除网络站点。 使用下面的过程可创建或修改网络站点。 

### <a name="to-create-a-network-site"></a>创建网络站点

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 

3.  在左侧导航栏中，单击" **网络配置"**，然后单击"站点 **"**。

4.  在“站点”页上，单击“新建”。

5.  在“新建站点”的“名称”字段中，键入此站点的名称。

    > [!NOTE]  
    > 站点名称在部署中必须Skype for Business Server唯一。

6.  在“区域”下拉列表中，选择与此站点关联的网络区域。

7.  （可选）如果要对此站点的音频或视频呼叫设置带宽限制，请从“带宽策略”下拉列表中选择具有相应设置的带宽策略配置文件。
 
    > [!NOTE]  
    > 可以在"网络配置"组的"策略分析"页上查看可用带宽策略配置文件的详细信息，或创建新的 **带宽策略** 配置文件。 有关详细信息，请参阅 [管理网络带宽策略配置文件](managing-network-bandwidth-policy-profiles.md)。

8.  （可选）如果要为此站点提供位置设置，请从“位置策略”下拉列表中选择位置策略。

    > [!NOTE]  
    > 位置策略会将特定的增强型 9-1-1 (E9-1-1) 和客户端位置设置分配给站点。 在“网络配置”组的“位置策略”页上，可以查看可用位置策略的详细信息，或创建新的位置策略。 

9.  （可选）在“说明”字段中键入值，用以提供仅通过名称无法表达的更多有关该站点的信息。

10. 单击“提交”。

    > [!NOTE]  
    > 创建新网络站点时，不要使用“关联子网”表。 创建或修改子网时，会将子网与站点相关联。 有关详细信息，请参阅 [管理网络子网](managing-network-subnets.md)。

### <a name="to-modify-a-network-site"></a>修改网络站点

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 

3.  在左侧导航栏中，单击" **网络配置"**，然后单击"站点 **"**。

4.  在“站点”页上，单击要修改的站点。

5.  在“编辑”菜单上，单击“显示详细信息”。

6.  在“编辑站点”页上，可以修改与站点关联的说明、区域、带宽策略配置文件以及位置策略。 有关详细信息，请参阅 [上面的创建网络](#to-create-a-network-site) 站点。

7.  单击“提交”。

不能修改此页面中的“关联子网”表。关联子网列表仅供参考，以使您注意修改站点设置时将影响的子网。


## <a name="delete-an-existing-network-site"></a>删除现有网络站点

网络站点是指在部署了呼叫允许控制 (CAC) 或增强型 9-1-1 的每个区域中配置的办公室或位置。 可以使用"Skype for Business Server控制面板"配置网站并将其与区域关联。 例如，可将北美网络区域与 Chicago、Redmond 和 Vancouver 之类的网络站点关联。 必须为组织中的每个站点创建一个 CAC 网络站点，即使该站点没有带宽限制也应如此。 从Skype for Business Server控制面板中，可以创建、修改和删除网络站点。 使用以下过程可删除现有网络站点。 有关创建或修改网络站点的详细信息，请参阅管理网站的呼叫 [允许控制](managing-call-admission-control-for-sites.md)。


### <a name="to-delete-a-network-site"></a>删除网络站点

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 

3.  在左侧导航栏中，单击" **网络配置"**，然后单击"站点 **"**。

4.  在“站点”页上，单击要删除的站点。

    > [!NOTE]  
    > 可一次性删除多个站点。要执行此操作，请按住 Ctrl 键，同时选择多个站点。或者，要选择全部站点，请单击“编辑”菜单中的“全选”。

5.  在“编辑”菜单上，单击“删除”。

6.  单击“确定”。
    

    > [!WARNING]  
    > 不能删除与网络子网关联的网络站点。如果尝试删除与某个子网关联的站点，您将收到错误消息。要查看站点是否与任何子网关联，请单击相应的站点，然后单击“编辑”菜单中的“显示详细信息”。


## <a name="see-also"></a>另请参阅


[New-CsNetworkInterSitePolicy](/powershell/module/skype/New-CsNetworkInterSitePolicy) 
 
[Set-CsNetworkInterSitePolicy](/powershell/module/skype/Set-CsNetworkInterSitePolicy)  

[Remove-CsNetworkInterSitePolicy](/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  

[Get-CsNetworkInterSitePolicy](/powershell/module/skype/Get-CsNetworkInterSitePolicy)  

[Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[New-CsNetworkSite](/powershell/module/skype/New-CsNetworkSite)

[Set-CsNetworkSite](/powershell/module/skype/Set-CsNetworkSite)

[Remove-CsNetworkSite](/powershell/module/skype/Remove-CsNetworkSite)  

[Get-CsNetworkSite](/powershell/module/skype/Get-CsNetworkSite)