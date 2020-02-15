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
description: 如果已为用户启用 Skype for business Server，则可以通过将适当的策略应用于特定用户，在 Skype for Business Server 控制面板中配置 SIP 联合身份验证、远程用户访问和公共即时消息（IM）连接。
ms.openlocfilehash: c03eb957679877ec512b042e0db624adbb3e6f52
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043674"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a>将外部用户访问策略分配给启用 Skype for Business 的用户

如果已为用户启用 Skype for business Server，则可以通过将适当的策略应用于特定用户，在 Skype for Business Server 控制面板中配置 SIP 联合身份验证、远程用户访问和公共即时消息（IM）连接。 例如，如果创建了一个支持远程用户访问的策略，则必须将其应用于用户，然后用户才能从远程位置连接到 Skype for Business Server，并从远程位置与内部用户进行协作。


> [!NOTE]  
> 要支持外部用户访问，必须启用对要支持的每种外部用户访问类型的支持，并配置相应的策略及其他选项以控制其使用。 有关详细信息，请参阅[管理对 Skype For Business Server 的联盟和外部访问](../managing-federation-and-external-access.md)。


使用本主题中的过程将以前创建的外部用户访问策略应用于一个或多个用户帐户。


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>将外部用户策略应用于用户帐户

1.  使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 Skype for Business Server 控制面板。 

3.  在左侧导航栏中，单击“用户”****，然后搜索要配置的用户帐户。

4.  在列出搜索结果的表中，单击相应的用户帐户，再单击“编辑”****，然后单击“显示详细信息”****。

5.  在 "**编辑 Skype For Business Server 用户**" 中的 "**外部访问策略**" 下，选择要应用的用户策略。
     
> [!NOTE]  
> " ** \<自动>** 设置将应用默认的服务器或全局策略设置。


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 分配每用户外部访问策略

可以使用 Windows PowerShell 和 Set-csexternalaccesspolicy cmdlet 分配每用户外部访问策略。 此 cmdlet 可从 Skype for Business Server 命令行管理程序或从 Windows PowerShell 的远程会话中运行。 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>向单个用户分配每用户外部访问策略

  - 此命令向用户 Ken Myer 分配每用户外部访问策略 RedmondExternalAccessPolicy。
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>为多个用户分配每用户外部访问策略

  - 此命令向在 Active Directory 的 UnitedStates OU 中拥有帐户的所有用户分配每用户外部访问策略 USAExternalAccessPolicy。 有关此命令中使用的 OU 参数的详细信息，请参阅[get-csuser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet 的相关文档。
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a>取消分配每用户外部访问策略

  - 此命令取消分配之前为 Ken Myer 分配的任何每用户外部访问策略。在取消分配每用户策略后，将自动使用全局策略或本地站点策略（如果有）管理 Ken Myer。站点策略优先于全局策略。
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null



有关详细信息，请参阅[set-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) cmdlet 的帮助主题。


