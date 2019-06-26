---
title: 使用 PowerShell 控制对团队的来宾访问
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/25/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: 使用 PowerShell 在 Microsoft Teams 中允许或阻止对团队的来宾访问
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0b429d4e2411e697c4e3357ebd7b5fc66ab27376
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2019
ms.locfileid: "35220883"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a><span data-ttu-id="cdc9b-103">使用 PowerShell 控制对团队的来宾访问</span><span class="sxs-lookup"><span data-stu-id="cdc9b-103">Use PowerShell to control guest access to a team</span></span>
================================================

<span data-ttu-id="cdc9b-104">除了使用 Microsoft 365 管理中心和 Azure Active Directory (Azure AD) 门户之外, 你还可以使用 Windows PowerShell 控制来宾访问。</span><span class="sxs-lookup"><span data-stu-id="cdc9b-104">In addition to using the Microsoft 365 admin center and the Azure Active Directory (Azure AD) portal, you can use Windows PowerShell to control guest access.</span></span> <span data-ttu-id="cdc9b-105">使用 PowerShell 可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="cdc9b-105">With PowerShell, you can do the following:</span></span>
  
- <span data-ttu-id="cdc9b-106">允许或阻止对所有团队和 Office 365 组的来宾访问</span><span class="sxs-lookup"><span data-stu-id="cdc9b-106">Allow or block guest access to all teams and Office 365 Groups</span></span>

- <span data-ttu-id="cdc9b-107">允许将来宾添加到所有团队和 Office 365 组</span><span class="sxs-lookup"><span data-stu-id="cdc9b-107">Allow guests to be added to all teams and Office 365 Groups</span></span>

- <span data-ttu-id="cdc9b-108">在特定团队或 Office 365 组中允许或阻止来宾用户</span><span class="sxs-lookup"><span data-stu-id="cdc9b-108">Allow or block guest users from a specific team or Office 365 group</span></span>

<span data-ttu-id="cdc9b-109">有关详细信息, 请参阅在[Office 365 组中管理来宾访问](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups#use-powershell-to-control-guest-access)中的 "使用 PowerShell 控制来宾访问"。</span><span class="sxs-lookup"><span data-stu-id="cdc9b-109">For details, see "Use PowerShell to control guest access" in [Manage guest access in Office 365 Groups](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups#use-powershell-to-control-guest-access).</span></span>
  
<span data-ttu-id="cdc9b-110">你还可以使用 PowerShell 根据来宾用户的域允许或阻止来宾用户。</span><span class="sxs-lookup"><span data-stu-id="cdc9b-110">You can also use PowerShell to allow or block a guest user based on their domain.</span></span> <span data-ttu-id="cdc9b-111">例如，假定你的企业 (Contoso) 与另一家企业 (Fabrikam) 有合作关系。</span><span class="sxs-lookup"><span data-stu-id="cdc9b-111">For example, let's say your business (Contoso) has a partnership with another business (Fabrikam).</span></span> <span data-ttu-id="cdc9b-112">你可以将 Fabrikam 添加到你的允许列表，以便你的用户可以将那些来宾添加到其组。</span><span class="sxs-lookup"><span data-stu-id="cdc9b-112">You can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span> <span data-ttu-id="cdc9b-113">有关详细信息, 请参阅[允许/阻止来宾访问 Office 365 组](https://go.microsoft.com/fwlink/?linkid=854001)。</span><span class="sxs-lookup"><span data-stu-id="cdc9b-113">For more information, see [Allow/Block guest access to Office 365 Groups](https://go.microsoft.com/fwlink/?linkid=854001).</span></span>
  
<span data-ttu-id="cdc9b-114">如果你想要阻止团队中的来宾, 但仍希望允许他们访问 SharePoint 网站, 则可以使用 Azure AD Powershell cmdlet 禁用公司对象上的 AllowGuestsToAccessGroups 参数, 假设已为 SharePoint 网站启用外部共享.</span><span class="sxs-lookup"><span data-stu-id="cdc9b-114">If you want to block guests in Teams and still want to allow them to access SharePoint sites, you can use Azure AD Powershell cmdlets to disable the AllowGuestsToAccessGroups parameter on the Company object, assuming external sharing is turned on for SharePoint sites.</span></span>

## <a name="guest-access-vs-external-access"></a><span data-ttu-id="cdc9b-115">来宾访问和外部访问</span><span class="sxs-lookup"><span data-stu-id="cdc9b-115">Guest access vs. external access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
