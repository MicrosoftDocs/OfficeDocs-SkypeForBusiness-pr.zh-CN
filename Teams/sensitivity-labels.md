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
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: 了解如何在 Microsoft 团队中定义和使用敏感度标签。
ms.openlocfilehash: 21d70bf48448ccef5555078e4aba65bb10d5d6a2
ms.sourcegitcommit: d7e0406276def8bc731aa6dcbd49802441ec5138
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2020
ms.locfileid: "48476717"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a><span data-ttu-id="6788d-103">Microsoft 团队的灵敏度标签</span><span class="sxs-lookup"><span data-stu-id="6788d-103">Sensitivity labels for Microsoft Teams</span></span>

<span data-ttu-id="6788d-104">[敏感度标签](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) 允许团队管理员控制在团队内协作期间创建的敏感组织内容的访问权限。</span><span class="sxs-lookup"><span data-stu-id="6788d-104">[Sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) allow Teams admins to regulate access to sensitive organizational content created during collaboration within teams.</span></span> <span data-ttu-id="6788d-105">你可以在 [安全 & 合规中心](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)中定义灵敏度标签及其关联的策略。</span><span class="sxs-lookup"><span data-stu-id="6788d-105">You can define sensitivity labels and their associated policies in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span></span> <span data-ttu-id="6788d-106">这些标签和策略将自动应用于你的组织中的团队。</span><span class="sxs-lookup"><span data-stu-id="6788d-106">These labels and policies are automatically applied to teams in your organization.</span></span>  

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a><span data-ttu-id="6788d-107">灵敏度标签和团队分类标签之间有何区别？</span><span class="sxs-lookup"><span data-stu-id="6788d-107">What's the difference between sensitivity labels and Teams classification labels?</span></span>

<span data-ttu-id="6788d-108">敏感度标签不同于需要使用 PowerShell 创建的分类标签。</span><span class="sxs-lookup"><span data-stu-id="6788d-108">Sensitivity labels are different from classification labels that require you to create them using PowerShell.</span></span> <span data-ttu-id="6788d-109">分类标签是可与组相关联但没有任何相关联的实际策略的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="6788d-109">Classification labels are text strings that can be associated with a group but don't have any actual policies associated with them.</span></span> <span data-ttu-id="6788d-110">将分类标签用作元数据以通过内部工具和脚本手动强制实施策略。</span><span class="sxs-lookup"><span data-stu-id="6788d-110">You use classification labels as metadata to manually enforce policies through internal tools and scripts.</span></span>

<span data-ttu-id="6788d-111">另一方面，灵敏度标签和其策略通过组平台、安全 & 合规中心和团队服务的组合自动实施端到端。</span><span class="sxs-lookup"><span data-stu-id="6788d-111">On the other hand, sensitivity labels and their policies are automatically enforced end-to-end through a combination of the Groups platform, Security & Compliance Center, and Teams services.</span></span> <span data-ttu-id="6788d-112">灵敏度标签提供强大的基础结构支持以保护组织的敏感数据。</span><span class="sxs-lookup"><span data-stu-id="6788d-112">Sensitivity labels provide powerful infrastructure support for securing your organization's sensitive data.</span></span>  

<span data-ttu-id="6788d-113">若要将现有组从使用分类标签到使用灵敏度标签迁移，请使用 [Microsoft 365 组的 Azure Active Directory 分类和敏感度标签](https://docs.microsoft.com/microsoft-365/compliance/migrate-aad-classification-sensitivity-labels)中的说明。</span><span class="sxs-lookup"><span data-stu-id="6788d-113">To migrate your existing Groups from using classification labels to using sensitivity labels, use the instructions in [Azure Active Directory classification and sensitivity labels for Microsoft 365 groups](https://docs.microsoft.com/microsoft-365/compliance/migrate-aad-classification-sensitivity-labels).</span></span>
## <a name="create-manage-and-publish-sensitivity-labels-for-teams"></a><span data-ttu-id="6788d-114">为团队创建、管理和发布灵敏度标签</span><span class="sxs-lookup"><span data-stu-id="6788d-114">Create, manage, and publish sensitivity labels for Teams</span></span>

<span data-ttu-id="6788d-115">有关如何为团队启用、创建和发布敏感度标签的详细说明，请参阅 [Microsoft 365 组的 Azure Active Directory 分类和灵敏度标签](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)。</span><span class="sxs-lookup"><span data-stu-id="6788d-115">For how to enable, create, and publish sensitivity labels for Teams, see [Azure Active Directory classification and sensitivity labels for Microsoft 365 groups](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

>[!IMPORTANT]
><span data-ttu-id="6788d-116">创建、更新和删除灵敏度标签需要对用户发布标签的仔细排序。</span><span class="sxs-lookup"><span data-stu-id="6788d-116">Creating, updating and deleting sensitivity labels require careful sequencing with publishing labels to users.</span></span> <span data-ttu-id="6788d-117">序列中的任何偏差都可能会导致所有用户的持久团队创建错误。</span><span class="sxs-lookup"><span data-stu-id="6788d-117">Any deviation in the sequence can result in persistent team creation errors for all users.</span></span> <span data-ttu-id="6788d-118">因此，在 <a href="#createpublishlabels">创建和发布标签</a>、 <a href="#modifydeletelabels">修改和删除已发布标签</a>以及 <a href="#manageerrors">管理团队创建错误</a>时，执行以下操作非常重要。</span><span class="sxs-lookup"><span data-stu-id="6788d-118">Therefore, it's critical to do the following when you <a href="#createpublishlabels">create and publish labels</a>, <a href="#modifydeletelabels">modify and delete published labels</a>, and <a href="#manageerrors">manage team creation errors</a>.</span></span>

<span data-ttu-id="6788d-119">**创建和发布标签** <a name="createpublishlabels"> </a></span><span class="sxs-lookup"><span data-stu-id="6788d-119">**Create and publish labels** <a name="createpublishlabels"> </a></span></span>

<span data-ttu-id="6788d-120">在安全 & 合规中心创建和发布标签时，该标签最多可能需要10分钟才能使标签在团队创建界面中变为可见。</span><span class="sxs-lookup"><span data-stu-id="6788d-120">When a label is created and published in the Security & Compliance Center, it can take up to 10 minutes for the label to become visible in the teams creation interface.</span></span> <span data-ttu-id="6788d-121">使用以下步骤为租户中的所有用户发布标签：</span><span class="sxs-lookup"><span data-stu-id="6788d-121">Use the following steps to publish the label for all users in the tenant:</span></span>
1. <span data-ttu-id="6788d-122">创建标签并将其发布到租户中的几个选择用户帐户。</span><span class="sxs-lookup"><span data-stu-id="6788d-122">Create the label and publish it for a few select user accounts in the tenant.</span></span>
2. <span data-ttu-id="6788d-123">当标签已发布时，请等待10分钟。</span><span class="sxs-lookup"><span data-stu-id="6788d-123">When the label is published, wait 10 minutes.</span></span>
3. <span data-ttu-id="6788d-124">10分钟后，请尝试使用有权访问标签的用户帐户创建带有标签的团队。</span><span class="sxs-lookup"><span data-stu-id="6788d-124">After 10 minutes, try to create a team with the label using one of the user accounts that have access to the label.</span></span>
4. <span data-ttu-id="6788d-125">如果团队在步骤3中成功创建，则继续并为租户中的其余用户发布标签。</span><span class="sxs-lookup"><span data-stu-id="6788d-125">If the team successfully created in step 3, then go ahead and publish the label for the remaining users in the tenant.</span></span>

<span data-ttu-id="6788d-126">**修改和删除已发布的标签** <a name="modifydeletelabels"> </a></span><span class="sxs-lookup"><span data-stu-id="6788d-126">**Modify and delete published labels** <a name="modifydeletelabels"> </a></span></span>

<span data-ttu-id="6788d-127">删除或修改与灵敏度策略相关联的标签可能会导致整个租户中的团队创建失败。</span><span class="sxs-lookup"><span data-stu-id="6788d-127">Deleting or modifying the label while it's associated with sensitivity policies can result in team creation failures across the tenant.</span></span> <span data-ttu-id="6788d-128">因此，在删除或修改标签之前，必须首先解除标签与其关联的策略的关联。</span><span class="sxs-lookup"><span data-stu-id="6788d-128">Therefore, before you delete or modify a label, you must first disassociate the label from its associated policies.</span></span> <span data-ttu-id="6788d-129">使用以下步骤</span><span class="sxs-lookup"><span data-stu-id="6788d-129">Use the following steps</span></span>  
<span data-ttu-id="6788d-130">要删除或修改标签，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6788d-130">to delete or modify a label:</span></span>
1. <span data-ttu-id="6788d-131">从使用该标签的所有策略中删除标签。</span><span class="sxs-lookup"><span data-stu-id="6788d-131">Remove the label from all policies that use the label.</span></span> <span data-ttu-id="6788d-132">或者，也可以删除策略本身。</span><span class="sxs-lookup"><span data-stu-id="6788d-132">Alternatively, you can also delete the policies themselves.</span></span>
2. <span data-ttu-id="6788d-133">当从策略中删除标签或策略本身被删除时，请等待10分钟后再继续。</span><span class="sxs-lookup"><span data-stu-id="6788d-133">When the label is removed from the policies or the policies themselves are deleted, wait 10 minutes before proceeding further.</span></span>
3. <span data-ttu-id="6788d-134">10分钟后，启动团队创建界面并确保该标签对于租户中的任何用户不再可见。</span><span class="sxs-lookup"><span data-stu-id="6788d-134">After 10 minutes, launch the team creation interface and ensure that the label is no longer visible for any user in the tenant.</span></span>
4. <span data-ttu-id="6788d-135">现在，您可以安全地删除或修改标签。</span><span class="sxs-lookup"><span data-stu-id="6788d-135">Now you can safely delete or modify the label.</span></span>

<span data-ttu-id="6788d-136">**管理团队创建错误** <a name="manageerrors"> </a></span><span class="sxs-lookup"><span data-stu-id="6788d-136">**Manage team creation errors** <a name="manageerrors"> </a></span></span>

<span data-ttu-id="6788d-137">如果团队创建在公共预览版中的任何时候开始失败，您有两种选择：</span><span class="sxs-lookup"><span data-stu-id="6788d-137">If team creation begins to fail at any point during the public preview, you have two options:</span></span>
 - <span data-ttu-id="6788d-138">确保在创建团队期间对任何用户不强制使用灵敏度标签。</span><span class="sxs-lookup"><span data-stu-id="6788d-138">Ensure that sensitivity labels are not mandatory for any user during team creation.</span></span>
 - <span data-ttu-id="6788d-139">使用 " [启用此预览](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#enable-this-preview)" 中的脚本关闭灵敏度标签。</span><span class="sxs-lookup"><span data-stu-id="6788d-139">Turn off sensitivity labels using the scripts in [Enable this preview](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#enable-this-preview).</span></span>

<span data-ttu-id="6788d-140">请注意，EnableMIPLabels 设置必须设置为 false，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6788d-140">Note that the EnableMIPLabels setting must be set to false as follows:</span></span>

```console
$setting["EnableMIPLabels"] = "False"
```

## <a name="using-sensitivity-labels-with-teams"></a><span data-ttu-id="6788d-141">将灵敏度标签与团队配合使用</span><span class="sxs-lookup"><span data-stu-id="6788d-141">Using sensitivity labels with Teams</span></span>

<span data-ttu-id="6788d-142">下面是一些有关如何将敏感度标签与组织中的团队配合使用的示例方案。</span><span class="sxs-lookup"><span data-stu-id="6788d-142">Here are some example scenarios of how you can use sensitivity labels with Teams in your organization.</span></span>

### <a name="privacy-setting-of-teams"></a><span data-ttu-id="6788d-143">团队的隐私设置</span><span class="sxs-lookup"><span data-stu-id="6788d-143">Privacy setting of teams</span></span>

<span data-ttu-id="6788d-144">你可以创建在团队创建期间应用的敏感度标签，以允许用户使用特定隐私 (公共或专用) 设置创建团队。</span><span class="sxs-lookup"><span data-stu-id="6788d-144">You can create a sensitivity label that, when applied during team creation, allows users to create teams with a specific privacy (public or private) setting.</span></span>

<span data-ttu-id="6788d-145">例如，在安全 & 合规中心创建名为 "保密" 的标签，并配置团队，以便使用此标签创建的任何团队都必须是专用团队。</span><span class="sxs-lookup"><span data-stu-id="6788d-145">For example, you create a label named “Confidential” in the Security & Compliance Center and you configure Teams so that any team that's created with this label must be a private team.</span></span> <span data-ttu-id="6788d-146">当用户创建新团队并选择 " **机密** " 标签时，用户可用的唯一隐私选项是 " **专用**"。</span><span class="sxs-lookup"><span data-stu-id="6788d-146">When a user creates a new team and selects the **Confidential** label, the only privacy option that's available to the user is **Private**.</span></span> <span data-ttu-id="6788d-147">用户已禁用其他隐私选项，如公共和组织范围。</span><span class="sxs-lookup"><span data-stu-id="6788d-147">Other privacy options such as Public and Org-wide are disabled for the user.</span></span>

![机密敏感度标签的屏幕截图](media/sensitivity-labels-confidential-example.png)

<span data-ttu-id="6788d-149">同样，如果用户在创建新团队时选择 " **常规** "，则他们只能创建公共团队或组织级团队。</span><span class="sxs-lookup"><span data-stu-id="6788d-149">Similarly, if the user selects **General** when they create a new team, they can only create public or org-wide teams.</span></span>

![常规灵敏度标签的屏幕截图](media/sensitivity-labels-general-example.png)

<span data-ttu-id="6788d-151">创建团队时，灵敏度标签显示在团队频道的右上角。</span><span class="sxs-lookup"><span data-stu-id="6788d-151">When the team is created, the sensitivity label is visible in the upper-right corner of channels in the team.</span></span>

![团队频道中灵敏度标签的屏幕截图](media/sensitivity-labels-channel.png)

<span data-ttu-id="6788d-153">团队所有者可以随时更改团队的敏感度标签和隐私设置，方法是转到团队，然后单击 " **编辑团队**"。</span><span class="sxs-lookup"><span data-stu-id="6788d-153">A team owner can change the sensitivity label and the privacy setting of the team at any time by going to the team, and then clicking **Edit team**.</span></span>

![团队频道中灵敏度标签的屏幕截图](media/sensitivity-labels-edit-team.png)

### <a name="guest-access-to-teams"></a><span data-ttu-id="6788d-155">对团队的来宾访问</span><span class="sxs-lookup"><span data-stu-id="6788d-155">Guest access to teams</span></span>

<span data-ttu-id="6788d-156">你可以指定使用特定标签创建的团队是否允许来宾访问。</span><span class="sxs-lookup"><span data-stu-id="6788d-156">You can specify whether a team created with a specific label allows guest access.</span></span> <span data-ttu-id="6788d-157">使用不允许来宾访问的标签创建的团队仅对您的组织中的用户可用。</span><span class="sxs-lookup"><span data-stu-id="6788d-157">Teams created with a label that doesn't allow guest access are only available to users in your organization.</span></span> <span data-ttu-id="6788d-158">无法将组织外部的人员添加到团队。</span><span class="sxs-lookup"><span data-stu-id="6788d-158">People outside your organization can't be added to the team.</span></span>

### <a name="sensitivity-labels-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="6788d-159">Microsoft 团队管理中心中的敏感度标签</span><span class="sxs-lookup"><span data-stu-id="6788d-159">Sensitivity labels in the Microsoft Teams admin center</span></span>

<span data-ttu-id="6788d-160">在 Microsoft 团队管理中心创建或编辑团队时，可以设置敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="6788d-160">You can set sensitivity labels when you create or edit a team in the Microsoft Teams admin center.</span></span> <span data-ttu-id="6788d-161">灵敏度标签还会显示在团队属性和 Microsoft 团队管理中心的 "管理团队" 页面上的 " **分类** " 列中。</span><span class="sxs-lookup"><span data-stu-id="6788d-161">Sensitivity labels are also visible in team properties and in the **Classification** column on the Manage teams page of the Microsoft Teams admin center.</span></span>

## <a name="known-issues"></a><span data-ttu-id="6788d-162">已知问题</span><span class="sxs-lookup"><span data-stu-id="6788d-162">Known issues</span></span>

<span data-ttu-id="6788d-163">**对团队图形 Api、Powershell cmdlet 和模板中的灵敏度标签的支持**</span><span class="sxs-lookup"><span data-stu-id="6788d-163">**Support for sensitivity labels in Teams Graph APIs, Powershell cmdlets and templates**</span></span>

<span data-ttu-id="6788d-164">当前，用户无法对直接通过图形 Api、Powershell cmdlet 和模板创建的团队应用敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="6788d-164">Currently, users won't be able to apply sensitivity labels on teams that are created directly through Graph APIs, Powershell cmdlets, and templates.</span></span>

<span data-ttu-id="6788d-165">**团队教育机构 Sku 中的灵敏度标签支持**</span><span class="sxs-lookup"><span data-stu-id="6788d-165">**Support for sensitivity labels in Teams EDU SKUs**</span></span>

<span data-ttu-id="6788d-166">当前使用团队教育 Sku 的客户不支持灵敏度标签。</span><span class="sxs-lookup"><span data-stu-id="6788d-166">Sensitivity labels are currently unsupported for customers using Teams Education SKUs.</span></span>

<span data-ttu-id="6788d-167">**直接在专用频道的 SharePoint 网站集上编辑灵敏度标签**</span><span class="sxs-lookup"><span data-stu-id="6788d-167">**Editing sensitivity labels directly on a SharePoint site collection for private channels**</span></span>

<span data-ttu-id="6788d-168">在团队中创建的专用频道将继承应用于团队的灵敏度标签。</span><span class="sxs-lookup"><span data-stu-id="6788d-168">Private channels that are created in a team inherit the sensitivity label which was applied on a team.</span></span> <span data-ttu-id="6788d-169">此外，将在专用频道的 SharePoint 网站集上自动应用相同的标签。</span><span class="sxs-lookup"><span data-stu-id="6788d-169">Furthermore, the same label is automatically applied on the SharePoint site collection for the private channel.</span></span>

<span data-ttu-id="6788d-170">如果用户在专用频道的 SharePoint 网站集上直接更新灵敏度标签，则不会在团队客户端中更新该标签。</span><span class="sxs-lookup"><span data-stu-id="6788d-170">If a user directly updates the sensitivity label on a SharePoint site collection for a private channel, that label isn't updated in the Teams client.</span></span> <span data-ttu-id="6788d-171">在这种情况下，用户将继续在专用信道标题中看到团队中应用的灵敏度标签。</span><span class="sxs-lookup"><span data-stu-id="6788d-171">In this scenario, users will continue to see the sensitivity label applied on a team in the private channel header.</span></span>

<span data-ttu-id="6788d-172">**应用于团队应用外的灵敏度标签的更改的传播时间**</span><span class="sxs-lookup"><span data-stu-id="6788d-172">**Propagation times for changes applied to sensitivity labels outside the Teams app**</span></span>

<span data-ttu-id="6788d-173">对 "团队" 应用外的灵敏度标签所做的更改最多需要24小时才能反映在 "团队" 应用中。</span><span class="sxs-lookup"><span data-stu-id="6788d-173">Changes made to sensitivity labels outside the Teams app can take up to 24 hours to reflect in the Teams app.</span></span> <span data-ttu-id="6788d-174">这适用于为租户启用或禁用标签、更改标签名称、设置和策略所做的任何更改。</span><span class="sxs-lookup"><span data-stu-id="6788d-174">This applies to any changes made to enable or disable labels for a tenant, changes to label names, settings, and policies.</span></span>

<span data-ttu-id="6788d-175">此外，直接对支持团队的组或 SharePoint 网站集直接更改标签的任何更改最多可能需要24小时才能传播到团队应用。</span><span class="sxs-lookup"><span data-stu-id="6788d-175">Additionally, any changes to a label made directly to a group or SharePoint site collection that backs the team can take up to 24 hours to propagate to the Teams app.</span></span>
