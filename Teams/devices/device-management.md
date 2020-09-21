---
title: 在 Microsoft Teams 中管理设备
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
ms.custom:
- ms.teamsadmincenter.managedevices.overview
- ms.teamsadmincenter.devicemanagement.overview
description: 了解如何管理组织中与团队一起使用的设备。
localization_priority: Normal
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9ac6c0b503266a83033a72940ea6572feeaffaf5
ms.sourcegitcommit: b255db7ef816d1884c9c71af86a901bd83a1d9ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "47964793"
---
# <a name="manage-your-devices-in-microsoft-teams"></a><span data-ttu-id="fbde2-103">在 Microsoft Teams 中管理设备</span><span class="sxs-lookup"><span data-stu-id="fbde2-103">Manage your devices in Microsoft Teams</span></span>

<span data-ttu-id="fbde2-104">你可以从 Microsoft 团队管理中心管理你的组织中的 Microsoft 团队使用的设备。</span><span class="sxs-lookup"><span data-stu-id="fbde2-104">You can manage devices used with Microsoft Teams in your organization from the Microsoft Teams admin center.</span></span> <span data-ttu-id="fbde2-105">你可以查看和管理你的组织的设备清单，并执行一些任务，如更新、重启和监视设备诊断。</span><span class="sxs-lookup"><span data-stu-id="fbde2-105">You can view and manage the device inventory for your organization and do tasks such as update, restart, and monitor diagnostics for devices.</span></span> <span data-ttu-id="fbde2-106">你还可以创建配置文件并将其分配给设备或设备组。</span><span class="sxs-lookup"><span data-stu-id="fbde2-106">You can also create and assign configuration profiles to a device or groups of devices.</span></span>

<span data-ttu-id="fbde2-107">若要管理设备（如更改设备配置、重启设备、管理更新或查看设备和外围设备运行状况），您需要分配以下 Microsoft 365 管理员角色之一：</span><span class="sxs-lookup"><span data-stu-id="fbde2-107">To manage devices, such as changing device configuration, restarting devices, managing updates, or viewing device and peripheral health, you need to be assigned one of the following Microsoft 365 admin roles:</span></span>

- <span data-ttu-id="fbde2-108">Microsoft 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="fbde2-108">Microsoft 365 Global admin</span></span>
- <span data-ttu-id="fbde2-109">团队服务管理员</span><span class="sxs-lookup"><span data-stu-id="fbde2-109">Teams Service admin</span></span>
- <span data-ttu-id="fbde2-110">团队设备管理员</span><span class="sxs-lookup"><span data-stu-id="fbde2-110">Teams Device admin</span></span>

<span data-ttu-id="fbde2-111">有关团队中的管理员角色的详细信息，请参阅 [使用 Microsoft 团队管理员角色管理团队](../using-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="fbde2-111">For more information about admin roles in Teams, see [Use Microsoft Teams administrator roles to manage Teams](../using-admin-roles.md).</span></span>

## <a name="what-devices-can-you-manage"></a><span data-ttu-id="fbde2-112">可以管理哪些设备？</span><span class="sxs-lookup"><span data-stu-id="fbde2-112">What devices can you manage?</span></span>

<span data-ttu-id="fbde2-113">你可以管理已认证且已注册团队的任何设备。</span><span class="sxs-lookup"><span data-stu-id="fbde2-113">You can manage any device that's certified for, and enrolled in, Teams.</span></span> <span data-ttu-id="fbde2-114">当用户第一次登录设备上的团队时，将自动注册设备。</span><span class="sxs-lookup"><span data-stu-id="fbde2-114">A device is automatically enrolled the first time a user signs into Teams on the device.</span></span> <span data-ttu-id="fbde2-115">有关可管理的认证设备的列表，请参阅：</span><span class="sxs-lookup"><span data-stu-id="fbde2-115">For a list of certified devices that can be managed, see:</span></span>

- [<span data-ttu-id="fbde2-116">Microsoft Teams 会议室</span><span class="sxs-lookup"><span data-stu-id="fbde2-116">Microsoft Teams Rooms</span></span>](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=20)
- [<span data-ttu-id="fbde2-117">会议电话</span><span class="sxs-lookup"><span data-stu-id="fbde2-117">Conference phones</span></span>](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73)
- [<span data-ttu-id="fbde2-118">桌面电话</span><span class="sxs-lookup"><span data-stu-id="fbde2-118">Desk phones</span></span>](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- [<span data-ttu-id="fbde2-119">协作栏</span><span class="sxs-lookup"><span data-stu-id="fbde2-119">Collaboration bars</span></span>](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=16)

<span data-ttu-id="fbde2-120">这些设备在 [Microsoft 团队管理中心](https://admin.teams.microsoft.com) 中管理，并在左侧导航中的 " **设备**" 下拥有各自的分区。</span><span class="sxs-lookup"><span data-stu-id="fbde2-120">These devices are managed the in the [Microsoft Teams admin center](https://admin.teams.microsoft.com) and have their own respective sections in the left navigation under **Devices**.</span></span> <span data-ttu-id="fbde2-121">这使你可以单独管理每种类型的设备。</span><span class="sxs-lookup"><span data-stu-id="fbde2-121">This lets you manage each type of device separately.</span></span>

## <a name="manage-teams-rooms-devices"></a><span data-ttu-id="fbde2-122">管理团队聊天室设备</span><span class="sxs-lookup"><span data-stu-id="fbde2-122">Manage Teams Rooms devices</span></span>

<span data-ttu-id="fbde2-123">你可以使用团队管理中心在你的组织内查看和远程管理团队聊天室设备。</span><span class="sxs-lookup"><span data-stu-id="fbde2-123">You can use the Teams admin center to view and remotely manage your Teams Rooms devices across your organization.</span></span> <span data-ttu-id="fbde2-124">团队管理中心使你可以轻松查看哪些设备运行正常，哪些设备需要引起注意，让你专注于特定设备以查看有关设备运行状况、会议性能、呼叫质量和外围设备的详细信息。</span><span class="sxs-lookup"><span data-stu-id="fbde2-124">The Teams admin center makes it easy to see, at a glance, which devices are healthy and which need attention, and lets you focus on specific devices to see detailed information about device health, meeting performance, call quality, and peripherals.</span></span> 

<span data-ttu-id="fbde2-125">下面是可用于管理团队聊天室设备的一些操作。</span><span class="sxs-lookup"><span data-stu-id="fbde2-125">Here are some things you can do to manage your Teams Rooms devices.</span></span> <span data-ttu-id="fbde2-126">团队聊天室设备可在 "**设备**团队" 会议室下的 " [Microsoft 团队管理中心](https://admin.teams.microsoft.com)" 中找到  >  **Teams Rooms**。</span><span class="sxs-lookup"><span data-stu-id="fbde2-126">Teams Rooms devices can be found in the [Microsoft Teams admin center](https://admin.teams.microsoft.com) under **Devices** > **Teams Rooms**.</span></span>

<span data-ttu-id="fbde2-127">有关如何管理团队聊天室设备的详细信息，请参阅 [管理 Microsoft 团队聊天室](../rooms/rooms-manage.md)。</span><span class="sxs-lookup"><span data-stu-id="fbde2-127">For details about how to manage your Teams Rooms devices, see [Manage Microsoft Teams Rooms](../rooms/rooms-manage.md).</span></span>

| <span data-ttu-id="fbde2-128">若要执行此操作 .。。</span><span class="sxs-lookup"><span data-stu-id="fbde2-128">To do this...</span></span> | <span data-ttu-id="fbde2-129">要执行的操作</span><span class="sxs-lookup"><span data-stu-id="fbde2-129">Do this</span></span>|
|---------------|--------|
| <span data-ttu-id="fbde2-130">在一个或多个设备上更改设置</span><span class="sxs-lookup"><span data-stu-id="fbde2-130">Change settings on one or more devices</span></span> | <span data-ttu-id="fbde2-131">选择一个或多个设备 > " **编辑设置**"。</span><span class="sxs-lookup"><span data-stu-id="fbde2-131">Select one or more devices > **Edit settings**.</span></span> <span data-ttu-id="fbde2-132">如果你选择多个设备，你更改的值将替换所有选定设备上的值。</span><span class="sxs-lookup"><span data-stu-id="fbde2-132">If you select multiple devices, the values you change will replace the values on all the selected devices.</span></span> |
| <span data-ttu-id="fbde2-133">重启设备</span><span class="sxs-lookup"><span data-stu-id="fbde2-133">Restart devices</span></span> | <span data-ttu-id="fbde2-134">选择一个或多个设备 > **重启**。</span><span class="sxs-lookup"><span data-stu-id="fbde2-134">Select one or more devices > **Restart**.</span></span> <span data-ttu-id="fbde2-135">重新启动设备时，可以选择是立即重新启动设备，还是选择 " **计划重启** " 以在特定日期和时间重启设备。</span><span class="sxs-lookup"><span data-stu-id="fbde2-135">When you restart a device, you can choose whether to restart the device immediately or select **Schedule restart** to restart the device at a specific date and time.</span></span> <span data-ttu-id="fbde2-136">您选择的日期和时间对重新启动的设备而言是本地的。</span><span class="sxs-lookup"><span data-stu-id="fbde2-136">The date and time you select are local to the device being restarted.</span></span>|
| <span data-ttu-id="fbde2-137">查看会议活动</span><span class="sxs-lookup"><span data-stu-id="fbde2-137">View meeting activity</span></span> | <span data-ttu-id="fbde2-138">选择设备名称以打开 "设备详细信息" > " **活动**"。</span><span class="sxs-lookup"><span data-stu-id="fbde2-138">Select a device name to open device details > **Activity**.</span></span> <span data-ttu-id="fbde2-139">打开 " **活动** " 选项卡时，你可以看到设备参与的所有会议。</span><span class="sxs-lookup"><span data-stu-id="fbde2-139">When you open the **Activity** tab, you can see all the meetings that the device has participated in.</span></span> <span data-ttu-id="fbde2-140">此摘要视图显示会议开始时间、参与者数、持续时间和整体通话质量。</span><span class="sxs-lookup"><span data-stu-id="fbde2-140">This summary view shows the meeting start time, the number of participants, its duration, and the overall call quality.</span></span>|
| <span data-ttu-id="fbde2-141">查看会议详细信息</span><span class="sxs-lookup"><span data-stu-id="fbde2-141">View meeting details</span></span> |  <span data-ttu-id="fbde2-142">选择设备名称以打开 "设备详细信息" > " **活动** " > 选择会议。</span><span class="sxs-lookup"><span data-stu-id="fbde2-142">Select a device name to open device details > **Activity** > select a meeting.</span></span> <span data-ttu-id="fbde2-143">当您打开会议的详细信息时，您可以查看会议中的所有参与者、通话时间、团队授课类型以及个人通话质量。</span><span class="sxs-lookup"><span data-stu-id="fbde2-143">When you open a meeting's details, you can see all of the participants in the meeting, how long they were in the call, the Teams session types, and their individual call quality.</span></span> <span data-ttu-id="fbde2-144">如果您想要查看有关参与者的通话的技术信息，请选择参与者的通话开始时间。</span><span class="sxs-lookup"><span data-stu-id="fbde2-144">If you want to see technical information about a participant's call, select the participant's call start time.</span></span>|

## <a name="manage-phones-and-collaboration-bars-in-teams"></a><span data-ttu-id="fbde2-145">管理团队中的电话和协作栏</span><span class="sxs-lookup"><span data-stu-id="fbde2-145">Manage phones and collaboration bars in Teams</span></span>

<span data-ttu-id="fbde2-146">在 "团队管理中心" 中，您可以查看和管理您的组织中已注册团队的手机和协作栏。</span><span class="sxs-lookup"><span data-stu-id="fbde2-146">In the Teams admin center, you can view and manage phones and collaboration bars enrolled in Teams in your organization.</span></span> <span data-ttu-id="fbde2-147">您将看到的每个设备的信息包括设备名称、制造商、型号、用户、状态、操作、上次查看和历史记录。</span><span class="sxs-lookup"><span data-stu-id="fbde2-147">Information that you'll see for each device includes device name, manufacturer, model, user, status, action, last seen, and history.</span></span> <span data-ttu-id="fbde2-148">你可以自定义视图以显示符合你的需求的信息。</span><span class="sxs-lookup"><span data-stu-id="fbde2-148">You can customize the view to show the information that fits your needs.</span></span>

<span data-ttu-id="fbde2-149">如果你注册了手机和协作栏，则会在 Microsoft Intune 中自动注册。</span><span class="sxs-lookup"><span data-stu-id="fbde2-149">Phones and collaboration bars are automatically enrolled in Microsoft Intune, if you've signed up for it.</span></span> <span data-ttu-id="fbde2-150">注册设备后，将确认设备合规性，并将条件访问策略应用到设备。</span><span class="sxs-lookup"><span data-stu-id="fbde2-150">After a device is enrolled, device compliance is confirmed and conditional access policies are applied to the device.</span></span>

<span data-ttu-id="fbde2-151">下面是如何管理组织中的电话和协作栏的一些示例。</span><span class="sxs-lookup"><span data-stu-id="fbde2-151">Here are some examples of how you can manage phones and collaboration bars in your organization.</span></span>  

|<span data-ttu-id="fbde2-152">若要执行此操作 .。。</span><span class="sxs-lookup"><span data-stu-id="fbde2-152">To do this...</span></span>  |<span data-ttu-id="fbde2-153">要执行的操作</span><span class="sxs-lookup"><span data-stu-id="fbde2-153">Do this</span></span> |
|---------|---------|
| <span data-ttu-id="fbde2-154">更改设备信息</span><span class="sxs-lookup"><span data-stu-id="fbde2-154">Change device information</span></span>               | <span data-ttu-id="fbde2-155">选择 > **编辑**的设备。</span><span class="sxs-lookup"><span data-stu-id="fbde2-155">Select a device > **Edit**.</span></span> <span data-ttu-id="fbde2-156">你可以编辑设备名称、资产标记和添加笔记等详细信息。</span><span class="sxs-lookup"><span data-stu-id="fbde2-156">You can edit details such as device name, asset tag, and add notes.</span></span>     |
| <span data-ttu-id="fbde2-157">管理软件更新</span><span class="sxs-lookup"><span data-stu-id="fbde2-157">Manage software updates</span></span>                 | <span data-ttu-id="fbde2-158">选择 > **更新**的设备。</span><span class="sxs-lookup"><span data-stu-id="fbde2-158">Select a device > **Update**.</span></span> <span data-ttu-id="fbde2-159">你可以查看适用于该设备的软件和固件更新的列表，并选择要安装的更新。</span><span class="sxs-lookup"><span data-stu-id="fbde2-159">You can view the list of software and firmware updates available for the device and choose the updates to install.</span></span> <span data-ttu-id="fbde2-160">有关更新设备的详细信息，请参阅 [远程更新 Microsoft 团队设备](remote-update.md)</span><span class="sxs-lookup"><span data-stu-id="fbde2-160">For more information about updating devices, see [Update Microsoft Teams devices remotely](remote-update.md)</span></span>   |
| <span data-ttu-id="fbde2-161">分配或更改配置策略</span><span class="sxs-lookup"><span data-stu-id="fbde2-161">Assign or change configuration policies</span></span> | <span data-ttu-id="fbde2-162">选择一个或多个设备 > " **分配配置**"。</span><span class="sxs-lookup"><span data-stu-id="fbde2-162">Select one or more devices > **Assign configuration**.</span></span>                                                                                                                                                                                                                   |
| <span data-ttu-id="fbde2-163">添加或删除设备标记</span><span class="sxs-lookup"><span data-stu-id="fbde2-163">Add or remove device tags</span></span>               | <span data-ttu-id="fbde2-164">选择一个或多个设备 > **管理标记**。</span><span class="sxs-lookup"><span data-stu-id="fbde2-164">Select one or more devices > **Manage tags**.</span></span> <span data-ttu-id="fbde2-165">有关设备标记的详细信息，请参阅 [管理和筛选 Microsoft 团队设备](manage-device-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="fbde2-165">For more information about device tags, see [Manage Manage and filter Microsoft Teams device](manage-device-tags.md).</span></span>                                                                                                      |
| <span data-ttu-id="fbde2-166">重启设备</span><span class="sxs-lookup"><span data-stu-id="fbde2-166">Restart devices</span></span>                         | <span data-ttu-id="fbde2-167">选择一个或多个设备 > **重启**。</span><span class="sxs-lookup"><span data-stu-id="fbde2-167">Select one or more devices > **Restart**.</span></span>                                                                                                                                                                                                                                |
| <span data-ttu-id="fbde2-168">使用设备标签筛选设备</span><span class="sxs-lookup"><span data-stu-id="fbde2-168">Filter devices using device tags</span></span>        | <span data-ttu-id="fbde2-169">选择 "筛选器" 图标，选择 " **标记** " 字段，指定要筛选的设备标记，然后选择 " **应用**"。</span><span class="sxs-lookup"><span data-stu-id="fbde2-169">Select the filter icon, select the **Tag** field, specify a device tag to filter on, and select **Apply**.</span></span> <span data-ttu-id="fbde2-170">有关使用设备标记对设备进行筛选的详细信息，请参阅 [使用筛选器返回具有特定标记的设备](manage-device-tags.md#use-filters-to-return-devices-with-a-specific-tag)。</span><span class="sxs-lookup"><span data-stu-id="fbde2-170">For more information about filtering devices using device tags, see [Use filters to return devices with a specific tag](manage-device-tags.md#use-filters-to-return-devices-with-a-specific-tag).</span></span>|
| <span data-ttu-id="fbde2-171">查看设备历史记录</span><span class="sxs-lookup"><span data-stu-id="fbde2-171">View device history</span></span>                     | <span data-ttu-id="fbde2-172">选择一个设备 > **历史记录**。</span><span class="sxs-lookup"><span data-stu-id="fbde2-172">Select a device > **History**.</span></span> <span data-ttu-id="fbde2-173">你可以查看设备的更新历史记录。</span><span class="sxs-lookup"><span data-stu-id="fbde2-173">You can view the update history for the device.</span></span>                                                                                                                                                                                |
| <span data-ttu-id="fbde2-174">查看诊断</span><span class="sxs-lookup"><span data-stu-id="fbde2-174">View diagnostics</span></span>                        | <span data-ttu-id="fbde2-175">选择一个设备 > **诊断**。</span><span class="sxs-lookup"><span data-stu-id="fbde2-175">Select a device > **Diagnostics**.</span></span>                                                                                                                                                                                                                            |


### <a name="use-configuration-profiles-in-teams"></a><span data-ttu-id="fbde2-176">使用团队中的配置文件</span><span class="sxs-lookup"><span data-stu-id="fbde2-176">Use configuration profiles in Teams</span></span>

<span data-ttu-id="fbde2-177">使用配置文件管理组织中的团队电话和协作栏的设置和功能。</span><span class="sxs-lookup"><span data-stu-id="fbde2-177">Use configuration profiles to manage settings and features for Teams phones and collaboration bars in your organization.</span></span> <span data-ttu-id="fbde2-178">你可以创建或上载配置文件，以包含要启用或禁用的设置和功能，然后将配置文件分配给设备或设备组。</span><span class="sxs-lookup"><span data-stu-id="fbde2-178">You can create or upload configuration profiles to include settings and features you want to enable or disable and then assign a profile to a device or groups of devices.</span></span> 

#### <a name="create-a-configuration-profile"></a><span data-ttu-id="fbde2-179">创建配置文件</span><span class="sxs-lookup"><span data-stu-id="fbde2-179">Create a configuration profile</span></span>

1. <span data-ttu-id="fbde2-180">在左侧导航中，转到 "**设备**  >  **配置文件**"。</span><span class="sxs-lookup"><span data-stu-id="fbde2-180">In the left navigation, go to **Devices** > **Configuration profiles**.</span></span>
2. <span data-ttu-id="fbde2-181">单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fbde2-181">Click **Add**.</span></span>
3. <span data-ttu-id="fbde2-182">输入配置文件的名称，如果需要，请添加一个友好描述。</span><span class="sxs-lookup"><span data-stu-id="fbde2-182">Enter a name for the profile and if you want, add a friendly description.</span></span>
4. <span data-ttu-id="fbde2-183">为配置文件指定所需的设置，然后单击 " **保存**"。</span><span class="sxs-lookup"><span data-stu-id="fbde2-183">Specify the settings you want for the profile, and then click **Save**.</span></span>

#### <a name="assign-a-configuration-profile"></a><span data-ttu-id="fbde2-184">分配配置文件</span><span class="sxs-lookup"><span data-stu-id="fbde2-184">Assign a configuration profile</span></span>

1. <span data-ttu-id="fbde2-185">在左侧导航中，转到 "**设备**  >  **配置文件**"。</span><span class="sxs-lookup"><span data-stu-id="fbde2-185">In the left navigation, go to **Devices** > **Configuration profiles**.</span></span>
2. <span data-ttu-id="fbde2-186">选择要分配的 **配置文件** ，然后单击 " **分配给设备**"。</span><span class="sxs-lookup"><span data-stu-id="fbde2-186">Select the **Configuration profile** you want to assign, and then click **Assign to device**.</span></span>  
3. <span data-ttu-id="fbde2-187">在 " **将设备分配给配置文件** 窗格" 中，搜索并选择要分配的设备。</span><span class="sxs-lookup"><span data-stu-id="fbde2-187">In the **Assign devices to a configuration profile** pane, search for and select the devices you want to assign.</span></span>
4. <span data-ttu-id="fbde2-188">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="fbde2-188">Click **Save**.</span></span>

