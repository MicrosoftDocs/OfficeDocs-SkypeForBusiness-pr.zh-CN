---
title: 配置策略以控制联盟用户访问
ms.reviewer: ''
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
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
description: '如果将策略配置为支持与联盟伙伴进行通信，则策略将适用于联盟域用户。 '
ms.openlocfilehash: 86d3988df429b3bc9ef2972aa27e0a6ed03ceb72
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58588584"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a>配置策略以控制联盟用户访问Skype for Business Server

如果将策略配置为支持与联盟伙伴进行通信，则策略将适用于联盟域用户。 您可以配置一个或多个外部用户访问策略，以控制联盟域的用户是否可以与联盟Skype for Business Server协作。 要控制联盟用户访问，可以在全局、站点和用户级别配置策略。 Skype for Business Server一个策略级别应用的策略设置可以覆盖在另一个策略级别应用的设置。 Skype for Business 服务器策略优先级是：用户策略（最大影响力）覆盖站点策略，然后站点策略覆盖全局策略（最小影响）。 这意味着，策略设置越接近策略影响的对象，它对对象的影响就越大。


> [!NOTE]  
> 即使没有为组织启用联盟，也可以配置控制联盟用户访问的策略。 但是，只有为组织启用联盟后，配置的策略才会生效。 有关启用联盟的详细信息，请参阅 [启用或禁用远程用户访问](../access-edge/enable-or-disable-remote-user-access.md)。  此外，如果指定用户策略来控制联盟用户访问，则此策略仅适用于启用了联盟Skype for Business Server配置为使用该策略的用户。


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a>配置策略以支持联盟域用户访问

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。

3.  在左侧导航栏中，单击“外部用户访问”，然后单击“外部访问策略”。

4.  在“外部访问策略”页上，执行下列操作之一：
    
      - 要将全局策略配置为支持联盟用户访问，请单击该全局策略，再单击“编辑”，然后单击“显示详细信息”。
    
      - 要创建新的站点策略，请单击“新建”，然后单击“站点策略”。在“选择站点”中，单击列表中相应的站点，然后单击“确定”。
    
      - 要创建新的用户策略，请单击“新建”，然后单击“用户策略”。在“新建外部访问策略”的“名称”字段中，创建一个唯一的名称以指示用户策略的作用范围（例如，**EnableFederatedUsers** 代表启用联盟域用户通信的用户策略）。
    
      - 要更改现有的策略，请单击表中列出的相应策略，再单击“编辑”，然后单击“显示详细信息”。

5.  （可选）如果要添加或编辑说明，请在“说明”中为策略指定相应的信息。

6.  执行下列操作之一：
    
      - 要为策略启用联盟用户访问，请选中“启用与联盟用户的通信”复选框。
    
      - 要为策略禁用联盟用户访问，请清除“启用与联盟用户的通信”复选框。

7.  单击“提交”。

要启用联盟用户访问，还必须在组织中启用对联盟的支持。 有关详细信息，请参阅启用 [或禁用联盟和公共 IM 连接](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)。

如果这是一个用户策略，则还必须将此策略应用于希望其可以与联盟用户进行协作的用户。 有关详细信息，请参阅 [分配外部用户访问策略](assign-an-external-user-access-policy.md)。

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>使用域配置现有Windows PowerShell以支持联盟域用户访问

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。

2.  Start the Skype for Busines Server Management Shell： Click **Start**， click **All Programs，** click **Skype for Business Server**， and then click Skype for Business Server **Management Shell**.

3.  在命令行管理程序Skype for Business Server以下内容：
    
    ```PowerShell
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > 参数"EnablePublicCloudAudioVideoAccess"在"控制面板"中Skype for Business Server选择


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>使用 Windows PowerShell 创建新策略以支持联盟域用户访问

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。

2.  启动命令行Skype for Business Server：单击"开始"，单击"所有程序"，单击 **"Microsoft Skype for Business Server"，** 然后单击"Skype for Business Server **命令行管理程序"。** 

3.  在命令行管理程序Skype for Business Server以下内容：
    
    ```PowerShell
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    创建新站点策略的示例：
    
    ```PowerShell
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>使用策略删除或重置Windows PowerShell以支持联盟域用户访问

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。

2.  在命令行管理程序Skype for Business Server以下内容
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    重置全局策略的示例（只能删除全局策略的设置，而无法删除全局策略本身）：
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    若要删除站点策略，请键入：
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    删除站点策略 Redmond。 若要删除名为 UserEAPPolicy 的用户策略，请键入：
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a>另请参阅


[启用或禁用联盟和公共 IM 连接](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[分配外部用户访问策略](assign-an-external-user-access-policy.md)

[管理组织的 SIP 联盟域](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[管理组织的 SIP 联盟提供程序](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[Set-CsExternalAccessPolicy](/powershell/module/skype/Set-CsExternalAccessPolicy)  
[New-CsExternalAccessPolicy](/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-CsExternalAccessPolicy](/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[Grant-CsExternalAccessPolicy](/powershell/module/skype/Grant-CsExternalAccessPolicy)  
