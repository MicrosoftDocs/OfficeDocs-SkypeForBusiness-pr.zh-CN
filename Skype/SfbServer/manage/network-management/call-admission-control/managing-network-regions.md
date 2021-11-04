---
title: 管理网络区域
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 网络区域* 是呼叫允许控制、E9-1-1 和媒体旁路配置中使用的网络中心或网络中枢。
ms.openlocfilehash: 5bfe3051404b41cd6a1d96bfac240e83070bbdbc
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759734"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a>在 Skype for Business Server 中管理网络区域

*网络区域* 是在呼叫允许控制、E9-1-1 和媒体旁路的配置中使用的网络中心或网络中枢。 使用以下过程可查看、创建或修改网络区域。 例如，如果已为一个语音功能创建网络区域，则不需要创建新的网络区域；其他高级企业语音功能也将使用相同的网络区域。 但是，可能需要修改现有的网络区域定义，以应用特定于功能的设置。 例如，如果已为 E9-1-1（它不要求有关联的中央站点）创建网络区域，然后部署呼叫允许控制，则需要修改网络区域定义，以指定中央站点。 

使用本文中的过程可查看网络区域信息或创建、修改或删除网络区域。 

## <a name="view-network-region-information"></a>查看网络区域信息 


网络区域将跨多个地理区域的网络的各个部分相互连接起来。 每个网络区域都必须与中央站点关联。 中央站点是运行呼叫允许控制 (CAC) 带宽策略服务的数据中心站点。 可以使用"Skype for Business Server"来查看网络区域。 网络区域包括确定音频和视频连接是否可以使用通过 Internet 的备用路径的设置。 使用本主题可查看现有网络区域。 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a>使用控制面板查看有关Skype for Business Server区域的信息

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 

3.  在左侧导航栏中，单击"**网络配置"，** 然后单击"区域 **"。**

4.  在“区域”页上，单击要查看的区域。
  
    > [!NOTE]  
    > 您一次只能查看一个区域。

5.  在“编辑”菜单上，单击“显示详细信息”。


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a>使用 cmdlet 查看Windows PowerShell信息

可以使用 **Get-CsNetworkRegion** cmdlet 和 Windows PowerShell查看网络区域信息。 可以从命令行管理程序或 Skype for Business Server远程会话中运行此 cmdlet Windows PowerShell。 

### <a name="to-view-network-region-information"></a>查看网络区域信息

  - 若要查看有关所有网络区域的信息，请在命令行管理程序中键入Skype for Business Server命令，然后按 Enter：
    
    **Get-CsNetworkRegion**
    
    这将返回与以下类似的信息：
    
    标识：太平洋-太平洋<br/>
    说明：<br/>
    BypassID ：3b232b84-2c1d-4da2-8181-e9330bafebe9<br/>
    CentralSite ： Site：Redmond1<br/>
    BWAlternatePaths ：{BWPolicyModality=Audio;AlternatePath=True， <br/>
                       BWPolicyModality=Video;AlternatePath=True}<br/>
    NetworkRegionID ： Pacific Northwest<br/>

有关详细信息，请参阅 [Get-CsNetworkRegion](/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet 的帮助主题。


## <a name="create-or-modify-network-regions"></a>创建或修改网络区域 

网络区域将跨多个地理区域的网络的各个部分相互连接起来。 每个网络区域都必须与中央站点关联。 中央站点是运行呼叫允许控制 (CAC) 带宽策略服务的数据中心站点。 可以使用"Skype for Business Server控制面板"配置网络区域。 网络区域包括确定音频和视频连接是否可以使用通过 Internet 的备用路径的设置。 从Skype for Business Server控制面板中，可以创建、修改或删除网络区域。 使用本主题创建和修改网络区域。 

### <a name="to-create-a-network-region"></a>创建网络区域

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 

3.  在左侧导航栏中，单击"**网络配置"，** 然后单击"区域 **"。**

4.  在"区域 **"页上**，单击"新建 **"。**

5.  在" **新建区域"** 页的"名称"字段中 **键入** 值。 此值在部署中必须Skype for Business Server。

6.  从 **中央站点** 下拉列表中，选择此网络区域的中央站点。

7.  默认情况下 **选中"** 启用音频备用路径"复选框。 如果主路径中不存在足够的带宽，此字段确定是否将通过备用路径路由音频呼叫。 仅在需要关闭卸载到 Internet 时清除此复选框。 如果任何呼叫将是 Internet 呼叫，则必须选中此复选框，而不考虑带宽设置。

8.  默认情况下 **选中"** 启用视频备用路径"复选框。 如果主路径中不存在足够的带宽，此字段确定是否将通过备用路径路由视频呼叫。 仅在需要关闭卸载到 Internet 时清除此复选框。 如果任何呼叫将是 Internet 呼叫，则必须选中此复选框，而不考虑带宽设置。

9.   (可选) 在"说明"字段中键入一个值，以提供无法单独用名称表示的此区域详细信息。

10. 单击“提交”。

" **关联的站点** "表不用于创建网络区域。 创建或修改网站时，可以将网站与区域关联。 有关详细信息，请参阅 [管理网站的呼叫允许控制](managing-call-admission-control-for-sites.md)。

### <a name="to-modify-a-network-region"></a>修改网络区域

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 

3.  在左侧导航栏中，单击"**网络配置"，** 然后单击"区域 **"。**

4.  在 **"区域** "页上，单击要修改的区域。

5.  在“编辑”菜单上，单击“显示详细信息”。

6.  在"编辑区域"页上，您可以修改用于启用和禁用音频和视频备用路径的设置，并更改说明 (了解详细信息，请参阅本主题前面介绍的"创建网络区域"部分。

7.  单击“提交”。

无法修改 **此页上的** 关联网站。 提供关联网站列表供参考，以便了解修改区域设置时将影响哪些网站。


## <a name="delete-existing-network-regions"></a>删除现有网络区域 

网络区域将跨多个地理区域的网络的各个部分相互连接起来。 每个网络区域都必须与中央站点关联。 中央站点是运行呼叫允许控制 (CAC) 带宽策略服务的数据中心站点。 可以使用"Skype for Business Server控制面板"配置网络区域。 网络区域包括确定音频和视频连接是否可以使用通过 Internet 的备用路径的设置。 从Skype for Business Server控制面板中，可以创建、修改或删除网络区域。 使用此主题可删除现有网络区域。 

### <a name="to-delete-a-network-region"></a>删除网络区域

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 

3.  在左侧导航栏中，单击"**网络配置"，** 然后单击"区域 **"。**

4.  在“区域”页上，单击要删除的区域。
  
    > [!NOTE]  
    > 可一次性删除多个区域。要执行此操作，请按住 Ctrl 键，同时选择多个区域。或者，要选择全部区域，请单击“编辑”菜单中的“全选”。

5.  在“编辑”菜单上，单击“删除”。

6.  单击“确定”。


    > [!WARNING]  
    > 如果网络区域与某个网络站点关联，则不能删除该网络区域。 如果您尝试删除与网站关联的区域，您将收到一条错误消息。 要查看区域是否与任何站点关联，请选择相应的区域，然后单击“编辑”菜单中的“显示详细信息”。


## <a name="see-also"></a>另请参阅

[管理网络区域路由](managing-network-region-routes.md)

[New-CsNetworkRegion](/powershell/module/skype/New-CsNetworkRegion)  

[Set-CsNetworkRegion](/powershell/module/skype/Set-CsNetworkRegion)  

[Remove-CsNetworkRegion](/powershell/module/skype/Remove-CsNetworkRegion)  

[Get-CsNetworkRegion](/powershell/module/skype/Get-CsNetworkRegionLink)