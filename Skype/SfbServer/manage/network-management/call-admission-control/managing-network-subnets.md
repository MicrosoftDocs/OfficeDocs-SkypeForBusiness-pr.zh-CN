---
title: 管理网络子网
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
description: 在实现了呼叫允许控制 (CAC) Skype for Business Server 中的大多数部署中，通常会存在大量子网。 因此，最好从 Skype for Business Server 命令行管理程序 配置子网。
ms.openlocfilehash: e2ac69190ab93b4b6d81fed13538cc6fcaa91f20
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816392"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a>在 Skype for Business Server 中管理网络子网

可以使用 Skype for Business Server 控制面板或 Skype for Business Server 命令行管理程序 管理网络子网。 在实现了呼叫允许控制 (CAC) Skype for Business Server 中的大多数部署中，通常会存在大量子网。 因此，最好从 Skype for Business Server 命令行管理程序 配置子网。

使用本文中的各节查看网络子网信息，或创建、修改或删除网络子网。 

## <a name="view-network-subnet-information"></a>查看网络子网信息 

您可使用以下过程查看网络子网。 在 Skype for Business Server 控制面板中，可以创建、修改或删除网络子网。 

### <a name="to-view-a-network-subnet"></a>查看网络子网

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或已分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。 

3.  在左侧导航栏中，单击 **"网络配置**"，然后单击"子网 **"。**

4.  在“子网”页上，单击要查看的子网。
 
    > [!NOTE]  
    > 一次只能查看一个子网。

5.  在“编辑”菜单上，单击“显示详细信息”。

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a>使用 cmdlet 查看网络子网Windows PowerShell信息

网络子网信息可通过使用 Windows PowerShell 和 Get-CsNetworkSubnet cmdlet 进行查看。 此 cmdlet 可以从 Skype for Business Server 命令行管理程序运行，也可以从远程会话Windows PowerShell。 

### <a name="to-view-network-subnet-information"></a>查看网络子网信息

  - 若要查看有关所有网络子网的信息，请在 Skype for Business Server 命令行管理程序 中键入以下命令，然后按 Enter：
    
        Get-CsNetworkSubnet
    
    这将返回与以下类似的信息：
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


有关详细信息，请参阅 [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) cmdlet 的帮助主题。


## <a name="create-or-modify-network-subnets"></a>创建或修改网络子网 

网络子网必须与一个网络站点关联，以便确定属于此子网的主机的地理位置。 可以使用 Skype for Business Server 控制面板配置子网。 在 Skype for Business Server 控制面板中，可以创建、修改或删除网络子网。 

在实现了呼叫允许控制 (CAC) Skype for Business Server 中的大多数部署中，通常会存在大量子网。 因此，最好从 Skype for Business Server 命令行管理程序 配置子网。 可以从中调用 **New-CsNetworkSubnet** 与 Windows PowerShell cmdlet **Import-CSV**。 通过将这些 cmdlet 配合使用，可以从逗号分隔值 (.csv) 文件读入子网设置，并且同时创建多个子网。 有关如何从 .csv 文件创建子网的示例，请参阅 [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)。


### <a name="to-create-a-network-subnet"></a>创建网络子网

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或已分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。 

3.  在左侧导航栏中，单击 **"网络配置**"，然后单击"子网 **"。**

4.  在“子网”页上，单击“新建”。

5.  在“新建子网”的“子网 ID”字段中输入值。该值必须是一个 IP 地址（例如 174.11.12.0），并且必须是子网所定义的 IP 地址范围中的第一个地址。

6.  在“掩码”字段中，输入一个 1 到 32 之间的数值。

    > [!NOTE]  
    > 该值是要应用于正在创建的子网的位掩码。

7.  在“网络站点 ID”中，选择该子网归属的站点。

8.  （可选）在“说明”字段中键入值，用以提供仅通过名称无法表达的更多有关该子网的信息。

9.  单击“提交”。


### <a name="to-modify-a-network-subnet"></a>修改网络子网

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或已分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。 

3.  在左侧导航栏中，单击 **"网络配置**"，然后单击"子网 **"。**

4.  在“子网”页上，单击要修改的子网。

5.  在“编辑”菜单上，单击“显示详细信息”。

6.  在“编辑子网”页上，可以修改位掩码、关联的网络站点或说明。如果要修改位掩码，请牢记子网 ID 必须仍为子网所定义的 IP 地址范围中的第一个地址。

7.  单击“提交”。

## <a name="delete-network-subnets"></a>删除网络子网

您可以使用以下过程删除子网。 在 Skype for Business Server 控制面板中，可以创建、修改或删除网络子网。 

在实现了呼叫允许控制 (CAC) Skype for Business Server 中的大多数部署中，通常会存在大量子网。 因此，最好从 Skype for Business Server 命令行管理程序 配置子网。 可以从中调用 **New-CsNetworkSubnet** 与 Windows PowerShell cmdlet **Import-CSV**。 通过将这些 cmdlet 配合使用，可以从逗号分隔值 (.csv) 文件读入子网设置，并且同时创建多个子网。 有关如何从 .csv 文件创建子网的示例，请参阅 [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)。


### <a name="to-delete-a-network-subnet"></a>删除网络子网

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或已分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。 

3.  在左侧导航栏中，单击 **"网络配置**"，然后单击"子网 **"。**

4.  在“子网”页上，单击要删除的子网。
 
    > [!NOTE]  
    > 您可以一次删除多个子网。为执行此操作，请按住 CTRL 键，同时选择多个子网。或者，要选择所有子网，请单击“编辑”菜单上的“全选”。

5.  在“编辑”菜单中，单击“删除”。

6.  单击“确定”。


## <a name="see-also"></a>另请参阅

[New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  

[Set-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  

[Remove-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  

[Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
