---
title: 使用 PowerShell 控制对团队的来宾访问
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 11/09/17
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
ms.openlocfilehash: 815a35efbce89404b012d5534e257752bef8d53e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33886379"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a><span data-ttu-id="d7454-103">使用 PowerShell 控制对团队的来宾访问</span><span class="sxs-lookup"><span data-stu-id="d7454-103">Use PowerShell to control guest access to a team</span></span>
================================================

<span data-ttu-id="d7454-104">除了使用在 Microsoft 365 管理中心和 Azure Active Directory 门户网站，您可以使用 Windows PowerShell 来控制来宾访问。</span><span class="sxs-lookup"><span data-stu-id="d7454-104">In addition to using the Microsoft 365 admin center and the Azure Active Directory portal, you can use Windows PowerShell to control guest access.</span></span> <span data-ttu-id="d7454-105">使用 PowerShell 可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d7454-105">With PowerShell, you can do the following:</span></span>
  
- <span data-ttu-id="d7454-106">允许或阻止来宾访问所有团队和 Office 365 组</span><span class="sxs-lookup"><span data-stu-id="d7454-106">Allow or block guest access to all teams and Office 365 groups</span></span>
    
- <span data-ttu-id="d7454-107">允许将来宾添加到所有团队和 Office 365 组</span><span class="sxs-lookup"><span data-stu-id="d7454-107">Allow guests to be added to all teams and Office 365 groups</span></span>
      
- <span data-ttu-id="d7454-108">在特定团队或 Office 365 组中允许或阻止来宾用户</span><span class="sxs-lookup"><span data-stu-id="d7454-108">Allow or block guest users from a specific team or Office 365 group</span></span>
    
<span data-ttu-id="d7454-109">有关详细信息，请参阅[来宾访问 Office 365 组中](https://support.office.com/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell)的管理选项卡上的"使用 PowerShell 来控制来宾访问"一节。</span><span class="sxs-lookup"><span data-stu-id="d7454-109">For details, see the section "Use PowerShell to control guest access" on the Manage tab of [Guest access in Office 365 Groups](https://support.office.com/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).</span></span>
  
<span data-ttu-id="d7454-110">你还可以使用 PowerShell 根据来宾用户的域允许或阻止来宾用户。</span><span class="sxs-lookup"><span data-stu-id="d7454-110">You can also use PowerShell to allow or block a guest user based on their domain.</span></span> <span data-ttu-id="d7454-111">例如，假定你的企业 (Contoso) 与另一家企业 (Fabrikam) 有合作关系。</span><span class="sxs-lookup"><span data-stu-id="d7454-111">For example, let's say your business (Contoso) has a partnership with another business (Fabrikam).</span></span> <span data-ttu-id="d7454-112">你可以将 Fabrikam 添加到你的允许列表，以便你的用户可以将那些来宾添加到其组。</span><span class="sxs-lookup"><span data-stu-id="d7454-112">You can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span> <span data-ttu-id="d7454-113">有关更多详细信息，请参阅[“允许/阻止对 Office 365 组的来宾访问”](https://go.microsoft.com/fwlink/?linkid=854001)。</span><span class="sxs-lookup"><span data-stu-id="d7454-113">For more information, see [Allow/Block guest access to Office 365 groups](https://go.microsoft.com/fwlink/?linkid=854001).</span></span>
  
<span data-ttu-id="d7454-114">如果您想要阻止在团队中的来宾并且仍要允许其访问 SharePoint 网站，您可以使用 Azure Active Directory Powershell cmdlet 禁用对公司的对象的 AllowGuestsToAccessGroups 参数假定外部共享为打开SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="d7454-114">If you want to block guests in Teams and still want to allow them to access SharePoint sites, you can use Azure Active Directory Powershell cmdlets to disable the AllowGuestsToAccessGroups parameter on the Company object, assuming external sharing is turned on for SharePoint sites.</span></span>   

## <a name="guest-access-vs-external-access"></a><span data-ttu-id="d7454-115">与外部访问的来宾访问</span><span class="sxs-lookup"><span data-stu-id="d7454-115">Guest access vs. external access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
