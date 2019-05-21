---
title: 管理网络区域
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 网络区域 * 是呼叫许可控制、E9-1 和媒体旁路的配置中使用的网络中心或 backbones。
ms.openlocfilehash: 8d1d60389fe910e2b5c2b8b1c357520aad30db96
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279527"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a>在 Skype for Business Server 中管理网络区域

*网络区域*是用于配置呼叫许可控制、E9-1 和媒体旁路的网络中心或 backbones。 使用以下过程查看、创建或修改网络区域。 例如, 如果已为一个语音功能创建了网络区域, 则不需要创建新的网络区域;其他高级企业语音功能将使用相同的网络区域。 但是，可能需要修改现有的网络区域定义，以应用特定于功能的设置。 例如，如果已为 E9-1-1（它不要求有关联的中央站点）创建网络区域，然后部署呼叫允许控制，则需要修改网络区域定义，以指定中央站点。 

使用本文中的过程查看网络区域信息或创建、修改或删除网络区域。 

## <a name="view-network-region-information"></a>查看网络区域信息 


网络区域跨多个地理区域互连网络的各个部分。 每个网络区域必须与一个中心网站相关联。 中心网站是运行呼叫许可控制 (CAC) 带宽策略服务的数据中心网站。 您可以使用 Skype for Business 服务器控制面板查看网络区域。 网络区域包括用于确定音频和视频连接是否允许通过 Internet 的备用路径的设置。 使用本主题查看现有的网络区域。 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a>使用 Skype for Business 服务器控制面板查看有关网络区域的信息

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 

3.  在左侧导航栏中, 单击 "**网络配置**", 然后单击 "**区域**"。

4.  在 "**区域**" 页面上, 单击要查看的区域。
  
    > [!NOTE]  
    > 一次只能查看一个区域。

5.  在“编辑”**** 菜单上，单击“显示详细信息”****。


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell cmdlet 查看网络区域信息

你可以使用 Windows PowerShell 和**CsNetworkRegion** cmdlet 查看网络区域信息。 你可以从 Skype for Business Server Management Shell 或 Windows PowerShell 的远程会话中运行此 cmdlet。 

### <a name="to-view-network-region-information"></a>查看网络区域信息

  - 若要查看有关所有网络区域的信息, 请在 Skype for Business Server 命令行管理器中键入以下命令, 然后按 ENTER:
    
        Get-CsNetworkRegion
    
    这将返回与以下类似的信息：
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

有关详细信息, 请参阅[CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet 的帮助主题。


## <a name="create-or-modify-network-regions"></a>创建或修改网络区域 

网络区域跨多个地理区域互连网络的各个部分。 每个网络区域必须与一个中心网站相关联。 中心网站是运行呼叫许可控制 (CAC) 带宽策略服务的数据中心网站。 您可以使用 Skype for Business 服务器控制面板配置网络区域。 网络区域包括用于确定音频和视频连接是否允许通过 Internet 的备用路径的设置。 在 "Skype for Business 服务器" 控制面板中, 可以创建、修改或删除网络区域。 使用本主题创建和修改网络区域。 

### <a name="to-create-a-network-region"></a>创建网络区域

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 

3.  在左侧导航栏中, 单击 "**网络配置**", 然后单击 "**区域**"。

4.  在 "**区域**" 页面上, 单击 "**新建**"。

5.  在 "**新区域**" 页面上, 在 "**名称**" 字段中键入值。 此值在 Skype for Business 服务器部署中必须是唯一的。

6.  从 "**中心站点**" 下拉列表中, 选择此网络区域的中心网站。

7.  默认情况下, "**启用音频备用路径**" 复选框处于选中状态。 此字段确定当主路径中不存在足够带宽时是否将通过备用路径路由音频呼叫。 仅当需要关闭将卸载到 Internet 时, 请清除此复选框。 如果你的任何呼叫将是 Internet 呼叫, 则必须选中此复选框, 无论带宽设置如何。

8.  默认情况下, "**启用视频备用路径**" 复选框处于选中状态。 此字段确定当主路径中不存在足够带宽时, 是否会通过备用路径路由视频呼叫。 仅当需要关闭将卸载到 Internet 时, 请清除此复选框。 如果你的任何呼叫将是 Internet 呼叫, 则必须选中此复选框, 无论带宽设置如何。

9.  可选在 "**说明**" 字段中键入一个值, 以提供有关无法单独使用名称表示的此区域的详细信息。

10. 单击“**提交**”。

**关联的网站**表不用于创建网络区域。 创建或修改网站时, 将网站与区域相关联。 有关详细信息, 请参阅[管理网站的呼叫许可控制](managing-call-admission-control-for-sites.md)。

### <a name="to-modify-a-network-region"></a>修改网络区域

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 

3.  在左侧导航栏中, 单击 "**网络配置**", 然后单击 "**区域**"。

4.  在 "**区域**" 页面上, 单击要修改的区域。

5.  在“编辑”**** 菜单上，单击“显示详细信息”****。

6.  在 "**编辑区域**" 页面上, 您可以修改启用和禁用音频和视频备用路径的设置, 并更改说明 (有关详细信息, 请参阅本主题前面的 "创建网络区域" 一节。

7.  单击“**提交**”。

您不能修改此页面上的**相关网站**。 将提供相关网站的列表以供参考, 以便你知道在修改区域设置时将受到哪些网站的影响。


## <a name="delete-existing-network-regions"></a>删除现有网络区域 

网络区域跨多个地理区域互连网络的各个部分。 每个网络区域必须与一个中心网站相关联。 中心网站是运行呼叫许可控制 (CAC) 带宽策略服务的数据中心网站。 您可以使用 Skype for Business 服务器控制面板配置网络区域。 网络区域包括用于确定音频和视频连接是否允许通过 Internet 的备用路径的设置。 在 "Skype for Business 服务器" 控制面板中, 可以创建、修改或删除网络区域。 使用本主题删除现有网络区域。 

### <a name="to-delete-a-network-region"></a>删除网络区域

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 

3.  在左侧导航栏中, 单击 "**网络配置**", 然后单击 "**区域**"。

4.  在 "**区域**" 页面上, 单击要删除的区域。
  
    > [!NOTE]  
    > 您可以一次删除多个区域。 若要执行此操作, 请在按住 CTRL 键的同时按 CTRL 并选择多个区域。 或者, 若要选择所有区域, 请单击 "**编辑**" 菜单上的 "**全选**"。

5.  在 "**编辑**" 菜单上, 单击 "**删除**"。

6.  单击“**确定**”。


    > [!WARNING]  
    > 如果网络区域与网络网站相关联, 则无法将其删除。 如果您尝试删除与网站相关联的区域, 您将收到一条错误消息。 若要查看某个区域是否与任何网站相关联, 请选择该区域, 然后单击 "**编辑**" 菜单上的 "**显示详细信息**"。


## <a name="see-also"></a>另请参阅

[管理网络区域路由](managing-network-region-routes.md)

[New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  

[Set-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  

[Remove-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  

[Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
