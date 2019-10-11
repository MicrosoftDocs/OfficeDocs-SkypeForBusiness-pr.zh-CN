---
title: 在 Microsoft Teams 中管理设备
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 11/12/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: kelsawi
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1keywords:
- ms.teamsadmincenter.managedevices.overview
- ms.teamsadmincenter.devicemanagement.overview
description: 了解如何管理组织中与团队一起使用的设备。
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 38d716396a61f259a3a1ac90f45b0b5b4b110e33
ms.sourcegitcommit: de7e0afbd40bbe52994ab99d85cf9e95ecbc4a6c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2019
ms.locfileid: "37434896"
---
# <a name="manage-your-devices-in-microsoft-teams"></a><span data-ttu-id="0bb69-103">在 Microsoft Teams 中管理设备</span><span class="sxs-lookup"><span data-stu-id="0bb69-103">Manage your devices in Microsoft Teams</span></span>

::: zone target="docs"
<span data-ttu-id="0bb69-104">作为管理员，你可以管理来自 Microsoft 团队管理中心的组织中的团队使用的所有设备。</span><span class="sxs-lookup"><span data-stu-id="0bb69-104">As an admin, you manage all devices used with Teams in your organization from the Microsoft Teams admin center.</span></span> <span data-ttu-id="0bb69-105">你可以查看和管理你的组织的设备清单，并执行一些任务，如更新、重启和监视设备诊断。</span><span class="sxs-lookup"><span data-stu-id="0bb69-105">You can view and manage the device inventory for your organization and do tasks such as update, restart, and monitor diagnostics for devices.</span></span> <span data-ttu-id="0bb69-106">你还可以创建配置文件并将其分配给设备或设备组。</span><span class="sxs-lookup"><span data-stu-id="0bb69-106">You can also create and assign configuration profiles to a device or groups of devices.</span></span> 

## <a name="what-devices-can-you-manage"></a><span data-ttu-id="0bb69-107">可以管理哪些设备？</span><span class="sxs-lookup"><span data-stu-id="0bb69-107">What devices can you manage?</span></span>
<span data-ttu-id="0bb69-108">设备必须经过认证，才能供团队和注册团队。</span><span class="sxs-lookup"><span data-stu-id="0bb69-108">Devices must be certified for Teams and enrolled in Teams.</span></span> <span data-ttu-id="0bb69-109">当用户第一次登录设备上的团队时，将自动注册设备。</span><span class="sxs-lookup"><span data-stu-id="0bb69-109">A device is automatically enrolled the first time a user signs in to Teams on the device.</span></span> <span data-ttu-id="0bb69-110">有关可管理的认证设备的列表，请参阅[电话会议](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=16)和[桌面电话](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=34)。</span><span class="sxs-lookup"><span data-stu-id="0bb69-110">For a list of certified devices that can be managed, see [Conference phones](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=16) and [Desk phones](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=34).</span></span>

> [!NOTE]
> <span data-ttu-id="0bb69-111">如果你有 Microsoft Intune，则会在 Intune 中自动注册设备。</span><span class="sxs-lookup"><span data-stu-id="0bb69-111">If you have Microsoft Intune, devices are automatically enrolled in Intune.</span></span> <span data-ttu-id="0bb69-112">注册设备后，将确认设备合规性，并将条件访问策略应用到设备。</span><span class="sxs-lookup"><span data-stu-id="0bb69-112">After a device is enrolled, device compliance is confirmed and conditional access policies are applied to the device.</span></span> 

## <a name="manage-devices-in-teams"></a><span data-ttu-id="0bb69-113">管理团队中的设备</span><span class="sxs-lookup"><span data-stu-id="0bb69-113">Manage devices in Teams</span></span>

<span data-ttu-id="0bb69-114">![](media/teams-logo-30x30.png) **使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标</span><span class="sxs-lookup"><span data-stu-id="0bb69-114">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="0bb69-115">在左侧导航中，转到 "**设备** > **管理设备**"。</span><span class="sxs-lookup"><span data-stu-id="0bb69-115">In the left navigation, go to **Devices** > **Manage Devices**.</span></span>
2. <span data-ttu-id="0bb69-116">选择 "**所有设备**"。</span><span class="sxs-lookup"><span data-stu-id="0bb69-116">Select **All devices**.</span></span>  

::: zone-end

 <span data-ttu-id="0bb69-117">从这里，您可以查看和管理您的组织中的团队注册的所有设备。</span><span class="sxs-lookup"><span data-stu-id="0bb69-117">From here, you can view and manage all devices enrolled in Teams in your organization.</span></span> <span data-ttu-id="0bb69-118">您将看到的每个设备的信息包括设备名称、制造商、型号、用户、状态、操作、上次查看和历史记录。</span><span class="sxs-lookup"><span data-stu-id="0bb69-118">Information that you'll see for each device includes device name, manufacturer, model, user, status, action, last seen, and history.</span></span> <span data-ttu-id="0bb69-119">你可以自定义视图以显示符合你的需求的信息。</span><span class="sxs-lookup"><span data-stu-id="0bb69-119">You can customize the view to show the information that fits your needs.</span></span>

 <span data-ttu-id="0bb69-120">下面是有关如何管理组织中的团队设备的一些示例。</span><span class="sxs-lookup"><span data-stu-id="0bb69-120">Here's some examples of how you can manage Teams devices in your organization.</span></span>  
    
|<span data-ttu-id="0bb69-121">若要执行此操作 .。。</span><span class="sxs-lookup"><span data-stu-id="0bb69-121">To do this...</span></span>  |<span data-ttu-id="0bb69-122">执行此操作</span><span class="sxs-lookup"><span data-stu-id="0bb69-122">Do this</span></span> |
|---------|---------|
|<span data-ttu-id="0bb69-123">更改设备信息</span><span class="sxs-lookup"><span data-stu-id="0bb69-123">Change device information</span></span>   | <span data-ttu-id="0bb69-124">选择 >**编辑**的设备。</span><span class="sxs-lookup"><span data-stu-id="0bb69-124">Select a device > **Edit**.</span></span> <span data-ttu-id="0bb69-125">你可以编辑设备名称、用户信息、资产标记和添加笔记等详细信息。</span><span class="sxs-lookup"><span data-stu-id="0bb69-125">You can edit details such as device name, user information, asset tag, and add notes.</span></span>     |
|<span data-ttu-id="0bb69-126">管理软件更新</span><span class="sxs-lookup"><span data-stu-id="0bb69-126">Manage software updates</span></span>   |<span data-ttu-id="0bb69-127">选择 >**更新**的设备。</span><span class="sxs-lookup"><span data-stu-id="0bb69-127">Select a device > **Update**.</span></span> <span data-ttu-id="0bb69-128">你可以查看适用于该设备的软件和固件更新的列表，并选择要安装的更新。</span><span class="sxs-lookup"><span data-stu-id="0bb69-128">You can view the list of software and firmware updates available for the device and choose the updates to install.</span></span>    |
|<span data-ttu-id="0bb69-129">重启设备</span><span class="sxs-lookup"><span data-stu-id="0bb69-129">Restart a device</span></span>   |<span data-ttu-id="0bb69-130">选择 >**重新启动**的设备。</span><span class="sxs-lookup"><span data-stu-id="0bb69-130">Select a device > **Restart**.</span></span>          |
|<span data-ttu-id="0bb69-131">查看设备历史记录</span><span class="sxs-lookup"><span data-stu-id="0bb69-131">View device history</span></span>  | <span data-ttu-id="0bb69-132">选择一个设备 >**历史记录**。</span><span class="sxs-lookup"><span data-stu-id="0bb69-132">Select a device > **History**.</span></span> <span data-ttu-id="0bb69-133">你可以查看设备的更新历史记录。</span><span class="sxs-lookup"><span data-stu-id="0bb69-133">You can view the update history for the device.</span></span>     |
|<span data-ttu-id="0bb69-134">查看诊断</span><span class="sxs-lookup"><span data-stu-id="0bb69-134">View diagnostics</span></span>  | <span data-ttu-id="0bb69-135">选择一个设备 >**诊断**。</span><span class="sxs-lookup"><span data-stu-id="0bb69-135">Select a device > **Diagnostics**.</span></span>        |

## <a name="use-configuration-profiles-in-teams"></a><span data-ttu-id="0bb69-136">使用团队中的配置文件</span><span class="sxs-lookup"><span data-stu-id="0bb69-136">Use configuration profiles in Teams</span></span>

<span data-ttu-id="0bb69-137">使用配置文件管理组织中团队设备的设置和功能。</span><span class="sxs-lookup"><span data-stu-id="0bb69-137">Use configuration profiles to manage settings and features for Teams devices in your organization.</span></span> <span data-ttu-id="0bb69-138">你可以创建或上载配置文件，以包含要启用或禁用的设置和功能，然后将配置文件分配给设备或设备组。</span><span class="sxs-lookup"><span data-stu-id="0bb69-138">You can create or upload configuration profiles to include settings and features you want to enable or disable and then assign a profile to a device or groups of devices.</span></span> 

### <a name="create-a-configuration-profile"></a><span data-ttu-id="0bb69-139">创建配置文件</span><span class="sxs-lookup"><span data-stu-id="0bb69-139">Create a configuration profile</span></span>

::: zone target="docs"

![显示 Microsoft 团队徽标的图标](media/teams-logo-30x30.png) <span data-ttu-id="0bb69-141">使用 Microsoft 团队 & Skype for Business 管理中心</span><span class="sxs-lookup"><span data-stu-id="0bb69-141">Using the Microsoft Teams & Skype for Business admin center</span></span>

1. <span data-ttu-id="0bb69-142">在左侧导航中，转到 "**设备** > **管理设备**"。</span><span class="sxs-lookup"><span data-stu-id="0bb69-142">In the left navigation, go to **Devices** > **Manage Devices**.</span></span>

::: zone-end

2. <span data-ttu-id="0bb69-143">选择 "**配置文件**"，然后选择 "**新建配置文件**"。</span><span class="sxs-lookup"><span data-stu-id="0bb69-143">Select **Configuration profiles**, and then select **New configuration profile**.</span></span>
3. <span data-ttu-id="0bb69-144">输入配置文件的名称，如果需要，请添加一个友好描述。</span><span class="sxs-lookup"><span data-stu-id="0bb69-144">Enter a name for the profile and if you want, add a friendly description.</span></span>
4. <span data-ttu-id="0bb69-145">为配置文件指定所需的设置，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="0bb69-145">Specify the settings you want for the profile, and then click **Save**.</span></span>

### <a name="assign-a-configuration-profile"></a><span data-ttu-id="0bb69-146">分配配置文件</span><span class="sxs-lookup"><span data-stu-id="0bb69-146">Assign a configuration profile</span></span>

::: zone target="docs"

![显示 Microsoft 团队徽标的图标](media/teams-logo-30x30.png) <span data-ttu-id="0bb69-148">使用 Microsoft 团队 & Skype for Business 管理中心</span><span class="sxs-lookup"><span data-stu-id="0bb69-148">Using the Microsoft Teams & Skype for Business admin center</span></span>

1. <span data-ttu-id="0bb69-149">在左侧导航中，转到 "**设备** > **管理设备**"。</span><span class="sxs-lookup"><span data-stu-id="0bb69-149">In the left navigation, go to **Devices** > **Manage Devices**.</span></span>

::: zone-end

2. <span data-ttu-id="0bb69-150">选择**配置文件**，然后在要分配的配置文件中的 "**分配给**" 下，单击该链接。</span><span class="sxs-lookup"><span data-stu-id="0bb69-150">Select **Configuration profile**, and then under **Assigned to** in the profile you want to assign, click the link.</span></span>  
3. <span data-ttu-id="0bb69-151">在 "**将设备分配给配置文件**窗格" 中，搜索并选择要分配的设备。</span><span class="sxs-lookup"><span data-stu-id="0bb69-151">In the **Assign devices to a configuration profile** pane, search for and select the devices you want to assign.</span></span>
4. <span data-ttu-id="0bb69-152">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="0bb69-152">Click **Save**.</span></span>
