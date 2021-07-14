---
title: 自定义应用中Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: v-tbasra
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何在应用中自定义Microsoft Teams。
ms.openlocfilehash: e2a217648abbcec4075e942b303542621f7d317a
ms.sourcegitcommit: f3e9989cbcc2f9f83ff94204bdd75b1e6ad43b5e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/13/2021
ms.locfileid: "53408741"
---
# <a name="customize-apps-in-microsoft-teams"></a><span data-ttu-id="19c72-103">自定义应用中Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="19c72-103">Customize apps in Microsoft Teams</span></span>

 <span data-ttu-id="19c72-104">Microsoft Teams提供应用自定义，以增强Teams体验。</span><span class="sxs-lookup"><span data-stu-id="19c72-104">Microsoft Teams provides app customization to enhance the Teams experience.</span></span> <span data-ttu-id="19c72-105">某些应用开发人员允许由管理员自定义Teams应用。管理员可以使用管理中心"管理应用"页，根据组织需求自定义或Teams **品牌**。</span><span class="sxs-lookup"><span data-stu-id="19c72-105">Some app developers allow an app to be customized by the Teams admin. The admin can customize or rebrand the app properties based on the organizational needs using the Teams admin center **Manage apps** page.</span></span> <span data-ttu-id="19c72-106">可以自定义的详细信息包括：</span><span class="sxs-lookup"><span data-stu-id="19c72-106">The details you can customize are:</span></span>

- <span data-ttu-id="19c72-107">短名称</span><span class="sxs-lookup"><span data-stu-id="19c72-107">Short name</span></span>
- <span data-ttu-id="19c72-108">简短说明</span><span class="sxs-lookup"><span data-stu-id="19c72-108">Short description</span></span>
- <span data-ttu-id="19c72-109">完整说明</span><span class="sxs-lookup"><span data-stu-id="19c72-109">Full description</span></span>
- <span data-ttu-id="19c72-110">隐私策略 URL</span><span class="sxs-lookup"><span data-stu-id="19c72-110">Privacy policy URL</span></span>
- <span data-ttu-id="19c72-111">网站 URL</span><span class="sxs-lookup"><span data-stu-id="19c72-111">Website URL</span></span>
- <span data-ttu-id="19c72-112">使用条款 URL</span><span class="sxs-lookup"><span data-stu-id="19c72-112">Terms of use URL</span></span>
- <span data-ttu-id="19c72-113">颜色图标</span><span class="sxs-lookup"><span data-stu-id="19c72-113">Color icon</span></span>
- <span data-ttu-id="19c72-114">"大纲"图标</span><span class="sxs-lookup"><span data-stu-id="19c72-114">Outline icon</span></span>
- <span data-ttu-id="19c72-115">主题色</span><span class="sxs-lookup"><span data-stu-id="19c72-115">Accent color</span></span>

<span data-ttu-id="19c72-116">有关[可Teams](/microsoftteams/platform/resources/schema/manifest-schema)字段的详细信息，请参阅清单架构。</span><span class="sxs-lookup"><span data-stu-id="19c72-116">See the [Teams Manifest schema](/microsoftteams/platform/resources/schema/manifest-schema) for details about the fields that you can customize.</span></span>

> [!NOTE]
> <span data-ttu-id="19c72-117">目前，政府社区云高 (GCCH) 或国防部 (DoD) 不支持自定义应用。</span><span class="sxs-lookup"><span data-stu-id="19c72-117">Customizing apps isn't supported in Government Community Cloud High (GCCH) or Department of Defense (DoD) at this time.</span></span>
> <span data-ttu-id="19c72-118">目前，此功能不适用于旁加载Microsoft Teams应用。</span><span class="sxs-lookup"><span data-stu-id="19c72-118">Currently, this feature is not available for sideloaded Microsoft Teams apps.</span></span>

## <a name="customize-the-apps-details"></a><span data-ttu-id="19c72-119">自定义应用的详细信息</span><span class="sxs-lookup"><span data-stu-id="19c72-119">Customize the app's details</span></span>

<span data-ttu-id="19c72-120">若要开始自定义应用，请完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="19c72-120">To start customizing an app, complete the following steps:</span></span>

1. <span data-ttu-id="19c72-121">登录到 Teams 管理中心。</span><span class="sxs-lookup"><span data-stu-id="19c72-121">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="19c72-122">展开 **Teams应用"，** 然后选择"**管理应用"。**</span><span class="sxs-lookup"><span data-stu-id="19c72-122">Expand **Teams Apps** and select **Manage apps**.</span></span>
3. <span data-ttu-id="19c72-123">检查 **应用列表** 的"可自定义"列，并按可自定义的应用进行排序。</span><span class="sxs-lookup"><span data-stu-id="19c72-123">Check the **Customizable** column of the apps list and sort by apps that are customizable.</span></span>

   ![已排序的自定义列](media/customize-column.png)

   <span data-ttu-id="19c72-125">有三个入口点可以访问自定义功能：</span><span class="sxs-lookup"><span data-stu-id="19c72-125">There are three entry points to access the customize feature:</span></span>

   - <span data-ttu-id="19c72-126">选择要自定义的应用旁边的 ，然后选择"自定义 **"。**</span><span class="sxs-lookup"><span data-stu-id="19c72-126">Select next to the app that you want to customize, and then select **Customize**.</span></span>

     ![自定义选择选项 1](media/select-app-to-customize1.png)

   - <span data-ttu-id="19c72-128">选择应用名称，然后选择"可 **自定义"。**</span><span class="sxs-lookup"><span data-stu-id="19c72-128">Select the app name and then **Customizable**.</span></span>

     ![自定义选择选项 2](media/app-details-customizable.png)

   - <span data-ttu-id="19c72-130">选择应用名称，然后从"操作 **"** 下拉列表中选择 **"自定义** "。</span><span class="sxs-lookup"><span data-stu-id="19c72-130">Select the app name, and then select **Customize** from the **Actions** dropdown.</span></span>

     ![自定义选择选项 3](media/customize-action-menu.png)

4. <span data-ttu-id="19c72-132">展开" **详细信息** "部分并自定义以下字段：</span><span class="sxs-lookup"><span data-stu-id="19c72-132">Expand the **Details** section and customize the following fields:</span></span>

    - <span data-ttu-id="19c72-133">短名称</span><span class="sxs-lookup"><span data-stu-id="19c72-133">Short name</span></span>
    - <span data-ttu-id="19c72-134">简短说明</span><span class="sxs-lookup"><span data-stu-id="19c72-134">Short description</span></span>
    - <span data-ttu-id="19c72-135">完整说明</span><span class="sxs-lookup"><span data-stu-id="19c72-135">Full description</span></span>
    - <span data-ttu-id="19c72-136">网站</span><span class="sxs-lookup"><span data-stu-id="19c72-136">Website</span></span>
    - <span data-ttu-id="19c72-137">隐私策略 URL</span><span class="sxs-lookup"><span data-stu-id="19c72-137">Privacy policy URL</span></span>
    - <span data-ttu-id="19c72-138">使用条款 URL</span><span class="sxs-lookup"><span data-stu-id="19c72-138">Terms of use URL</span></span>

   ![自定义设置](media/customize-settings.png)

> [!Note]
> <span data-ttu-id="19c72-140">只有应用开发人员已分配为可自定义的字段将可见。</span><span class="sxs-lookup"><span data-stu-id="19c72-140">Only the fields that the app developer has assigned as customizable will be visible.</span></span>

5. <span data-ttu-id="19c72-141">展开" **图标"** 部分。</span><span class="sxs-lookup"><span data-stu-id="19c72-141">Expand the **Icon** section.</span></span>

   <span data-ttu-id="19c72-142">a.</span><span class="sxs-lookup"><span data-stu-id="19c72-142">a.</span></span> <span data-ttu-id="19c72-143">Upload图标。</span><span class="sxs-lookup"><span data-stu-id="19c72-143">Upload an icon.</span></span> <span data-ttu-id="19c72-144">使用一个全颜色图标 (192x192) PNG 格式的像素。</span><span class="sxs-lookup"><span data-stu-id="19c72-144">Use one full-color icon (192x192) pixel in PNG format.</span></span>

   <span data-ttu-id="19c72-145">b.</span><span class="sxs-lookup"><span data-stu-id="19c72-145">b.</span></span> <span data-ttu-id="19c72-146">选择图标轮廓颜色。</span><span class="sxs-lookup"><span data-stu-id="19c72-146">Choose an icon outline color.</span></span> <span data-ttu-id="19c72-147">使用一个 32x32 (32x32) PNG 格式的透明轮廓。</span><span class="sxs-lookup"><span data-stu-id="19c72-147">Use one transparent outline (32x32) pixel in PNG format.</span></span>

   <span data-ttu-id="19c72-148">c.</span><span class="sxs-lookup"><span data-stu-id="19c72-148">c.</span></span> <span data-ttu-id="19c72-149">选择与图标匹配的应用主题色。</span><span class="sxs-lookup"><span data-stu-id="19c72-149">Select an app accent color that matches the icon.</span></span>

    ![自定义图标面板颜色选项](media/customize-app-colors.png)

6. <span data-ttu-id="19c72-151">自定义应用后，选择"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="19c72-151">Once your app has been customized, select **Apply**.</span></span>

7. <span data-ttu-id="19c72-152">选择 **"** 发布"以发布自定义应用。</span><span class="sxs-lookup"><span data-stu-id="19c72-152">Select **Publish** to publish the customized app.</span></span>

   <span data-ttu-id="19c72-153">自定义应用现在列在"管理应用 **"页** 中。</span><span class="sxs-lookup"><span data-stu-id="19c72-153">The customized app is now listed in your **Manage apps** page.</span></span> <span data-ttu-id="19c72-154">你将只有一个版本的应用，因为自定义应用功能不会创建应用的副本。</span><span class="sxs-lookup"><span data-stu-id="19c72-154">You'll have only one version of the app, since customizing the app features doesn't create a copy of the app.</span></span>

<span data-ttu-id="19c72-155">现在Teams最终用户可以打开其 Teams 客户端以查看自定义应用。</span><span class="sxs-lookup"><span data-stu-id="19c72-155">Now your Teams end users can open their Teams client to see the customized app.</span></span>

   ![客户端中的Teams应用](media/contoso-app.png)

### <a name="special-considerations-for-customizing-an-app"></a><span data-ttu-id="19c72-157">自定义应用的特殊注意事项</span><span class="sxs-lookup"><span data-stu-id="19c72-157">Special considerations for customizing an app</span></span>

<span data-ttu-id="19c72-158">以下说明包含有关自定义应用的重要详细信息。</span><span class="sxs-lookup"><span data-stu-id="19c72-158">The following note includes important details about customizing an app.</span></span>

> [!Note]
> - <span data-ttu-id="19c72-159">自定义应用以及与应用相关的任何说明时，请确保遵循任何自定义指南（如果应用发布者在文档或使用条款中提供）。</span><span class="sxs-lookup"><span data-stu-id="19c72-159">When you customize apps, and any description related to an app, ensure that you follow any customization guidelines if provided by the app publisher in their documentation or terms of use.</span></span> <span data-ttu-id="19c72-160">你还有责任尊重他人对可能使用的任何第三方图像的权利。</span><span class="sxs-lookup"><span data-stu-id="19c72-160">You're also responsible for respecting the rights of others regarding any third-party images you might use.</span></span>
> - <span data-ttu-id="19c72-161">管理员提供的自定义数据存储在最近的区域。</span><span class="sxs-lookup"><span data-stu-id="19c72-161">Admin-provided customization data is stored in the nearest region.</span></span>
> - <span data-ttu-id="19c72-162">你负责确保指向使用条款或隐私策略的链接有效。</span><span class="sxs-lookup"><span data-stu-id="19c72-162">You are responsible for ensuring that links to terms of use or privacy policy are valid.</span></span>
> - <span data-ttu-id="19c72-163">如果应用发布者不再允许自定义字段，应用详细信息页上会显示一条消息，通知管理员不再可以自定义的字段。</span><span class="sxs-lookup"><span data-stu-id="19c72-163">In case the app publisher no longer allows a field to be customizable, a message appears on the app details page notifying the admin about the fields that can't be customized any longer.</span></span> <span data-ttu-id="19c72-164">对该字段进行的所有更改都将还原为原始值。</span><span class="sxs-lookup"><span data-stu-id="19c72-164">All the changes made to that field will be reverted to the original values.</span></span>
> - <span data-ttu-id="19c72-165">建议在生产环境中执行Teams测试租户中的应用自定义更改。</span><span class="sxs-lookup"><span data-stu-id="19c72-165">We recommend testing app customization changes in a Teams test tenant before making these changes in your production environment.</span></span>
> - <span data-ttu-id="19c72-166">更改品牌可能需要最多 24 小时，用户才能看到更改。</span><span class="sxs-lookup"><span data-stu-id="19c72-166">Changes to branding might require up to 24 hours for the users to see the changes.</span></span>

## <a name="review-app-details"></a><span data-ttu-id="19c72-167">查看应用详细信息</span><span class="sxs-lookup"><span data-stu-id="19c72-167">Review app details</span></span>

<span data-ttu-id="19c72-168">你可能希望查看应用详细信息来查看信息。</span><span class="sxs-lookup"><span data-stu-id="19c72-168">You might want to see the app details to review the information.</span></span>

1. <span data-ttu-id="19c72-169">登录到 Teams 管理中心。</span><span class="sxs-lookup"><span data-stu-id="19c72-169">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="19c72-170">展开“**Teams 应用**”，选择“**管理应用**”。</span><span class="sxs-lookup"><span data-stu-id="19c72-170">Expand **Teams apps** and select **Manage apps**.</span></span>

3. <span data-ttu-id="19c72-171">选择应用名称。</span><span class="sxs-lookup"><span data-stu-id="19c72-171">Select the app name.</span></span>

4. <span data-ttu-id="19c72-172">查看应用详细信息，包括原始应用名称 **发布者的短名称**。</span><span class="sxs-lookup"><span data-stu-id="19c72-172">View the app details, including the original app name **Short name from publisher**.</span></span>

   ![自定义图标面板应用名称](media/original-app-version.png)

   <span data-ttu-id="19c72-174">只有在 **你更改了** 应用的短名称时，发布者的短名称字段才可见。</span><span class="sxs-lookup"><span data-stu-id="19c72-174">The **Short name from publisher** field is only visible if you've changed the app's short name.</span></span>

## <a name="reset-app-details-to-default"></a><span data-ttu-id="19c72-175">将应用详细信息重置为默认值</span><span class="sxs-lookup"><span data-stu-id="19c72-175">Reset app details to default</span></span>

<span data-ttu-id="19c72-176">你随时都可以将应用详细信息重置为原始设置。</span><span class="sxs-lookup"><span data-stu-id="19c72-176">At any time, you can reset the app details to the original settings.</span></span>

1. <span data-ttu-id="19c72-177">登录到 Teams 管理中心。</span><span class="sxs-lookup"><span data-stu-id="19c72-177">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="19c72-178">展开 **Teams应用"，** 然后选择"**管理应用"。**</span><span class="sxs-lookup"><span data-stu-id="19c72-178">Expand **Teams Apps** and select **Manage apps**.</span></span>

3. <span data-ttu-id="19c72-179">选择应用名称。</span><span class="sxs-lookup"><span data-stu-id="19c72-179">Select the app name.</span></span>

4. <span data-ttu-id="19c72-180">从 **"操作"下拉列表中选择\*\*\*\*"重置** 为默认值"。</span><span class="sxs-lookup"><span data-stu-id="19c72-180">Select **Reset to default** from the **Actions** dropdown.</span></span>

   ![选择"重置为默认"突出显示](media/select-reset.png)

## <a name="frequently-asked-questions"></a><span data-ttu-id="19c72-182">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="19c72-182">Frequently asked questions</span></span>

<span data-ttu-id="19c72-183">**我的用户需要多久来查看自定义应用？**</span><span class="sxs-lookup"><span data-stu-id="19c72-183">**How long will it take for my users to see the customized app?**</span></span>

<span data-ttu-id="19c72-184">虽然管理员可以立即在管理中心Teams更改，但最终用户最多可能需要 24 小时才能看到更改。</span><span class="sxs-lookup"><span data-stu-id="19c72-184">Although the admin can immediately see the changes in Teams Admin Center, it might take up to 24 hours for the end users to see the changes.</span></span>  

<span data-ttu-id="19c72-185">**应用提供商是否可为客户自定义应用？**</span><span class="sxs-lookup"><span data-stu-id="19c72-185">**Can the app provider customize the app for its customers?**</span></span>

 <span data-ttu-id="19c72-186">否，租户管理员需要使用管理中心为租户Teams应用。</span><span class="sxs-lookup"><span data-stu-id="19c72-186">No, the admin of a tenant needs to customize the app for their tenant using the Teams Admin Center.</span></span>

<span data-ttu-id="19c72-187">**自定义应用会自动部署以替换租户中的当前自定义应用吗？**</span><span class="sxs-lookup"><span data-stu-id="19c72-187">**Will the customized app automatically get deployed to replace my current custom app in a tenant?**</span></span>

<span data-ttu-id="19c72-188">否，租户管理员必须手动删除任何自定义应用并发布应用的自定义版本。</span><span class="sxs-lookup"><span data-stu-id="19c72-188">No, the tenant admins will have to manually remove any custom app and publish the customized version of the app.</span></span> <span data-ttu-id="19c72-189">如果你已自定义应用并将其发布为自定义应用，则使用应用自定义功能自定义的新应用不会替换当前的自定义应用。</span><span class="sxs-lookup"><span data-stu-id="19c72-189">If you have customized an app and published it as a custom app, the new app customized using the app customization feature won't replace the current custom app.</span></span>  

<span data-ttu-id="19c72-190">**应用使用情况报告还会显示自定义值（如自定义短名称）吗？**</span><span class="sxs-lookup"><span data-stu-id="19c72-190">**Will the app usage report also show the customized values such as customized short name?**</span></span>

 <span data-ttu-id="19c72-191">否，应用使用情况报告仍将显示从发布者发送的应用的原始名称。</span><span class="sxs-lookup"><span data-stu-id="19c72-191">No, the app usage report will still show the original name of the app sent from the publisher.</span></span>

<span data-ttu-id="19c72-192">**可以使用应用自定义功能自定义哪些应用？**</span><span class="sxs-lookup"><span data-stu-id="19c72-192">**Which apps can I customize using the app customization feature?**</span></span>

<span data-ttu-id="19c72-193">只能自定义应用发布者允许自定义的应用。</span><span class="sxs-lookup"><span data-stu-id="19c72-193">You can only customize apps that have been allowed to be customizable by the app publisher.</span></span> <span data-ttu-id="19c72-194">应用发布者将需要选择加入以允许其客户自定义应用。</span><span class="sxs-lookup"><span data-stu-id="19c72-194">The app publisher will need to opt in to allow its customers to customize the app.</span></span>

<span data-ttu-id="19c72-195">**自定义属性会显示在图形权限许可屏幕上吗？**</span><span class="sxs-lookup"><span data-stu-id="19c72-195">**Will the customized properties show up on the graph permission consent screen?**</span></span>

<span data-ttu-id="19c72-196">否，权限许可屏幕仍将显示发布者发送的原始值。</span><span class="sxs-lookup"><span data-stu-id="19c72-196">No, the permission consent screen will still show the original value sent by the publisher.</span></span>

## <a name="related-article"></a><span data-ttu-id="19c72-197">相关文章</span><span class="sxs-lookup"><span data-stu-id="19c72-197">Related article</span></span>

- [<span data-ttu-id="19c72-198">管理应用</span><span class="sxs-lookup"><span data-stu-id="19c72-198">Manage apps</span></span>](manage-apps.md)
- [<span data-ttu-id="19c72-199">自定义应用商店</span><span class="sxs-lookup"><span data-stu-id="19c72-199">Customize your app store</span></span>](customize-your-app-store.md)
- [<span data-ttu-id="19c72-200">为应用重新品牌</span><span class="sxs-lookup"><span data-stu-id="19c72-200">Rebrand your apps</span></span>](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/rebrand-apps-to-your-own-organization-s-branding-with-app/ba-p/2376296)
