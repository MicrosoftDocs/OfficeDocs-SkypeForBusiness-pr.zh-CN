---
title: 在 Teams 中自定义 Microsoft 应用
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: vaagarw
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
description: 了解如何在 Microsoft Teams 中自定义应用。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 9e9c7d250f60c3cc100f7d95b26f662ca8af6305
ms.sourcegitcommit: cfef9dd41cac0df83bd02b35036d8f8f1b472feb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51697787"
---
# <a name="customize-apps-in-microsoft-teams"></a><span data-ttu-id="0bcee-103">在 Microsoft Teams 中自定义应用</span><span class="sxs-lookup"><span data-stu-id="0bcee-103">Customize apps in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

 <span data-ttu-id="0bcee-104">Microsoft Teams 提供应用自定义来增强 Teams 体验。</span><span class="sxs-lookup"><span data-stu-id="0bcee-104">Microsoft Teams provides app customization to enhance the Teams experience.</span></span> <span data-ttu-id="0bcee-105">某些应用开发人员允许 Teams 管理员自定义应用。管理员可以使用 Teams 管理中心"管理应用"页面，根据组织需求自定义或重新设置 **应用属性** 的品牌。</span><span class="sxs-lookup"><span data-stu-id="0bcee-105">Some app developers allow an app to be customized by the Teams admin. The admin can customize or rebrand the app properties based on the organizational needs using the Teams admin center **Manage apps** page.</span></span> <span data-ttu-id="0bcee-106">可以自定义的详细信息包括：</span><span class="sxs-lookup"><span data-stu-id="0bcee-106">The details you can customize are:</span></span>

- <span data-ttu-id="0bcee-107">短名称</span><span class="sxs-lookup"><span data-stu-id="0bcee-107">Short name</span></span>
- <span data-ttu-id="0bcee-108">简短说明</span><span class="sxs-lookup"><span data-stu-id="0bcee-108">Short description</span></span>
- <span data-ttu-id="0bcee-109">完整说明</span><span class="sxs-lookup"><span data-stu-id="0bcee-109">Full description</span></span>
- <span data-ttu-id="0bcee-110">隐私策略 URL</span><span class="sxs-lookup"><span data-stu-id="0bcee-110">Privacy policy URL</span></span>
- <span data-ttu-id="0bcee-111">网站 URL</span><span class="sxs-lookup"><span data-stu-id="0bcee-111">Website URL</span></span>
- <span data-ttu-id="0bcee-112">使用条款 URL</span><span class="sxs-lookup"><span data-stu-id="0bcee-112">Terms of use URL</span></span>
- <span data-ttu-id="0bcee-113">颜色图标</span><span class="sxs-lookup"><span data-stu-id="0bcee-113">Color icon</span></span>
- <span data-ttu-id="0bcee-114">"大纲"图标</span><span class="sxs-lookup"><span data-stu-id="0bcee-114">Outline icon</span></span>
- <span data-ttu-id="0bcee-115">主题色</span><span class="sxs-lookup"><span data-stu-id="0bcee-115">Accent color</span></span>

<span data-ttu-id="0bcee-116">有关 [可自定义的](https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema) 字段的详细信息，请参阅 Teams 清单架构。</span><span class="sxs-lookup"><span data-stu-id="0bcee-116">See the [Teams Manifest schema](https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema) for details about the fields that you can customize.</span></span>

> <span data-ttu-id="0bcee-117">[!注意 目前，政府社区云高 (GCCH) 或国防部 (DoD) 不支持自定义应用。</span><span class="sxs-lookup"><span data-stu-id="0bcee-117">[!NOTE Customizing apps isn't supported in Government Community Cloud High (GCCH) or Department of Defense (DoD) at this time.</span></span>

## <a name="customize-the-apps-details"></a><span data-ttu-id="0bcee-118">自定义应用的详细信息</span><span class="sxs-lookup"><span data-stu-id="0bcee-118">Customize the app's details</span></span>

<span data-ttu-id="0bcee-119">若要开始自定义应用，请完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="0bcee-119">To start customizing an app, complete the following steps:</span></span>

1. <span data-ttu-id="0bcee-120">登录到 Teams 管理中心。</span><span class="sxs-lookup"><span data-stu-id="0bcee-120">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="0bcee-121">展开 **"Teams 应用"** 并选择"**管理应用"。**</span><span class="sxs-lookup"><span data-stu-id="0bcee-121">Expand **Teams Apps** and select **Manage apps**.</span></span>
3. <span data-ttu-id="0bcee-122">检查 **应用列表** 的"可自定义"列，并按可自定义的应用进行排序。</span><span class="sxs-lookup"><span data-stu-id="0bcee-122">Check the **Customizable** column of the apps list and sort by apps that are customizable.</span></span>

   ![已排序的自定义列](media/customize-column.png)

   <span data-ttu-id="0bcee-124">有三个入口点可以访问自定义功能：</span><span class="sxs-lookup"><span data-stu-id="0bcee-124">There are three entry points to access the customize feature:</span></span>

   - <span data-ttu-id="0bcee-125">选择要自定义的应用旁边的 ，然后选择"自定义 **"。**</span><span class="sxs-lookup"><span data-stu-id="0bcee-125">Select next to the app that you want to customize, and then select **Customize**.</span></span>

     ![自定义选择选项 1](media/select-app-to-customize1.png)

   - <span data-ttu-id="0bcee-127">选择应用名称，然后选择"可 **自定义"。**</span><span class="sxs-lookup"><span data-stu-id="0bcee-127">Select the app name and then **Customizable**.</span></span>

     ![自定义选择选项 2](media/app-details-customizable.png)

   - <span data-ttu-id="0bcee-129">选择应用名称，然后从"操作 **"** 下拉列表中选择 **"自定义** "。</span><span class="sxs-lookup"><span data-stu-id="0bcee-129">Select the app name, and then select **Customize** from the **Actions** dropdown.</span></span>

     ![自定义选择选项 3](media/customize-action-menu.png)

4. <span data-ttu-id="0bcee-131">展开" **详细信息** "部分并自定义以下字段：</span><span class="sxs-lookup"><span data-stu-id="0bcee-131">Expand the **Details** section and customize the following fields:</span></span>

    - <span data-ttu-id="0bcee-132">短名称</span><span class="sxs-lookup"><span data-stu-id="0bcee-132">Short name</span></span>
    - <span data-ttu-id="0bcee-133">简短说明</span><span class="sxs-lookup"><span data-stu-id="0bcee-133">Short description</span></span>
    - <span data-ttu-id="0bcee-134">完整说明</span><span class="sxs-lookup"><span data-stu-id="0bcee-134">Full description</span></span>
    - <span data-ttu-id="0bcee-135">网站</span><span class="sxs-lookup"><span data-stu-id="0bcee-135">Website</span></span>
    - <span data-ttu-id="0bcee-136">隐私策略 URL</span><span class="sxs-lookup"><span data-stu-id="0bcee-136">Privacy policy URL</span></span>
    - <span data-ttu-id="0bcee-137">使用条款 URL</span><span class="sxs-lookup"><span data-stu-id="0bcee-137">Terms of use URL</span></span>

   ![自定义设置](media/customize-settings.png)

> [!Note]
> <span data-ttu-id="0bcee-139">只有应用开发人员已分配为可自定义的字段将可见。</span><span class="sxs-lookup"><span data-stu-id="0bcee-139">Only the fields that the app developer has assigned as customizable will be visible.</span></span>

5. <span data-ttu-id="0bcee-140">展开" **图标"** 部分。</span><span class="sxs-lookup"><span data-stu-id="0bcee-140">Expand the **Icon** section.</span></span>

   <span data-ttu-id="0bcee-141">a.</span><span class="sxs-lookup"><span data-stu-id="0bcee-141">a.</span></span> <span data-ttu-id="0bcee-142">上传图标。</span><span class="sxs-lookup"><span data-stu-id="0bcee-142">Upload an icon.</span></span> <span data-ttu-id="0bcee-143">使用一个全颜色图标 (192x192) PNG 格式的像素。</span><span class="sxs-lookup"><span data-stu-id="0bcee-143">Use one full-color icon (192x192) pixel in PNG format.</span></span>

   <span data-ttu-id="0bcee-144">b.</span><span class="sxs-lookup"><span data-stu-id="0bcee-144">b.</span></span> <span data-ttu-id="0bcee-145">选择图标轮廓颜色。</span><span class="sxs-lookup"><span data-stu-id="0bcee-145">Choose an icon outline color.</span></span> <span data-ttu-id="0bcee-146">使用一个 32x32 (32x32) PNG 格式的透明轮廓。</span><span class="sxs-lookup"><span data-stu-id="0bcee-146">Use one transparent outline (32x32) pixel in PNG format.</span></span>

   <span data-ttu-id="0bcee-147">c.</span><span class="sxs-lookup"><span data-stu-id="0bcee-147">c.</span></span> <span data-ttu-id="0bcee-148">选择与图标匹配的应用主题色。</span><span class="sxs-lookup"><span data-stu-id="0bcee-148">Select an app accent color that matches the icon.</span></span>

    ![自定义图标面板颜色选项](media/customize-app-colors.png)

6. <span data-ttu-id="0bcee-150">自定义应用后，选择"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="0bcee-150">Once your app has been customized, select **Apply**.</span></span>

7. <span data-ttu-id="0bcee-151">选择 **"** 发布"以发布自定义应用。</span><span class="sxs-lookup"><span data-stu-id="0bcee-151">Select **Publish** to publish the customized app.</span></span>

   <span data-ttu-id="0bcee-152">自定义应用现在列在"管理应用 **"页** 中。</span><span class="sxs-lookup"><span data-stu-id="0bcee-152">The customized app is now listed in your **Manage apps** page.</span></span> <span data-ttu-id="0bcee-153">你将只有一个版本的应用，因为自定义应用功能不会创建应用的副本。</span><span class="sxs-lookup"><span data-stu-id="0bcee-153">You'll have only one version of the app, since customizing the app features doesn't create a copy of the app.</span></span>

<span data-ttu-id="0bcee-154">现在，Teams 最终用户可以打开其 Teams 客户端来查看自定义应用。</span><span class="sxs-lookup"><span data-stu-id="0bcee-154">Now your Teams end users can open their Teams client to see the customized app.</span></span>

   ![Teams 客户端中的自定义应用](media/find-customized-app.png)

### <a name="special-considerations-for-customizing-an-app"></a><span data-ttu-id="0bcee-156">自定义应用的特殊注意事项</span><span class="sxs-lookup"><span data-stu-id="0bcee-156">Special considerations for customizing an app</span></span>

<span data-ttu-id="0bcee-157">以下说明包含有关自定义应用的重要详细信息。</span><span class="sxs-lookup"><span data-stu-id="0bcee-157">The following note includes important details about customizing an app.</span></span>

> [!Note]
> - <span data-ttu-id="0bcee-158">自定义应用以及与应用相关的任何说明时，请确保遵循任何自定义指南（如果应用发布者在文档或使用条款中提供）。</span><span class="sxs-lookup"><span data-stu-id="0bcee-158">When you customize apps, and any description related to an app, ensure that you follow any customization guidelines if provided by the app publisher in their documentation or terms of use.</span></span> <span data-ttu-id="0bcee-159">你还有责任尊重他人对可能使用的任何第三方图像的权利。</span><span class="sxs-lookup"><span data-stu-id="0bcee-159">You're also responsible for respecting the rights of others regarding any third-party images you might use.</span></span>
> - <span data-ttu-id="0bcee-160">管理员提供的自定义数据存储在最近的区域。</span><span class="sxs-lookup"><span data-stu-id="0bcee-160">Admin-provided customization data is stored in the nearest region.</span></span>
> - <span data-ttu-id="0bcee-161">你负责确保指向使用条款或隐私策略的链接有效。</span><span class="sxs-lookup"><span data-stu-id="0bcee-161">You are responsible for ensuring that links to terms of use or privacy policy are valid.</span></span>
> - <span data-ttu-id="0bcee-162">如果应用发布者不再允许自定义字段，应用详细信息页上会显示一条消息，通知管理员不再可以自定义的字段。</span><span class="sxs-lookup"><span data-stu-id="0bcee-162">In case the app publisher no longer allows a field to be customizable, a message appears on the app details page notifying the admin about the fields that can't be customized any longer.</span></span> <span data-ttu-id="0bcee-163">对该字段进行的所有更改都将还原为原始值。</span><span class="sxs-lookup"><span data-stu-id="0bcee-163">All the changes made to that field will be reverted to the original values.</span></span>
> - <span data-ttu-id="0bcee-164">更改品牌可能需要最多 24 小时，用户才能看到更改。</span><span class="sxs-lookup"><span data-stu-id="0bcee-164">Changes to branding might require up to 24 hours for the users to see the changes.</span></span>

## <a name="review-app-details"></a><span data-ttu-id="0bcee-165">查看应用详细信息</span><span class="sxs-lookup"><span data-stu-id="0bcee-165">Review app details</span></span>

<span data-ttu-id="0bcee-166">你可能希望查看应用详细信息来查看信息。</span><span class="sxs-lookup"><span data-stu-id="0bcee-166">You might want to see the app details to review the information.</span></span>

1. <span data-ttu-id="0bcee-167">登录到 Teams 管理中心。</span><span class="sxs-lookup"><span data-stu-id="0bcee-167">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="0bcee-168">展开“**Teams 应用**”，选择“**管理应用**”。</span><span class="sxs-lookup"><span data-stu-id="0bcee-168">Expand **Teams apps** and select **Manage apps**.</span></span>

3. <span data-ttu-id="0bcee-169">选择应用名称。</span><span class="sxs-lookup"><span data-stu-id="0bcee-169">Select the app name.</span></span>

4. <span data-ttu-id="0bcee-170">查看应用详细信息，包括原始应用名称 **发布者的短名称**。</span><span class="sxs-lookup"><span data-stu-id="0bcee-170">View the app details, including the original app name **Short name from publisher**.</span></span>

   ![自定义图标面板应用名称](media/app-details-original-name.png)

   <span data-ttu-id="0bcee-172">只有在 **你更改了** 应用的短名称时，发布者的短名称字段才可见。</span><span class="sxs-lookup"><span data-stu-id="0bcee-172">The **Short name from publisher** field is only visible if you've changed the app's short name.</span></span>

## <a name="reset-app-details-to-default"></a><span data-ttu-id="0bcee-173">将应用详细信息重置为默认值</span><span class="sxs-lookup"><span data-stu-id="0bcee-173">Reset app details to default</span></span>

<span data-ttu-id="0bcee-174">你随时都可以将应用详细信息重置为原始设置。</span><span class="sxs-lookup"><span data-stu-id="0bcee-174">At any time, you can reset the app details to the original settings.</span></span>

1. <span data-ttu-id="0bcee-175">登录到 Teams 管理中心。</span><span class="sxs-lookup"><span data-stu-id="0bcee-175">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="0bcee-176">展开 **"Teams 应用"** 并选择"**管理应用"。**</span><span class="sxs-lookup"><span data-stu-id="0bcee-176">Expand **Teams Apps** and select **Manage apps**.</span></span>

3. <span data-ttu-id="0bcee-177">选择应用名称。</span><span class="sxs-lookup"><span data-stu-id="0bcee-177">Select the app name.</span></span>

4. <span data-ttu-id="0bcee-178">从 **"操作"下拉列表中选择\*\*\*\*"重置** 为默认值"。</span><span class="sxs-lookup"><span data-stu-id="0bcee-178">Select **Reset to default** from the **Actions** dropdown.</span></span>

   ![选择"重置为默认"突出显示](media/select-reset.png)

## <a name="frequently-asked-questions"></a><span data-ttu-id="0bcee-180">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="0bcee-180">Frequently asked questions</span></span>

<span data-ttu-id="0bcee-181">**我的用户需要多久来查看自定义应用？**</span><span class="sxs-lookup"><span data-stu-id="0bcee-181">**How long will it take for my users to see the customized app?**</span></span>

<span data-ttu-id="0bcee-182">虽然管理员可以立即在 Teams 管理中心看到更改，但最终用户最多可能需要 24 小时才能看到更改。</span><span class="sxs-lookup"><span data-stu-id="0bcee-182">Although the admin can immediately see the changes in Teams Admin Center, it might take up to 24 hours for the end users to see the changes.</span></span>  

<span data-ttu-id="0bcee-183">**应用提供商是否可为客户自定义应用？**</span><span class="sxs-lookup"><span data-stu-id="0bcee-183">**Can the app provider customize the app for its customers?**</span></span>

 <span data-ttu-id="0bcee-184">否，租户的管理员需要使用 Teams 管理中心为租户自定义应用。</span><span class="sxs-lookup"><span data-stu-id="0bcee-184">No, the admin of a tenant needs to customize the app for their tenant using the Teams Admin Center.</span></span>

<span data-ttu-id="0bcee-185">**自定义应用会自动部署以替换租户中的当前自定义应用吗？**</span><span class="sxs-lookup"><span data-stu-id="0bcee-185">**Will the customized app automatically get deployed to replace my current custom app in a tenant?**</span></span>

<span data-ttu-id="0bcee-186">否，租户管理员必须手动删除任何自定义应用并发布应用的自定义版本。</span><span class="sxs-lookup"><span data-stu-id="0bcee-186">No, the tenant admins will have to manually remove any custom app and publish the customized version of the app.</span></span> <span data-ttu-id="0bcee-187">如果你已自定义应用并将其发布为自定义应用，则使用应用自定义功能自定义的新应用不会替换当前的自定义应用。</span><span class="sxs-lookup"><span data-stu-id="0bcee-187">If you have customized an app and published it as a custom app, the new app customized using the app customization feature won't replace the current custom app.</span></span>  

<span data-ttu-id="0bcee-188">**应用使用情况报告还会显示自定义值（如自定义短名称）吗？**</span><span class="sxs-lookup"><span data-stu-id="0bcee-188">**Will the app usage report also show the customized values such as customized short name?**</span></span>

 <span data-ttu-id="0bcee-189">否，应用使用情况报告仍将显示从发布者发送的应用的原始名称。</span><span class="sxs-lookup"><span data-stu-id="0bcee-189">No, the app usage report will still show the original name of the app sent from the publisher.</span></span>

<span data-ttu-id="0bcee-190">**可以使用应用自定义功能自定义哪些应用？**</span><span class="sxs-lookup"><span data-stu-id="0bcee-190">**Which apps can I customize using the app customization feature?**</span></span>

<span data-ttu-id="0bcee-191">只能自定义应用发布者允许自定义的应用。</span><span class="sxs-lookup"><span data-stu-id="0bcee-191">You can only customize apps that have been allowed to be customizable by the app publisher.</span></span> <span data-ttu-id="0bcee-192">应用发布者将需要选择加入以允许其客户自定义应用。</span><span class="sxs-lookup"><span data-stu-id="0bcee-192">The app publisher will need to opt in to allow its customers to customize the app.</span></span>

<span data-ttu-id="0bcee-193">**自定义属性会显示在图形权限许可屏幕上吗？**</span><span class="sxs-lookup"><span data-stu-id="0bcee-193">**Will the customized properties show up on the graph permission consent screen?**</span></span>

<span data-ttu-id="0bcee-194">否，权限许可屏幕仍将显示发布者发送的原始值。</span><span class="sxs-lookup"><span data-stu-id="0bcee-194">No, the permission consent screen will still show the original value sent by the publisher.</span></span>

## <a name="related-article"></a><span data-ttu-id="0bcee-195">相关文章</span><span class="sxs-lookup"><span data-stu-id="0bcee-195">Related article</span></span>

- [<span data-ttu-id="0bcee-196">管理应用</span><span class="sxs-lookup"><span data-stu-id="0bcee-196">Manage apps</span></span>](manage-apps.md)
- [<span data-ttu-id="0bcee-197">自定义应用商店</span><span class="sxs-lookup"><span data-stu-id="0bcee-197">Customize your app store</span></span>](customize-your-app-store.md)
