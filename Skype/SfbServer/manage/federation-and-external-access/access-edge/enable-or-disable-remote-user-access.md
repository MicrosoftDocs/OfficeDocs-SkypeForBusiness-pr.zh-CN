---
title: 启用或禁用远程用户访问
ms.reviewer: ''
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 如果为远程用户启用远程用户访问，则受支持的远程用户通过 Internet 连接，并且不需要使用 VPN 进行连接，以便使用 Skype for Business Server 与内部用户进行协作。
ms.openlocfilehash: c20f6891b463f44fdcd424ca870fbba0826d33bd
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58608189"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a>启用或禁用远程用户访问Skype for Business Server

远程用户是组织内拥有持久 Active Directory 标识的用户。 当远程用户未连接到Skype for Business Server网络时，他们通常使用虚拟专用网络 (VPN) 从网络外部登录。 远程用户包括在家或在路上工作的员工以及其他远程工作者，如已被授予企业凭据的受信任供应商。 如果为远程用户启用远程用户访问，则受支持的远程用户通过 Internet 连接，并且不需要使用 VPN 进行连接，以便使用 Skype for Business Server 与内部用户进行协作。

要支持远程用户访问，必须启用远程用户访问。启用远程用户访问即为整个组织启用。如果稍后要暂时或永久阻止远程用户访问，可以为组织将其禁用。可以使用本节中的步骤为组织启用或禁用远程用户访问。


> [!NOTE]  
> 启用远程用户访问仅指定运行访问边缘服务的服务器支持与远程用户的通信，但远程用户不能参与组织中即时消息 (IM) 或会议，除非还配置了至少一个策略来管理远程用户访问的使用。 Skype for Business Server一个策略级别应用的策略设置可以覆盖在另一个策略级别应用的设置。 Skype for Business 服务器策略优先级是：用户策略（最大影响力）覆盖站点策略，然后站点策略覆盖全局策略（最小影响）。 这意味着，策略设置越接近策略影响的对象，它对对象的影响就越大。 有关配置使用远程用户访问的策略的详细信息，请参阅配置策略以控制远程用户访问[Skype for Business Server。](../external-access-policies/configure-policies-to-control-remote-user-access.md)


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a>为组织启用或禁用远程用户访问

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 

3.  在左侧导航栏中，单击“联盟和外部访问”，然后单击“访问边缘配置”。

4.  在“访问边缘配置”页上，单击“全局”，再单击“编辑”，然后单击“显示详细信息”。

5.  在“编辑访问边缘配置”中，执行下列操作之一：
    
      - 要为组织启用远程用户访问，请选中“启用远程用户访问”复选框。
    
      - 要为组织禁用远程用户访问，请清除“启用远程用户访问”复选框。

6.  单击“提交”。

若要允许远程用户登录到运行 Skype for Business Server 的服务器，还必须至少配置一个外部访问策略以支持远程用户访问。 有关详细信息，请参阅[Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md)。


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a>使用 cmdlet 启用或禁用Windows PowerShell用户访问

远程用户访问可通过使用 Windows PowerShell 和 Set-CsAccessEdgeConfiguration cmdlet 进行管理。 此 cmdlet 可以从 Skype for Business Server 2013 命令行管理程序运行，也可以从 Windows PowerShell 的远程会话中运行。 

## <a name="to-enable-remote-user-access"></a>启用远程用户访问

  - 要启用远程用户访问，请将 **AllowOutsideUsers** 属性的值设置为 True ($True)：
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## <a name="to-disable-remote-user-access"></a>禁用远程用户访问

  - 要禁用远程用户访问，请将 **AllowOutsideUsers** 属性的值设置为 False ($False)：
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False


