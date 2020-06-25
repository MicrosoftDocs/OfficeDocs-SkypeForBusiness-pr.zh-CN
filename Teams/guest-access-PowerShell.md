---
title: 使用 PowerShell 控制对团队的来宾访问
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
f1.keywords:
- NOCSH
description: 了解如何使用 PowerShell 允许或阻止对 Microsoft 团队中的所有团队或特定团队的来宾访问。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8c77b34103913d850b29c84096251b3b2795f684
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/24/2020
ms.locfileid: "44867979"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a>使用 PowerShell 控制对团队的来宾访问
================================================

除了使用 Microsoft 365 管理中心和 Azure Active Directory （Azure AD）门户之外，你还可以使用 Windows PowerShell 控制来宾访问。 使用 PowerShell 可以执行以下操作：
  
- 允许或阻止对所有团队和 Microsoft 365 组的来宾访问

- 允许将来宾添加到所有团队和 Microsoft 365 组

- 允许或阻止来自特定团队或 Microsoft 365 组的来宾用户

有关详细信息，请参阅在[Microsoft 365 组中管理来宾访问](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups)中的 "使用 PowerShell 控制来宾访问"。

  
你还可以使用 PowerShell 根据来宾用户的域允许或阻止来宾用户。 例如，假定你的企业 (Contoso) 与另一家企业 (Fabrikam) 有合作关系。 你可以将 Fabrikam 添加到你的允许列表，以便你的用户可以将那些来宾添加到其组。 有关详细信息，请参阅[允许/阻止来宾访问 Microsoft 365 组](https://go.microsoft.com/fwlink/?linkid=854001)。
  
如果要阻止团队中的来宾，但仍希望允许他们访问 SharePoint 网站，则可以使用 Azure AD Powershell cmdlet 禁用公司对象上的 AllowGuestsToAccessGroups 参数，前提是已为 SharePoint 网站启用外部共享。

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a>使用 PowerShell 打开或关闭来宾访问

1.    从下载 Skype for Business Online PowerShell 模块https://www.microsoft.com/download/details.aspx?id=39366
 
2.    将 PowerShell 会话连接到 Skype for Business Online 终结点。

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.    检查您的配置，如果 `AllowGuestUser` 是 `$False` ，请使用[CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet 将其设置为 `$True` 。

    ```PowerShell
    Get-CsTeamsClientConfiguration

    Identity                         : Global
    AllowEmailIntoChannel            : True
    RestrictedSenderList             :
    AllowDropBox                     : True
    AllowBox                         : True
    AllowGoogleDrive                 : True
    AllowShareFile                   : True
    AllowOrganizationTab             : True
    AllowSkypeBusinessInterop        : True
    ContentPin                       : RequiredOutsideScheduleMeeting
    AllowResourceAccountSendMessage  : True
    ResourceAccountContentAccess     : NoAccess
    AllowGuestUser                   : True
    AllowScopedPeopleSearchandAccess : False
    
    Set-CsTeamsClientConfiguration -AllowGuestUser $True -Identity Global
    ```
您现在可以在组织的工作组中拥有来宾用户。


## <a name="guest-access-vs-external-access"></a>来宾访问和外部访问

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
