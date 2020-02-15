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
description: 使用 PowerShell 在 Microsoft Teams 中允许或阻止对团队的来宾访问
appliesto:
- Microsoft Teams
ms.openlocfilehash: 73fba41958711b533f541bf382be0496276f850b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42012515"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a>使用 PowerShell 控制对团队的来宾访问
================================================

除了使用 Microsoft 365 管理中心和 Azure Active Directory （Azure AD）门户之外，你还可以使用 Windows PowerShell 控制来宾访问。 使用 PowerShell 可以执行以下操作：
  
- 允许或阻止对所有团队和 Office 365 组的来宾访问

- 允许将来宾添加到所有团队和 Office 365 组

- 在特定团队或 Office 365 组中允许或阻止来宾用户

有关详细信息，请参阅在[Office 365 组中管理来宾访问](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups#use-powershell-to-control-guest-access)中的 "使用 PowerShell 控制来宾访问"。

  
你还可以使用 PowerShell 根据来宾用户的域允许或阻止来宾用户。 例如，假定你的企业 (Contoso) 与另一家企业 (Fabrikam) 有合作关系。 你可以将 Fabrikam 添加到你的允许列表，以便你的用户可以将那些来宾添加到其组。 有关详细信息，请参阅[允许/阻止来宾访问 Office 365 组](https://go.microsoft.com/fwlink/?linkid=854001)。
  
如果你想要阻止团队中的来宾，但仍希望允许他们访问 SharePoint 网站，则可以使用 Azure AD Powershell cmdlet 禁用公司对象上的 AllowGuestsToAccessGroups 参数，假设已为 SharePoint 网站启用外部共享.

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a>使用 PowerShell 打开或关闭来宾访问

1.  从下载 Skype for Business Online PowerShell 模块https://www.microsoft.com/download/details.aspx?id=39366
 
2.  将 PowerShell 会话连接到 Skype for Business Online 终结点。

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  检查您的配置， `AllowGuestUser`如果`$False`是，请使用[CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet 将其设置为`$True`。

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
