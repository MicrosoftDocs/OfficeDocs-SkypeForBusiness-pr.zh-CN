---
title: 使用 PowerShell 控制对团队的来宾访问
ms.author: mikeplum
author: MikePlumleyMSFT
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
ms.openlocfilehash: 0c8a2e23f5c03420c4b0ce644a80e0733f9f69a5
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814331"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a><span data-ttu-id="71d3c-103">使用 PowerShell 控制对团队的来宾访问</span><span class="sxs-lookup"><span data-stu-id="71d3c-103">Use PowerShell to control guest access to a team</span></span>
================================================

<span data-ttu-id="71d3c-104">除了使用 Microsoft 365 管理中心和 Azure Active Directory) 门户 (Azure AD，你还可以使用 Windows PowerShell 控制来宾访问。</span><span class="sxs-lookup"><span data-stu-id="71d3c-104">In addition to using the Microsoft 365 admin center and the Azure Active Directory (Azure AD) portal, you can use Windows PowerShell to control guest access.</span></span> <span data-ttu-id="71d3c-105">使用 PowerShell 可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="71d3c-105">With PowerShell, you can do the following:</span></span>
  
- <span data-ttu-id="71d3c-106">允许或阻止对所有团队和 Microsoft 365 组的来宾访问</span><span class="sxs-lookup"><span data-stu-id="71d3c-106">Allow or block guest access to all teams and Microsoft 365 Groups</span></span>

- <span data-ttu-id="71d3c-107">允许将来宾添加到所有团队和 Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="71d3c-107">Allow guests to be added to all teams and Microsoft 365 Groups</span></span>

- <span data-ttu-id="71d3c-108">允许或阻止来自特定团队或 Microsoft 365 组的来宾用户</span><span class="sxs-lookup"><span data-stu-id="71d3c-108">Allow or block guest users from a specific team or Microsoft 365 group</span></span>

<span data-ttu-id="71d3c-109">有关详细信息，请参阅在 [Microsoft 365 组中管理来宾访问](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups)中的 "使用 PowerShell 控制来宾访问"。</span><span class="sxs-lookup"><span data-stu-id="71d3c-109">For details, see "Use PowerShell to control guest access" in [Manage guest access in Microsoft 365 Groups](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups).</span></span>

  
<span data-ttu-id="71d3c-110">你还可以使用 PowerShell 根据来宾用户的域允许或阻止来宾用户。</span><span class="sxs-lookup"><span data-stu-id="71d3c-110">You can also use PowerShell to allow or block a guest user based on their domain.</span></span> <span data-ttu-id="71d3c-111">例如，假定你的企业 (Contoso) 与另一家企业 (Fabrikam) 有合作关系。</span><span class="sxs-lookup"><span data-stu-id="71d3c-111">For example, let's say your business (Contoso) has a partnership with another business (Fabrikam).</span></span> <span data-ttu-id="71d3c-112">你可以将 Fabrikam 添加到你的允许列表，以便你的用户可以将那些来宾添加到其组。</span><span class="sxs-lookup"><span data-stu-id="71d3c-112">You can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span> <span data-ttu-id="71d3c-113">有关详细信息，请参阅 [允许/阻止来宾访问 Microsoft 365 组](https://go.microsoft.com/fwlink/?linkid=854001)。</span><span class="sxs-lookup"><span data-stu-id="71d3c-113">For more information, see [Allow/Block guest access to Microsoft 365 Groups](https://go.microsoft.com/fwlink/?linkid=854001).</span></span>
  
<span data-ttu-id="71d3c-114">如果要阻止团队中的来宾，但仍希望允许他们访问 SharePoint 网站，则可以使用 Azure AD PowerShell cmdlet 禁用公司对象上的 AllowGuestsToAccessGroups 参数，前提是已为 SharePoint 网站启用外部共享。</span><span class="sxs-lookup"><span data-stu-id="71d3c-114">If you want to block guests in Teams and still want to allow them to access SharePoint sites, you can use Azure AD PowerShell cmdlets to disable the AllowGuestsToAccessGroups parameter on the Company object, assuming external sharing is turned on for SharePoint sites.</span></span>

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a><span data-ttu-id="71d3c-115">使用 PowerShell 打开或关闭来宾访问</span><span class="sxs-lookup"><span data-stu-id="71d3c-115">Use PowerShell to turn guest access on or off</span></span>

1.  <span data-ttu-id="71d3c-116">从下载 Skype for Business Online PowerShell 模块 https://www.microsoft.com/download/details.aspx?id=39366</span><span class="sxs-lookup"><span data-stu-id="71d3c-116">Download the Skype for Business Online PowerShell module from https://www.microsoft.com/download/details.aspx?id=39366</span></span>
 
2.  <span data-ttu-id="71d3c-117">将 PowerShell 会话连接到 Skype for Business Online 终结点。</span><span class="sxs-lookup"><span data-stu-id="71d3c-117">Connect a PowerShell session to the Skype for Business Online endpoint.</span></span>

> [!NOTE]
> <span data-ttu-id="71d3c-118">Skype for Business Online 连接器目前是最新团队 PowerShell 模块的一部分。</span><span class="sxs-lookup"><span data-stu-id="71d3c-118">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="71d3c-119">如果您使用的是最新的 [团队 PowerShell 公共版本](https://www.powershellgallery.com/packages/MicrosoftTeams/)，则无需安装 Skype For Business Online 连接器。</span><span class="sxs-lookup"><span data-stu-id="71d3c-119">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

    ```powershell
    Import-Module -Name MicrosoftTeams
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
    
3.  <span data-ttu-id="71d3c-120">检查您的配置，如果 `AllowGuestUser` 是 `$False` ，请使用 [CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet 将其设置为 `$True` 。</span><span class="sxs-lookup"><span data-stu-id="71d3c-120">Check your configuration and if `AllowGuestUser` is `$False`, use the [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet to set it to `$True`.</span></span>

    ```powershell
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
<span data-ttu-id="71d3c-121">您现在可以在组织的工作组中拥有来宾用户。</span><span class="sxs-lookup"><span data-stu-id="71d3c-121">You can now have guest users in Teams for your organization.</span></span>


## <a name="guest-access-vs-external-access"></a><span data-ttu-id="71d3c-122">来宾访问和外部访问</span><span class="sxs-lookup"><span data-stu-id="71d3c-122">Guest access vs. external access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
