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
ms.openlocfilehash: b2e924da384b5bff54e63872aa7026d2da456311
ms.sourcegitcommit: 88cb2362d07bca88402cf771a6f366c972e26001
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/31/2021
ms.locfileid: "51471496"
---
# <a name="customize-apps-in-microsoft-teams"></a><span data-ttu-id="b02d5-103">在 Microsoft Teams 中自定义应用</span><span class="sxs-lookup"><span data-stu-id="b02d5-103">Customize apps in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

 <span data-ttu-id="b02d5-104">Microsoft Teams 提供应用自定义来增强 Teams 体验。</span><span class="sxs-lookup"><span data-stu-id="b02d5-104">Microsoft Teams provides app customization to enhance the Teams experience.</span></span> <span data-ttu-id="b02d5-105">某些应用开发人员允许 Teams 管理员自定义应用。管理员可以使用 Teams 管理中心"管理应用"页面，根据组织需求自定义或重新设置 **应用属性** 的品牌。</span><span class="sxs-lookup"><span data-stu-id="b02d5-105">Some app developers allow an app to be customized by the Teams admin. The admin can customize or rebrand the app properties based on the organizational needs using the Teams admin center **Manage apps** page.</span></span> <span data-ttu-id="b02d5-106">可以自定义的详细信息包括：</span><span class="sxs-lookup"><span data-stu-id="b02d5-106">The details you can customize are:</span></span>

- <span data-ttu-id="b02d5-107">短名称</span><span class="sxs-lookup"><span data-stu-id="b02d5-107">Short name</span></span>
- <span data-ttu-id="b02d5-108">简短说明</span><span class="sxs-lookup"><span data-stu-id="b02d5-108">Short description</span></span>
- <span data-ttu-id="b02d5-109">完整说明</span><span class="sxs-lookup"><span data-stu-id="b02d5-109">Full description</span></span>
- <span data-ttu-id="b02d5-110">隐私策略 URL</span><span class="sxs-lookup"><span data-stu-id="b02d5-110">Privacy policy URL</span></span>
- <span data-ttu-id="b02d5-111">网站 URL</span><span class="sxs-lookup"><span data-stu-id="b02d5-111">Website URL</span></span>
- <span data-ttu-id="b02d5-112">使用条款 URL</span><span class="sxs-lookup"><span data-stu-id="b02d5-112">Terms of use URL</span></span>
- <span data-ttu-id="b02d5-113">颜色图标</span><span class="sxs-lookup"><span data-stu-id="b02d5-113">Color icon</span></span>
- <span data-ttu-id="b02d5-114">"大纲"图标</span><span class="sxs-lookup"><span data-stu-id="b02d5-114">Outline icon</span></span>
- <span data-ttu-id="b02d5-115">主题色</span><span class="sxs-lookup"><span data-stu-id="b02d5-115">Accent color</span></span>

<span data-ttu-id="b02d5-116">有关 [可自定义的](https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema) 字段的详细信息，请参阅 Teams 清单架构。</span><span class="sxs-lookup"><span data-stu-id="b02d5-116">See the [Teams Manifest schema](https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema) for details about the fields that you can customize.</span></span>

## <a name="customize-the-apps-details"></a><span data-ttu-id="b02d5-117">自定义应用的详细信息</span><span class="sxs-lookup"><span data-stu-id="b02d5-117">Customize the app's details</span></span>

<span data-ttu-id="b02d5-118">若要开始自定义应用，请完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="b02d5-118">To start customizing an app, complete the following steps:</span></span>

1. <span data-ttu-id="b02d5-119">登录到 Teams 管理中心。</span><span class="sxs-lookup"><span data-stu-id="b02d5-119">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="b02d5-120">展开 **"Teams 应用"** 并选择"**管理应用"。**</span><span class="sxs-lookup"><span data-stu-id="b02d5-120">Expand **Teams Apps** and select **Manage apps**.</span></span>
3. <span data-ttu-id="b02d5-121">检查 **应用列表** 的"可自定义"列，并按可自定义的应用进行排序。</span><span class="sxs-lookup"><span data-stu-id="b02d5-121">Check the **Customizable** column of the apps list and sort by apps that are customizable.</span></span>

   ![已排序的自定义列](media/customize-column.png)

   <span data-ttu-id="b02d5-123">有三个入口点可以访问自定义功能：</span><span class="sxs-lookup"><span data-stu-id="b02d5-123">There are three entry points to access the customize feature:</span></span>

   - <span data-ttu-id="b02d5-124">选择要自定义的应用旁边的 ，然后选择"自定义 **"。**</span><span class="sxs-lookup"><span data-stu-id="b02d5-124">Select next to the app that you want to customize, and then select **Customize**.</span></span>

     ![自定义选择选项 1](media/select-app-to-customize1.png)

   - <span data-ttu-id="b02d5-126">选择应用名称，然后选择"可 **自定义"。**</span><span class="sxs-lookup"><span data-stu-id="b02d5-126">Select the app name and then **Customizable**.</span></span>

     ![自定义选择选项 2](media/app-details-customizable.png)

   - <span data-ttu-id="b02d5-128">选择应用名称，然后从"操作 **"** 下拉列表中选择 **"自定义** "。</span><span class="sxs-lookup"><span data-stu-id="b02d5-128">Select the app name, and then select **Customize** from the **Actions** dropdown.</span></span>

     ![自定义选择选项 3](media/customize-action-menu.png)

4. <span data-ttu-id="b02d5-130">展开" **详细信息** "部分并自定义以下字段：</span><span class="sxs-lookup"><span data-stu-id="b02d5-130">Expand the **Details** section and customize the following fields:</span></span>

    - <span data-ttu-id="b02d5-131">短名称</span><span class="sxs-lookup"><span data-stu-id="b02d5-131">Short name</span></span>
    - <span data-ttu-id="b02d5-132">简短说明</span><span class="sxs-lookup"><span data-stu-id="b02d5-132">Short description</span></span>
    - <span data-ttu-id="b02d5-133">完整说明</span><span class="sxs-lookup"><span data-stu-id="b02d5-133">Full description</span></span>
    - <span data-ttu-id="b02d5-134">网站</span><span class="sxs-lookup"><span data-stu-id="b02d5-134">Website</span></span>
    - <span data-ttu-id="b02d5-135">隐私策略 URL</span><span class="sxs-lookup"><span data-stu-id="b02d5-135">Privacy policy URL</span></span>
    - <span data-ttu-id="b02d5-136">使用条款 URL</span><span class="sxs-lookup"><span data-stu-id="b02d5-136">Terms of use URL</span></span>

   ![自定义设置](media/customize-settings.png)

> [!Note]
> <span data-ttu-id="b02d5-138">只有应用开发人员已分配为可自定义的字段将可见。</span><span class="sxs-lookup"><span data-stu-id="b02d5-138">Only the fields that the app developer has assigned as customizable will be visible.</span></span>

5. <span data-ttu-id="b02d5-139">展开" **图标"** 部分。</span><span class="sxs-lookup"><span data-stu-id="b02d5-139">Expand the **Icon** section.</span></span>

   <span data-ttu-id="b02d5-140">a.</span><span class="sxs-lookup"><span data-stu-id="b02d5-140">a.</span></span> <span data-ttu-id="b02d5-141">上传图标。</span><span class="sxs-lookup"><span data-stu-id="b02d5-141">Upload an icon.</span></span> <span data-ttu-id="b02d5-142">使用一个全颜色图标 (192x192) PNG 格式的像素。</span><span class="sxs-lookup"><span data-stu-id="b02d5-142">Use one full-color icon (192x192) pixel in PNG format.</span></span>

   <span data-ttu-id="b02d5-143">b.</span><span class="sxs-lookup"><span data-stu-id="b02d5-143">b.</span></span> <span data-ttu-id="b02d5-144">选择图标轮廓颜色。</span><span class="sxs-lookup"><span data-stu-id="b02d5-144">Choose an icon outline color.</span></span> <span data-ttu-id="b02d5-145">使用一个 32x32 (32x32) PNG 格式的透明轮廓。</span><span class="sxs-lookup"><span data-stu-id="b02d5-145">Use one transparent outline (32x32) pixel in PNG format.</span></span>

   <span data-ttu-id="b02d5-146">c.</span><span class="sxs-lookup"><span data-stu-id="b02d5-146">c.</span></span> <span data-ttu-id="b02d5-147">选择与图标匹配的应用主题色。</span><span class="sxs-lookup"><span data-stu-id="b02d5-147">Select an app accent color that matches the icon.</span></span>

    ![自定义图标面板颜色选项](media/customize-app-colors.png)

6. <span data-ttu-id="b02d5-149">自定义应用后，选择"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="b02d5-149">Once your app has been customized, select **Apply**.</span></span>

7. <span data-ttu-id="b02d5-150">选择 **"** 发布"以发布自定义应用。</span><span class="sxs-lookup"><span data-stu-id="b02d5-150">Select **Publish** to publish the customized app.</span></span>

   <span data-ttu-id="b02d5-151">自定义应用现在列在"管理应用 **"页** 中。</span><span class="sxs-lookup"><span data-stu-id="b02d5-151">The customized app is now listed in your **Manage apps** page.</span></span> <span data-ttu-id="b02d5-152">你将只有一个版本的应用，因为自定义应用功能不会创建应用的副本。</span><span class="sxs-lookup"><span data-stu-id="b02d5-152">You'll have only one version of the app, since customizing the app features doesn't create a copy of the app.</span></span>

<span data-ttu-id="b02d5-153">现在，Teams 最终用户可以打开其 Teams 客户端来查看自定义应用。</span><span class="sxs-lookup"><span data-stu-id="b02d5-153">Now your Teams end users can open their Teams client to see the customized app.</span></span>

   ![Teams 客户端中的自定义应用](media/find-customized-app.png)

### <a name="special-considerations-for-customizing-an-app"></a><span data-ttu-id="b02d5-155">自定义应用的特殊注意事项</span><span class="sxs-lookup"><span data-stu-id="b02d5-155">Special considerations for customizing an app</span></span>

<span data-ttu-id="b02d5-156">以下说明包含有关自定义应用的重要详细信息。</span><span class="sxs-lookup"><span data-stu-id="b02d5-156">The following note includes important details about customizing an app.</span></span>

> [!Note]
> - <span data-ttu-id="b02d5-157">自定义应用和与应用相关的任何说明时，请确保遵循应用发布者提供的自定义指南。</span><span class="sxs-lookup"><span data-stu-id="b02d5-157">When you customize apps and any description related to an app, ensure that you follow the Customization Guidelines provided by the app publisher.</span></span> <span data-ttu-id="b02d5-158">你有责任尊重他人有关你可能使用的第三方图像的权利。</span><span class="sxs-lookup"><span data-stu-id="b02d5-158">You're responsible for respecting the rights of others regarding third-party images you might use.</span></span>
> - <span data-ttu-id="b02d5-159">管理员提供的自定义数据存储在最近的区域中的"设置存储"中。</span><span class="sxs-lookup"><span data-stu-id="b02d5-159">Admin-provided customization data is stored in the Settings Store in the nearest region.</span></span> <span data-ttu-id="b02d5-160">它并不一定在任何 GoLocal Cloud Teams 部署中。</span><span class="sxs-lookup"><span data-stu-id="b02d5-160">It isn't necessarily in any GoLocal Cloud Teams deployment.</span></span>
> - <span data-ttu-id="b02d5-161">你负责确保指向使用条款或隐私策略的链接有效。</span><span class="sxs-lookup"><span data-stu-id="b02d5-161">You're responsible for ensuring that the links to the terms of use or privacy policy are valid.</span></span> <span data-ttu-id="b02d5-162">你必须提供对它们所做的更改的适当管理 (或允许对) 元数据进行更改。</span><span class="sxs-lookup"><span data-stu-id="b02d5-162">You must provide appropriate management of the changes they make (or allow to be made) to app metadata.</span></span> <span data-ttu-id="b02d5-163">当前实现将提供支持，以帮助还原到开发人员提供的 URL。</span><span class="sxs-lookup"><span data-stu-id="b02d5-163">Current implementation will provide support to help you to revert to developer-provided URLs.</span></span> <span data-ttu-id="b02d5-164">如果应用允许自定义 url (，则不能在没有 URL 的情况下配置) 。</span><span class="sxs-lookup"><span data-stu-id="b02d5-164">You may not configure the app without a URL (if the app allows customization of the URLs).</span></span>
> - <span data-ttu-id="b02d5-165">如果应用发布者不再允许自定义字段，应用详细信息页上会显示一条消息，通知管理员不再可以自定义的字段。</span><span class="sxs-lookup"><span data-stu-id="b02d5-165">In case the app publisher no longer allows a field to be customizable, a message appears on the app details page notifying the admin about the fields that can't be customized any longer.</span></span> <span data-ttu-id="b02d5-166">对该字段进行的所有更改都将还原为原始值。</span><span class="sxs-lookup"><span data-stu-id="b02d5-166">All the changes made to that field will be reverted to the original values.</span></span>
> - <span data-ttu-id="b02d5-167">更改品牌可能需要最多 24 小时，用户才能看到更改。</span><span class="sxs-lookup"><span data-stu-id="b02d5-167">Changes to branding might require up to 24 hours for the users to see the changes.</span></span>

## <a name="review-app-details"></a><span data-ttu-id="b02d5-168">查看应用详细信息</span><span class="sxs-lookup"><span data-stu-id="b02d5-168">Review app details</span></span>

<span data-ttu-id="b02d5-169">你可能希望查看应用详细信息来查看信息。</span><span class="sxs-lookup"><span data-stu-id="b02d5-169">You might want to see the app details to review the information.</span></span>

1. <span data-ttu-id="b02d5-170">登录到 Teams 管理中心。</span><span class="sxs-lookup"><span data-stu-id="b02d5-170">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="b02d5-171">展开“**Teams 应用**”，选择“**管理应用**”。</span><span class="sxs-lookup"><span data-stu-id="b02d5-171">Expand **Teams apps** and select **Manage apps**.</span></span>

3. <span data-ttu-id="b02d5-172">选择应用名称。</span><span class="sxs-lookup"><span data-stu-id="b02d5-172">Select the app name.</span></span>

4. <span data-ttu-id="b02d5-173">查看应用详细信息，包括原始应用名称 **发布者的短名称**。</span><span class="sxs-lookup"><span data-stu-id="b02d5-173">View the app details, including the original app name **Short name from publisher**.</span></span>

   ![自定义图标面板应用名称](media/app-details-original-name.png)

   <span data-ttu-id="b02d5-175">只有在 **你更改了** 应用的短名称时，发布者的短名称字段才可见。</span><span class="sxs-lookup"><span data-stu-id="b02d5-175">The **Short name from publisher** field is only visible if you've changed the app's short name.</span></span>

## <a name="reset-app-details-to-default"></a><span data-ttu-id="b02d5-176">将应用详细信息重置为默认值</span><span class="sxs-lookup"><span data-stu-id="b02d5-176">Reset app details to default</span></span>

<span data-ttu-id="b02d5-177">你随时都可以将应用详细信息重置为原始设置。</span><span class="sxs-lookup"><span data-stu-id="b02d5-177">At any time, you can reset the app details to the original settings.</span></span>

1. <span data-ttu-id="b02d5-178">登录到 Teams 管理中心。</span><span class="sxs-lookup"><span data-stu-id="b02d5-178">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="b02d5-179">展开 **"Teams 应用"** 并选择"**管理应用"。**</span><span class="sxs-lookup"><span data-stu-id="b02d5-179">Expand **Teams Apps** and select **Manage apps**.</span></span>

3. <span data-ttu-id="b02d5-180">选择应用名称。</span><span class="sxs-lookup"><span data-stu-id="b02d5-180">Select the app name.</span></span>

4. <span data-ttu-id="b02d5-181">从 **"操作"下拉列表中选择\*\*\*\*"重置** 为默认值"。</span><span class="sxs-lookup"><span data-stu-id="b02d5-181">Select **Reset to default** from the **Actions** dropdown.</span></span>

   ![选择"重置为默认"突出显示](media/select-reset.png)

## <a name="frequently-asked-questions"></a><span data-ttu-id="b02d5-183">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="b02d5-183">Frequently asked questions</span></span>

<span data-ttu-id="b02d5-184">**我的用户需要多久来查看自定义应用？**</span><span class="sxs-lookup"><span data-stu-id="b02d5-184">**How long will it take for my users to see the customized app?**</span></span>

<span data-ttu-id="b02d5-185">虽然管理员可以立即在 Teams 管理中心看到更改，但最终用户最多可能需要 24 小时才能看到更改。</span><span class="sxs-lookup"><span data-stu-id="b02d5-185">Although the admin can immediately see the changes in Teams Admin Center, it might take up to 24 hours for the end users to see the changes.</span></span>  

<span data-ttu-id="b02d5-186">**应用提供商是否可为客户自定义应用？**</span><span class="sxs-lookup"><span data-stu-id="b02d5-186">**Can the app provider customize the app for its customers?**</span></span>

 <span data-ttu-id="b02d5-187">否，租户的管理员需要使用 Teams 管理中心为租户自定义应用。</span><span class="sxs-lookup"><span data-stu-id="b02d5-187">No, the admin of a tenant needs to customize the app for their tenant using the Teams Admin Center.</span></span>

<span data-ttu-id="b02d5-188">**自定义应用会自动部署以替换租户中的当前自定义应用吗？**</span><span class="sxs-lookup"><span data-stu-id="b02d5-188">**Will the customized app automatically get deployed to replace my current custom app in a tenant?**</span></span>

<span data-ttu-id="b02d5-189">否，租户管理员必须手动删除任何自定义应用并发布应用的自定义版本。</span><span class="sxs-lookup"><span data-stu-id="b02d5-189">No, the tenant admins will have to manually remove any custom app and publish the customized version of the app.</span></span> <span data-ttu-id="b02d5-190">如果你已自定义应用并将其发布为自定义应用，则使用应用自定义功能自定义的新应用不会替换当前的自定义应用。</span><span class="sxs-lookup"><span data-stu-id="b02d5-190">If you have customized an app and published it as a custom app, the new app customized using the app customization feature won't replace the current custom app.</span></span>  

<span data-ttu-id="b02d5-191">**应用使用情况报告还会显示自定义值（如自定义短名称）吗？**</span><span class="sxs-lookup"><span data-stu-id="b02d5-191">**Will the app usage report also show the customized values such as customized short name?**</span></span>

 <span data-ttu-id="b02d5-192">否，应用使用情况报告仍将显示从发布者发送的应用的原始名称。</span><span class="sxs-lookup"><span data-stu-id="b02d5-192">No, the app usage report will still show the original name of the app sent from the publisher.</span></span>

<span data-ttu-id="b02d5-193">**可以使用应用自定义功能自定义哪些应用？**</span><span class="sxs-lookup"><span data-stu-id="b02d5-193">**Which apps can I customize using the app customization feature?**</span></span>

<span data-ttu-id="b02d5-194">只能自定义应用发布者允许自定义的应用。</span><span class="sxs-lookup"><span data-stu-id="b02d5-194">You can only customize apps that have been allowed to be customizable by the app publisher.</span></span> <span data-ttu-id="b02d5-195">应用发布者将需要选择加入以允许其客户自定义应用。</span><span class="sxs-lookup"><span data-stu-id="b02d5-195">The app publisher will need to opt in to allow its customers to customize the app.</span></span>

<span data-ttu-id="b02d5-196">**自定义属性会显示在图形权限许可屏幕上吗？**</span><span class="sxs-lookup"><span data-stu-id="b02d5-196">**Will the customized properties show up on the graph permission consent screen?**</span></span>

<span data-ttu-id="b02d5-197">否，权限许可屏幕仍将显示发布者发送的原始值。</span><span class="sxs-lookup"><span data-stu-id="b02d5-197">No, the permission consent screen will still show the original value sent by the publisher.</span></span>

## <a name="related-article"></a><span data-ttu-id="b02d5-198">相关文章</span><span class="sxs-lookup"><span data-stu-id="b02d5-198">Related article</span></span>

- [<span data-ttu-id="b02d5-199">管理应用</span><span class="sxs-lookup"><span data-stu-id="b02d5-199">Manage apps</span></span>](manage-apps.md)
- [<span data-ttu-id="b02d5-200">自定义应用商店</span><span class="sxs-lookup"><span data-stu-id="b02d5-200">Customize your app store</span></span>](customize-your-app-store.md)
