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
appliesto:
- Microsoft Teams
ms.openlocfilehash: ef6412ff40d71a21f619b08ee5e334819d5470ca
ms.sourcegitcommit: a597b1572f1eca095144288446a2c038e5daa5f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/10/2020
ms.locfileid: "42587298"
---
# <a name="manage-your-devices-in-microsoft-teams"></a><span data-ttu-id="3c591-103">在 Microsoft Teams 中管理设备</span><span class="sxs-lookup"><span data-stu-id="3c591-103">Manage your devices in Microsoft Teams</span></span>

<span data-ttu-id="3c591-104">作为管理员，你可以管理来自 Microsoft 团队管理中心的组织中的团队使用的设备。</span><span class="sxs-lookup"><span data-stu-id="3c591-104">As an admin, you can manage devices used with Teams in your organization from the Microsoft Teams admin center.</span></span> <span data-ttu-id="3c591-105">你可以查看和管理你的组织的设备清单，并执行一些任务，如更新、重启和监视设备诊断。</span><span class="sxs-lookup"><span data-stu-id="3c591-105">You can view and manage the device inventory for your organization and do tasks such as update, restart, and monitor diagnostics for devices.</span></span> <span data-ttu-id="3c591-106">你还可以创建配置文件并将其分配给设备或设备组。</span><span class="sxs-lookup"><span data-stu-id="3c591-106">You can also create and assign configuration profiles to a device or groups of devices.</span></span> 

## <a name="what-devices-can-you-manage"></a><span data-ttu-id="3c591-107">可以管理哪些设备？</span><span class="sxs-lookup"><span data-stu-id="3c591-107">What devices can you manage?</span></span>
<span data-ttu-id="3c591-108">你可以管理已认证且已注册团队的任何设备。</span><span class="sxs-lookup"><span data-stu-id="3c591-108">You can manage any device that's certified for, and enrolled in, Teams.</span></span> <span data-ttu-id="3c591-109">当用户第一次登录设备上的团队时，将自动注册设备。</span><span class="sxs-lookup"><span data-stu-id="3c591-109">A device is automatically enrolled the first time a user signs in to Teams on the device.</span></span> <span data-ttu-id="3c591-110">有关可管理的认证设备的列表，请参阅：</span><span class="sxs-lookup"><span data-stu-id="3c591-110">For a list of certified devices that can be managed, see:</span></span>

- [<span data-ttu-id="3c591-111">会议电话</span><span class="sxs-lookup"><span data-stu-id="3c591-111">Conference phones</span></span>](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=16)
- [<span data-ttu-id="3c591-112">桌面电话</span><span class="sxs-lookup"><span data-stu-id="3c591-112">Desk phones</span></span>](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- <span data-ttu-id="3c591-113">协作栏</span><span class="sxs-lookup"><span data-stu-id="3c591-113">Collaboration bars</span></span>

<span data-ttu-id="3c591-114">在左侧导航中的 "**设备**" 下的 " [Microsoft 团队管理中心](https://admin.teams.microsoft.com)" 中管理设备。</span><span class="sxs-lookup"><span data-stu-id="3c591-114">Devices are managed in the [Microsoft Teams admin center](https://admin.teams.microsoft.com) under **Devices** in the left navigation.</span></span>

> [!NOTE]
> <span data-ttu-id="3c591-115">如果你有 Microsoft Intune，则会在 Intune 中自动注册设备。</span><span class="sxs-lookup"><span data-stu-id="3c591-115">If you have Microsoft Intune, devices are automatically enrolled in Intune.</span></span> <span data-ttu-id="3c591-116">注册设备后，将确认设备合规性，并将条件访问策略应用到设备。</span><span class="sxs-lookup"><span data-stu-id="3c591-116">After a device is enrolled, device compliance is confirmed and conditional access policies are applied to the device.</span></span>

## <a name="manage-phones-and-collaboration-bars-in-teams"></a><span data-ttu-id="3c591-117">管理团队中的电话和协作栏</span><span class="sxs-lookup"><span data-stu-id="3c591-117">Manage phones and collaboration bars in Teams</span></span>

<span data-ttu-id="3c591-118">尽管在 Microsoft 团队管理中心中，手机和协作栏的管理方式相同，但它们在左侧导航中的 "**设备**" 下有各自的分区。</span><span class="sxs-lookup"><span data-stu-id="3c591-118">Even though phones and collaboration bars are managed the same in the Microsoft Teams admin center, they have their own respective sections in the left navigation under **Devices**.</span></span> <span data-ttu-id="3c591-119">这使你可以单独管理每种类型的设备。</span><span class="sxs-lookup"><span data-stu-id="3c591-119">This lets you manage each type of device separately.</span></span>

<span data-ttu-id="3c591-120">从这里，您可以查看和管理您的组织中的团队注册的电话和协作栏。</span><span class="sxs-lookup"><span data-stu-id="3c591-120">From here, you can view and manage phones and collaboration bars enrolled in Teams in your organization.</span></span> <span data-ttu-id="3c591-121">您将看到的每个设备的信息包括设备名称、制造商、型号、用户、状态、操作、上次查看和历史记录。</span><span class="sxs-lookup"><span data-stu-id="3c591-121">Information that you'll see for each device includes device name, manufacturer, model, user, status, action, last seen, and history.</span></span> <span data-ttu-id="3c591-122">你可以自定义视图以显示符合你的需求的信息。</span><span class="sxs-lookup"><span data-stu-id="3c591-122">You can customize the view to show the information that fits your needs.</span></span>

<span data-ttu-id="3c591-123">下面是有关如何管理组织中的团队设备的一些示例。</span><span class="sxs-lookup"><span data-stu-id="3c591-123">Here's some examples of how you can manage Teams devices in your organization.</span></span>  
    
|<span data-ttu-id="3c591-124">若要执行此操作 .。。</span><span class="sxs-lookup"><span data-stu-id="3c591-124">To do this...</span></span>  |<span data-ttu-id="3c591-125">执行此操作</span><span class="sxs-lookup"><span data-stu-id="3c591-125">Do this</span></span> |
|---------|---------|
|<span data-ttu-id="3c591-126">更改设备信息</span><span class="sxs-lookup"><span data-stu-id="3c591-126">Change device information</span></span>   | <span data-ttu-id="3c591-127">选择 >**编辑**的设备。</span><span class="sxs-lookup"><span data-stu-id="3c591-127">Select a device > **Edit**.</span></span> <span data-ttu-id="3c591-128">你可以编辑设备名称、资产标记和添加笔记等详细信息。</span><span class="sxs-lookup"><span data-stu-id="3c591-128">You can edit details such as device name, asset tag, and add notes.</span></span>     |
|<span data-ttu-id="3c591-129">管理软件更新</span><span class="sxs-lookup"><span data-stu-id="3c591-129">Manage software updates</span></span>   |<span data-ttu-id="3c591-130">选择 >**更新**的设备。</span><span class="sxs-lookup"><span data-stu-id="3c591-130">Select a device > **Update**.</span></span> <span data-ttu-id="3c591-131">你可以查看适用于该设备的软件和固件更新的列表，并选择要安装的更新。</span><span class="sxs-lookup"><span data-stu-id="3c591-131">You can view the list of software and firmware updates available for the device and choose the updates to install.</span></span>    |
|<span data-ttu-id="3c591-132">重启设备</span><span class="sxs-lookup"><span data-stu-id="3c591-132">Restart a device</span></span>   |<span data-ttu-id="3c591-133">选择 >**重新启动**的设备。</span><span class="sxs-lookup"><span data-stu-id="3c591-133">Select a device > **Restart**.</span></span>          |
|<span data-ttu-id="3c591-134">查看设备历史记录</span><span class="sxs-lookup"><span data-stu-id="3c591-134">View device history</span></span>  | <span data-ttu-id="3c591-135">选择一个设备 >**历史记录**。</span><span class="sxs-lookup"><span data-stu-id="3c591-135">Select a device > **History**.</span></span> <span data-ttu-id="3c591-136">你可以查看设备的更新历史记录。</span><span class="sxs-lookup"><span data-stu-id="3c591-136">You can view the update history for the device.</span></span>     |
|<span data-ttu-id="3c591-137">查看诊断</span><span class="sxs-lookup"><span data-stu-id="3c591-137">View diagnostics</span></span>  | <span data-ttu-id="3c591-138">选择一个设备 >**诊断**。</span><span class="sxs-lookup"><span data-stu-id="3c591-138">Select a device > **Diagnostics**.</span></span>        |

## <a name="use-configuration-profiles-in-teams"></a><span data-ttu-id="3c591-139">使用团队中的配置文件</span><span class="sxs-lookup"><span data-stu-id="3c591-139">Use configuration profiles in Teams</span></span>

<span data-ttu-id="3c591-140">使用配置文件管理组织中团队设备的设置和功能。</span><span class="sxs-lookup"><span data-stu-id="3c591-140">Use configuration profiles to manage settings and features for Teams devices in your organization.</span></span> <span data-ttu-id="3c591-141">你可以创建或上载配置文件，以包含要启用或禁用的设置和功能，然后将配置文件分配给设备或设备组。</span><span class="sxs-lookup"><span data-stu-id="3c591-141">You can create or upload configuration profiles to include settings and features you want to enable or disable and then assign a profile to a device or groups of devices.</span></span> 

### <a name="create-a-configuration-profile"></a><span data-ttu-id="3c591-142">创建配置文件</span><span class="sxs-lookup"><span data-stu-id="3c591-142">Create a configuration profile</span></span>

1. <span data-ttu-id="3c591-143">在左侧导航中，转到 "**设备** > **配置文件**"。</span><span class="sxs-lookup"><span data-stu-id="3c591-143">In the left navigation, go to **Devices** > **Configuration profiles**.</span></span>
2. <span data-ttu-id="3c591-144">单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3c591-144">Click **Add**.</span></span>
3. <span data-ttu-id="3c591-145">输入配置文件的名称，如果需要，请添加一个友好描述。</span><span class="sxs-lookup"><span data-stu-id="3c591-145">Enter a name for the profile and if you want, add a friendly description.</span></span>
4. <span data-ttu-id="3c591-146">为配置文件指定所需的设置，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="3c591-146">Specify the settings you want for the profile, and then click **Save**.</span></span>

### <a name="assign-a-configuration-profile"></a><span data-ttu-id="3c591-147">分配配置文件</span><span class="sxs-lookup"><span data-stu-id="3c591-147">Assign a configuration profile</span></span>

1. <span data-ttu-id="3c591-148">在左侧导航中，转到 "**设备** > **配置文件**"。</span><span class="sxs-lookup"><span data-stu-id="3c591-148">In the left navigation, go to **Devices** > **Configuration profiles**.</span></span>
2. <span data-ttu-id="3c591-149">选择要分配的**配置文件**，然后单击 "**分配给设备**"。</span><span class="sxs-lookup"><span data-stu-id="3c591-149">Select the **Configuration profile** you want to assign, and then click **Assign to device**.</span></span>  
3. <span data-ttu-id="3c591-150">在 "**将设备分配给配置文件**窗格" 中，搜索并选择要分配的设备。</span><span class="sxs-lookup"><span data-stu-id="3c591-150">In the **Assign devices to a configuration profile** pane, search for and select the devices you want to assign.</span></span>
4. <span data-ttu-id="3c591-151">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="3c591-151">Click **Save**.</span></span>
