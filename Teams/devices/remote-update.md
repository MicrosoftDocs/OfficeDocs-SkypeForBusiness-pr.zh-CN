---
title: 远程Microsoft Teams更新设备
ms.author: dstrome
author: dstrome
ms.reviewer: rahulmi
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: 使用 Microsoft Teams 管理Teams远程更新手机、Teams面板和 Teams协作栏
ms.openlocfilehash: 67b76d8330de5a801625a22c25cd1f9637048d05
ms.sourcegitcommit: e72599d5437773322ae6ef985f804a19101ed84f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2021
ms.locfileid: "50347883"
---
# <a name="update-microsoft-teams-devices-remotely"></a><span data-ttu-id="8c457-103">远程Microsoft Teams更新设备</span><span class="sxs-lookup"><span data-stu-id="8c457-103">Update Microsoft Teams devices remotely</span></span>

<span data-ttu-id="8c457-104">使用 Microsoft Teams 管理中心，可以远程更新 Teams 设备，例如 Teams 手机、Teams 面板和协作栏，还可以选择设备固件自动更新行为。</span><span class="sxs-lookup"><span data-stu-id="8c457-104">Using the Microsoft Teams admin center, you can update your Teams devices, such as Teams phones, Teams panels, and collaboration bars, remotely, and you can choose device firmware automatic-update behavior.</span></span> <span data-ttu-id="8c457-105">可以使用管理中心在设备上Teams以下内容：</span><span class="sxs-lookup"><span data-stu-id="8c457-105">You can update the following on your devices using the Teams admin center:</span></span>

- <span data-ttu-id="8c457-106">Teams应用和 Teams 管理员代理</span><span class="sxs-lookup"><span data-stu-id="8c457-106">Teams app and teams admin agent</span></span>
- <span data-ttu-id="8c457-107">公司门户应用</span><span class="sxs-lookup"><span data-stu-id="8c457-107">Company portal app</span></span>
- <span data-ttu-id="8c457-108">OEM 代理应用</span><span class="sxs-lookup"><span data-stu-id="8c457-108">OEM agent app</span></span>
- <span data-ttu-id="8c457-109">设备固件</span><span class="sxs-lookup"><span data-stu-id="8c457-109">Device firmware</span></span>

<span data-ttu-id="8c457-110">可以自动应用设备固件更新，也可以计划在将来的日期和时间进行更新。</span><span class="sxs-lookup"><span data-stu-id="8c457-110">Device firmware updates can either be applied automatically or scheduled for a future date and time.</span></span> <span data-ttu-id="8c457-111">其他可用的设备更新不会自动应用，但可以手动应用或计划在将来的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="8c457-111">Other available device updates aren't applied automatically, but can be applied manually or scheduled for a future date and time.</span></span>

> [!NOTE]
> <span data-ttu-id="8c457-112">虽然可以计划设备固件更新，但如果计划的日期和时间低于配置的最长 30 天或 90 天延迟，则当达到最大延迟时，将应用固件更新。</span><span class="sxs-lookup"><span data-stu-id="8c457-112">While device firmware updates can be scheduled, if the scheduled date and time falls after the configured maximum 30 or 90 day delay, the firmware update is applied when the maximum delay is reached.</span></span> <span data-ttu-id="8c457-113">将忽略计划的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="8c457-113">The scheduled date and time are ignored.</span></span> <span data-ttu-id="8c457-114">此外，Microsoft Teams远程更新设备是美国政府云租户 (GCC-High) 。</span><span class="sxs-lookup"><span data-stu-id="8c457-114">Additionally, updating Microsoft Teams devices remotely is a feature not yet available on US Government Cloud tenants (GCC-High).</span></span>

<span data-ttu-id="8c457-115">若要管理设备，需要是全局管理员、Teams管理员或Teams管理员。有关管理员角色详细信息，请参阅使用 Microsoft Teams[管理员角色管理Teams。](../using-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="8c457-115">To manage devices, you need to be a Global admin, Teams Service admin, or Teams Device admin. For more information about admin roles, see [Use Microsoft Teams administrator roles to manage Teams](../using-admin-roles.md).</span></span>

## <a name="choose-automatic-device-firmware-update-behavior"></a><span data-ttu-id="8c457-116">选择自动设备固件更新行为</span><span class="sxs-lookup"><span data-stu-id="8c457-116">Choose automatic device firmware update behavior</span></span>

<span data-ttu-id="8c457-117">将自动应用设备固件更新。</span><span class="sxs-lookup"><span data-stu-id="8c457-117">Device firmware updates are applied automatically.</span></span> <span data-ttu-id="8c457-118">可以决定是否在发布更新后应用更新 (如果选择此选项，更新将在更新发布) 后的第一个周末或更新发布后的 30 或 90 天内应用。</span><span class="sxs-lookup"><span data-stu-id="8c457-118">You can decide whether to apply updates as soon as one is released (if you choose this option, updates are applied on the first weekend after an update is released), or 30 or 90 days after an update is released.</span></span> <span data-ttu-id="8c457-119">默认情况下，设备固件更新在发布后 30 天内应用。</span><span class="sxs-lookup"><span data-stu-id="8c457-119">By default, device firmware updates are applied 30 days one released.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8c457-120">最新的固件更新版本不会应用到Teams设备上。</span><span class="sxs-lookup"><span data-stu-id="8c457-120">The latest firmware update release isn't applied on your Teams device.</span></span> <span data-ttu-id="8c457-121">相反，在设备上自动应用的更新会延迟一个版本。</span><span class="sxs-lookup"><span data-stu-id="8c457-121">Instead, the update that's automatically applied on your device is delayed by one version.</span></span> <span data-ttu-id="8c457-122">例如，假设设备应用了版本"10"，并且发布了版本"11"。</span><span class="sxs-lookup"><span data-stu-id="8c457-122">For example, assume your device has version "10" applied, and version "11" is released.</span></span> <span data-ttu-id="8c457-123">版本"11"尚未应用。</span><span class="sxs-lookup"><span data-stu-id="8c457-123">Version "11" won't be applied yet.</span></span> <span data-ttu-id="8c457-124">而是仅在发布版本"12"后将设备更新到版本"11"。</span><span class="sxs-lookup"><span data-stu-id="8c457-124">Instead your device will only be updated to version "11" after version "12" is released.</span></span>

> [!NOTE]
> <span data-ttu-id="8c457-125">某些设备尚不支持自动固件更新。</span><span class="sxs-lookup"><span data-stu-id="8c457-125">Some devices don't support automatic firmware update yet.</span></span> <span data-ttu-id="8c457-126">在不支持自动更新的设备上应用自动固件更新设置不会影响这些设备。</span><span class="sxs-lookup"><span data-stu-id="8c457-126">Applying automatic firmware update settings on devices that don't support automatic updates won't have any affect on those devices.</span></span> <span data-ttu-id="8c457-127">有关设备是否支持自动固件更新的问题，请与设备制造商联系。</span><span class="sxs-lookup"><span data-stu-id="8c457-127">For questions about whether your device will support automatic firmware updates, contact your device manufacturer.</span></span>

<span data-ttu-id="8c457-128">若要选择设备的自动更新行为，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="8c457-128">To choose the automatic update behavior for your devices, do the following:</span></span>

1. <span data-ttu-id="8c457-129">通过访问 Microsoft Teams登录到管理中心 https://admin.teams.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="8c457-129">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="8c457-130">导航 **设备**  >  **IP 电话** 或 **协作栏或\*\*\*\*Teams面板**。</span><span class="sxs-lookup"><span data-stu-id="8c457-130">Navigate **Devices** > **IP phones** or **Collaboration bars** or **Teams panels**.</span></span>
3. <span data-ttu-id="8c457-131">选择一个或多个设备，然后选择"更新 **"。**</span><span class="sxs-lookup"><span data-stu-id="8c457-131">Select one or more devices and then select **Update**.</span></span>
4. <span data-ttu-id="8c457-132">在 **"固件自动更新"** 下，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="8c457-132">Under **Firmware auto-update**, select one of the following:</span></span>
    - <span data-ttu-id="8c457-133">**一旦可用** 最新设备固件更新在最新更新发布后的第一个周末应用。</span><span class="sxs-lookup"><span data-stu-id="8c457-133">**As soon as available** Second-newest device firmware update is applied on the first weekend after the latest update is released.</span></span>
    - <span data-ttu-id="8c457-134">**推迟 30 天** 最新设备固件更新在最新更新发布后的 30 天内应用。</span><span class="sxs-lookup"><span data-stu-id="8c457-134">**Defer 30 days** Second-newest device firmware update is applied 30 days after the latest update is released.</span></span>
    - <span data-ttu-id="8c457-135">**推迟 90 天** 最新设备固件更新在最新更新发布后的 90 天内应用。</span><span class="sxs-lookup"><span data-stu-id="8c457-135">**Defer 90 days** Second-newest device firmware update is applied 90 days after the latest update is released.</span></span>
5. <span data-ttu-id="8c457-136">选择"**更新"。**</span><span class="sxs-lookup"><span data-stu-id="8c457-136">Select **Update**.</span></span>

<span data-ttu-id="8c457-137">如果出于任何原因需要还原设备固件更新，则需要将设备重置为出厂设置。</span><span class="sxs-lookup"><span data-stu-id="8c457-137">If, for whatever reason, you need to revert a device firmware update, you need to reset your device to its factory settings.</span></span> <span data-ttu-id="8c457-138">按照制造商的说明重置设备。</span><span class="sxs-lookup"><span data-stu-id="8c457-138">Reset your device using the instructions from its manufacturer.</span></span>  

## <a name="manually-update-remote-devices"></a><span data-ttu-id="8c457-139">手动更新远程设备</span><span class="sxs-lookup"><span data-stu-id="8c457-139">Manually update remote devices</span></span>

<span data-ttu-id="8c457-140">使用管理中心更新一个或多个设备时，可以决定是立即更新设备，还是计划将来日期和时间的更新。</span><span class="sxs-lookup"><span data-stu-id="8c457-140">When you update one or more devices using the admin center, you can decide whether to update the devices immediately or schedule an update for a future date and time.</span></span>

<span data-ttu-id="8c457-141">若要手动更新远程设备，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="8c457-141">To manually update remote devices, do the following:</span></span>

1. <span data-ttu-id="8c457-142">通过访问 Microsoft Teams登录到管理中心 https://admin.teams.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="8c457-142">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="8c457-143">导航 **设备**  >  **IP 电话** 或 **协作栏或\*\*\*\*Teams面板**。</span><span class="sxs-lookup"><span data-stu-id="8c457-143">Navigate  **Devices** > **IP phones** or **Collaboration bars** or **Teams panels**.</span></span>
3. <span data-ttu-id="8c457-144">选择一个或多个设备，然后选择"更新 **"。**</span><span class="sxs-lookup"><span data-stu-id="8c457-144">Select one or more devices and then select **Update**.</span></span>
4. <span data-ttu-id="8c457-145">在 **"手动更新**" **下** ，如果要将更新计划为将来的日期和时间，请选择"计划"。</span><span class="sxs-lookup"><span data-stu-id="8c457-145">Under **Manual updates**, select **Schedule** if you want to schedule the update for a future date and time.</span></span> <span data-ttu-id="8c457-146">更新在时区 中选定的时区中的 **日期和时间应用**。</span><span class="sxs-lookup"><span data-stu-id="8c457-146">The updates are applied at the date and time in the timezone selected in **Timezone**.</span></span>

<span data-ttu-id="8c457-147">将看到的信息取决于是否选择了一个或多个设备。</span><span class="sxs-lookup"><span data-stu-id="8c457-147">What you'll see depends on whether you have one, or multiple, devices selected.</span></span> <span data-ttu-id="8c457-148">下面的左侧图像显示了选中的多个设备，而右侧图像显示选中的单个设备。</span><span class="sxs-lookup"><span data-stu-id="8c457-148">The left image below shows multiple devices selected while the image on the right shows a single device selected.</span></span>

:::image type="content" source="../media/device-update-status.png" alt-text="设备更新状态窗格中的单个和多个设备视图":::

<span data-ttu-id="8c457-150">选择多个设备时，可以选择要应用到每个所选设备的更新类型。</span><span class="sxs-lookup"><span data-stu-id="8c457-150">When you select multiple devices, you can choose which update types to apply to each selected device.</span></span> <span data-ttu-id="8c457-151">选择要应用的更新类型，然后选择"更新 **"。**</span><span class="sxs-lookup"><span data-stu-id="8c457-151">Select the update types you want to apply and select **Update**.</span></span>

<span data-ttu-id="8c457-152">选择单个设备时，会显示适用于设备的更新。</span><span class="sxs-lookup"><span data-stu-id="8c457-152">When you select a single device, updates that are available for the device are shown.</span></span> <span data-ttu-id="8c457-153">如果设备有多个更新类型可用，请选择要应用的每个更新类型。</span><span class="sxs-lookup"><span data-stu-id="8c457-153">If multiple update types are available for the device, select each update type to apply.</span></span> <span data-ttu-id="8c457-154">可以查看设备上 **应用的** 当前版本和 **要应用的** 新版本。</span><span class="sxs-lookup"><span data-stu-id="8c457-154">You can view the **Current version** applied on the device and the **New version** that will be applied.</span></span> <span data-ttu-id="8c457-155">选择要 (更新) ，然后选择"更新 **"。**</span><span class="sxs-lookup"><span data-stu-id="8c457-155">Select the update(s) you want to apply and select **Update**.</span></span>

<span data-ttu-id="8c457-156">选择" **更新**"后，如果计划了更新，则更新将在你选择的日期和时间应用到你的设备。</span><span class="sxs-lookup"><span data-stu-id="8c457-156">After you select **Update**, updates are applied to your devices at the date and time you selected if you scheduled an update.</span></span> <span data-ttu-id="8c457-157">如果未选择将来的日期和时间，则更新将几分钟内应用到设备。</span><span class="sxs-lookup"><span data-stu-id="8c457-157">If you didn't select a future date and time, updates are applied to your devices within a few minutes.</span></span>
