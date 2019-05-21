---
title: 管理网络子网
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 在大多数部署呼叫许可控制 (CAC) 的 Skype for business 服务器中, 通常会有大量子网。 因此, 通常最好从 Skype for Business Server 命令行管理程序配置子网。
ms.openlocfilehash: 354dd43fd526ba2a6c6f88c8e1f30d0aae37b3bb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279478"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a>在 Skype for Business Server 中管理网络子网

你可以使用 Skype for Business 服务器控制面板或 Skype for Business Server Management Shell 管理网络子网。 在大多数部署呼叫许可控制 (CAC) 的 Skype for business 服务器中, 通常会有大量子网。 因此, 通常最好从 Skype for Business Server 命令行管理程序配置子网。

使用本文中的部分可查看网络子网信息或创建、修改或删除网络子网。 

## <a name="view-network-subnet-information"></a>查看网络子网信息 

你可以使用以下过程查看网络子网。 在 "Skype for Business 服务器" 控制面板中, 可以创建、修改或删除网络子网。 

### <a name="to-view-a-network-subnet"></a>查看网络子网

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 

3.  在左侧导航栏中, 单击 "**网络配置**", 然后单击 "**子网**"。

4.  在 "**子网**" 页面上, 单击要查看的子网。
 
    > [!NOTE]  
    > 一次只能查看一个子网。

5.  在“编辑”**** 菜单上，单击“显示详细信息”****。

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell cmdlet 查看网络子网配置信息

可使用 Windows PowerShell 和 CsNetworkSubnet cmdlet 查看网络子网信息。 此 cmdlet 既可以从 Skype for Business 服务器管理外壳运行, 也可以从 Windows PowerShell 的远程会话运行。 

### <a name="to-view-network-subnet-information"></a>查看网络子网信息

  - 若要查看有关所有网络子网的信息, 请在 Skype for Business Server 命令行管理器中键入以下命令, 然后按 ENTER:
    
        Get-CsNetworkSubnet
    
    这将返回与以下类似的信息：
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


有关详细信息, 请参阅[CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) cmdlet 的帮助主题。


## <a name="create-or-modify-network-subnets"></a>创建或修改网络子网 

为了确定属于该子网的主机的地理位置, 网络子网必须与网络站点相关联。 您可以使用 Skype for Business 服务器控制面板配置子网。 在 "Skype for Business 服务器" 控制面板中, 可以创建、修改或删除网络子网。 

在大多数部署呼叫许可控制 (CAC) 的 Skype for business 服务器中, 通常会有大量子网。 因此, 通常最好从 Skype for Business Server 命令行管理程序配置子网。 从这里, 你可以将 CsNetworkSubnet 与 Windows PowerShell cmdlet **Import-CSV**结合在一起调用**新的**。 通过将这些 cmdlet 结合使用, 你可以从逗号分隔值 (.csv) 文件中读取子网设置, 并同时创建多个子网。 有关如何从 .csv 文件创建子网的示例, 请参阅[CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)。


### <a name="to-create-a-network-subnet"></a>创建网络子网

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 

3.  在左侧导航栏中, 单击 "**网络配置**", 然后单击 "**子网**"。

4.  在 "**子网**" 页面上, 单击 "**新建**"。

5.  在 "**新建子网**" 中, 在 "**子网 ID** " 字段中输入值。 这必须是 IP 地址 (例如, 174.11.12.0), 并且它必须是子网定义的 IP 地址范围中的第一个地址。

6.  在 "**掩码**" 字段中, 输入从1到32的数字值。

    > [!NOTE]  
    > 此值是要应用到正在创建的子网的位掩码。

7.  在 "**网络站点 ID**" 中, 选择此子网所属的站点。

8.  可选在 "**说明**" 字段中键入一个值, 以提供有关无法单独以名称表示的该子网的详细信息。

9.  单击“**提交**”。


### <a name="to-modify-a-network-subnet"></a>修改网络子网

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 

3.  在左侧导航栏中, 单击 "**网络配置**", 然后单击 "**子网**"。

4.  在 "**子网**" 页面上, 单击要修改的子网。

5.  在“编辑”**** 菜单上，单击“显示详细信息”****。

6.  在 "**编辑子网**" 页面上, 您可以修改位掩码、关联的网络站点或说明。 如果您修改了位掩码, 请记住子网 ID 必须仍然是子网定义的 IP 地址范围中的第一个地址。

7.  单击“**提交**”。

## <a name="delete-network-subnets"></a>删除网络子网

可以使用以下过程删除子网。 在 "Skype for Business 服务器" 控制面板中, 可以创建、修改或删除网络子网。 

在大多数部署呼叫许可控制 (CAC) 的 Skype for business 服务器中, 通常会有大量子网。 因此, 通常最好从 Skype for Business Server 命令行管理程序配置子网。 从这里, 你可以将 CsNetworkSubnet 与 Windows PowerShell cmdlet **Import-CSV**结合在一起调用**新的**。 通过将这些 cmdlet 结合使用, 你可以从逗号分隔值 (.csv) 文件中读取子网设置, 并同时创建多个子网。 有关如何从 .csv 文件创建子网的示例, 请参阅[CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)。


### <a name="to-delete-a-network-subnet"></a>删除网络子网

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 

3.  在左侧导航栏中, 单击 "**网络配置**", 然后单击 "**子网**"。

4.  在 "**子网**" 页面上, 单击要删除的子网。
 
    > [!NOTE]  
    > 您可以一次删除多个子网。 若要执行此操作, 请在按住 CTRL 键的同时按 CTRL 并选择多个子网。 或者, 若要选择所有子网, 请单击 "**编辑**" 菜单上的 "**全选**"。

5.  在 "**编辑**" 菜单上, 单击 "**删除**"。

6.  单击“**确定**”。


## <a name="see-also"></a>另请参阅

[New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  

[Set-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  

[Remove-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  

[Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
