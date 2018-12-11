---
title: 管理网络带宽策略配置文件
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 使用本文中的过程以查看、 创建、 修改或删除网络带宽策略配置文件。
ms.openlocfilehash: 58a73774a55a64ac6cb81f0bdf887eb0d1493a35
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222938"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a>管理 Business Server Skype 中的网络带宽策略配置文件

使用本文中的过程以查看、 创建、 修改或删除网络带宽策略配置文件。

## <a name="view-network-bandwidth-policy-profile-information"></a>查看网络带宽策略配置文件信息

作为呼叫允许控制 (CAC) 的一部分，带宽策略用于定义特定形式的带宽限制。 在业务服务器 Skype，可以将仅音频和视频形式分配带宽限制。 您可以设置总体带宽限制和会话限制。 为业务 Server Control Panel Skype 可用于创建、 修改或删除这些策略容器配置文件。 每个带宽策略配置文件可以与一个或多个网络站点相关联。 使用以下过程可以查看带宽策略配置文件。 

### <a name="to-view-a-bandwidth-policy-profile"></a>若要查看带宽策略配置文件

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 

3.  在左侧的导航栏中，单击**网络配置**，然后单击**带宽策略**。

4.  在**带宽策略**页上，单击您想要查看的带宽策略配置文件。

5.  在“编辑”**** 菜单上，单击“显示详细信息”****。


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a>通过使用 Windows PowerShell cmdlet 查看网络带宽策略配置文件信息

可以通过使用 Windows PowerShell 和 Get-csnetworkbandwidthpolicyprofile cmdlet 查看网络带宽配置文件。 从业务 Server 命令行管理程序 Skype 或 Windows PowerShell 远程会话，则可以运行此 cmdlet。 


### <a name="to-view-network-bandwidth-policy-profile-information"></a>若要查看网络带宽策略配置文件信息

  - 若要查看有关所有网络带宽策略配置文件的信息，业务 Server Management Shell，Skype 中键入以下命令，然后按 ENTER:
    
        Get-CsNetworkBandwidthPolicyProfile
    
    这将返回与以下类似的信息：
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :


有关详细信息，请参阅[Get-csnetworkbandwidthpolicyprofile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) cmdlet 的帮助主题。


## <a name="create-or-modify-bandwidth-policy-profiles"></a>创建或修改带宽策略配置文件

作为呼叫允许控制 (CAC) 的一部分，带宽策略用于定义特定形式的带宽限制。 在业务服务器 Skype，可以将仅音频和视频形式分配带宽限制。 您可以设置总体带宽限制和会话限制。 为业务 Server Control Panel Skype 可用于创建、 修改或删除这些策略容器配置文件。 每个带宽策略配置文件可以与一个或多个网络站点相关联。 使用以下过程可创建或修改带宽策略配置文件。 

### <a name="to-create-a-new-bandwidth-policy-profile"></a>创建新的带宽策略配置文件

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 

3.  在左侧的导航栏中，单击**网络配置**，然后单击**带宽策略**。

4.  在**带宽策略**页上，单击**新建**。

5.  在**新的带宽策略配置文件**中，键入**名称**字段中的名称。 此名称必须是唯一的所有带宽策略配置文件。

6.  在**音频限制**字段中，键入一个数字值。 此值为的最大带宽为所有音频连接，表示单位： kbps 分配量。

7.  在**音频会话限制**字段中输入一个数值。 此值为的最大带宽为个别音频连接，表示单位： kbps 分配量。 该值必须是 40 或更高版本。

8.  在**视频限制**字段中输入一个数值。 此值为的最大带宽为所有视频连接，表示单位： kbps 分配量。

9.  在**视频会话限制**字段中输入一个数值。 此值为的最大带宽为个别视频连接，表示单位： kbps 分配量。 该值必须是 100 个或更高版本。

10. （可选）在**说明**字段，以提供有关通过名称本身不能表示该带宽策略配置文件的详细信息，请键入一个值。

11. 单击“**提交**”。

    > [!NOTE]  
    > 创建新的带宽策略配置文件不自动强制带宽限制。 首先必须与网站关联的策略配置文件。 


### <a name="to-modify-a-bandwidth-policy-profile"></a>修改带宽策略配置文件

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 

3.  在左侧的导航栏中，单击**网络配置**，然后单击**带宽策略**。

4.  在**带宽策略**页上，单击您想要修改的带宽策略配置文件。

5.  在“编辑”**** 菜单上，单击“显示详细信息”****。

6.  在**编辑带宽策略配置文件**页上，根据需要修改字段 （有关详细信息，请参阅[创建新的带宽策略配置文件](#to-create-a-new-bandwidth-policy-profile)）。

7.  单击“**提交**”。

    > [!NOTE]  
    > 修改带宽策略配置文件时，会立即更新与此带宽策略配置文件关联的所有网络站点的带宽限制。

  
## <a name="delete-network-bandwidth-policy-profiles"></a>删除网络带宽策略配置文件

作为呼叫允许控制 (CAC) 的一部分，带宽策略用于定义特定形式的带宽限制。 在业务服务器 Skype，可以将仅音频和视频形式分配带宽限制。 您可以设置总体带宽限制和会话限制。 为业务 Server Control Panel Skype 可用于创建、 修改或删除这些策略容器配置文件。 使用以下过程可删除网络带宽策略配置文件。 

### <a name="to-delete-a-bandwidth-policy-profile"></a>删除带宽策略配置文件

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 

3.  在左侧的导航栏中，单击**网络配置**，然后单击**带宽策略**。

4.  在**带宽策略**页上，单击要删除的带宽策略配置文件。

    > [!NOTE]  
    > 您可以一次删除多个配置文件。 若要执行此操作，请按住 CTRL 并按住 CTRL 键选择多个配置文件。 或者，若要选择所有配置文件，**选择全部**上单击**编辑**菜单。

5.  在**编辑**菜单上，单击**删除**。
   

    > [!WARNING]  
    > 不能删除与网络站点相关联的带宽策略配置文件。 您可以删除配置文件之前，必须先删除与网络站点关联。 


## <a name="see-also"></a>另请参阅

[管理网站的呼叫允许控制](managing-call-admission-control-for-sites.md)
 
[New-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  

[Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  

[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[Remove-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

