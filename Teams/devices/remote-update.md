---
title: 远程更新 Microsoft 团队设备
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
description: 使用团队管理中心远程更新 Microsoft 团队的电话和协作栏
ms.openlocfilehash: e57ca3f357deeb005f845d37a17c4b20db5d2035
ms.sourcegitcommit: b255db7ef816d1884c9c71af86a901bd83a1d9ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962883"
---
# <a name="update-microsoft-teams-devices-remotely"></a><span data-ttu-id="1d6cf-103">远程更新 Microsoft 团队设备</span><span class="sxs-lookup"><span data-stu-id="1d6cf-103">Update Microsoft Teams devices remotely</span></span>

<span data-ttu-id="1d6cf-104">使用 Microsoft 团队管理中心，您可以通过远程方式更新团队设备（如电话和协作栏），并且可以选择设备固件自动更新行为。</span><span class="sxs-lookup"><span data-stu-id="1d6cf-104">Using the Microsoft Teams admin center, you can update your Teams devices, such as phones and collaboration bars, remotely, and you can choose device firmware automatic-update behavior.</span></span> <span data-ttu-id="1d6cf-105">你可以使用团队管理中心在你的设备上更新以下内容：</span><span class="sxs-lookup"><span data-stu-id="1d6cf-105">You can update the following on your devices using the Teams admin center:</span></span>

- <span data-ttu-id="1d6cf-106">团队应用和团队管理员代理</span><span class="sxs-lookup"><span data-stu-id="1d6cf-106">Teams app and teams admin agent</span></span>
- <span data-ttu-id="1d6cf-107">公司门户应用</span><span class="sxs-lookup"><span data-stu-id="1d6cf-107">Company portal app</span></span>
- <span data-ttu-id="1d6cf-108">OEM 代理应用</span><span class="sxs-lookup"><span data-stu-id="1d6cf-108">OEM agent app</span></span>
- <span data-ttu-id="1d6cf-109">设备固件</span><span class="sxs-lookup"><span data-stu-id="1d6cf-109">Device firmware</span></span>

<span data-ttu-id="1d6cf-110">设备固件更新可以自动应用，也可以计划在将来的日期和时间使用。</span><span class="sxs-lookup"><span data-stu-id="1d6cf-110">Device firmware updates can either be applied automatically or scheduled for a future date and time.</span></span> <span data-ttu-id="1d6cf-111">其他可用的设备更新不会自动应用，但可以手动或计划在将来的日期和时间应用。</span><span class="sxs-lookup"><span data-stu-id="1d6cf-111">Other available device updates aren't applied automatically, but can be applied manually or scheduled for a future date and time.</span></span>

> [!NOTE]
> <span data-ttu-id="1d6cf-112">虽然可以计划设备固件更新，但如果计划的日期和时间位于配置的最大30个或90天的延迟之后，则会在达到最大延迟时应用固件更新。</span><span class="sxs-lookup"><span data-stu-id="1d6cf-112">While device firmware updates can be scheduled, if the scheduled date and time falls after the configured maximum 30 or 90 day delay, the firmware update is applied when the maximum delay is reached.</span></span> <span data-ttu-id="1d6cf-113">将忽略计划的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="1d6cf-113">The scheduled date and time are ignored.</span></span> <span data-ttu-id="1d6cf-114">此外，"远程更新 Microsoft 团队设备" 是尚未在美国政府云租户 (GCC-高) 中提供的功能。</span><span class="sxs-lookup"><span data-stu-id="1d6cf-114">Additionally, updating Microsoft Teams devices remotely is a feature not yet available on US Government Cloud tenants (GCC-High).</span></span>

<span data-ttu-id="1d6cf-115">若要管理设备，您必须是全局管理员、团队服务管理员或团队设备管理员。有关管理员角色的详细信息，请参阅 [使用 Microsoft 团队管理员角色管理团队](../using-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="1d6cf-115">To manage devices, you need to be a Global admin, Teams Service admin, or Teams Device admin. For more information about admin roles, see [Use Microsoft Teams administrator roles to manage Teams](../using-admin-roles.md).</span></span>

## <a name="choose-automatic-device-firmware-update-behavior"></a><span data-ttu-id="1d6cf-116">选择 "自动设备固件更新" 行为</span><span class="sxs-lookup"><span data-stu-id="1d6cf-116">Choose automatic device firmware update behavior</span></span>

<span data-ttu-id="1d6cf-117">将自动应用设备固件更新。</span><span class="sxs-lookup"><span data-stu-id="1d6cf-117">Device firmware updates are applied automatically.</span></span> <span data-ttu-id="1d6cf-118">你可以决定是否在发布一个更新后立即应用更新 (如果选择此选项，则会在发布更新后的第一个周末应用更新) ，或者在发布更新后30天或90天内应用更新。</span><span class="sxs-lookup"><span data-stu-id="1d6cf-118">You can decide whether to apply updates as soon as one is released (if you choose this option, updates are applied on the first weekend after an update is released), or 30 or 90 days after an update is released.</span></span> <span data-ttu-id="1d6cf-119">默认情况下，设备固件更新将在30天发布后应用。</span><span class="sxs-lookup"><span data-stu-id="1d6cf-119">By default, device firmware updates are applied 30 days one released.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1d6cf-120">你的团队设备未应用最新的固件更新版本。</span><span class="sxs-lookup"><span data-stu-id="1d6cf-120">The latest firmware update release isn't applied on your Teams device.</span></span> <span data-ttu-id="1d6cf-121">而是在设备上自动应用的更新被延迟一个版本。</span><span class="sxs-lookup"><span data-stu-id="1d6cf-121">Instead, the update that's automatically applied on your device is delayed by one version.</span></span> <span data-ttu-id="1d6cf-122">例如，假设你的设备应用了版本 "10"，并且版本 "11" 已释放。</span><span class="sxs-lookup"><span data-stu-id="1d6cf-122">For example, assume your device has version "10" applied, and version "11" is released.</span></span> <span data-ttu-id="1d6cf-123">版本 "11" 尚不适用。</span><span class="sxs-lookup"><span data-stu-id="1d6cf-123">Version "11" won't be applied yet.</span></span> <span data-ttu-id="1d6cf-124">在版本 "12" 发布后，你的设备将仅更新到版本 "11"。</span><span class="sxs-lookup"><span data-stu-id="1d6cf-124">Instead your device will only be updated to version "11" after version "12" is released.</span></span>

> [!NOTE]
> <span data-ttu-id="1d6cf-125">某些设备尚不支持自动固件更新。</span><span class="sxs-lookup"><span data-stu-id="1d6cf-125">Some devices don't support automatic firmware update yet.</span></span> <span data-ttu-id="1d6cf-126">在不支持自动更新的设备上应用自动固件更新设置不会对这些设备产生任何影响。</span><span class="sxs-lookup"><span data-stu-id="1d6cf-126">Applying automatic firmware update settings on devices that don't support automatic updates won't have any affect on those devices.</span></span> <span data-ttu-id="1d6cf-127">有关设备是否支持自动固件更新的问题，请与您的设备制造商联系。</span><span class="sxs-lookup"><span data-stu-id="1d6cf-127">For questions about whether your device will support automatic firmware updates, contact your device manufacturer.</span></span>

<span data-ttu-id="1d6cf-128">若要为你的设备选择自动更新行为，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="1d6cf-128">To choose the automatic update behavior for your devices, do the following:</span></span>

1. <span data-ttu-id="1d6cf-129">通过访问登录到 Microsoft 团队管理中心 https://admin.teams.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="1d6cf-129">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com</span></span>
2. <span data-ttu-id="1d6cf-130">导航**设备**  >  **电话**或**协作栏**</span><span class="sxs-lookup"><span data-stu-id="1d6cf-130">Navigate **Devices** > **Phones** or **Collaboration bars**</span></span>
3. <span data-ttu-id="1d6cf-131">选择一个或多个设备，然后选择 "**更新**"</span><span class="sxs-lookup"><span data-stu-id="1d6cf-131">Select one or more devices and then select **Update**</span></span>
4. <span data-ttu-id="1d6cf-132">在 " **固件自动更新**" 下，选择下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="1d6cf-132">Under **Firmware auto-update**, select one of the following:</span></span>
    - <span data-ttu-id="1d6cf-133">只要**可用**第二个最新的设备固件更新应用于发布最新更新后的第一个周末。</span><span class="sxs-lookup"><span data-stu-id="1d6cf-133">**As soon as available** Second-newest device firmware update is applied on the first weekend after the latest update is released.</span></span>
    - <span data-ttu-id="1d6cf-134">**推迟30天** 第二个最新的设备固件更新将在最新更新发布30天后生效。</span><span class="sxs-lookup"><span data-stu-id="1d6cf-134">**Defer 30 days** Second-newest device firmware update is applied 30 days after the latest update is released.</span></span>
    - <span data-ttu-id="1d6cf-135">**推迟90天** 第二个最新的设备固件更新将在最新更新发布90天后生效。</span><span class="sxs-lookup"><span data-stu-id="1d6cf-135">**Defer 90 days** Second-newest device firmware update is applied 90 days after the latest update is released.</span></span>
5. <span data-ttu-id="1d6cf-136">选择 "**更新**"</span><span class="sxs-lookup"><span data-stu-id="1d6cf-136">Select **Update**</span></span>

<span data-ttu-id="1d6cf-137">如果出于任何原因需要还原设备固件更新，则需要将设备重置为出厂设置。</span><span class="sxs-lookup"><span data-stu-id="1d6cf-137">If, for whatever reason, you need to revert a device firmware update, you need to reset your device to its factory settings.</span></span> <span data-ttu-id="1d6cf-138">使用制造商提供的说明重置您的设备。</span><span class="sxs-lookup"><span data-stu-id="1d6cf-138">Reset your device using the instructions from its manufacturer.</span></span>  

## <a name="manually-update-remote-devices"></a><span data-ttu-id="1d6cf-139">手动更新远程设备</span><span class="sxs-lookup"><span data-stu-id="1d6cf-139">Manually update remote devices</span></span>

<span data-ttu-id="1d6cf-140">当您使用管理中心更新一个或多个设备时，您可以决定是立即更新设备还是安排未来日期和时间的更新。</span><span class="sxs-lookup"><span data-stu-id="1d6cf-140">When you update one or more devices using the admin center, you can decide whether to update the devices immediately or schedule an update for a future date and time.</span></span>

<span data-ttu-id="1d6cf-141">若要手动更新远程设备，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="1d6cf-141">To manually update remote devices, do the following:</span></span>

1. <span data-ttu-id="1d6cf-142">通过访问登录到 Microsoft 团队管理中心 https://admin.teams.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="1d6cf-142">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com</span></span>
2. <span data-ttu-id="1d6cf-143">导航**设备**  >  **电话**或**协作栏**</span><span class="sxs-lookup"><span data-stu-id="1d6cf-143">Navigate  **Devices** > **Phones** or **Collaboration bars**</span></span>
3. <span data-ttu-id="1d6cf-144">选择一个或多个设备，然后选择 "**更新**"</span><span class="sxs-lookup"><span data-stu-id="1d6cf-144">Select one or more devices and then select **Update**</span></span>
4. <span data-ttu-id="1d6cf-145">在 " **手动更新**" 下，如果想要计划更新未来日期和时间，请选择 " **计划** "。</span><span class="sxs-lookup"><span data-stu-id="1d6cf-145">Under **Manual updates**, select **Schedule** if you want to schedule the update for a future date and time.</span></span> <span data-ttu-id="1d6cf-146">将在 " **时区**" 中选择的时区中的日期和时间应用更新。</span><span class="sxs-lookup"><span data-stu-id="1d6cf-146">The updates are applied at the date and time in the timezone selected in **Timezone**.</span></span>

<span data-ttu-id="1d6cf-147">你将看到的内容取决于你是否选择了一个或多个设备。</span><span class="sxs-lookup"><span data-stu-id="1d6cf-147">What you'll see depends on whether you have one, or multiple, devices selected.</span></span> <span data-ttu-id="1d6cf-148">下面的左图显示了选定的多个设备，而右侧的图像显示选定的单个设备。</span><span class="sxs-lookup"><span data-stu-id="1d6cf-148">The left image below shows multiple devices selected while the image on the right shows a single device selected.</span></span>

:::image type="content" source="../media/device-update-status.png" alt-text="设备更新状态窗格中的单个和多个设备视图":::

<span data-ttu-id="1d6cf-150">选择多个设备时，可以选择要对每个选定设备应用的更新类型。</span><span class="sxs-lookup"><span data-stu-id="1d6cf-150">When you select multiple devices, you can choose which update types to apply to each selected device.</span></span> <span data-ttu-id="1d6cf-151">选择要应用的更新类型，然后选择 " **更新**"。</span><span class="sxs-lookup"><span data-stu-id="1d6cf-151">Select the update types you want to apply and select **Update**.</span></span>

<span data-ttu-id="1d6cf-152">选择单个设备时，将显示适用于该设备的更新。</span><span class="sxs-lookup"><span data-stu-id="1d6cf-152">When you select a single device, updates that are available for the device are shown.</span></span> <span data-ttu-id="1d6cf-153">如果有多个更新类型可用于设备，请选择要应用的每个更新类型。</span><span class="sxs-lookup"><span data-stu-id="1d6cf-153">If multiple update types are available for the device, select each update type to apply.</span></span> <span data-ttu-id="1d6cf-154">你可以查看在设备上应用的 **当前版本** 以及将应用的 **新版本** 。</span><span class="sxs-lookup"><span data-stu-id="1d6cf-154">You can view the **Current version** applied on the device and the **New version** that will be applied.</span></span> <span data-ttu-id="1d6cf-155">选择要应用) 的更新 (，然后选择 " **更新**"。</span><span class="sxs-lookup"><span data-stu-id="1d6cf-155">Select the update(s) you want to apply and select **Update**.</span></span>

<span data-ttu-id="1d6cf-156">选择 " **更新**" 后，如果你计划更新，将在你选择的日期和时间将更新应用到你的设备。</span><span class="sxs-lookup"><span data-stu-id="1d6cf-156">After you select **Update**, updates are applied to your devices at the date and time you selected if you scheduled an update.</span></span> <span data-ttu-id="1d6cf-157">如果您没有选择将来的日期和时间，则在几分钟内将更新应用到您的设备。</span><span class="sxs-lookup"><span data-stu-id="1d6cf-157">If you didn't select a future date and time, updates are applied to your devices within a few minutes.</span></span>
