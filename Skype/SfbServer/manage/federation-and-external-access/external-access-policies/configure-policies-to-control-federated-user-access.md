---
title: 配置策略以控制联盟用户访问
ms.reviewer: ''
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: '配置策略以支持与联盟伙伴通信时，策略应用于联盟域用户。 '
ms.openlocfilehash: df5702fb217d238a26a8a9975e7e4a0792787399
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199896"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a>配置策略以控制业务服务器中 Skype 的联盟的用户访问

配置策略以支持与联盟伙伴通信时，策略应用于联盟域用户。 您可以配置一个或多个外部用户访问策略以控制是否联盟域用户可以与您 Skype 业务 Server 用户进行协作。 若要控制联盟的用户访问，可以配置策略在全局、 站点和用户级别。 Skype 的于一个策略级别的企业服务器策略设置可以覆盖其他策略级别应用的设置。 业务服务器策略优先顺序的 Skype 是： 用户策略 （大多数影响） 将覆盖站点策略，然后网站策略将覆盖全局策略 （最低影响）。 这意味着，策略设置与策略所影响的对象距离越近，它对该对象的影响力越大。


> [!NOTE]  
> 即使您没有为组织启用联盟，您可以配置策略以控制联盟的用户访问。 但是，您配置的策略实际上是将仅当已为组织启用联盟。 有关启用联合身份验证的详细信息，请参阅[启用或禁用远程用户访问](../access-edge/enable-or-disable-remote-user-access.md)。  此外，如果您指定一个用户策略控制联盟的用户访问，该策略仅适用于 Skype 业务服务器启用和配置为使用该策略的用户。


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a>配置策略以支持联盟域用户访问

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。

3.  在左侧的导航栏中，单击**外部用户访问**，然后单击**外部访问策略**。

4.  在**外部访问策略**页上，执行以下任一操作：
    
      - 要配置全局策略以支持联盟的用户访问，请单击该全局策略，单击**编辑**，然后单击**显示详细信息**。
    
      - 若要创建新的站点策略，单击**新建**，然后单击**站点策略**。 在**选择站点**单击列表中的相应站点，然后单击**确定**。
    
      - 若要创建一个新用户策略，单击**新建**，然后单击**用户策略**。 在**新外部访问策略**中，创建一个唯一的名称，在**名称**字段，该值指示哪些用户策略介绍 (例如， **EnableFederatedUsers**用户策略启用的联盟的域用户的通信的)。
    
      - 若要更改现有策略，单击表中列出的相应策略，单击**编辑**，然后单击**显示详细信息**。

5.  （可选）如果您想要添加或编辑说明，请在**说明**指定策略的信息。

6.  请执行下列操作之一：
    
      - 若要启用联盟的用户访问的策略，请选中**启用与联盟用户的通信**复选框。
    
      - 若要禁用联盟的用户访问的策略，请清除**启用与联盟用户的通信**复选框。

7.  单击“**提交**”。

若要启用联盟的用户访问，您还必须在组织中启用联盟支持。 有关详细信息，请参阅[启用或禁用联盟和公共 IM 连接](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)。

如果这是用户策略，您必须向您希望能够与联盟用户进行协作的用户应用策略。 有关详细信息，请参阅[将外部用户访问策略分配](assign-an-external-user-access-policy.md)。

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>若要配置现有策略使用 Windows PowerShell 以支持联盟域用户访问

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  为业务 Server 命令行管理程序启动 Skype： 单击**开始**，单击**所有程序**、 都单击**Skype 业务服务器**，，然后都单击**Skype 的业务 Server Management Shell**。

3.  Skype 中键入以下内容的业务 Server 命令行管理程序：
    
    ```
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > 参数"EnablePublicCloudAudioVideoAccess"对应的所选内容中没有 Skype 的业务 Server Control Panel


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>若要创建新策略使用 Windows PowerShell 以支持联盟域用户访问

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  为业务 Server 命令行管理程序启动 Skype： 单击**开始**，单击**所有程序**，都单击**Microsoft Skype 业务服务器**，，然后都单击**Skype 的业务 Server Management Shell**。

3.  Skype 中键入以下内容的业务 Server 命令行管理程序：
    
    ```
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    创建新的站点策略的示例：
    
    ```
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>删除或重置使用 Windows PowerShell 以支持联盟域用户访问策略

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  Skype 中键入以下内容的业务 Server 命令行管理程序
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    下面举例说明重置全局策略 （全局策略只能有其设置已删除。 无法删除策略）：
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    若要删除的站点策略，请键入：
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    删除 Redmond 的站点策略。 若要删除名为 UserEAPPolicy 的用户策略，请键入：
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a>另请参阅


[启用或禁用联盟和公共 IM 连接](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[分配外部用户访问策略](assign-an-external-user-access-policy.md)

[管理组织的 SIP 联盟域](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[管理组织的 SIP 联盟提供程序](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[设置 CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExternalAccessPolicy)  
[新 CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-csexternalaccesspolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-csexternalaccesspolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[Grant-csexternalaccesspolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

