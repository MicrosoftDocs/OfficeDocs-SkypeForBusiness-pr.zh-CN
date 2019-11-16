---
title: Microsoft 团队的灵敏度标签
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: abgupta
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何在 Microsoft 团队中定义和使用敏感度标签。
ms.openlocfilehash: 3a0c40a51653a525587a0662949a3fdd4e63faf4
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2019
ms.locfileid: "38653563"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a><span data-ttu-id="67146-103">Microsoft 团队的灵敏度标签</span><span class="sxs-lookup"><span data-stu-id="67146-103">Sensitivity labels for Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="67146-104">[敏感度标签](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)允许团队管理员控制在团队内协作期间创建的敏感组织内容的访问权限。</span><span class="sxs-lookup"><span data-stu-id="67146-104">[Sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) allow Teams admins to regulate access to sensitive organizational content created during collaboration within teams.</span></span> <span data-ttu-id="67146-105">你可以在[安全 & 合规中心](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)中定义灵敏度标签及其关联的策略。</span><span class="sxs-lookup"><span data-stu-id="67146-105">You can define sensitivity labels and their associated policies in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span></span> <span data-ttu-id="67146-106">这些标签和策略将自动应用于你的组织中的团队。</span><span class="sxs-lookup"><span data-stu-id="67146-106">These labels and policies are automatically applied to teams in your organization.</span></span>  

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a><span data-ttu-id="67146-107">灵敏度标签和团队分类标签之间有何区别？</span><span class="sxs-lookup"><span data-stu-id="67146-107">What's the difference between sensitivity labels and Teams classification labels?</span></span>

<span data-ttu-id="67146-108">敏感度标签不同于需要使用 PowerShell 创建的分类标签。</span><span class="sxs-lookup"><span data-stu-id="67146-108">Sensitivity labels are different from classification labels that require you to create them using PowerShell.</span></span> <span data-ttu-id="67146-109">分类标签是可与组相关联但没有任何相关联的实际策略的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="67146-109">Classification labels are text strings that can be associated with a group but don't have any actual policies associated with them.</span></span> <span data-ttu-id="67146-110">将分类标签用作元数据以通过内部工具和脚本手动强制实施策略。</span><span class="sxs-lookup"><span data-stu-id="67146-110">You use classification labels as metadata to manually enforce policies through internal tools and scripts.</span></span>

<span data-ttu-id="67146-111">另一方面，灵敏度标签和其策略通过组平台、安全 & 合规中心和团队服务的组合自动实施端到端。</span><span class="sxs-lookup"><span data-stu-id="67146-111">On the other hand, sensitivity labels and their policies are automatically enforced end-to-end through a combination of the Groups platform, Security & Compliance Center, and Teams services.</span></span> <span data-ttu-id="67146-112">灵敏度标签提供强大的基础结构支持以保护组织的敏感数据。</span><span class="sxs-lookup"><span data-stu-id="67146-112">Sensitivity labels provide powerful infrastructure support for securing your organization's sensitive data.</span></span>  

## <a name="create-and-publish-sensitivity-labels-for-teams"></a><span data-ttu-id="67146-113">创建和发布团队的灵敏度标签</span><span class="sxs-lookup"><span data-stu-id="67146-113">Create and publish sensitivity labels for Teams</span></span>

<span data-ttu-id="67146-114">有关如何为团队启用、创建和发布敏感度标签的详细说明，请参阅[将敏感度标签与 Microsoft 团队、Office 365 组和 SharePoint 网站结合使用](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)。</span><span class="sxs-lookup"><span data-stu-id="67146-114">For how to enable, create, and publish sensitivity labels for Teams, see [Use sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

## <a name="using-sensitivity-labels-with-teams"></a><span data-ttu-id="67146-115">将灵敏度标签与团队配合使用</span><span class="sxs-lookup"><span data-stu-id="67146-115">Using sensitivity labels with Teams</span></span>

<span data-ttu-id="67146-116">下面是一些有关如何将敏感度标签与组织中的团队配合使用的示例方案。</span><span class="sxs-lookup"><span data-stu-id="67146-116">Here are some example scenarios of how you can use sensitivity labels with Teams in your organization.</span></span>

### <a name="privacy-setting-of-teams"></a><span data-ttu-id="67146-117">团队的隐私设置</span><span class="sxs-lookup"><span data-stu-id="67146-117">Privacy setting of teams</span></span>

<span data-ttu-id="67146-118">你可以创建在团队创建期间应用的敏感度标签，以允许用户使用特定隐私（公共或专用）设置创建团队。</span><span class="sxs-lookup"><span data-stu-id="67146-118">You can create a sensitivity label that, when applied during team creation, allows users to create teams with a specific privacy (public or private) setting.</span></span>

<span data-ttu-id="67146-119">例如，在安全 & 合规中心创建名为 "保密" 的标签，并配置团队，以便使用此标签创建的任何团队都必须是专用团队。</span><span class="sxs-lookup"><span data-stu-id="67146-119">For example, you create a label named “Confidential” in the Security & Compliance Center and you configure Teams so that any team that's created with this label must be a private team.</span></span> <span data-ttu-id="67146-120">当用户创建新团队并选择 "**机密**" 标签时，用户可用的唯一隐私选项是 "**专用**"。</span><span class="sxs-lookup"><span data-stu-id="67146-120">When a user creates a new team and selects the **Confidential** label, the only privacy option that's available to the user is **Private**.</span></span> <span data-ttu-id="67146-121">用户已禁用其他隐私选项，如公共和组织范围。</span><span class="sxs-lookup"><span data-stu-id="67146-121">Other privacy options such as Public and Org-wide are disabled for the user.</span></span>

![机密敏感度标签的屏幕截图](media/sensitivity-labels-confidential-example.png)

<span data-ttu-id="67146-123">同样，如果用户在创建新团队时选择 "**常规**"，则他们只能创建公共团队或组织级团队。</span><span class="sxs-lookup"><span data-stu-id="67146-123">Similarly, if the user selects **General** when they create a new team, they can only create public or org-wide teams.</span></span>

![常规灵敏度标签的屏幕截图](media/sensitivity-labels-general-example.png)

<span data-ttu-id="67146-125">创建团队时，灵敏度标签显示在团队频道的右上角。</span><span class="sxs-lookup"><span data-stu-id="67146-125">When the team is created, the sensitivity label is visible in the upper-right corner of channels in the team.</span></span>

![团队频道中灵敏度标签的屏幕截图](media/sensitivity-labels-channel.png)

<span data-ttu-id="67146-127">团队所有者可以随时更改团队的敏感度标签和隐私设置，方法是转到团队，然后单击 "**编辑团队**"。</span><span class="sxs-lookup"><span data-stu-id="67146-127">A team owner can change the sensitivity label and the privacy setting of the team at any time by going to the team, and then clicking **Edit team**.</span></span>

![团队频道中灵敏度标签的屏幕截图](media/sensitivity-labels-edit-team.png)

### <a name="guest-access-to-teams"></a><span data-ttu-id="67146-129">对团队的来宾访问</span><span class="sxs-lookup"><span data-stu-id="67146-129">Guest access to teams</span></span>

<span data-ttu-id="67146-130">你可以指定使用特定标签创建的团队是否允许来宾访问。</span><span class="sxs-lookup"><span data-stu-id="67146-130">You can specify whether a team created with a specific label allows guest access.</span></span> <span data-ttu-id="67146-131">使用不允许来宾访问的标签创建的团队仅对您的组织中的用户可用。</span><span class="sxs-lookup"><span data-stu-id="67146-131">Teams created with a label that doesn't allow guest access are only available to users in your organization.</span></span> <span data-ttu-id="67146-132">无法将组织外部的人员添加到团队。</span><span class="sxs-lookup"><span data-stu-id="67146-132">People outside your organization can't be added to the team.</span></span>

## <a name="known-issues"></a><span data-ttu-id="67146-133">已知问题</span><span class="sxs-lookup"><span data-stu-id="67146-133">Known issues</span></span>

<span data-ttu-id="67146-134">**Microsoft 团队管理中心中对灵敏度标签的支持**</span><span class="sxs-lookup"><span data-stu-id="67146-134">**Support for sensitivity labels in the Microsoft Teams admin center**</span></span>

<span data-ttu-id="67146-135">目前，Microsoft 团队管理中心不支持敏感性标签。</span><span class="sxs-lookup"><span data-stu-id="67146-135">Currently, sensitivity labels are not supported in the Microsoft Teams admin center.</span></span> <span data-ttu-id="67146-136">如果使用灵敏度标签，则在创建或编辑团队时将无法设置灵敏度标签。</span><span class="sxs-lookup"><span data-stu-id="67146-136">If you use sensitivity labels, you won't be able to set sensitivity labels when you create or edit a team.</span></span> <span data-ttu-id="67146-137">灵敏度标签在团队属性中也不可见，并且在 Microsoft 团队管理中心的 "**分类**" 列中不可见。</span><span class="sxs-lookup"><span data-stu-id="67146-137">Sensitivity labels are also not visible in team properties and won't be visible in the **Classification** column in the Microsoft Teams admin center.</span></span>

<span data-ttu-id="67146-138">**对团队图形 Api、Powershell cmdlet 和模板中的灵敏度标签的支持**</span><span class="sxs-lookup"><span data-stu-id="67146-138">**Support for sensitivity labels in Teams Graph APIs, Powershell cmdlets and templates**</span></span>

<span data-ttu-id="67146-139">当前，用户无法对直接通过图形 Api、Powershell cmdlet 和模板创建的团队应用敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="67146-139">Currently, users won't be able to apply sensitivity labels on teams that are created directly through Graph APIs, Powershell cmdlets, and templates.</span></span>

<span data-ttu-id="67146-140">**直接在专用频道的 SharePoint 网站集上编辑灵敏度标签**</span><span class="sxs-lookup"><span data-stu-id="67146-140">**Editing sensitivity labels directly on a SharePoint site collection for private channels**</span></span>

<span data-ttu-id="67146-141">在团队中创建的专用频道将继承应用于团队的灵敏度标签。</span><span class="sxs-lookup"><span data-stu-id="67146-141">Private channels that are created in a team inherit the sensitivity label which was applied on a team.</span></span> <span data-ttu-id="67146-142">此外，将在专用频道的 SharePoint 网站集上自动应用相同的标签。</span><span class="sxs-lookup"><span data-stu-id="67146-142">Furthermore, the same label is automatically applied on the SharePoint site collection for the private channel.</span></span>

<span data-ttu-id="67146-143">如果用户在专用频道的 SharePoint 网站集上直接更新灵敏度标签，则不会在团队客户端中更新该标签。</span><span class="sxs-lookup"><span data-stu-id="67146-143">If a user directly updates the sensitivity label on a SharePoint site collection for a private channel, that label isn't updated in the Teams client.</span></span> <span data-ttu-id="67146-144">在这种情况下，用户将继续在专用信道标题中看到团队中应用的灵敏度标签。</span><span class="sxs-lookup"><span data-stu-id="67146-144">In this scenario, users will continue to see the sensitivity label applied on a team in the private channel header.</span></span>

<span data-ttu-id="67146-145">**应用于团队应用外的灵敏度标签的更改的传播时间**</span><span class="sxs-lookup"><span data-stu-id="67146-145">**Propagation times for changes applied to sensitivity labels outside the Teams app**</span></span>

<span data-ttu-id="67146-146">对 "团队" 应用外的灵敏度标签所做的更改最多需要24小时才能反映在 "团队" 应用中。</span><span class="sxs-lookup"><span data-stu-id="67146-146">Changes made to sensitivity labels outside the Teams app can take up to 24 hours to reflect in the Teams app.</span></span> <span data-ttu-id="67146-147">这适用于为租户启用或禁用标签、更改标签名称、设置和策略所做的任何更改。</span><span class="sxs-lookup"><span data-stu-id="67146-147">This applies to any changes made to enable or disable labels for a tenant, changes to label names, settings, and policies.</span></span>

<span data-ttu-id="67146-148">此外，直接对支持团队的组或 SharePoint 网站集直接更改标签的任何更改最多可能需要24小时才能传播到团队应用。</span><span class="sxs-lookup"><span data-stu-id="67146-148">Additionally, any changes to a label made directly to a group or SharePoint site collection that backs the team can take up to 24 hours to propagate to the Teams app.</span></span>