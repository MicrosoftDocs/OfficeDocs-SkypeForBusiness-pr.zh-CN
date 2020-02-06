---
title: 分配外部用户访问策略
ms.reviewer: ''
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 如果用户已启用 Skype for business 服务器的用户，则可以通过向特定用户应用相应的策略来在 Skype for business 服务器控制面板中配置 SIP 联盟、远程用户访问和公共即时消息（IM）连接。
ms.openlocfilehash: b87eb377b23063dbcdfd9562a99533da230a8f30
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818323"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a>将外部用户访问策略分配给启用 Skype for Business 的用户

如果用户已启用 Skype for business 服务器的用户，则可以通过向特定用户应用相应的策略来在 Skype for business 服务器控制面板中配置 SIP 联盟、远程用户访问和公共即时消息（IM）连接。 例如，如果你创建了支持远程用户访问的策略，则必须先将其应用于用户，然后用户才能从远程位置连接到 Skype for Business 服务器，并从远程位置与内部用户进行协作。


> [!NOTE]  
> 若要支持外部用户访问，必须启用对要支持的每种类型的外部用户访问的支持，并配置相应的策略和其他选项以控制其使用。 有关详细信息，请参阅[管理对 Skype for Business 服务器的联盟和外部访问](../managing-federation-and-external-access.md)。


使用本主题中的过程将以前创建的外部用户访问策略应用于一个或多个用户帐户。


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>将外部用户策略应用于用户帐户

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 

3.  在左侧导航栏中，单击“**用户**”，然后搜索要配置的用户帐户。

4.  在列出搜索结果的表中，单击相应的用户帐户，再单击“**编辑**”，然后单击“**显示详细信息**”。

5.  在 "**编辑 Skype For Business 服务器" 用户**的 "**外部访问策略**" 下，选择要应用的用户策略。
     
> [!NOTE]  
> 自动>设置将应用默认服务器或全局策略设置。 ** \<**


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 分配每用户外部访问策略

可以使用 Windows PowerShell 和 CsExternalAccessPolicy cmdlet 分配每用户外部访问策略。 此 cmdlet 既可以从 Skype for Business 服务器管理外壳运行，也可以从 Windows PowerShell 的远程会话运行。 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>将每用户外部访问策略分配给单个用户

  - 此命令将每用户外部访问策略 RedmondExternalAccessPolicy 分配给用户 Ken Myer。
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>为多个用户分配每个用户的外部访问策略

  - 此命令将每用户外部访问策略 USAExternalAccessPolicy 分配给在 Active Directory 中的美国组织单位中拥有帐户的所有用户。 有关此命令中使用的 OU 参数的详细信息，请参阅[move-csuser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) cmdlet 的文档。
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a>取消分配每用户外部访问策略

  - 此命令取消之前分配给 Ken Myer 的任何每用户外部访问策略。 取消分配每用户策略后，将自动使用全局策略或本地站点策略（如果存在）管理 Ken Myer。 站点策略优先于全局策略。
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null



有关详细信息，请参阅[CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy) cmdlet 的帮助主题。


