---
title: 分配外部用户访问策略
ms.reviewer: ''
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 如果用户已启用 Skype for Business Server，则可以通过将相应的策略应用于特定用户，在 Skype for Business Server 控制面板中配置 SIP 联盟、远程用户访问和公共即时消息 (IM) 连接。
ms.openlocfilehash: dbb4c89fd67f128fff0707e1190e8720ad2a166b72b861bb4510496ac0cd5744
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54320194"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a>将外部用户访问策略分配给Skype for Business用户

如果用户已启用 Skype for Business Server，则可以通过将相应的策略应用于特定用户，在 Skype for Business Server 控制面板中配置 SIP 联盟、远程用户访问和公共即时消息 (IM) 连接。 例如，如果创建了支持远程用户访问的策略，则必须将其应用于用户，然后用户才能从远程位置连接到 Skype for Business Server 并与远程位置的内部用户进行协作。


> [!NOTE]  
> 要支持外部用户访问，必须启用对要支持的每种外部用户访问类型的支持，并配置相应的策略及其他选项以控制其使用。 有关详细信息，请参阅[Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md)。


使用本主题中的过程将以前创建的外部用户访问策略应用于一个或多个用户帐户。


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>将外部用户策略应用于用户帐户

1.  使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 

3.  在左侧导航栏中，单击“用户”，然后搜索要配置的用户帐户。

4.  在列出搜索结果的表中，单击相应的用户帐户，再单击“编辑”，然后单击“显示详细信息”。

5.  在 **"Skype for Business Server** 访问 **策略**"下的"编辑用户"中，选择要应用的用户策略。
     
> [!NOTE]  
> 这些设置 **\<Automatic>** 将应用默认服务器或全局策略设置。


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>使用 Per-User Cmdlet 分配Windows PowerShell访问策略

每用户外部访问策略可以使用 Windows PowerShell cmdlet Grant-CsExternalAccessPolicy分配。 此 cmdlet 可以从命令行管理程序Skype for Business Server远程会话运行Windows PowerShell。 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>将每用户外部访问策略分配给单个用户

  - 此命令向用户 Ken Myer 分配每用户外部访问策略 RedmondExternalAccessPolicy。
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>将每用户外部访问策略分配给多个用户

  - 此命令向在 Active Directory 的 UnitedStates OU 中拥有帐户的所有用户分配每用户外部访问策略 USAExternalAccessPolicy。 有关此命令中使用的 OU 参数详细信息，请参阅 [Get-CsUser](/powershell/module/skype/Get-CsUser) cmdlet 的文档。
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a>取消分配每用户外部访问策略

  - 此命令取消分配之前为 Ken Myer 分配的任何每用户外部访问策略。在取消分配每用户策略后，将自动使用全局策略或本地站点策略（如果有）管理 Ken Myer。站点策略优先于全局策略。
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null



有关详细信息，请参阅 [Grant-CsExternalAccessPolicy](/powershell/module/skype/Grant-CsExternalAccessPolicy) cmdlet 的帮助主题。