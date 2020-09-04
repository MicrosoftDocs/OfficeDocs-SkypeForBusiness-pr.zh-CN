---
title: 管理和筛选 Microsoft 团队设备标签
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: kelsawi
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
description: 了解如何在 Microsoft 团队设备上管理和筛选标记。
localization_priority: Normal
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: e5987588fd3df8f327502eace7f31b29483a2eba
ms.sourcegitcommit: ab56033346426a018a8a6920d67526a9772f644c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2020
ms.locfileid: "47363355"
---
# <a name="manage-microsoft-teams-device-tags"></a><span data-ttu-id="6d191-103">管理 Microsoft 团队设备标签</span><span class="sxs-lookup"><span data-stu-id="6d191-103">Manage Microsoft Teams device tags</span></span>

<span data-ttu-id="6d191-104">Microsoft 团队中的设备标记使你可以对你的组织中部署的设备进行分组、组织和更轻松地管理。</span><span class="sxs-lookup"><span data-stu-id="6d191-104">Device tags in Microsoft Teams let you group, organize, and more easily manage the devices you've deployed in your organization.</span></span> <span data-ttu-id="6d191-105">使用 Microsoft 团队管理中心，你可以向设备添加一个或多个标记，使用筛选器查看与你指定的标记匹配的设备，然后对具有该标记的设备执行操作。</span><span class="sxs-lookup"><span data-stu-id="6d191-105">With the Microsoft Teams admin center, you can add one or more tags to devices, use filters to view devices that match the tag you specify, and then perform actions the devices that have that tag.</span></span>

<span data-ttu-id="6d191-106">你可以将设备标记添加到多台设备类型。</span><span class="sxs-lookup"><span data-stu-id="6d191-106">You can add a device tag to more than one device type.</span></span> <span data-ttu-id="6d191-107">但是，当您在管理中心中打开设备窗格时，只会返回该类型的设备。</span><span class="sxs-lookup"><span data-stu-id="6d191-107">However, when you open a device pane in the admin center, only the devices of that type are returned.</span></span> <span data-ttu-id="6d191-108">例如，您可以将 "公司" 标记分配给电话和团队室设备。</span><span class="sxs-lookup"><span data-stu-id="6d191-108">For example, you can assign the "Corporate" tag to both phones and Teams Rooms devices.</span></span> <span data-ttu-id="6d191-109">如果在 "**设备**电话" 中搜索 "公司" 标记  >  **Phones**，则仅返回手机。</span><span class="sxs-lookup"><span data-stu-id="6d191-109">If you search for the "Corporate" tag while in **Devices** > **Phones**, only phones are returned.</span></span> <span data-ttu-id="6d191-110">同样，如果在 "**设备**" 团队聊天室中搜索 "公司" 标记  >  **Teams Rooms**，则仅返回团队会议室设备。</span><span class="sxs-lookup"><span data-stu-id="6d191-110">Similarly, if you search for the "Corporate" tag in **Devices** > **Teams Rooms**, only Teams Rooms devices are returned.</span></span>

<span data-ttu-id="6d191-111">若要管理设备标记，您必须是全局管理员或团队服务管理员。</span><span class="sxs-lookup"><span data-stu-id="6d191-111">To manage device tags, you need to be either a Global admin or a Teams service admin.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6d191-112">设备标记分配给登录设备的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="6d191-112">Device tags are assigned to the resource account that's logged into a device.</span></span> <span data-ttu-id="6d191-113">如果你将资源帐户从一个设备注销，然后使用它登录到其他设备，则设备标记将应用到新设备。</span><span class="sxs-lookup"><span data-stu-id="6d191-113">If you sign a resource account out of one device and then use it to sign into another devices, the device tags are applied to new device.</span></span>

## <a name="create-remove-or-rename-device-tags"></a><span data-ttu-id="6d191-114">创建、删除或重命名设备标签</span><span class="sxs-lookup"><span data-stu-id="6d191-114">Create, remove, or rename device tags</span></span>

<span data-ttu-id="6d191-115">使用 "设备标签管理" 面板，您可以：</span><span class="sxs-lookup"><span data-stu-id="6d191-115">Using the device tag management panel, you can:</span></span>

- <span data-ttu-id="6d191-116">查看所有设备标记。</span><span class="sxs-lookup"><span data-stu-id="6d191-116">See all your device tags.</span></span>
- <span data-ttu-id="6d191-117">轻松创建多个设备标记，稍后再将其分配给设备。</span><span class="sxs-lookup"><span data-stu-id="6d191-117">Create multiple device tags easily and then assign them to devices at a later time.</span></span> <span data-ttu-id="6d191-118">标记最多可以有25个字符。</span><span class="sxs-lookup"><span data-stu-id="6d191-118">Tags can be up to 25 characters.</span></span>
- <span data-ttu-id="6d191-119">删除不再需要的设备标记。</span><span class="sxs-lookup"><span data-stu-id="6d191-119">Remove device tags that are no longer needed.</span></span> <span data-ttu-id="6d191-120">在删除设备标记之前，你需要将其从已添加的所有设备中删除。</span><span class="sxs-lookup"><span data-stu-id="6d191-120">Before you can remove a device tag, you'll need to remove it from all of the devices it has been added to.</span></span>
- <span data-ttu-id="6d191-121">重命名设备标签。</span><span class="sxs-lookup"><span data-stu-id="6d191-121">Rename device tags.</span></span> <span data-ttu-id="6d191-122">重命名设备标记时，该更改将反映在已添加到的所有设备上。</span><span class="sxs-lookup"><span data-stu-id="6d191-122">When you rename a device tag, that change is reflected on all the devices it's been added to.</span></span> <span data-ttu-id="6d191-123">标记最多可以有25个字符。</span><span class="sxs-lookup"><span data-stu-id="6d191-123">Tags can be up to 25 characters.</span></span>

1. <span data-ttu-id="6d191-124">通过访问登录到 Microsoft 团队管理中心 https://admin.teams.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="6d191-124">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="6d191-125">导航到 " **设备** "，然后选择任意设备窗格，如 " **电话**"。</span><span class="sxs-lookup"><span data-stu-id="6d191-125">Navigate to **Devices** and then choose any device pane, such as **Phones**.</span></span>
3. <span data-ttu-id="6d191-126">选择页面右上角的 " **操作** "，然后选择 " **所有设备标签**"。</span><span class="sxs-lookup"><span data-stu-id="6d191-126">Select **Actions** in the upper-right corner of the page and select **All device tags**.</span></span>
4. <span data-ttu-id="6d191-127">若要创建设备标记，请选择 " **+ 添加**"，为设备标记提供一个值，然后选择 " **保存** " 图标。</span><span class="sxs-lookup"><span data-stu-id="6d191-127">To create a device tag, select **+ Add**, provide a value for the device tag, and select the **Save** icon.</span></span>
5. <span data-ttu-id="6d191-128">若要删除设备标记，请选择要删除的设备标记旁边 **的省略号 "..."** ，然后选择 " **删除**"。</span><span class="sxs-lookup"><span data-stu-id="6d191-128">To remove a device tag, select the ellipsis **...** next to the device tag you want to remove, and select **Delete**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="6d191-129">如果你尝试删除已添加到设备的设备标记，你将收到一条消息，询问你是否要将其从所有设备中删除。</span><span class="sxs-lookup"><span data-stu-id="6d191-129">If you try to remove a device tag that's been added to devices, you'll receive a message asking if you want to remove it from all devices.</span></span> <span data-ttu-id="6d191-130">如果要执行此操作并继续删除设备标记，请选择 " **取消标记设备**"。</span><span class="sxs-lookup"><span data-stu-id="6d191-130">If you want to do this and continue to remove the device tag, select **Untag devices**.</span></span>
6. <span data-ttu-id="6d191-131">若要重命名设备标记，请选择要重命名的设备 **标记旁边的省略号 "..."** ，然后选择 " **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="6d191-131">To rename a device tag, select the ellipsis **...** next to the device tag you want to rename, and select **Edit**.</span></span> <span data-ttu-id="6d191-132">为设备标签提供新值，然后选择 " **保存** " 图标。</span><span class="sxs-lookup"><span data-stu-id="6d191-132">Provide a new value for the device tag and select the **Save** icon.</span></span>

## <a name="add-or-remove-tags-on-a-single-device"></a><span data-ttu-id="6d191-133">在单个设备上添加或删除标记</span><span class="sxs-lookup"><span data-stu-id="6d191-133">Add or remove tags on a single device</span></span>

<span data-ttu-id="6d191-134">将标记添加到设备时，可以选择现有标记或创建一个新标记。</span><span class="sxs-lookup"><span data-stu-id="6d191-134">When you add tags to a device, you can either select an existing tag or create a new one.</span></span> <span data-ttu-id="6d191-135">标记最多可以有25个字符。</span><span class="sxs-lookup"><span data-stu-id="6d191-135">Tags can be up to 25 characters.</span></span>

1. <span data-ttu-id="6d191-136">通过访问登录到 Microsoft 团队管理中心 https://admin.teams.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="6d191-136">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="6d191-137">导航到 " **设备** "，然后选择包含要在其上添加或删除标记的设备的设备窗格。</span><span class="sxs-lookup"><span data-stu-id="6d191-137">Navigate to **Devices** and then choose the device pane that contains the device you want to add or remove tags on.</span></span>
3. <span data-ttu-id="6d191-138">在要添加或删除标记的设备旁边放置复选标记，然后选择 " **管理标记**"。</span><span class="sxs-lookup"><span data-stu-id="6d191-138">Place a check mark next to the device you want to add or remove tags on and select **Manage tags**.</span></span>
4. <span data-ttu-id="6d191-139">如果要添加标记：</span><span class="sxs-lookup"><span data-stu-id="6d191-139">If you want to add a tag:</span></span>
    1. <span data-ttu-id="6d191-140">开始键入要添加的标记名称。</span><span class="sxs-lookup"><span data-stu-id="6d191-140">Start typing the tag name you want to add.</span></span>
    2. <span data-ttu-id="6d191-141">如果该标记已存在，请从返回的标记列表中选择它。</span><span class="sxs-lookup"><span data-stu-id="6d191-141">If the tag already exists, select it from the list of tags that are returned.</span></span>
    3. <span data-ttu-id="6d191-142">如果标记不存在，请选择 **"添加" \<tag name> 作为新标记**。</span><span class="sxs-lookup"><span data-stu-id="6d191-142">If the tag doesn't exist, select **Add "\<tag name>" as a new tag**.</span></span> <span data-ttu-id="6d191-143">标记最多可以有25个字符。</span><span class="sxs-lookup"><span data-stu-id="6d191-143">Tags can be up to 25 characters.</span></span>
5. <span data-ttu-id="6d191-144">如果要删除标记，请选择要删除的标记旁边的 " **X** "。</span><span class="sxs-lookup"><span data-stu-id="6d191-144">If you want to remove a tag, select **X** next to the tag you want to remove.</span></span>
6. <span data-ttu-id="6d191-145">如果要添加或删除更多标记，请重复上面的步骤。</span><span class="sxs-lookup"><span data-stu-id="6d191-145">Repeat the steps above if you want to add or remove more tags.</span></span>
7. <span data-ttu-id="6d191-146">选择 " **应用**"。</span><span class="sxs-lookup"><span data-stu-id="6d191-146">Select **Apply**.</span></span>

## <a name="add-or-remove-tags-on-multiple-devices"></a><span data-ttu-id="6d191-147">在多台设备上添加或删除标记</span><span class="sxs-lookup"><span data-stu-id="6d191-147">Add or remove tags on multiple devices</span></span>

<span data-ttu-id="6d191-148">将标记添加到设备时，可以选择现有标记或创建一个新标记。</span><span class="sxs-lookup"><span data-stu-id="6d191-148">When you add tags to a device, you can either select an existing tag or create a new one.</span></span> <span data-ttu-id="6d191-149">标记最多可以有25个字符。</span><span class="sxs-lookup"><span data-stu-id="6d191-149">Tags can be up to 25 characters.</span></span> <span data-ttu-id="6d191-150">如果你想要从多个设备中删除标记，你需要选择与设备关联的团队用户并删除用户的标记。</span><span class="sxs-lookup"><span data-stu-id="6d191-150">If you want to remove a tag from multiple devices, you need to select the Teams user that's associated with the device and remove the tag from the user.</span></span>

1. <span data-ttu-id="6d191-151">通过访问登录到 Microsoft 团队管理中心 https://admin.teams.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="6d191-151">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="6d191-152">导航到 " **设备** "，然后选择包含要在其上添加或删除标记的设备的设备窗格。</span><span class="sxs-lookup"><span data-stu-id="6d191-152">Navigate to **Devices** and then choose the device pane that contains the devices you want to add or remove tags on.</span></span>
3. <span data-ttu-id="6d191-153">在要添加或删除标记的设备旁边放置复选标记，然后选择 " **管理标记**"。</span><span class="sxs-lookup"><span data-stu-id="6d191-153">Place a check mark next to the devices you want to add or remove tags on and select **Manage tags**.</span></span>
4. <span data-ttu-id="6d191-154">如果要添加标记：</span><span class="sxs-lookup"><span data-stu-id="6d191-154">If you want to add a tag:</span></span>
    1. <span data-ttu-id="6d191-155">开始键入要在 " **管理所有设备用户的设备" 标记**中添加的标记名称。</span><span class="sxs-lookup"><span data-stu-id="6d191-155">Start typing the tag name you want to add in **Manage tags for all devices of Teams users**.</span></span>
    2. <span data-ttu-id="6d191-156">如果该标记已存在，请从返回的标记列表中选择它。</span><span class="sxs-lookup"><span data-stu-id="6d191-156">If the tag already exists, select it from the list of tags that are returned.</span></span>
    3. <span data-ttu-id="6d191-157">如果标记不存在，请选择 **"添加" \<tag name> 作为新标记**。</span><span class="sxs-lookup"><span data-stu-id="6d191-157">If the tag doesn't exist, select **Add "\<tag name>" as a new tag**.</span></span>
5. <span data-ttu-id="6d191-158">如果要删除标记，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6d191-158">If you want to remove a tag:</span></span>
    1. <span data-ttu-id="6d191-159">展开 " **选择团队用户**"。</span><span class="sxs-lookup"><span data-stu-id="6d191-159">Expand **Select Teams users**.</span></span>
    2. <span data-ttu-id="6d191-160">展开要从中删除标记的团队用户的姓名下的\*\* \<x> 标记\*\*。</span><span class="sxs-lookup"><span data-stu-id="6d191-160">Expand **\<x> tags** under the name of the Teams user you want to remove tags from.</span></span>
    3. <span data-ttu-id="6d191-161">选择要删除的标记旁边的 " **X** "。</span><span class="sxs-lookup"><span data-stu-id="6d191-161">Select **X** next to the tag you want to remove.</span></span>
6. <span data-ttu-id="6d191-162">如果要添加或删除更多标记，请重复上面的步骤。</span><span class="sxs-lookup"><span data-stu-id="6d191-162">Repeat the steps above if you want to add or remove more tags.</span></span>
7. <span data-ttu-id="6d191-163">选择 " **应用**"。</span><span class="sxs-lookup"><span data-stu-id="6d191-163">Select **Apply**.</span></span>

## <a name="use-filters-to-return-devices-with-a-specific-tag"></a><span data-ttu-id="6d191-164">使用筛选器返回具有特定标记的设备</span><span class="sxs-lookup"><span data-stu-id="6d191-164">Use filters to return devices with a specific tag</span></span>

<span data-ttu-id="6d191-165">如果你已将设备标记添加到你的设备，则可以使用它们来筛选设备列表，以仅返回已向其添加了指定标记的设备。</span><span class="sxs-lookup"><span data-stu-id="6d191-165">If you've added device tags to your devices, you can use them to filter the device list to return only the devices that have had a specified tag added to them.</span></span> <span data-ttu-id="6d191-166">如果你只想查看特定聊天室中的所有设备、特定类型的所有设备或添加标记时使用的任何其他条件，这可能会很有用。</span><span class="sxs-lookup"><span data-stu-id="6d191-166">This can be helpful if you just want to view all the devices in a specific room, all the devices of a certain type, or any other criteria you used when adding your tags.</span></span> <span data-ttu-id="6d191-167">你还可以在返回的设备上执行批量操作，例如以波形方式应用更新或设置不同的配置策略，具体取决于使用设备标记确定的设备组。</span><span class="sxs-lookup"><span data-stu-id="6d191-167">You can also perform bulk actions on returned devices, such as applying updates in waves, or setting different configuration policies depending on the groups of devices identified using device tags.</span></span>

1. <span data-ttu-id="6d191-168">通过访问登录到 Microsoft 团队管理中心 https://admin.teams.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="6d191-168">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="6d191-169">导航到 " **设备** "，然后选择包含要筛选的设备的设备窗格。</span><span class="sxs-lookup"><span data-stu-id="6d191-169">Navigate to **Devices** and then choose the device pane that contains the devices you want to filter.</span></span>
3. <span data-ttu-id="6d191-170">选择 " **筛选器** " 图标。</span><span class="sxs-lookup"><span data-stu-id="6d191-170">Select the **Filter** icon.</span></span>
4. <span data-ttu-id="6d191-171">如果你只想指定单个标记，或者想要查找具有你指定的所有标记的设备，请选择 " **匹配所有这些条件**"。</span><span class="sxs-lookup"><span data-stu-id="6d191-171">If you only want to specify a single tag, or if you want to find devices that have all the tags you specify, select **Match all of these conditions**.</span></span>
5. <span data-ttu-id="6d191-172">如果要查找与一个或多个设备标记匹配的设备，请选择 " **匹配其中任一条件**"。</span><span class="sxs-lookup"><span data-stu-id="6d191-172">If you want to find devices that match one or more device tags, select **Match any one of these conditions**.</span></span>
6. <span data-ttu-id="6d191-173">选择 " **标记** " 字段，然后在 " **输入值** " 字段中指定设备标记名称。</span><span class="sxs-lookup"><span data-stu-id="6d191-173">Select the **Tag** field and then specify a device tag name in the **Enter a value** field.</span></span>
7. <span data-ttu-id="6d191-174">如果要添加更多设备标记，请选择 " **添加更多** "，然后为要添加的每个标记重复步骤6。</span><span class="sxs-lookup"><span data-stu-id="6d191-174">If you want to add more device tags, select **Add more** and repeat step 6 for each tag you want to add.</span></span>
8. <span data-ttu-id="6d191-175">选择 " **应用**"。</span><span class="sxs-lookup"><span data-stu-id="6d191-175">Select **Apply**.</span></span>

<span data-ttu-id="6d191-176">在设备列表中筛选设备后，您可以像平常一样对其执行操作。</span><span class="sxs-lookup"><span data-stu-id="6d191-176">After you've filtered the devices in your device list, you can perform actions on them as you normally would.</span></span> <span data-ttu-id="6d191-177">例如，你可以选择它们，然后分配配置、编辑其设置 (如果它们是团队会议室设备) 等。</span><span class="sxs-lookup"><span data-stu-id="6d191-177">For example, you can select them and then assign configurations, edit their settings (if they're Teams Rooms devices), and so on.</span></span> <span data-ttu-id="6d191-178">完成后，您可以通过选择**标记**筛选器条目旁边的**X**或选择列表右侧的 "**全部清除**" 来删除筛选。</span><span class="sxs-lookup"><span data-stu-id="6d191-178">When you're done, you can remove the filter by selecting the **X**  next to the **Tag** filter entry or by selecting **Clear all** on the right side of the list.</span></span>
