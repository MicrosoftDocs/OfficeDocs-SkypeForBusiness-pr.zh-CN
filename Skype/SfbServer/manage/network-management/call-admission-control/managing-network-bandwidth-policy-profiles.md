---
title: 管理网络带宽策略配置文件
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 使用本文中的过程查看、创建、修改或删除网络带宽策略配置文件。
ms.openlocfilehash: 4905a80f402b15328f4bca5476dc47262030f323cee8ec12910b25e35aee6eda
ms.sourcegitcommit: 0e9516c51105e4d89c550d2ea2bd8e7649a1163b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2021
ms.locfileid: "54590956"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a>在 Skype for Business Server 中管理网络带宽策略配置文件

使用本文中的过程查看、创建、修改或删除网络带宽策略配置文件。

## <a name="view-network-bandwidth-policy-profile-information"></a>查看网络带宽策略配置文件信息

作为呼叫允许控制 (CAC) 的一部分，使用带宽策略可定义某些形式的带宽限制。 在Skype for Business Server，只能为音频和视频形式分配带宽限制。 您可以设置总体带宽限制和会话限制。 可以使用"Skype for Business Server控制面板"创建、修改或删除这些策略的容器配置文件。 每个带宽策略配置文件都可以与一个或多个网络站点相关联。 使用下列过程可查看带宽策略配置文件。 

### <a name="to-view-a-bandwidth-policy-profile"></a>查看带宽策略配置文件

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 

3.  在左侧导航栏中，单击“网络配置”，然后单击“带宽策略”。

4.  在 **"带宽策略"** 页上，单击要查看的带宽策略配置文件。

5.  在“编辑”菜单上，单击“显示详细信息”。


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a>使用 cmdlet 查看网络带宽策略Windows PowerShell信息

通过使用 cmdlet 和 Windows PowerShell 可以查看Get-CsNetworkBandwidthPolicyProfile配置文件。 此 cmdlet 可以从命令行管理程序Skype for Business Server远程会话运行Windows PowerShell。 


### <a name="to-view-network-bandwidth-policy-profile-information"></a>查看网络带宽策略配置文件信息

  - 若要查看有关所有网络带宽策略配置文件的信息，请在命令行管理程序中键入Skype for Business Server命令，然后按 Enter：
    
    **Get-CsNetworkBandwidthPolicyProfile**
    
    这将返回与以下类似的信息：
    
    标识 ：RedmondBandwidthPolicy<br/>
    BWPolicy ： {BWLimit=200;BWSessionLimit=200;<br/>
                        BWPolicyModality=Audio， <br/>
                        BWLimit=1400;BWSessionLimit=500;<br/>
                        BWPolicyModality=Video}<br/>
    BWPolicyProfileID ：RedmondBandwidthPolicy<br/>
    说明：

有关详细信息，请参阅[Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) cmdlet 的帮助主题。


## <a name="create-or-modify-bandwidth-policy-profiles"></a>创建或修改带宽策略配置文件

作为呼叫允许控制 (CAC) 的一部分，使用带宽策略可定义某些形式的带宽限制。 在Skype for Business Server，只能为音频和视频形式分配带宽限制。 您可以设置总体带宽限制和会话限制。 可以使用"Skype for Business Server控制面板"创建、修改或删除这些策略的容器配置文件。 每个带宽策略配置文件都可以与一个或多个网络站点相关联。 可使用以下过程创建或修改带宽策略配置文件。 

### <a name="to-create-a-new-bandwidth-policy-profile"></a>创建新的带宽策略配置文件

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 

3.  在左侧导航栏中，单击"**网络配置"，** 然后单击"带宽 **策略"。**

4.  在“带宽策略”页上，单击“新建”。

5.  在“新建带宽策略配置文件”的“名称”字段中键入名称。此名称必须在所有带宽策略配置文件中是唯一的。

6.  在“音频限制”字段中，键入一个数值。此值是要为所有音频连接分配的最大带宽量，以 kbps 为单位表示。

7.  在“音频会话限制”字段中输入一个数值。此值是要为单个音频连接分配的最大带宽量，以 kbps 为单位表示。此值必须为 40 或更大。

8.  在“视频限制”字段中输入一个数值。此值是要为所有视频连接分配的最大带宽量，以 kbps 为单位表示。

9.  在“视频会话限制”字段中输入一个数值。此值是要为单个视频连接分配的最大带宽量，以 kbps 为单位表示。此值必须为 100 或更大。

10. （可选）在“说明”字段中键入值，用以提供仅通过名称无法表达的更多有关该带宽策略配置文件的信息。

11. 单击“提交”。

    > [!NOTE]  
    > 创建新的带宽策略配置文件不会自动强制实施带宽限制。 必须先将策略配置文件与站点相关联。 


### <a name="to-modify-a-bandwidth-policy-profile"></a>修改带宽策略配置文件

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 

3.  在左侧导航栏中，单击"**网络配置"，** 然后单击"带宽 **策略"。**

4.  在“带宽策略”页上，单击要修改的带宽策略配置文件。

5.  在“编辑”菜单上，单击“显示详细信息”。

6.  在" **编辑带宽策略配置文件** "页上，根据需要 (字段，有关详细信息，请参阅创建新的带宽策略 [配置文件](#to-create-a-new-bandwidth-policy-profile)) 。

7.  单击“提交”。

    > [!NOTE]  
    > 修改带宽策略配置文件时，会立即更新与此带宽策略配置文件关联的所有网络站点的带宽限制。

  
## <a name="delete-network-bandwidth-policy-profiles"></a>删除网络带宽策略配置文件

作为呼叫允许控制 (CAC) 的一部分，使用带宽策略可定义某些形式的带宽限制。 在Skype for Business Server，只能为音频和视频形式分配带宽限制。 您可以设置总体带宽限制和会话限制。 可以使用"Skype for Business Server控制面板"创建、修改或删除这些策略的容器配置文件。 请使用下列过程删除网络带宽策略配置文件。 

### <a name="to-delete-a-bandwidth-policy-profile"></a>删除带宽策略配置文件

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 

3.  在左侧导航栏中，单击"**网络配置"，** 然后单击"带宽 **策略"。**

4.  在“带宽策略”页上，单击要删除的带宽策略配置文件。

    > [!NOTE]  
    > 可一次性删除多个配置文件。要执行此操作，请按住 Ctrl 键，同时选择多个配置文件。或者，要选择全部配置文件，请单击“编辑”菜单中的“全选”。

5.  在“编辑”菜单上，单击“删除”。
   

    > [!WARNING]  
    > 不能删除与网络站点关联的带宽策略配置文件。 只有先删除配置文件与网络站点之间的关联，然后才能将配置文件删除。 


## <a name="see-also"></a>另请参阅

[管理网站的呼叫允许控制](managing-call-admission-control-for-sites.md)
 
[New-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  

[Set-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  

[Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[Remove-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
