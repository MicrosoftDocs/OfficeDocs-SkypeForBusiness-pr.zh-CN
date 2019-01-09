---
title: 使用 PowerShell 控制对团队的来宾访问
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 11/09/17
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: sbhatta
search.appverid: MET150
description: 使用 PowerShell 在 Microsoft Teams 中允许或阻止对团队的来宾访问
appliesto:
- Microsoft Teams
ms.openlocfilehash: e1e8eaa8722893316f761566a425b7e8ed6f2aaa
ms.sourcegitcommit: 454ded73af5854d7b81a3b996702a6464b3fc313
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "27772718"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a><span data-ttu-id="b9409-103">使用 PowerShell 控制对团队的来宾访问</span><span class="sxs-lookup"><span data-stu-id="b9409-103">Use PowerShell to control guest access to a team</span></span>
================================================

<span data-ttu-id="b9409-104">除了使用 Office 365 管理中心和 Azure Active Directory 门户外，你还可以使用 Windows PowerShell 控制来宾访问。</span><span class="sxs-lookup"><span data-stu-id="b9409-104">In addition to using the Office 365 admin center and the Azure Active Directory portal, you can use Windows PowerShell to control guest access.</span></span> <span data-ttu-id="b9409-105">使用 PowerShell 可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b9409-105">With PowerShell, you can do the following:</span></span>
  
- <span data-ttu-id="b9409-106">允许或阻止来宾访问所有团队和 Office 365 组</span><span class="sxs-lookup"><span data-stu-id="b9409-106">Allow or block guest access to all teams and Office 365 groups</span></span>
    
  
- <span data-ttu-id="b9409-107">允许将来宾添加到所有团队和 Office 365 组</span><span class="sxs-lookup"><span data-stu-id="b9409-107">Allow guests to be added to all teams and Office 365 groups</span></span>
    
  
- <span data-ttu-id="b9409-108">在特定团队或 Office 365 组中允许或阻止来宾用户</span><span class="sxs-lookup"><span data-stu-id="b9409-108">Allow or block guest users from a specific team or Office 365 group</span></span>
    
  
<span data-ttu-id="b9409-109">有关更多详细信息，请参阅 [Office 365 组中的来宾访问](https://support.office.com/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell)的“管理”选项卡中的“使用 PowerShell 控制来宾访问”部分。</span><span class="sxs-lookup"><span data-stu-id="b9409-109">For more details, see the section "Use PowerShell to control guest access" on the Manage tab of [Guest access in Office 365 Groups](https://support.office.com/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).</span></span>
  
<span data-ttu-id="b9409-110">你还可以使用 PowerShell 根据来宾用户的域允许或阻止来宾用户。</span><span class="sxs-lookup"><span data-stu-id="b9409-110">You can also use PowerShell to allow or block a guest user based on their domain.</span></span> <span data-ttu-id="b9409-111">例如，假定你的企业 (Contoso) 与另一家企业 (Fabrikam) 有合作关系。</span><span class="sxs-lookup"><span data-stu-id="b9409-111">For example, let's say your business (Contoso) has a partnership with another business (Fabrikam).</span></span> <span data-ttu-id="b9409-112">你可以将 Fabrikam 添加到你的允许列表，以便你的用户可以将那些来宾添加到其组。</span><span class="sxs-lookup"><span data-stu-id="b9409-112">You can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span> <span data-ttu-id="b9409-113">有关更多详细信息，请参阅[“允许/阻止对 Office 365 组的来宾访问”](https://go.microsoft.com/fwlink/?linkid=854001)。</span><span class="sxs-lookup"><span data-stu-id="b9409-113">For more information, see [Allow/Block guest access to Office 365 groups](https://go.microsoft.com/fwlink/?linkid=854001).</span></span>
  
 
<span data-ttu-id="b9409-114">如果你要在团队中阻止来宾，但仍允许来宾访问 SharePoint 网站，你可以使用 Azure Active Directory Powershell cmdlet 对 Company 对象禁用 AllowGuestAccessToGroups 参数，从而实现对 SharePoint 网站开启外部共享。</span><span class="sxs-lookup"><span data-stu-id="b9409-114">If you want to block guests in teams and still allow guests to access SharePoint sites, you can use Azure Active Directory Powershell cmdlets to disable the AllowGuestAccessToGroups parameter on the Company object, assuming external sharing is turned on for SharePoint sites.</span></span>   

