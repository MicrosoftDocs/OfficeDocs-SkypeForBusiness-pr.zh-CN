---
title: 管理网络子网
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 在大多数部署中的 Skype 实现呼叫允许控制 (CAC) 的业务服务器，通常将大量的子网。 因此，通常最好为业务 Server 命令行管理程序配置从 Skype 的子网。
ms.openlocfilehash: 3b61ad1b4e1eb7f11d61b32c15e337bcd4ff77c8
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32198906"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a>在 Skype for Business Server 中管理网络子网

您可用于任一 Skype 业务 Server Control Panel 或业务 Server 命令行管理程序 Skype 管理网络子网。 在大多数部署中的 Skype 实现呼叫允许控制 (CAC) 的业务服务器，通常将大量的子网。 因此，通常最好为业务 Server 命令行管理程序配置从 Skype 的子网。

使用本文中的部分以查看网络子网信息或创建、 修改或删除网络子网。 

## <a name="view-network-subnet-information"></a>查看网络子网信息 

您可以使用以下过程以查看网络子网。 从业务 Server 控制面板的 Skype，您可以创建、 修改或删除网络子网。 

### <a name="to-view-a-network-subnet"></a>若要查看网络子网

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 

3.  在左侧的导航栏中，单击**网络配置**，然后单击**子网**。

4.  在**子网**页上，单击您想要查看的子网。
 
    > [!NOTE]  
    > 一次只能查看一个子网。

5.  在“编辑”**** 菜单上，单击“显示详细信息”****。

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a>通过使用 Windows PowerShell cmdlet 查看网络子网配置信息

可以使用 Windows PowerShell 和 Get-csnetworksubnet cmdlet 查看网络子网信息。 从业务 Server 命令行管理程序 Skype 或 Windows PowerShell 远程会话，则可以运行此 cmdlet。 

### <a name="to-view-network-subnet-information"></a>若要查看网络子网信息

  - 若要查看有关所有网络子网的信息，业务 Server 命令行管理程序 Skype 中键入以下命令，然后按 ENTER:
    
        Get-CsNetworkSubnet
    
    这将返回与以下类似的信息：
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


有关详细信息，请参阅[Get-csnetworksubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) cmdlet 的帮助主题。


## <a name="create-or-modify-network-subnets"></a>创建或修改网络子网 

为了确定属于此子网的主机的地理位置，必须与一个网络站点相关联网络子网。 您可以使用业务 Server Control Panel 的 Skype 配置子网。 从业务 Server 控制面板的 Skype，您可以创建、 修改或删除网络子网。 

在大多数部署中的 Skype 实现呼叫允许控制 (CAC) 的业务服务器，通常将大量的子网。 因此，通常最好为业务 Server 命令行管理程序配置从 Skype 的子网。 从中可以结合使用 Windows PowerShell cmdlet**导入 CSV**调用**New-csnetworksubnet** 。 通过一起使用这些 cmdlet，您可以阅读以逗号分隔值 (.csv) 文件中的子网设置，并同时创建多个子网。 有关如何从.csv 文件创建子网的示例，请参阅[New-csnetworksubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)。


### <a name="to-create-a-network-subnet"></a>创建网络子网

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 

3.  在左侧的导航栏中，单击**网络配置**，然后单击**子网**。

4.  在**子网**页上，单击**新建**。

5.  在**新的子网**，输入**子网 ID**字段中的值。 这必须是 IP 地址 (例如，174.11.12.0)，并且必须由子网 IP 地址范围内的第一个地址。

6.  在**掩码**字段中，输入一个数值 1 到 32 之间。

    > [!NOTE]  
    > 此值为要应用于正在创建的子网的位掩码。

7.  在**网络站点 ID**框中，选择该子网归属的站点。

8.  （可选）在**说明**字段，以提供有关通过名称本身不能表示此子网的详细信息，请键入一个值。

9.  单击“**提交**”。


### <a name="to-modify-a-network-subnet"></a>修改网络子网

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 

3.  在左侧的导航栏中，单击**网络配置**，然后单击**子网**。

4.  在**子网**页上，单击要修改的子网。

5.  在“编辑”**** 菜单上，单击“显示详细信息”****。

6.  在**编辑子网**页上，您可以修改的位掩码，关联的网络站点或说明。 如果您修改的位掩码，请记住，子网 ID 仍必须定义的子网 IP 地址范围内的第一个地址。

7.  单击“**提交**”。

## <a name="delete-network-subnets"></a>删除网络子网

可以使用以下过程可删除子网。 从业务 Server 控制面板的 Skype，您可以创建、 修改或删除网络子网。 

在大多数部署中的 Skype 实现呼叫允许控制 (CAC) 的业务服务器，通常将大量的子网。 因此，通常最好为业务 Server 命令行管理程序配置从 Skype 的子网。 从中可以结合使用 Windows PowerShell cmdlet**导入 CSV**调用**New-csnetworksubnet** 。 通过一起使用这些 cmdlet，您可以阅读以逗号分隔值 (.csv) 文件中的子网设置，并同时创建多个子网。 有关如何从.csv 文件创建子网的示例，请参阅[New-csnetworksubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)。


### <a name="to-delete-a-network-subnet"></a>删除网络子网

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 

3.  在左侧的导航栏中，单击**网络配置**，然后单击**子网**。

4.  在**子网**页上，单击要删除的子网。
 
    > [!NOTE]  
    > 您可以一次删除多个子网。 若要执行此操作，请按住 CTRL 并按住 CTRL 键选择多个子网。 或者，若要选择的所有子网，请**选择全部**上单击**编辑**菜单。

5.  在**编辑**菜单上，单击**删除**。

6.  单击“**确定**”。


## <a name="see-also"></a>另请参阅

[New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  

[Set-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  

[Remove-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  

[Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
