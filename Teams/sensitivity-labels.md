---
title: Microsoft Teams 的敏感度标签
ms.author: mikeplum
author: cabailey
manager: laurawi
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
description: 了解如何使用敏感度标签在 Microsoft Teams 中保护团队。
ms.openlocfilehash: 6929e9c51f35cb4483c81323048b2a1f9ec6243a
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/18/2021
ms.locfileid: "50875102"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a><span data-ttu-id="864ef-103">Microsoft Teams 的敏感度标签</span><span class="sxs-lookup"><span data-stu-id="864ef-103">Sensitivity labels for Microsoft Teams</span></span>

<span data-ttu-id="864ef-104">[敏感度标签](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) 允许 Teams 管理员保护和管理对在团队内协作期间创建的敏感组织内容的访问。</span><span class="sxs-lookup"><span data-stu-id="864ef-104">[Sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) allow Teams admins to protect and regulate access to sensitive organizational content created during collaboration within teams.</span></span> <span data-ttu-id="864ef-105">在 [Microsoft](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)合规性中心中配置敏感度标签及其关联策略后，这些标签可以应用于组织的团队。</span><span class="sxs-lookup"><span data-stu-id="864ef-105">After you configure sensitivity labels with their associated policies in the [Microsoft compliance center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center), these labels can be applied to teams in your organization.</span></span>

<span data-ttu-id="864ef-106">使用 Teams 教育 SKUS 的客户目前不支持敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="864ef-106">Sensitivity labels are currently unsupported for customers using Teams Education SKUs.</span></span> <span data-ttu-id="864ef-107">若要详细了解许可，请参阅 Microsoft [Teams 服务说明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)。</span><span class="sxs-lookup"><span data-stu-id="864ef-107">To learn more about licensing, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a><span data-ttu-id="864ef-108">敏感度标签和 Teams 分类标签之间有什么区别？</span><span class="sxs-lookup"><span data-stu-id="864ef-108">What's the difference between sensitivity labels and Teams classification labels?</span></span>

<span data-ttu-id="864ef-109">敏感度标签不同于分类标签，也称为 Azure AD 组分类。</span><span class="sxs-lookup"><span data-stu-id="864ef-109">Sensitivity labels are different from classification labels, also known as Azure AD group classification.</span></span> <span data-ttu-id="864ef-110">分类标签是可与 Microsoft 365 组关联的文本字符串，但没有任何与之关联的实际策略。</span><span class="sxs-lookup"><span data-stu-id="864ef-110">Classification labels are text strings that can be associated with a Microsoft 365 group but don't have any actual policies associated with them.</span></span> <span data-ttu-id="864ef-111">使用分类标签作为元数据，然后必须使用其他方法（例如内部工具和脚本）来强制实施策略。</span><span class="sxs-lookup"><span data-stu-id="864ef-111">You use classification labels as metadata and then must use other methods such as internal tools and scripts, to enforce policies.</span></span>

<span data-ttu-id="864ef-112">使用敏感度标签的好处是，通过 Microsoft 365 组平台、合规性中心和 Teams 服务的组合，自动端到端地强制实施其策略。</span><span class="sxs-lookup"><span data-stu-id="864ef-112">The benefit of using sensitivity labels is that their policies are automatically enforced end-to-end through a combination of the Microsoft 365 Groups platform, the compliance center, and Teams services.</span></span> <span data-ttu-id="864ef-113">敏感度标签提供强大的基础结构支持，用于保护组织的敏感数据并确保符合内部策略或法规。</span><span class="sxs-lookup"><span data-stu-id="864ef-113">Sensitivity labels provide powerful infrastructure support for securing your organization's sensitive data and ensuring compliance with your internal policies or regulations.</span></span>

<span data-ttu-id="864ef-114">如果当前使用分类标签，请参阅以下文档，详细了解如何将它们迁移到敏感度标签： [经典 Azure AD 组分类](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification)。</span><span class="sxs-lookup"><span data-stu-id="864ef-114">If you currently use classification labels, see the following documentation for more information and instructions how to migrate them to sensitivity labels: [Classic Azure AD group classification](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification).</span></span>

## <a name="example-scenarios-for-sensitivity-labels"></a><span data-ttu-id="864ef-115">敏感度标签的示例方案</span><span class="sxs-lookup"><span data-stu-id="864ef-115">Example scenarios for sensitivity labels</span></span>

<span data-ttu-id="864ef-116">如何对组织中 Teams 使用敏感度标签的示例方案：</span><span class="sxs-lookup"><span data-stu-id="864ef-116">Example scenarios for how you can use sensitivity labels with Teams in your organization:</span></span>

- [<span data-ttu-id="864ef-117">为团队设置 (隐私级别) 隐私级别</span><span class="sxs-lookup"><span data-stu-id="864ef-117">Set the privacy level (public or private) for teams</span></span>](#set-the-privacy-level-for-teams)
- [<span data-ttu-id="864ef-118">控制来宾对团队的访问</span><span class="sxs-lookup"><span data-stu-id="864ef-118">Control guest access to teams</span></span>](#control-guest-access-to-teams)

### <a name="set-the-privacy-level-for-teams"></a><span data-ttu-id="864ef-119">设置团队的隐私级别</span><span class="sxs-lookup"><span data-stu-id="864ef-119">Set the privacy level for teams</span></span>

<span data-ttu-id="864ef-120">可以创建和配置敏感度标签，在团队创建期间应用该标签时，允许用户创建具有特定隐私性 (公共或) 设置。</span><span class="sxs-lookup"><span data-stu-id="864ef-120">You can create and configure a sensitivity label that, when applied during team creation, allows users to create teams with a specific privacy (public or private) setting.</span></span>

<span data-ttu-id="864ef-121">例如，创建并发布名为"机密"的敏感度标签，该标签隐私选项配置为"私密 **"。**</span><span class="sxs-lookup"><span data-stu-id="864ef-121">For example, you create and publish a sensitivity label named "Confidential" that has the label privacy option configured as **Private**.</span></span> <span data-ttu-id="864ef-122">因此，使用此标签创建的任何团队都必须是专用团队。</span><span class="sxs-lookup"><span data-stu-id="864ef-122">As a result, any team that's created with this label must be a private team.</span></span> 

<span data-ttu-id="864ef-123">当用户创建新团队并选择"机密"标签时，可供用户使用的唯一隐私选项是"专用 **"。**</span><span class="sxs-lookup"><span data-stu-id="864ef-123">When a user creates a new team and selects the **Confidential** label, the only privacy option that's available to the user is **Private**.</span></span> <span data-ttu-id="864ef-124">用户无法选择其他隐私选项，例如"公共"和"组织范围"：</span><span class="sxs-lookup"><span data-stu-id="864ef-124">Other privacy options such as Public and Org-wide aren't available for the user to select:</span></span>

![机密敏感度标签的屏幕截图](media/sensitivity-labels-confidential-example.png)

<span data-ttu-id="864ef-126">同样，创建并发布名为"常规"的敏感度标签，该标签隐私选项配置为"**公共"。**</span><span class="sxs-lookup"><span data-stu-id="864ef-126">Similarly, you create and publish a sensitivity label named "General" that has the label privacy option configured as **Public**.</span></span> <span data-ttu-id="864ef-127">当用户创建新团队时，他们只能在选择此标签时创建公共团队或组织范围的团队：</span><span class="sxs-lookup"><span data-stu-id="864ef-127">When a user creates a new team, they can only create public or org-wide teams when they select this label:</span></span>

![常规敏感度标签的屏幕截图](media/sensitivity-labels-general-example.png)

<span data-ttu-id="864ef-129">创建团队时，敏感度标签显示在团队中频道的右上角。</span><span class="sxs-lookup"><span data-stu-id="864ef-129">When the team is created, the sensitivity label is visible in the upper-right corner of channels in the team.</span></span> <span data-ttu-id="864ef-130">请注意，如果使用分层父子标签（如"Confidential\Finance"），则频道标头中只会显示父标签。</span><span class="sxs-lookup"><span data-stu-id="864ef-130">Note that if you are using hierarchical parent child labels such as "Confidential\Finance" then only the parent label will be showin the channel header.</span></span>


![团队频道中敏感度标签的屏幕截图](media/sensitivity-labels-channel.png)

<span data-ttu-id="864ef-132">团队所有者可以通过访问团队，然后单击"编辑团队"，随时更改该团队的敏感度标签和 **隐私设置**。</span><span class="sxs-lookup"><span data-stu-id="864ef-132">A team owner can change the sensitivity label and the privacy setting of the team at any time by going to the team, and then click **Edit team**.</span></span>

![团队属性中敏感度标签的屏幕截图](media/sensitivity-labels-edit-team.png)

### <a name="control-guest-access-to-teams"></a><span data-ttu-id="864ef-134">控制来宾对团队的访问</span><span class="sxs-lookup"><span data-stu-id="864ef-134">Control guest access to teams</span></span>

<span data-ttu-id="864ef-135">可以使用敏感度标签来控制来宾对团队的访问。</span><span class="sxs-lookup"><span data-stu-id="864ef-135">You can use sensitivity labels to control guest access to your teams.</span></span> <span data-ttu-id="864ef-136">使用不允许来宾访问的标签创建的团队仅对贵组织的用户可用。</span><span class="sxs-lookup"><span data-stu-id="864ef-136">Teams created with a label that doesn't allow guest access are only available to users in your organization.</span></span> <span data-ttu-id="864ef-137">无法将组织外部人员添加到团队。</span><span class="sxs-lookup"><span data-stu-id="864ef-137">People outside your organization can't be added to the team.</span></span>

## <a name="microsoft-teams-admin-center"></a><span data-ttu-id="864ef-138">Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="864ef-138">Microsoft Teams admin center</span></span>

<span data-ttu-id="864ef-139">在 Microsoft Teams 管理中心创建或编辑团队时，可以应用敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="864ef-139">You can apply sensitivity labels when you create or edit a team in the Microsoft Teams admin center.</span></span> 

<span data-ttu-id="864ef-140">敏感度标签在团队属性和 Microsoft Teams 管理中心的"管理团队 **"** 页面上的"分类"列中也可见。</span><span class="sxs-lookup"><span data-stu-id="864ef-140">Sensitivity labels are also visible in team properties and in the **Classification** column on the **Manage teams** page of the Microsoft Teams admin center.</span></span>

## <a name="limitations"></a><span data-ttu-id="864ef-141">限制</span><span class="sxs-lookup"><span data-stu-id="864ef-141">Limitations</span></span>

<span data-ttu-id="864ef-142">为 Teams 使用敏感度标签之前，请注意以下限制：</span><span class="sxs-lookup"><span data-stu-id="864ef-142">Before you use sensitivity labels for Teams, be aware of the following limitations:</span></span>

- <span data-ttu-id="864ef-143">**子标签不显示父标签名称**</span><span class="sxs-lookup"><span data-stu-id="864ef-143">**Parent label names aren't displayed for sublabels**</span></span>
    
    <span data-ttu-id="864ef-144">Teams 支持子标签，但不显示父标签的名称。</span><span class="sxs-lookup"><span data-stu-id="864ef-144">Teams supports sublabels but doesn't display the name of the parent label.</span></span> <span data-ttu-id="864ef-145">例如，"**机密** \\ **所有员工"** 显示为"**所有员工"。**</span><span class="sxs-lookup"><span data-stu-id="864ef-145">For example, **Confidential** \\ **All Employees** displays as **All Employees**.</span></span>

- <span data-ttu-id="864ef-146">**Teams Graph API、PowerShell cmdlet 和模板不支持敏感度标签**</span><span class="sxs-lookup"><span data-stu-id="864ef-146">**Sensitivity labels aren't supported by Teams Graph APIs, PowerShell cmdlets, and templates**</span></span>
    
    <span data-ttu-id="864ef-147">用户无法对通过 Teams Graph API、Teams PowerShell cmdlet 和 Teams 模板直接创建的团队应用敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="864ef-147">Users won't be able to apply sensitivity labels on teams that are created directly through Teams Graph APIs, Teams PowerShell cmdlets, and Teams templates.</span></span>

- <span data-ttu-id="864ef-148">**支持专用频道**</span><span class="sxs-lookup"><span data-stu-id="864ef-148">**Support for private channels**</span></span>
    
    <span data-ttu-id="864ef-149">在团队中创建的专用频道将继承应用于团队的敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="864ef-149">Private channels that are created in a team inherit the sensitivity label that was applied on a team.</span></span> <span data-ttu-id="864ef-150">该标签会自动应用于专用频道的 SharePoint 网站集。</span><span class="sxs-lookup"><span data-stu-id="864ef-150">The same label is automatically applied on the SharePoint site collection for the private channel.</span></span>
    
    <span data-ttu-id="864ef-151">但是，如果用户直接更改专用频道的 SharePoint 网站上敏感度标签，该标签更改不会反映在 Teams 客户端中。</span><span class="sxs-lookup"><span data-stu-id="864ef-151">However, if a user directly changes the sensitivity label on a SharePoint site for a private channel, that label change isn't reflected in the Teams client.</span></span> <span data-ttu-id="864ef-152">在此方案中，用户继续在专用频道标题中看到应用于团队的原始敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="864ef-152">In this scenario, users continue to see the original sensitivity label applied on the team in the private channel header.</span></span>

## <a name="how-to-create-and-configure-sensitivity-labels-for-teams"></a><span data-ttu-id="864ef-153">如何为 Teams 创建和配置敏感度标签</span><span class="sxs-lookup"><span data-stu-id="864ef-153">How to create and configure sensitivity labels for Teams</span></span>

<span data-ttu-id="864ef-154">使用 Microsoft 365 文档中的说明为 Teams 创建和配置敏感度标签：</span><span class="sxs-lookup"><span data-stu-id="864ef-154">Use the instructions from the Microsoft 365 documentation to create and configure sensitivity labels for Teams:</span></span> 

- <span data-ttu-id="864ef-155">[使用敏感度标签保护 Microsoft Teams、Microsoft 365 组和 SharePoint 网站中的内容](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)。</span><span class="sxs-lookup"><span data-stu-id="864ef-155">[Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>
