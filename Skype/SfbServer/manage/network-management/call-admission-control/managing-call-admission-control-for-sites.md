---
title: 管理网站的呼叫许可控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 网络站点是呼叫许可控制 (CAC)、E9-1 和媒体绕过部署的每个网络区域内的办公室或位置。
ms.openlocfilehash: a90781eae38d92d560dd1bf34db3b6918e8aeaf5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279541"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a>在 Skype for Business Server 中管理站点的呼叫允许控制

网络站点是呼叫许可控制 (CAC)、E9-1 和媒体绕过部署的每个网络区域内的办公室或位置。 使用本文中的过程配置网络站点的 "呼叫许可控制"。

## <a name="configure-network-site-links"></a>配置网络站点链接

在呼叫许可控制 (CAC) 配置中, 你可以创建网络间策略来定义直接链接的网站之间的带宽限制。 当网络站点共享直接链接时, 可以在这两个站点之间定义音频和视频连接的带宽限制。 您不能使用 Skype for Business 服务器控制面板配置网络站点策略, 只能通过使用 Skype for Business Server 命令行管理程序中的 cmdlet 来执行此操作。 你可以从 Skype for Business Server 命令行管理程序创建、修改和删除网络网站链接 (也称为网络内部站点策略)。

### <a name="to-create-a-network-site-link"></a>创建网络站点链接

1.  登录到安装了 Skype for Business 服务器管理外壳的计算机作为 RTCUniversalServerAdmins 组的成员或具有必要的用户权限。

2.  启动 Skype for Business 服务器命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **skype for business 服务器**", 然后单击 " **skype for business 服务器管理外壳**"。

3.  在命令提示符处, 键入以下命令, 替换适用于您的配置的有效值:
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    此示例创建一个名为 Reno\_的新网络网站链接, 该链接设置 Reno 和网络站点之间的带宽限制。 运行此命令之前, 网络站点和带宽策略配置文件必须已经存在。

有关详细的参数说明, 请参阅[CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)。 若要检索可应用于网络站点链接的带宽策略配置文件的列表, 请调用**CsNetworkBandwidthPolicyProfile** cmdlet。 有关详细信息, 请参阅[CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)。

### <a name="to-modify-a-network-site-link"></a>修改网络站点链接

1.  登录到安装了 Skype for Business 服务器管理外壳的计算机作为 RTCUniversalServerAdmins 组的成员或具有必要的用户权限。

2.  启动 Skype for Business 服务器命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **skype for business 服务器**", 然后单击 " **skype for business 服务器管理外壳**"。

3.  使用**CsNetworkInterSitePolicy** cmdlet 修改给定网络网站链接的属性。 您可以修改两个 (或两者) 或连接的网站, 并且可以修改与链接关联的带宽策略配置文件。 下面是修改名为 Reno\_的网站链接的带宽策略配置文件的示例:
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

有关详细的参数说明, 请参阅[Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)。


### <a name="to-delete-a-network-site-link"></a>删除网络网站链接

1.  登录到安装了 Skype for Business 服务器管理外壳的计算机作为 RTCUniversalServerAdmins 组的成员或具有必要的用户权限。

2.  启动 Skype for Business 服务器命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **skype for business 服务器**", 然后单击 " **skype for business 服务器管理外壳**"。

3.  使用**CsNetworkInterSitePolicy** cmdlet 删除网络站点链接。 以下示例删除 Reno\_的 "上海" 网络网站链接:
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

有关详细的参数说明, 请参阅[Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)。


## <a name="view-network-site-information"></a>查看网络网站信息

网络站点是在呼叫许可控制 (CAC) 或增强的9-1-1 部署的每个区域内配置的办公室或位置。 您可以在 Skype for Business Server 控制面板或 Skype for business Server 命令行管理程序中查看网络站点信息。 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a>在 "Skype for Business 服务器" 控制面板中查看网络站点信息

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 

3.  在左侧导航栏中, 单击 "**网络配置**", 然后单击 "**网站**"。

4.  在 "**网站**" 页面上, 单击要查看的网站。
 
    > [!NOTE]  
    > 您一次只能查看一个网站的信息。

5.  在“编辑”**** 菜单上，单击“显示详细信息”****。


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell cmdlet 查看网络网站信息

你可以使用 Windows PowerShell 和 CsNetworkSite cmdlet 查看网络网站信息。 此 cmdlet 既可以从 Skype for Business 服务器管理外壳运行, 也可以从 Windows PowerShell 的远程会话运行。 

### <a name="to-view-network-site-information"></a>查看网络站点信息

  - 若要查看有关所有网络网站的信息, 请在 Skype for Business Server 命令行管理程序中键入以下命令, 然后按 ENTER:
    
        Get-CsNetworkSite
    
    这将返回与以下类似的信息：
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

有关详细信息, 请参阅[CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) cmdlet 的帮助主题。


## <a name="create-or-modify-network-sites"></a>创建或修改网络站点 

网络站点是在呼叫许可控制 (CAC) 或增强的9-1-1 部署的每个区域内配置的办公室或位置。 您可以使用 Skype for Business 服务器控制面板配置网站并将其与区域相关联。 例如, 北美洲的网络区域可能与诸如芝加哥、雷德蒙和范区的网络站点相关联。 必须为组织内的每个网站创建 CAC 网络网站, 即使该网站没有带宽限制也是如此。 从 Skype for Business 服务器控制面板, 您可以创建、修改和删除网络站点。 使用以下过程创建或修改网络网站。 

### <a name="to-create-a-network-site"></a>创建网络网站

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 

3.  在左侧导航栏中, 单击 "**网络配置**", 然后单击 "**网站**"。

4.  在 "**网站**" 页面上, 单击 "**新建**"。

5.  在 "**新建网站**" 中, 在 "**名称**" 字段中键入此网站的名称。

    > [!NOTE]  
    > 网站名称在 Skype for Business 服务器部署中必须是唯一的。

6.  在 "**区域**" 下拉列表中, 选择要与此网站相关联的网络区域。

7.  可选如果要对此网站的音频或视频呼叫设置带宽限制, 请从 "**带宽策略**" 下拉列表中选择具有相应设置的 "带宽策略配置文件"。
 
    > [!NOTE]  
    > 你可以在 "**网络配置**" 组的 "**策略 Profil** " 页面上查看可用带宽策略配置文件的详细信息, 或者创建新的带宽策略配置文件。 有关详细信息, 请参阅[管理网络带宽策略配置文件](managing-network-bandwidth-policy-profiles.md)。

8.  可选如果要为此网站提供位置设置, 请从 "**位置策略**" 下拉列表中选择一个位置策略。

    > [!NOTE]  
    > 位置策略将特定的增强 9-1-1 (E9-1) 和客户端位置设置分配给该网站。 你可以从 "**网络配置**" 组的 "**位置策略**" 页查看可用位置策略的详细信息, 或者创建新的位置策略。 

9.  可选在 "**说明**" 字段中键入一个值, 以提供有关此网站的详细信息, 该信息不能单独以名称表示。

10. 单击“**提交**”。

    > [!NOTE]  
    > 创建新网络网站时, 请不要使用**关联的子网**表。 创建或修改子网时, 将子网与网站相关联。 有关详细信息, 请参阅[管理网络子网](managing-network-subnets.md)。

### <a name="to-modify-a-network-site"></a>修改网络网站

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 

3.  在左侧导航栏中, 单击 "**网络配置**", 然后单击 "**网站**"。

4.  在 "**网站**" 页面上, 单击要修改的网站。

5.  在“编辑”**** 菜单上，单击“显示详细信息”****。

6.  在 "**编辑网站**" 页面上, 您可以修改与该网站相关联的说明、区域、带宽策略配置文件和位置策略。 有关详细信息, 请参阅[在上面创建网络站点](#to-create-a-network-site)。

7.  单击“**提交**”。

不能在此页面上修改**关联的子网**表。 将为参考提供关联子网的列表, 以便你在修改网站设置时知道将受到哪些子网的影响。


## <a name="delete-an-existing-network-site"></a>删除现有网络网站

网络站点是在呼叫许可控制 (CAC) 或增强的9-1-1 部署的每个区域内配置的办公室或位置。 您可以使用 Skype for Business 服务器控制面板配置网站并将其与区域相关联。 例如, 北美洲的网络区域可能与诸如芝加哥、雷德蒙和范区的网络站点相关联。 必须为组织内的每个网站创建 CAC 网络网站, 即使该网站没有带宽限制也是如此。 从 Skype for Business 服务器控制面板, 您可以创建、修改和删除网络站点。 使用以下过程删除现有网络网站。 有关创建或修改网络站点的详细信息, 请参阅[管理网站的呼叫许可控制](managing-call-admission-control-for-sites.md)。


### <a name="to-delete-a-network-site"></a>删除网络网站

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 

3.  在左侧导航栏中, 单击 "**网络配置**", 然后单击 "**网站**"。

4.  在 "**网站**" 页面上, 单击要删除的网站。

    > [!NOTE]  
    > 您可以一次删除多个网站。 若要执行此操作, 请在按住 CTRL 键的同时按 CTRL 并选择多个网站。 或者, 若要选择 "所有网站", 请单击 "**编辑**" 菜单上的 "**全选**"。

5.  在 "**编辑**" 菜单上, 单击 "**删除**"。

6.  单击“**确定**”。
    

    > [!WARNING]  
    > 如果网络站点与网络子网相关联, 则不能将其删除。 如果您尝试删除与子网相关联的网站, 您将收到一条错误消息。 若要查看某个网站是否与任何子网相关联, 请单击该网站, 然后单击 "**编辑**" 菜单上的 "**显示详细信息**"。


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
