---
title: 管理网站的呼叫允许控制
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 网络站点间办公室或位置中的每个网络区域呼叫允许控制 (CAC)、 E9-1-1 和媒体绕过部署。
ms.openlocfilehash: ecf23a8a052afbd21b02f8ff5507c248d42b7118
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "27223169"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a>管理 Business Server Skype 中的网站的呼叫允许控制

网络站点间办公室或位置中的每个网络区域呼叫允许控制 (CAC)、 E9-1-1 和媒体绕过部署。 使用本文中的过程配置网络站点的呼叫允许控制。

## <a name="configure-network-site-links"></a>配置网络站点链接

在呼叫允许控制 (CAC) 配置，您可以创建网络定义直接链接的站点间带宽限制的站点间策略。 当网络站点共享直接链接时，可以在这些两个站点之间定义连接音频和视频的带宽限制。 您无法使用的业务 Server Control Panel Skype 配置网络站点策略，这可以仅通过使用 for Business Server Management Shell cmdlet 从 Skype 完成。 您可以创建、 修改和删除业务 Server 命令行管理程序从 Skype 网络站点链接 （也称为网络站点间策略）。

### <a name="to-create-a-network-site-link"></a>创建网络站点链接

1.  登录到计算机的业务 Server Management Shell 的 Skype 或使用的必要用户权限的 RTCUniversalServerAdmins 组成员身份的安装。

2.  为业务 Server 命令行管理程序启动 Skype： 单击**开始**，单击**所有程序**、 都单击**Skype 业务服务器**，，然后都单击**Skype 的业务 Server Management Shell**。

3.  在命令提示符处，键入以下命令，取代有效的配置的值：
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    本示例创建新的网络站点链接名为 Reno\_波特兰里诺和波特兰网络站点之间设置带宽限制。 网络站点和带宽策略配置文件必须运行此命令之前已经存在。

有关详细的参数说明，请参阅[新建 CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)。 若要检索可应用于网络站点链接的带宽策略配置文件的列表，请调用**Get-csnetworkbandwidthpolicyprofile** cmdlet。 有关详细信息，请参阅[Get-csnetworkbandwidthpolicyprofile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)。

### <a name="to-modify-a-network-site-link"></a>修改网络站点链接

1.  登录到计算机的业务 Server Management Shell 的 Skype 或使用的必要用户权限的 RTCUniversalServerAdmins 组成员身份的安装。

2.  为业务 Server 命令行管理程序启动 Skype： 单击**开始**，单击**所有程序**、 都单击**Skype 业务服务器**，，然后都单击**Skype 的业务 Server Management Shell**。

3.  使用**Set-csnetworkintersitepolicy** cmdlet 可以修改给定的网络站点链接的属性。 您可以修改 （或两者） 或连接的站点，并且您可以修改与链接关联的带宽策略配置文件。 下面是一个示例修改名为 Reno 站点链接的带宽策略配置文件的\_波特兰：
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

有关详细的参数说明，请参阅[Set-csnetworkintersitepolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)。


### <a name="to-delete-a-network-site-link"></a>删除网络站点链接

1.  登录到计算机的业务 Server Management Shell 的 Skype 或使用的必要用户权限的 RTCUniversalServerAdmins 组成员身份的安装。

2.  为业务 Server 命令行管理程序启动 Skype： 单击**开始**，单击**所有程序**、 都单击**Skype 业务服务器**，，然后都单击**Skype 的业务 Server Management Shell**。

3.  使用**Remove-csnetworkintersitepolicy** cmdlet 可以删除网络站点链接。 下面的示例删除 Reno\_波特兰网络站点链接：
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

有关详细的参数说明，请参阅[Remove-csnetworkintersitepolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)。


## <a name="view-network-site-information"></a>查看网络站点信息

网络站点的办公室或配置呼叫允许控制 (CAC) 或增强型 9-1-1 部署的每个区域中的位置。 您可以查看网络站点信息中任一 Skype 业务 Server Control Panel 或 Skype 的业务 Server Management Shell。 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a>若要查看网络站点信息 Skype 中的业务 Server Control Panel

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 

3.  在左侧的导航栏中，单击**网络配置**，然后单击**网站**。

4.  在**网站**页上，单击您想要查看的站点。
 
    > [!NOTE]  
    > 您只能查看一个站点一次的信息。

5.  在“编辑”**** 菜单上，单击“显示详细信息”****。


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a>通过使用 Windows PowerShell cmdlet 查看网络站点信息

您可以使用 Windows PowerShell 和 Get-csnetworksite cmdlet 查看网络站点信息。 从业务 Server 命令行管理程序 Skype 或 Windows PowerShell 远程会话，则可以运行此 cmdlet。 

### <a name="to-view-network-site-information"></a>若要查看网络站点信息

  - 若要查看有关所有网络站点的信息，业务 Server Management Shell，Skype 中键入以下命令，然后按 ENTER:
    
        Get-CsNetworkSite
    
    这将返回与以下类似的信息：
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

有关详细信息，请参阅[Get-csnetworksite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) cmdlet 的帮助主题。


## <a name="create-or-modify-network-sites"></a>创建或修改网络站点 

网络站点的办公室或配置呼叫允许控制 (CAC) 或增强型 9-1-1 部署的每个区域中的位置。 为业务 Server Control Panel Skype 可用于配置站点和将它们与区域关联。 例如，网络区域北美可能与芝加哥，Redmond，等 Vancouver 的网络站点相关联。 CAC 网络站点必须创建为在组织内每个站点，即使该网站具有没有带宽限制。 从业务 Server Control Panel Skype 您可以创建、 修改和删除网络站点。 使用以下过程可创建或修改网络站点。 

### <a name="to-create-a-network-site"></a>创建网络站点

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 

3.  在左侧的导航栏中，单击**网络配置**，然后单击**网站**。

4.  在**网站**页上，单击**新建**。

5.  在**新的网站**中，键入此网站的**名称**字段的名称。

    > [!NOTE]  
    > 网站名称必须是唯一的业务服务器部署 Skype。

6.  在**区域**下拉列表中，选择与此站点关联的网络区域。

7.  （可选）如果您想要访问此网站的音频或视频呼叫设置带宽限制，具有相应设置从**带宽策略**下拉列表中选择带宽策略配置文件。
 
    > [!NOTE]  
    > 您可以查看可用带宽策略配置文件的详细信息，或创建一个新的带宽策略配置文件，在**网络配置**组**策略 Profil**网页上。 有关详细信息，请参阅[Managing 网络带宽策略配置文件](managing-network-bandwidth-policy-profiles.md)。

8.  （可选）如果您想要为此站点提供位置设置，请从**位置策略**下拉列表中选择位置策略。

    > [!NOTE]  
    > 位置策略分配特定的增强型 9-1-1 (E9-1-1) 和客户端位置设置到网站。 您可以查看可用位置策略的详细信息，或创建新的位置策略，从**位置策略**页上的**网络配置**组。 

9.  （可选）在**说明**字段，以提供有关该站点的名称本身不能表示的详细信息，请键入一个值。

10. 单击“**提交**”。

    > [!NOTE]  
    > 创建新的网络站点时不使用**关联子网**表。 当您创建或修改子网与站点关联子网。 有关详细信息，请参阅[管理网络子网](managing-network-subnets.md)。

### <a name="to-modify-a-network-site"></a>修改网络站点

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 

3.  在左侧的导航栏中，单击**网络配置**，然后单击**网站**。

4.  在**网站**页上，单击要修改的站点。

5.  在“编辑”**** 菜单上，单击“显示详细信息”****。

6.  在**编辑站点**页上，可以修改说明、 区域、 带宽策略配置文件和与网站关联的位置策略。 有关详细信息，请参阅[创建网络站点](#to-create-a-network-site)上面。

7.  单击“**提交**”。

不能修改此页上的**关联子网**表格。 关联子网列表提供的引用，以便了解当您修改的网站设置时，将影响哪些子网。


## <a name="delete-an-existing-network-site"></a>删除现有网络站点

网络站点的办公室或配置呼叫允许控制 (CAC) 或增强型 9-1-1 部署的每个区域中的位置。 为业务 Server Control Panel Skype 可用于配置站点和将它们与区域关联。 例如，网络区域北美可能与芝加哥，Redmond，等 Vancouver 的网络站点相关联。 CAC 网络站点必须创建为在组织内每个站点，即使该网站具有没有带宽限制。 从业务 Server Control Panel Skype 您可以创建、 修改和删除网络站点。 使用以下过程可删除现有网络站点。 有关创建或修改网络站点的详细信息，请参阅[Managing 呼叫允许控制的网站](managing-call-admission-control-for-sites.md)。


### <a name="to-delete-a-network-site"></a>删除网络站点

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 

3.  在左侧的导航栏中，单击**网络配置**，然后单击**网站**。

4.  在**网站**页上，单击您要删除的站点。

    > [!NOTE]  
    > 您可以一次删除多个站点。 若要执行此操作，请按住 CTRL 并按住 CTRL 键选择多个站点。 或者，若要选择所有网站，**都选择全部**上单击**编辑**菜单。

5.  在**编辑**菜单上，单击**删除**。

6.  单击“确定”****。
    

    > [!WARNING]  
    > 网络子网与关联时，不能删除网络站点。 如果尝试删除站点与子网关联将收到一条错误消息。 要查看网站是否与任何子网关联，请单击网站，然后单击**编辑**菜单上的**显示详细信息**。


## <a name="see-also"></a>另请参阅


[New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) 
 
[Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  

[Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  

[Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  

[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

[Set-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

[Remove-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  

[Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  