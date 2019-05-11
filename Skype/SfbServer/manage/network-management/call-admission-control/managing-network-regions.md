---
title: 管理网络区域
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 网络区域 * 是网络中心或网络中枢的呼叫允许控制、 E9-1-1 和媒体绕过配置中使用。
ms.openlocfilehash: c7559c8fa09d0f0d7fac4fa5067d2df91c52defe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33913368"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a>在 Skype for Business Server 中管理网络区域

*网络区域*的网络中心或网络中枢的呼叫允许控制、 E9-1-1 和媒体绕过配置中使用。 使用以下过程以查看、 创建或修改网络区域。 例如，如果您已经创建一个语音功能的网络区域，您不需要创建新的网络区域;其他高级的企业语音功能将使用这些相同的网络区域。 但是，可能需要修改现有的网络区域定义，以应用特定于功能的设置。 例如，如果已为 E9-1-1（它不要求有关联的中央站点）创建网络区域，然后部署呼叫允许控制，则需要修改网络区域定义，以指定中央站点。 

使用本文中的过程以查看网络区域信息或创建、 修改或删除网络区域。 

## <a name="view-network-region-information"></a>查看网络区域信息 


网络区域互连跨多个地理区域的网络的各个部分。 每个网络区域必须与中央站点相关联。 中央站点是在其运行呼叫允许控制 (CAC) 带宽策略服务数据中心站点。 您可以使用业务 Server Control Panel 的 Skype 查看网络区域。 网络区域包括确定是否允许通过 Internet 的备用路径对音频和视频连接的设置。 使用本主题可查看现有的网络区域。 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a>若要查看有关 Business Server Control Panel 与 Skype 的网络区域信息

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 

3.  在左侧的导航栏中，单击**网络配置**，然后单击**区域**。

4.  在**区域**页上，单击您想要查看的区域。
  
    > [!NOTE]  
    > 一次只能查看一个区域。

5.  在“编辑”**** 菜单上，单击“显示详细信息”****。


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a>通过使用 Windows PowerShell cmdlet 查看网络区域信息

您可以使用 Windows PowerShell 和**Get-csnetworkregion** cmdlet 查看网络区域信息。 可以从 Skype 业务 Server 命令行管理程序或从 Windows PowerShell 远程会话来运行此 cmdlet。 

### <a name="to-view-network-region-information"></a>若要查看网络区域信息

  - 若要查看有关所有网络区域的信息，业务 Server Management Shell，Skype 中键入以下命令，然后按 ENTER:
    
        Get-CsNetworkRegion
    
    这将返回与以下类似的信息：
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

有关详细信息，请参阅[Get-csnetworkregion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet 的帮助主题。


## <a name="create-or-modify-network-regions"></a>创建或修改网络区域 

网络区域互连跨多个地理区域的网络的各个部分。 每个网络区域必须与中央站点相关联。 中央站点是在其运行呼叫允许控制 (CAC) 带宽策略服务数据中心站点。 您可以使用业务 Server Control Panel 的 Skype 配置网络区域。 网络区域包括确定是否允许通过 Internet 的备用路径对音频和视频连接的设置。 从业务 Server 控制面板的 Skype，您可以创建、 修改或删除网络区域。 本主题可用于创建和修改网络区域。 

### <a name="to-create-a-network-region"></a>创建网络区域

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 

3.  在左侧的导航栏中，单击**网络配置**，然后单击**区域**。

4.  在**区域**页上，单击**新建**。

5.  在**新建区域**页中，键入**名称**字段中的值。 此值必须是唯一您 Skype 业务服务器部署中。

6.  从**中央站点**下拉列表中选择此网络区域的中央站点。

7.  默认情况下选中**启用音频的备用路径**复选框。 此字段确定是否主路径中没有足够带宽，是否将通过备用路径中路由音频呼叫。 仅当您需要关闭卸载到 Internet，请清除此复选框。 如果任何呼叫是 Internet 呼叫，此复选框必须选中，无论带宽设置。

8.  默认情况下选中**启用视频的备用路径**复选框。 此字段确定是否主路径中没有足够带宽，是否将通过备用路径中路由视频呼叫。 仅当您需要关闭卸载到 Internet，请清除此复选框。 如果任何呼叫是 Internet 呼叫，此复选框必须选中，无论带宽设置。

9.  （可选）在**说明**字段，以提供有关通过名称本身不能表示该区域的详细信息，请键入一个值。

10. 单击“**提交**”。

**关联网站**表不用于创建网络区域。 创建或修改站点时，可以与区域关联网站。 有关详细信息，请参阅[Managing 呼叫允许控制的网站](managing-call-admission-control-for-sites.md)。

### <a name="to-modify-a-network-region"></a>修改网络区域

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 

3.  在左侧的导航栏中，单击**网络配置**，然后单击**区域**。

4.  在**区域**页上，单击您想要修改的区域。

5.  在“编辑”**** 菜单上，单击“显示详细信息”****。

6.  在**编辑区域**页中中，您可以修改设置启用和禁用音频和视频备用路径，并更改说明 （有关详细信息，请参阅"创建网络区域"一节本主题中前面。

7.  单击“**提交**”。

不能修改此页上的**关联网站**。 使您了解当您修改的区域设置时，将影响的网站，供参考提供关联的网站的列表。


## <a name="delete-existing-network-regions"></a>删除现有网络区域 

网络区域互连跨多个地理区域的网络的各个部分。 每个网络区域必须与中央站点相关联。 中央站点是在其运行呼叫允许控制 (CAC) 带宽策略服务数据中心站点。 您可以使用业务 Server Control Panel 的 Skype 配置网络区域。 网络区域包括确定是否允许通过 Internet 的备用路径对音频和视频连接的设置。 从业务 Server 控制面板的 Skype，您可以创建、 修改或删除网络区域。 使用本主题可删除现有网络区域。 

### <a name="to-delete-a-network-region"></a>删除网络区域

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 

3.  在左侧的导航栏中，单击**网络配置**，然后单击**区域**。

4.  在**区域**页上，单击您想要删除的区域。
  
    > [!NOTE]  
    > 您可以一次删除多个区域。 若要执行此操作，请按住 CTRL 并按住 CTRL 键选择多个区域。 或者，若要选择所有区域，**都选择全部**上单击**编辑**菜单。

5.  在**编辑**菜单上，单击**删除**。

6.  单击“**确定**”。


    > [!WARNING]  
    > 无法删除网络区域，如果它是与网络站点关联。 如果尝试删除与网站关联的区域，您将收到一条错误消息。 若要查看是否区域相关联的任何网站，选择的区域，然后单击**编辑**菜单上的**显示详细信息**。


## <a name="see-also"></a>另请参阅

[管理网络区域路由](managing-network-region-routes.md)

[New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  

[Set-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  

[Remove-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  

[Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
