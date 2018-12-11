---
title: 启用或禁用远程用户访问
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 如果您启用远程用户的远程用户访问，支持远程用户通过 Internet 连接，且不具有才能与内部用户使用 Skype 业务服务器的协作使用 VPN 进行连接。
ms.openlocfilehash: 34733c4d1912461090ef868e24ae24dc1c870a94
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222875"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a>启用或禁用远程用户访问在 Skype 业务服务器

远程用户是贵组织拥有持久的 Active Directory 标识组织内的用户。 远程用户通常登录到 Skype 业务服务器从外部网络在不连接到组织的网络时通过虚拟专用网络 (VPN)。 远程用户包含员工在家工作或在旅途中以及其他远程工作者，例如受信任供应商，人员已被授予企业凭据。 如果您启用远程用户的远程用户访问，支持远程用户通过 Internet 连接，且不具有才能与内部用户使用 Skype 业务服务器的协作使用 VPN 进行连接。

若要支持远程用户访问，必须启用远程用户访问。 当您启用远程用户访问时，您可以为整个组织启用它。 如果您以后想要临时或永久阻止远程用户访问，您可以为组织禁用它。 使用本节中的过程以启用或禁用组织的远程用户访问。


> [!NOTE]  
> 仅启用远程用户访问指定运行访问边缘服务的服务器支持与远程用户的通信，但远程用户无法参与即时消息 (IM) 或您的组织中的会议配置在之前若要管理的远程用户访问使用的至少一个策略。 Skype 的于一个策略级别的企业服务器策略设置可以覆盖其他策略级别应用的设置。 业务服务器策略优先顺序的 Skype 是： 用户策略 （大多数影响） 将覆盖站点策略，然后网站策略将覆盖全局策略 （最低影响）。 这意味着，策略设置与策略所影响的对象距离越近，它对该对象的影响力越大。 有关配置为使用远程用户访问的策略的详细信息，请参阅[配置策略以控制 Skype 业务服务器中的远程用户访问](../external-access-policies/configure-policies-to-control-remote-user-access.md)。


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a>启用或禁用组织的远程用户访问

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 

3.  在左侧导航栏中，单击“**联盟和外部访问**”，然后单击“**访问边缘配置**”。

4.  在**访问边缘配置**页上，单击**全局**，单击**编辑**，然后单击**显示详细信息**。

5.  在**编辑访问边缘配置**中，执行下列选项之一：
    
      - 要为组织的远程用户访问，请选中**启用远程用户访问**复选框。
    
      - 若要禁用组织的远程用户访问，请清除**启用远程用户访问**复选框。

6.  单击“**提交**”。

若要启用远程用户登录到运行 Skype 业务服务器的服务器，还必须配置至少一个外部访问策略以支持远程用户访问。 有关详细信息，请参阅[配置策略以控制 Skype 业务服务器中的远程用户访问](../external-access-policies/configure-policies-to-control-remote-user-access.md)。


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a>启用或禁用远程用户访问使用 Windows PowerShell cmdlet

可以使用 Windows PowerShell 和 Set-csaccessedgeconfiguration cmdlet 来管理远程用户访问。 从业务 Server 2013 命令行管理程序 Skype 或 Windows PowerShell 远程会话，则可以运行此 cmdlet。 

## <a name="to-enable-remote-user-access"></a>若要启用远程用户访问

  - 要启用远程用户访问，请将**AllowOutsideUsers**属性的值设置为 True ($True) 中：
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## <a name="to-disable-remote-user-access"></a>若要禁用远程用户访问

  - 要禁用远程用户访问，请将**AllowOutsideUsers**属性的值设置为 False ($False) 中：
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False


