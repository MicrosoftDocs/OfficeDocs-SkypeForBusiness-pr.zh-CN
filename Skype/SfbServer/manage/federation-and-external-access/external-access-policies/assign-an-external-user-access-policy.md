---
title: 分配外部用户访问策略
ms.reviewer: ''
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 如果用户已启用的 Skype 业务服务器，您可以配置 SIP 联盟、 远程用户访问和公共即时消息的业务 Server Control Panel 的 Skype 中的 (IM) 连接，通过向特定用户应用适当的策略。
ms.openlocfilehash: f07a407fee6f32f4cd4207c93ca19341e409ea78
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881498"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a>将外部用户访问策略分配给 Skype 业务启用用户

如果用户已启用的 Skype 业务服务器，您可以配置 SIP 联盟、 远程用户访问和公共即时消息的业务 Server Control Panel 的 Skype 中的 (IM) 连接，通过向特定用户应用适当的策略。 例如，如果您创建策略，以支持远程用户访问，必须应用于用户之前，用户可以从远程位置的业务服务器连接到 Skype 并与从远程位置的内部用户协作。


> [!NOTE]  
> 若要支持外部用户访问，必须启用支持的每种类型的外部用户访问您想要支持，并配置适当的策略和其他选项，以控制其使用。 有关详细信息，请参阅[Managing 联盟和外部访问 Skype 业务服务器](../managing-federation-and-external-access.md)。


使用本主题中的过程将以前创建的外部用户访问策略应用于一个或多个用户帐户。


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>外部用户策略应用于用户帐户

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 

3.  在左侧导航栏中，单击“**用户**”，然后搜索要配置的用户帐户。

4.  在列出搜索结果的表中，单击相应的用户帐户，再单击“**编辑**”，然后单击“**显示详细信息**”。

5.  在**外部访问策略**下**的企业服务器用户编辑 Skype** ，选择要应用的用户策略。
     
> [!NOTE]  
> ** \<Automatic>** 设置应用默认服务器或全局策略设置。


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 分配每用户外部访问策略

可以通过使用 Windows PowerShell 和 Grant-csexternalaccesspolicy cmdlet 分配每用户外部访问策略。 从业务 Server 命令行管理程序 Skype 或 Windows PowerShell 远程会话，则可以运行此 cmdlet。 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>向单个用户分配每用户外部访问策略

  - 此命令向用户 Ken Myer 分配每用户外部访问策略 RedmondExternalAccessPolicy。
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>向多个用户分配每用户外部访问策略

  - 此命令将每用户外部访问策略 USAExternalAccessPolicy 分配给 Active Directory 中的美国 OU 中拥有帐户的所有用户。 此命令使用 OU 参数的详细信息，请参阅[Get-csuser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) cmdlet 的文档。
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a>若要取消分配每用户外部访问策略

  - 此命令 unassigns 以前分配给 Ken myer 的用户的任何每用户外部访问策略。 取消分配每用户策略后，将自动使用全局策略或本地站点策略（如果存在）管理 Ken Myer。 站点策略优先于全局策略。
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null



有关详细信息，请参阅[Grant-csexternalaccesspolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy) cmdlet 的帮助主题。


