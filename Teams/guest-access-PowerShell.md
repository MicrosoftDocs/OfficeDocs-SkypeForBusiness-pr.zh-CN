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
ms.openlocfilehash: d438b9d5cf3af8d200da07fcebe39f4222c2b25a
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2020
ms.locfileid: "44637301"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a><span data-ttu-id="be554-103">使用 PowerShell 控制对团队的来宾访问</span><span class="sxs-lookup"><span data-stu-id="be554-103">Use PowerShell to control guest access to a team</span></span>
================================================

<span data-ttu-id="be554-104">除了使用 Microsoft 365 管理中心和 Azure Active Directory （Azure AD）门户之外，你还可以使用 Windows PowerShell 控制来宾访问。</span><span class="sxs-lookup"><span data-stu-id="be554-104">In addition to using the Microsoft 365 admin center and the Azure Active Directory (Azure AD) portal, you can use Windows PowerShell to control guest access.</span></span> <span data-ttu-id="be554-105">使用 PowerShell 可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="be554-105">With PowerShell, you can do the following:</span></span>
  
- <span data-ttu-id="be554-106">允许或阻止对所有团队和 Microsoft 365 组的来宾访问</span><span class="sxs-lookup"><span data-stu-id="be554-106">Allow or block guest access to all teams and Microsoft 365 Groups</span></span>

- <span data-ttu-id="be554-107">允许将来宾添加到所有团队和 Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="be554-107">Allow guests to be added to all teams and Microsoft 365 Groups</span></span>

- <span data-ttu-id="be554-108">允许或阻止来自特定团队或 Microsoft 365 组的来宾用户</span><span class="sxs-lookup"><span data-stu-id="be554-108">Allow or block guest users from a specific team or Microsoft 365 group</span></span>

<span data-ttu-id="be554-109">有关详细信息，请参阅在[Microsoft 365 组中管理来宾访问](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups#use-powershell-to-control-guest-access)中的 "使用 PowerShell 控制来宾访问"。</span><span class="sxs-lookup"><span data-stu-id="be554-109">For details, see "Use PowerShell to control guest access" in [Manage guest access in Microsoft 365 Groups](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups#use-powershell-to-control-guest-access).</span></span>

  
<span data-ttu-id="be554-110">你还可以使用 PowerShell 根据来宾用户的域允许或阻止来宾用户。</span><span class="sxs-lookup"><span data-stu-id="be554-110">You can also use PowerShell to allow or block a guest user based on their domain.</span></span> <span data-ttu-id="be554-111">例如，假定你的企业 (Contoso) 与另一家企业 (Fabrikam) 有合作关系。</span><span class="sxs-lookup"><span data-stu-id="be554-111">For example, let's say your business (Contoso) has a partnership with another business (Fabrikam).</span></span> <span data-ttu-id="be554-112">你可以将 Fabrikam 添加到你的允许列表，以便你的用户可以将那些来宾添加到其组。</span><span class="sxs-lookup"><span data-stu-id="be554-112">You can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span> <span data-ttu-id="be554-113">有关详细信息，请参阅[允许/阻止来宾访问 Microsoft 365 组](https://go.microsoft.com/fwlink/?linkid=854001)。</span><span class="sxs-lookup"><span data-stu-id="be554-113">For more information, see [Allow/Block guest access to Microsoft 365 Groups](https://go.microsoft.com/fwlink/?linkid=854001).</span></span>
  
<span data-ttu-id="be554-114">如果要阻止团队中的来宾，但仍希望允许他们访问 SharePoint 网站，则可以使用 Azure AD Powershell cmdlet 禁用公司对象上的 AllowGuestsToAccessGroups 参数，前提是已为 SharePoint 网站启用外部共享。</span><span class="sxs-lookup"><span data-stu-id="be554-114">If you want to block guests in Teams and still want to allow them to access SharePoint sites, you can use Azure AD Powershell cmdlets to disable the AllowGuestsToAccessGroups parameter on the Company object, assuming external sharing is turned on for SharePoint sites.</span></span>

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a><span data-ttu-id="be554-115">使用 PowerShell 打开或关闭来宾访问</span><span class="sxs-lookup"><span data-stu-id="be554-115">Use PowerShell to turn guest access on or off</span></span>

1.    <span data-ttu-id="be554-116">从下载 Skype for Business Online PowerShell 模块https://www.microsoft.com/download/details.aspx?id=39366</span><span class="sxs-lookup"><span data-stu-id="be554-116">Download the Skype for Business Online PowerShell module from https://www.microsoft.com/download/details.aspx?id=39366</span></span>
 
2.    <span data-ttu-id="be554-117">将 PowerShell 会话连接到 Skype for Business Online 终结点。</span><span class="sxs-lookup"><span data-stu-id="be554-117">Connect a PowerShell session to the Skype for Business Online endpoint.</span></span>

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.    <span data-ttu-id="be554-118">检查您的配置，如果 `AllowGuestUser` 是 `$False` ，请使用[CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet 将其设置为 `$True` 。</span><span class="sxs-lookup"><span data-stu-id="be554-118">Check your configuration and if `AllowGuestUser` is `$False`, use the [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet to set it to `$True`.</span></span>

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
<span data-ttu-id="be554-119">您现在可以在组织的工作组中拥有来宾用户。</span><span class="sxs-lookup"><span data-stu-id="be554-119">You can now have guest users in Teams for your organization.</span></span>


## <a name="guest-access-vs-external-access"></a><span data-ttu-id="be554-120">来宾访问和外部访问</span><span class="sxs-lookup"><span data-stu-id="be554-120">Guest access vs. external access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
