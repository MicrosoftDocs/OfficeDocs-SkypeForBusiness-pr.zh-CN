---
title: 管理网络带宽策略配置文件
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
description: 使用本文中的过程查看、创建、修改或删除网络带宽策略配置文件。
ms.openlocfilehash: a9203c0935673e0dfd12d052876f06583c7c92c8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817501"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a>在 Skype for Business Server 中管理网络带宽策略配置文件

使用本文中的过程查看、创建、修改或删除网络带宽策略配置文件。

## <a name="view-network-bandwidth-policy-profile-information"></a>查看网络带宽策略配置文件信息

作为呼叫许可控制（CAC）的一部分，带宽策略用于定义某些形式的带宽限制。 在 Skype for Business 服务器中，只有音频和视频形式可以分配带宽限制。 你可以设置整体带宽限制和会话限制。 你可以使用 Skype for Business 服务器控制面板为这些策略创建、修改或删除容器配置文件。 每个带宽策略配置文件都可以与一个或多个网络网站相关联。 使用以下过程查看带宽策略配置文件。 

### <a name="to-view-a-bandwidth-policy-profile"></a>查看带宽策略配置文件

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 

3.  在左侧导航栏中，单击 "**网络配置**"，然后单击 "**带宽策略**"。

4.  在 "**带宽策略**" 页面上，单击要查看的带宽策略配置文件。

5.  在“编辑”**** 菜单上，单击“显示详细信息”****。


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell cmdlet 查看网络带宽策略配置文件信息

可以使用 Windows PowerShell 和 CsNetworkBandwidthPolicyProfile cmdlet 查看网络带宽配置文件。 此 cmdlet 既可以从 Skype for Business 服务器管理外壳运行，也可以从 Windows PowerShell 的远程会话运行。 


### <a name="to-view-network-bandwidth-policy-profile-information"></a>查看网络带宽策略配置文件信息

  - 若要查看所有网络带宽策略配置文件的信息，请在 Skype for Business Server 命令行管理器中键入以下命令，然后按 ENTER：
    
        Get-CsNetworkBandwidthPolicyProfile
    
    这将返回与以下类似的信息：
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :


有关详细信息，请参阅[CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) cmdlet 的帮助主题。


## <a name="create-or-modify-bandwidth-policy-profiles"></a>创建或修改带宽策略配置文件

作为呼叫许可控制（CAC）的一部分，带宽策略用于定义某些形式的带宽限制。 在 Skype for Business 服务器中，只有音频和视频形式可以分配带宽限制。 你可以设置整体带宽限制和会话限制。 你可以使用 Skype for Business 服务器控制面板为这些策略创建、修改或删除容器配置文件。 每个带宽策略配置文件都可以与一个或多个网络网站相关联。 使用以下过程创建或修改带宽策略配置文件。 

### <a name="to-create-a-new-bandwidth-policy-profile"></a>创建新的带宽策略配置文件

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 

3.  在左侧导航栏中，单击 "**网络配置**"，然后单击 "**带宽策略**"。

4.  在 "**带宽策略**" 页面上，单击 "**新建**"。

5.  在**新的带宽策略配置文件**中，在 "**名称**" 字段中键入名称。 此名称在所有带宽策略配置文件中必须是唯一的。

6.  在 "**音频限制**" 字段中，键入一个数字值。 此值表示为所有音频连接分配的最大带宽量（以 kbps 为单位）。

7.  在 "**音频会话限制**" 字段中输入一个数字值。 此值表示为单个音频连接分配的最大带宽量（以 kbps 为单位）。 此值必须为40或更高版本。

8.  在 "**视频限制**" 字段中输入一个数字值。 此值表示为所有视频连接分配的最大带宽量（以 kbps 为单位）。

9.  在 "**视频会话限制**" 字段中输入一个数字值。 此值表示为单个视频连接分配的最大带宽量（以 kbps 为单位）。 此值必须为100或更高版本。

10. 可选在 "**说明**" 字段中键入一个值，以提供有关无法单独以名称表示的此带宽策略配置文件的详细信息。

11. 单击“**提交**”。

    > [!NOTE]  
    > 创建新的带宽策略配置文件不会自动强制实施带宽限制。 必须首先将策略配置文件与网站相关联。 


### <a name="to-modify-a-bandwidth-policy-profile"></a>修改带宽策略配置文件

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 

3.  在左侧导航栏中，单击 "**网络配置**"，然后单击 "**带宽策略**"。

4.  在 "**带宽策略**" 页面上，单击要修改的带宽策略配置文件。

5.  在“编辑”**** 菜单上，单击“显示详细信息”****。

6.  在 "**编辑带宽策略配置文件**" 页面上，根据需要修改字段（有关详细信息，请参阅[创建新的带宽策略配置文件](#to-create-a-new-bandwidth-policy-profile)）。

7.  单击“**提交**”。

    > [!NOTE]  
    > 修改带宽策略配置文件时，它将立即更新与此带宽策略配置文件相关联的所有网络站点的带宽限制。

  
## <a name="delete-network-bandwidth-policy-profiles"></a>删除网络带宽策略配置文件

作为呼叫许可控制（CAC）的一部分，带宽策略用于定义某些形式的带宽限制。 在 Skype for Business 服务器中，只有音频和视频形式可以分配带宽限制。 你可以设置整体带宽限制和会话限制。 你可以使用 Skype for Business 服务器控制面板为这些策略创建、修改或删除容器配置文件。 使用以下过程删除网络带宽策略配置文件。 

### <a name="to-delete-a-bandwidth-policy-profile"></a>删除带宽策略配置文件

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 

3.  在左侧导航栏中，单击 "**网络配置**"，然后单击 "**带宽策略**"。

4.  在 "**带宽策略**" 页面上，单击要删除的带宽策略配置文件。

    > [!NOTE]  
    > 您可以一次删除多个配置文件。 若要执行此操作，请在按住 CTRL 键的同时按 CTRL 并选择多个配置文件。 或者，若要选择所有配置文件，请单击 "**编辑**" 菜单上的 "**全选**"。

5.  在 "**编辑**" 菜单上，单击 "**删除**"。
   

    > [!WARNING]  
    > 您不能删除与网络站点相关联的带宽策略配置文件。 您必须先删除与网络站点的关联，然后才能删除配置文件。 


## <a name="see-also"></a>另请参阅

[管理网站的呼叫许可控制](managing-call-admission-control-for-sites.md)
 
[New-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  

[Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  

[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[Remove-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

