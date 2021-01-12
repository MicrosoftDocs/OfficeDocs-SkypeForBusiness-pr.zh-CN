---
title: Microsoft Teams 的敏感度标签
ms.author: mikeplum
author: MikePlumleyMSFT
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
description: 了解如何在 Microsoft Teams 中定义和使用敏感度标签。
ms.openlocfilehash: d021954a32cc2d93fb7b17726720396e66b4fd39
ms.sourcegitcommit: b68a7b5100fc2b47ae81f465d48d1ac2348c1744
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2021
ms.locfileid: "49795768"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a><span data-ttu-id="0a787-103">Microsoft Teams 的敏感度标签</span><span class="sxs-lookup"><span data-stu-id="0a787-103">Sensitivity labels for Microsoft Teams</span></span>

<span data-ttu-id="0a787-104">[敏感度标签](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) 允许 Teams 管理员管理对在团队内协作期间创建的敏感组织内容的访问。</span><span class="sxs-lookup"><span data-stu-id="0a787-104">[Sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) allow Teams admins to regulate access to sensitive organizational content created during collaboration within teams.</span></span> <span data-ttu-id="0a787-105">可以在合规性中心定义敏感度标签及其关联的 [策略](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)。</span><span class="sxs-lookup"><span data-stu-id="0a787-105">You can define sensitivity labels and their associated policies in the [Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span></span> <span data-ttu-id="0a787-106">这些标签和策略会自动应用于组织中团队。</span><span class="sxs-lookup"><span data-stu-id="0a787-106">These labels and policies are automatically applied to teams in your organization.</span></span>  

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a><span data-ttu-id="0a787-107">敏感度标签和 Teams 分类标签之间有什么区别？</span><span class="sxs-lookup"><span data-stu-id="0a787-107">What's the difference between sensitivity labels and Teams classification labels?</span></span>

<span data-ttu-id="0a787-108">敏感度标签不同于分类标签。</span><span class="sxs-lookup"><span data-stu-id="0a787-108">Sensitivity labels are different from classification labels.</span></span> <span data-ttu-id="0a787-109">分类标签是可与 Microsoft 365 组关联的文本字符串，但没有任何与之关联的实际策略。</span><span class="sxs-lookup"><span data-stu-id="0a787-109">Classification labels are text strings that can be associated with a Microsoft 365 Group but don't have any actual policies associated with them.</span></span> <span data-ttu-id="0a787-110">使用分类标签作为元数据，通过内部工具和脚本手动强制实施策略。</span><span class="sxs-lookup"><span data-stu-id="0a787-110">You use classification labels as metadata to manually enforce policies through internal tools and scripts.</span></span>

<span data-ttu-id="0a787-111">另一方面，敏感度标签及其策略是通过组平台、安全与合规中心与 Teams 服务的组合&端到端强制实施的。</span><span class="sxs-lookup"><span data-stu-id="0a787-111">On the other hand, sensitivity labels and their policies are automatically enforced end-to-end through a combination of the Groups platform, Security & Compliance Center, and Teams services.</span></span> <span data-ttu-id="0a787-112">敏感度标签提供强大的基础结构支持，用于保护组织的敏感数据。</span><span class="sxs-lookup"><span data-stu-id="0a787-112">Sensitivity labels provide powerful infrastructure support for securing your organization's sensitive data.</span></span>  

<span data-ttu-id="0a787-113">若要将现有组从使用分类标签迁移到使用敏感度标签，请使用 Azure Active [Directory 分类和 Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/migrate-aad-classification-sensitivity-labels)组的敏感度标签中的说明。</span><span class="sxs-lookup"><span data-stu-id="0a787-113">To migrate your existing groups from using classification labels to using sensitivity labels, use the instructions in [Azure Active Directory classification and sensitivity labels for Microsoft 365 groups](https://docs.microsoft.com/microsoft-365/compliance/migrate-aad-classification-sensitivity-labels).</span></span>

## <a name="create-manage-and-publish-sensitivity-labels-for-teams"></a><span data-ttu-id="0a787-114">为 Teams 创建、管理和发布敏感度标签</span><span class="sxs-lookup"><span data-stu-id="0a787-114">Create, manage, and publish sensitivity labels for Teams</span></span>

<span data-ttu-id="0a787-115">若要了解如何为 Teams 启用、创建和发布敏感度标签，请参阅"使用敏感度标签保护 [Microsoft Teams、Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)组和 SharePoint 网站中的内容"。</span><span class="sxs-lookup"><span data-stu-id="0a787-115">For how to enable, create, and publish sensitivity labels for Teams, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

>[!IMPORTANT]
><span data-ttu-id="0a787-116">创建、更新和删除敏感度标签需要谨慎排序，将标签发布给用户。</span><span class="sxs-lookup"><span data-stu-id="0a787-116">Creating, updating and deleting sensitivity labels require careful sequencing with publishing labels to users.</span></span> <span data-ttu-id="0a787-117">序列中出现任何偏差都可能导致所有用户持续出现团队创建错误。</span><span class="sxs-lookup"><span data-stu-id="0a787-117">Any deviation in the sequence can result in persistent team creation errors for all users.</span></span> <span data-ttu-id="0a787-118">因此，创建和发布标签、修改和删除已发布的标签<a href="#createpublishlabels"></a>以及管理团队创建错误时<a href="#modifydeletelabels"></a>，必须<a href="#manageerrors">执行以下操作</a>。</span><span class="sxs-lookup"><span data-stu-id="0a787-118">Therefore, it's critical to do the following when you <a href="#createpublishlabels">create and publish labels</a>, <a href="#modifydeletelabels">modify and delete published labels</a>, and <a href="#manageerrors">manage team creation errors</a>.</span></span>

<span data-ttu-id="0a787-119">**创建和发布标签**<a name="createpublishlabels"></a></span><span class="sxs-lookup"><span data-stu-id="0a787-119">**Create and publish labels** <a name="createpublishlabels"> </a></span></span>

<span data-ttu-id="0a787-120">在合规性中心中创建和发布标签时，可能需要 10 分钟才能在团队创建界面中显示该标签。</span><span class="sxs-lookup"><span data-stu-id="0a787-120">When a label is created and published in the Compliance Center, it can take up to 10 minutes for the label to become visible in the teams creation interface.</span></span> <span data-ttu-id="0a787-121">使用以下步骤发布租户中所有用户的标签：</span><span class="sxs-lookup"><span data-stu-id="0a787-121">Use the following steps to publish the label for all users in the tenant:</span></span>
1. <span data-ttu-id="0a787-122">创建标签，并针对租户中的几个选定用户帐户发布该标签。</span><span class="sxs-lookup"><span data-stu-id="0a787-122">Create the label and publish it for a few select user accounts in the tenant.</span></span>
2. <span data-ttu-id="0a787-123">发布标签后，请等待 10 分钟。</span><span class="sxs-lookup"><span data-stu-id="0a787-123">When the label is published, wait 10 minutes.</span></span>
3. <span data-ttu-id="0a787-124">10 分钟后，尝试使用有权访问标签的用户帐户之一创建具有标签的团队。</span><span class="sxs-lookup"><span data-stu-id="0a787-124">After 10 minutes, try to create a team with the label using one of the user accounts that have access to the label.</span></span>
4. <span data-ttu-id="0a787-125">如果团队在步骤 3 中成功创建，则继续操作并发布租户中其余用户的标签。</span><span class="sxs-lookup"><span data-stu-id="0a787-125">If the team successfully created in step 3, then go ahead and publish the label for the remaining users in the tenant.</span></span>

<span data-ttu-id="0a787-126">**修改和删除已发布的标签**<a name="modifydeletelabels"></a></span><span class="sxs-lookup"><span data-stu-id="0a787-126">**Modify and delete published labels** <a name="modifydeletelabels"> </a></span></span>

<span data-ttu-id="0a787-127">在标签与敏感度策略关联时删除或修改标签可能会导致整个租户的团队创建失败。</span><span class="sxs-lookup"><span data-stu-id="0a787-127">Deleting or modifying the label while it's associated with sensitivity policies can result in team creation failures across the tenant.</span></span> <span data-ttu-id="0a787-128">因此，在删除或修改标签之前，必须先取消标签与其关联策略的关联。</span><span class="sxs-lookup"><span data-stu-id="0a787-128">Therefore, before you delete or modify a label, you must first disassociate the label from its associated policies.</span></span> <span data-ttu-id="0a787-129">使用以下步骤</span><span class="sxs-lookup"><span data-stu-id="0a787-129">Use the following steps</span></span>  
<span data-ttu-id="0a787-130">删除或修改标签：</span><span class="sxs-lookup"><span data-stu-id="0a787-130">to delete or modify a label:</span></span>
1. <span data-ttu-id="0a787-131">从使用该标签的所有策略中删除标签。</span><span class="sxs-lookup"><span data-stu-id="0a787-131">Remove the label from all policies that use the label.</span></span> <span data-ttu-id="0a787-132">或者，也可以删除策略本身。</span><span class="sxs-lookup"><span data-stu-id="0a787-132">Alternatively, you can also delete the policies themselves.</span></span>
2. <span data-ttu-id="0a787-133">从策略中删除标签或删除策略本身时，请等待 10 分钟，然后继续下一步。</span><span class="sxs-lookup"><span data-stu-id="0a787-133">When the label is removed from the policies or the policies themselves are deleted, wait 10 minutes before proceeding further.</span></span>
3. <span data-ttu-id="0a787-134">10 分钟后，启动团队创建界面，并确保该标签不再对租户中任何用户可见。</span><span class="sxs-lookup"><span data-stu-id="0a787-134">After 10 minutes, launch the team creation interface and ensure that the label is no longer visible for any user in the tenant.</span></span>
4. <span data-ttu-id="0a787-135">现在，可以安全地删除或修改标签。</span><span class="sxs-lookup"><span data-stu-id="0a787-135">Now you can safely delete or modify the label.</span></span>

<span data-ttu-id="0a787-136">**管理团队创建错误**<a name="manageerrors"></a></span><span class="sxs-lookup"><span data-stu-id="0a787-136">**Manage team creation errors** <a name="manageerrors"> </a></span></span>

<span data-ttu-id="0a787-137">如果团队创建在公共预览版期间的任何时间点开始失败，有两个选项：</span><span class="sxs-lookup"><span data-stu-id="0a787-137">If team creation begins to fail at any point during the public preview, you have two options:</span></span>
 - <span data-ttu-id="0a787-138">确保在创建团队期间，任何用户都不需要使用敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="0a787-138">Ensure that sensitivity labels are not mandatory for any user during team creation.</span></span>
 - <span data-ttu-id="0a787-139">使用"启用此预览"中的脚本 [关闭敏感度标签](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#enable-this-preview)。</span><span class="sxs-lookup"><span data-stu-id="0a787-139">Turn off sensitivity labels using the scripts in [Enable this preview](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#enable-this-preview).</span></span>

<span data-ttu-id="0a787-140">请注意，EnableMIPLabels 设置必须设置为 false，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0a787-140">Note that the EnableMIPLabels setting must be set to false as follows:</span></span>

```console
$setting["EnableMIPLabels"] = "False"
```

## <a name="using-sensitivity-labels-with-teams"></a><span data-ttu-id="0a787-141">将敏感度标签与 Teams 一起使用</span><span class="sxs-lookup"><span data-stu-id="0a787-141">Using sensitivity labels with Teams</span></span>

<span data-ttu-id="0a787-142">下面是一些示例方案，演示了如何在组织中将敏感度标签与 Teams 一同使用。</span><span class="sxs-lookup"><span data-stu-id="0a787-142">Here are some example scenarios of how you can use sensitivity labels with Teams in your organization.</span></span>

### <a name="privacy-setting-of-teams"></a><span data-ttu-id="0a787-143">团队的隐私设置</span><span class="sxs-lookup"><span data-stu-id="0a787-143">Privacy setting of teams</span></span>

<span data-ttu-id="0a787-144">你可以创建一个敏感度标签，在团队创建期间应用该标签时，允许用户创建具有特定隐私性 (公共或专用) 设置。</span><span class="sxs-lookup"><span data-stu-id="0a787-144">You can create a sensitivity label that, when applied during team creation, allows users to create teams with a specific privacy (public or private) setting.</span></span>

<span data-ttu-id="0a787-145">例如，在安全中心创建名为"机密"的标签&配置 Teams，以便使用此标签创建的任何团队都必须是专用团队。</span><span class="sxs-lookup"><span data-stu-id="0a787-145">For example, you create a label named “Confidential” in the Security & Compliance Center and you configure Teams so that any team that's created with this label must be a private team.</span></span> <span data-ttu-id="0a787-146">当用户创建新团队并选择"机密"标签时，可供用户使用的唯一隐私选项是 **"专用"。**</span><span class="sxs-lookup"><span data-stu-id="0a787-146">When a user creates a new team and selects the **Confidential** label, the only privacy option that's available to the user is **Private**.</span></span> <span data-ttu-id="0a787-147">用户禁用了其他隐私选项，例如"公共"和"组织范围"。</span><span class="sxs-lookup"><span data-stu-id="0a787-147">Other privacy options such as Public and Org-wide are disabled for the user.</span></span>

![机密敏感度标签的屏幕截图](media/sensitivity-labels-confidential-example.png)

<span data-ttu-id="0a787-149">同样，如果用户在创建新 **团队时选择了** "常规"，则他们只能创建公共团队或组织范围的团队。</span><span class="sxs-lookup"><span data-stu-id="0a787-149">Similarly, if the user selects **General** when they create a new team, they can only create public or org-wide teams.</span></span>

![常规敏感度标签的屏幕截图](media/sensitivity-labels-general-example.png)

<span data-ttu-id="0a787-151">创建团队后，敏感度标签显示在团队中频道的右上角。</span><span class="sxs-lookup"><span data-stu-id="0a787-151">When the team is created, the sensitivity label is visible in the upper-right corner of channels in the team.</span></span>

![团队频道中敏感度标签的屏幕截图](media/sensitivity-labels-channel.png)

<span data-ttu-id="0a787-153">团队所有者可以通过访问团队，然后单击"编辑团队"随时更改该团队的敏感度标签和 **隐私设置**。</span><span class="sxs-lookup"><span data-stu-id="0a787-153">A team owner can change the sensitivity label and the privacy setting of the team at any time by going to the team, and then clicking **Edit team**.</span></span>

![团队属性中敏感度标签的屏幕截图](media/sensitivity-labels-edit-team.png)

### <a name="guest-access-to-teams"></a><span data-ttu-id="0a787-155">团队的来宾访问权限</span><span class="sxs-lookup"><span data-stu-id="0a787-155">Guest access to teams</span></span>

<span data-ttu-id="0a787-156">可以指定使用特定标签创建的团队是否允许来宾访问。</span><span class="sxs-lookup"><span data-stu-id="0a787-156">You can specify whether a team created with a specific label allows guest access.</span></span> <span data-ttu-id="0a787-157">使用不允许来宾访问的标签创建的团队仅适用于您的组织中的用户。</span><span class="sxs-lookup"><span data-stu-id="0a787-157">Teams created with a label that doesn't allow guest access are only available to users in your organization.</span></span> <span data-ttu-id="0a787-158">不能将组织外部人员添加到团队。</span><span class="sxs-lookup"><span data-stu-id="0a787-158">People outside your organization can't be added to the team.</span></span>

### <a name="sensitivity-labels-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="0a787-159">Microsoft Teams 管理中心中的敏感度标签</span><span class="sxs-lookup"><span data-stu-id="0a787-159">Sensitivity labels in the Microsoft Teams admin center</span></span>

<span data-ttu-id="0a787-160">可以在 Microsoft Teams 管理中心创建或编辑团队时设置敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="0a787-160">You can set sensitivity labels when you create or edit a team in the Microsoft Teams admin center.</span></span> <span data-ttu-id="0a787-161">敏感度标签在团队属性和 Microsoft Teams 管理中心的"管理团队"页面上的"分类"列中也可见。</span><span class="sxs-lookup"><span data-stu-id="0a787-161">Sensitivity labels are also visible in team properties and in the **Classification** column on the Manage teams page of the Microsoft Teams admin center.</span></span>

## <a name="known-issues"></a><span data-ttu-id="0a787-162">已知问题</span><span class="sxs-lookup"><span data-stu-id="0a787-162">Known issues</span></span>

<span data-ttu-id="0a787-163">**支持 Teams Graph API、PowerShell cmdlet 和模板中的敏感度标签**</span><span class="sxs-lookup"><span data-stu-id="0a787-163">**Support for sensitivity labels in Teams Graph APIs, PowerShell cmdlets and templates**</span></span>

<span data-ttu-id="0a787-164">目前，用户无法对通过图形 API、PowerShell cmdlet 和模板直接创建的团队应用敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="0a787-164">Currently, users won't be able to apply sensitivity labels on teams that are created directly through Graph APIs, PowerShell cmdlets, and templates.</span></span>

<span data-ttu-id="0a787-165">**支持 Teams EDU SU 中的敏感度标签**</span><span class="sxs-lookup"><span data-stu-id="0a787-165">**Support for sensitivity labels in Teams EDU SKUs**</span></span>

<span data-ttu-id="0a787-166">使用 Teams 教育 SK 的客户提供敏感度标签目前不受支持。</span><span class="sxs-lookup"><span data-stu-id="0a787-166">Sensitivity labels are currently unsupported for customers using Teams Education SKUs.</span></span>

<span data-ttu-id="0a787-167">**直接在 SharePoint 网站集上编辑专用频道的敏感度标签**</span><span class="sxs-lookup"><span data-stu-id="0a787-167">**Editing sensitivity labels directly on a SharePoint site collection for private channels**</span></span>

<span data-ttu-id="0a787-168">在团队中创建的专用频道将继承应用于团队的敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="0a787-168">Private channels that are created in a team inherit the sensitivity label which was applied on a team.</span></span> <span data-ttu-id="0a787-169">此外，同一标签会自动应用于专用频道的 SharePoint 网站集。</span><span class="sxs-lookup"><span data-stu-id="0a787-169">Furthermore, the same label is automatically applied on the SharePoint site collection for the private channel.</span></span>

<span data-ttu-id="0a787-170">如果用户直接更新专用频道的 SharePoint 网站集上的敏感度标签，该标签不会在 Teams 客户端中更新。</span><span class="sxs-lookup"><span data-stu-id="0a787-170">If a user directly updates the sensitivity label on a SharePoint site collection for a private channel, that label isn't updated in the Teams client.</span></span> <span data-ttu-id="0a787-171">在此方案中，用户将继续在专用频道标题中看到应用于团队的敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="0a787-171">In this scenario, users will continue to see the sensitivity label applied on a team in the private channel header.</span></span>

<span data-ttu-id="0a787-172">**应用于 Teams 应用外部敏感度标签的更改传播时间**</span><span class="sxs-lookup"><span data-stu-id="0a787-172">**Propagation times for changes applied to sensitivity labels outside the Teams app**</span></span>

<span data-ttu-id="0a787-173">在 Teams 应用外部对敏感度标签所做的更改最多可能需要 24 小时才能反映在 Teams 应用中。</span><span class="sxs-lookup"><span data-stu-id="0a787-173">Changes made to sensitivity labels outside the Teams app can take up to 24 hours to reflect in the Teams app.</span></span> <span data-ttu-id="0a787-174">这适用于为租户启用或禁用标签而做出的任何更改、对标签名称、设置和策略的更改。</span><span class="sxs-lookup"><span data-stu-id="0a787-174">This applies to any changes made to enable or disable labels for a tenant, changes to label names, settings, and policies.</span></span>

<span data-ttu-id="0a787-175">此外，对直接对支持团队的组或 SharePoint 网站集的标签进行的任何更改最多可能需要 24 小时才能传播到 Teams 应用。</span><span class="sxs-lookup"><span data-stu-id="0a787-175">Additionally, any changes to a label made directly to a group or SharePoint site collection that backs the team can take up to 24 hours to propagate to the Teams app.</span></span>
