---
title: 配置策略以控制联盟用户访问
ms.reviewer: ''
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: '配置策略以支持与联盟伙伴的通信时, 这些策略适用于联盟域的用户。 '
ms.openlocfilehash: 00552dfd6e2cb92d1bd50cb851bfb8324122c5ff
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280164"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a>在 Skype for Business Server 中配置用于控制联盟用户访问的策略

配置策略以支持与联盟伙伴的通信时, 这些策略适用于联盟域的用户。 你可以配置一个或多个外部用户访问策略, 以控制联盟域的用户是否可以与你的 Skype for Business 服务器用户进行协作。 若要控制联盟用户访问, 可以在全局、网站和用户级别配置策略。 在一个策略级别应用的 Skype for business 服务器策略设置可以覆盖在其他策略级别应用的设置。 Skype for Business 服务器策略优先级为: 用户策略 (最受影响) 覆盖网站策略, 然后网站策略覆盖全局策略 (最不影响)。 这意味着，策略设置与策略所影响的对象距离越近，它对该对象的影响力越大。


> [!NOTE]  
> 你可以配置策略来控制联盟用户访问, 即使你没有为组织启用联盟也是如此。 但是, 仅当你的组织启用了联合身份验证时, 你配置的策略才有效。 有关启用联盟的详细信息, 请参阅[启用或禁用远程用户访问](../access-edge/enable-or-disable-remote-user-access.md)。  此外, 如果你指定用于控制联盟用户访问的用户策略, 该策略将仅应用于已启用 Skype for business 服务器的用户, 并且配置为使用该策略。


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a>将策略配置为支持由联盟域的用户访问

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。

3.  在左侧导航栏中, 单击 "**外部用户访问**", 然后单击 "**外部访问策略**"。

4.  在 "**外部访问策略**" 页面上, 执行下列操作之一:
    
      - 若要将全局策略配置为支持联合用户访问, 请单击全局策略, 单击 "**编辑**", 然后单击 "**显示详细信息**"。
    
      - 若要创建新的网站策略, 请单击 "**新建**", 然后单击 "**网站策略**"。 在 "**选择网站**" 中, 从列表中单击相应的网站, 然后单击 **"确定"**。
    
      - 若要创建新的用户策略, 请单击 "**新建**", 然后单击 "**用户策略**"。 在 "**新的外部访问策略**" 中, 在 "**名称**" 字段中创建一个唯一名称, 以指示用户策略所涉及的内容 (例如, **EnableFederatedUsers**为联合域用户启用通信的用户策略)。
    
      - 若要更改现有策略, 请单击表中列出的相应策略, 单击 "**编辑**", 然后单击 "**显示详细信息**"。

5.  可选如果要添加或编辑说明, 请在 "**说明**" 中指定策略的信息。

6.  请执行下列操作之一：
    
      - 若要为策略启用联盟用户访问权限, 请选中 "**启用与联盟用户的通信**" 复选框。
    
      - 若要对策略禁用联盟用户访问权限, 请清除 "**启用与联盟用户的通信**" 复选框。

7.  单击“**提交**”。

若要启用联盟用户访问, 还必须在你的组织中启用联合身份验证支持。 有关详细信息, 请参阅[启用或禁用联盟和公用 IM 连接](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)。

如果这是用户策略, 你还必须将策略应用于你希望能够与联盟用户协作的用户。 有关详细信息, 请参阅[分配外部用户访问策略](assign-an-external-user-access-policy.md)。

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>使用 Windows PowerShell 配置现有策略以支持联盟域的用户访问

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  启动 Skype for 名片 Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、"skype for business**服务器**", 然后单击 " **skype for business 服务器管理外壳**"。

3.  在 Skype for Business 服务器管理外壳程序中键入以下内容:
    
    ```
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > 在 Skype for Business 服务器控制面板中, 参数 "EnablePublicCloudAudioVideoAccess" 没有对应的选择


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>使用 Windows PowerShell 创建新策略以支持联盟域的用户访问

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  启动 Skype for Business 服务器命令行管理程序: 单击 "**开始**", 单击 "**所有程序**", 单击 " **Microsoft skype**for business 服务器", 然后单击 " **skype for business 服务器管理外壳**"。

3.  在 Skype for Business 服务器管理外壳程序中键入以下内容:
    
    ```
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    创建新网站策略的示例:
    
    ```
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>使用 Windows PowerShell 删除或重置策略以支持联盟域的用户访问

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  在 Skype for Business Server 命令行管理程序中键入以下命令
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    重置全局策略 (全局策略只能删除其设置) 的示例。 无法删除策略:
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    若要删除网站策略, 请键入:
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    删除网站策略 Redmond。 若要删除名为 UserEAPPolicy 的用户策略, 请键入:
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a>另请参阅


[启用或禁用联盟和公共 IM 连接](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[分配外部用户访问策略](assign-an-external-user-access-policy.md)

[管理组织的 SIP 联盟域](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[管理组织的 SIP 联盟提供程序](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[Set-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExternalAccessPolicy)  
[新-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsExternalAccessPolicy)  
[CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[授权-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

