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
ms.openlocfilehash: 7e47c9394eddfa73b8b55279b68ae59ff7b6de3d
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2020
ms.locfileid: "44944081"
---
# <a name="update-microsoft-teams-devices-remotely"></a><span data-ttu-id="67b33-103">远程更新 Microsoft 团队设备</span><span class="sxs-lookup"><span data-stu-id="67b33-103">Update Microsoft Teams devices remotely</span></span>

<span data-ttu-id="67b33-104">使用 Microsoft 团队管理中心，您可以通过远程方式更新团队设备（如电话和协作栏），并且可以选择设备固件自动更新行为。</span><span class="sxs-lookup"><span data-stu-id="67b33-104">Using the Microsoft Teams admin center, you can update your Teams devices, such as phones and collaboration bars, remotely, and you can choose device firmware automatic-update behavior.</span></span> <span data-ttu-id="67b33-105">你可以使用团队管理中心在你的设备上更新以下内容：</span><span class="sxs-lookup"><span data-stu-id="67b33-105">You can update the following on your devices using the Teams admin center:</span></span>

- <span data-ttu-id="67b33-106">团队应用和团队管理员代理</span><span class="sxs-lookup"><span data-stu-id="67b33-106">Teams app and teams admin agent</span></span>
- <span data-ttu-id="67b33-107">公司门户应用</span><span class="sxs-lookup"><span data-stu-id="67b33-107">Company portal app</span></span>
- <span data-ttu-id="67b33-108">OEM 代理应用</span><span class="sxs-lookup"><span data-stu-id="67b33-108">OEM agent app</span></span>
- <span data-ttu-id="67b33-109">设备固件</span><span class="sxs-lookup"><span data-stu-id="67b33-109">Device firmware</span></span>

<span data-ttu-id="67b33-110">设备固件更新可以自动应用，也可以计划在将来的日期和时间使用。</span><span class="sxs-lookup"><span data-stu-id="67b33-110">Device firmware updates can either be applied automatically or scheduled for a future date and time.</span></span> <span data-ttu-id="67b33-111">其他可用的设备更新不会自动应用，但可以手动或计划在将来的日期和时间应用。</span><span class="sxs-lookup"><span data-stu-id="67b33-111">Other available device updates aren't applied automatically, but can be applied manually or scheduled for a future date and time.</span></span>

> [!NOTE]
> <span data-ttu-id="67b33-112">虽然可以计划设备固件更新，但如果计划的日期和时间位于配置的最大30个或90天的延迟之后，则会在达到最大延迟时应用固件更新。</span><span class="sxs-lookup"><span data-stu-id="67b33-112">While device firmware updates can be scheduled, if the scheduled date and time falls after the configured maximum 30 or 90 day delay, the firmware update is applied when the maximum delay is reached.</span></span> <span data-ttu-id="67b33-113">将忽略计划的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="67b33-113">The scheduled date and time are ignored.</span></span>

## <a name="choose-automatic-device-firmware-update-behavior"></a><span data-ttu-id="67b33-114">选择 "自动设备固件更新" 行为</span><span class="sxs-lookup"><span data-stu-id="67b33-114">Choose automatic device firmware update behavior</span></span>

<span data-ttu-id="67b33-115">将自动应用设备固件更新。</span><span class="sxs-lookup"><span data-stu-id="67b33-115">Device firmware updates are applied automatically.</span></span> <span data-ttu-id="67b33-116">你可以决定是在发布更新后立即应用更新，还是在发布更新后30天或90天应用更新。</span><span class="sxs-lookup"><span data-stu-id="67b33-116">You can decide whether to apply updates as soon as one is released, or 30 or 90 days after an update is released.</span></span> <span data-ttu-id="67b33-117">默认情况下，设备固件更新将在30天发布后应用。</span><span class="sxs-lookup"><span data-stu-id="67b33-117">By default, device firmware updates are applied 30 days one released.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="67b33-118">你的团队设备未应用最新的固件更新版本。</span><span class="sxs-lookup"><span data-stu-id="67b33-118">The latest firmware update release isn't applied on your Teams device.</span></span> <span data-ttu-id="67b33-119">而是在设备上自动应用的更新被延迟一个版本。</span><span class="sxs-lookup"><span data-stu-id="67b33-119">Instead, the update that's automatically applied on your device is delayed by one version.</span></span> <span data-ttu-id="67b33-120">例如，假设你的设备应用了版本 "10"，并且版本 "11" 已释放。</span><span class="sxs-lookup"><span data-stu-id="67b33-120">For example, assume your device has version "10" applied, and version "11" is released.</span></span> <span data-ttu-id="67b33-121">版本 "11" 尚不适用。</span><span class="sxs-lookup"><span data-stu-id="67b33-121">Version "11" won't be applied yet.</span></span> <span data-ttu-id="67b33-122">在版本 "12" 发布后，你的设备将仅更新到版本 "11"。</span><span class="sxs-lookup"><span data-stu-id="67b33-122">Instead your device will only be updated to version "11" after version "12" is released.</span></span>

<span data-ttu-id="67b33-123">若要为你的设备选择自动更新行为，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="67b33-123">To choose the automatic update behavior for your devices, do the following:</span></span>

1. <span data-ttu-id="67b33-124">通过访问登录到 Microsoft 团队管理中心https://admin.teams.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="67b33-124">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com</span></span>
2. <span data-ttu-id="67b33-125">导航**设备**  >  **电话**或**协作栏**</span><span class="sxs-lookup"><span data-stu-id="67b33-125">Navigate **Devices** > **Phones** or **Collaboration bars**</span></span>
3. <span data-ttu-id="67b33-126">选择一个或多个设备，然后选择 "**更新**"</span><span class="sxs-lookup"><span data-stu-id="67b33-126">Select one or more devices and then select **Update**</span></span>
4. <span data-ttu-id="67b33-127">在 "**固件自动更新**" 下，选择下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="67b33-127">Under **Firmware auto-update**, select one of the following:</span></span>
    - <span data-ttu-id="67b33-128">只要**可用**第二个最新的设备固件更新将在最新更新发布后尽快应用。</span><span class="sxs-lookup"><span data-stu-id="67b33-128">**As soon as available** Second-newest device firmware update is applied as soon as possible after the latest update is released.</span></span>
    - <span data-ttu-id="67b33-129">**推迟30天**第二个最新的设备固件更新将在最新更新发布30天后生效。</span><span class="sxs-lookup"><span data-stu-id="67b33-129">**Defer 30 days** Second-newest device firmware update is applied 30 days after the latest update is released.</span></span>
    - <span data-ttu-id="67b33-130">**推迟90天**第二个最新的设备固件更新将在最新更新发布90天后生效。</span><span class="sxs-lookup"><span data-stu-id="67b33-130">**Defer 90 days** Second-newest device firmware update is applied 90 days after the latest update is released.</span></span>
5. <span data-ttu-id="67b33-131">选择 "**更新**"</span><span class="sxs-lookup"><span data-stu-id="67b33-131">Select **Update**</span></span>

<span data-ttu-id="67b33-132">如果出于任何原因需要还原设备固件更新，则需要将设备重置为出厂设置。</span><span class="sxs-lookup"><span data-stu-id="67b33-132">If, for whatever reason, you need to revert a device firmware update, you need to reset your device to its factory settings.</span></span> <span data-ttu-id="67b33-133">使用制造商提供的说明重置您的设备。</span><span class="sxs-lookup"><span data-stu-id="67b33-133">Reset your device using the instructions from its manufacturer.</span></span>  

## <a name="manually-update-remote-devices"></a><span data-ttu-id="67b33-134">手动更新远程设备</span><span class="sxs-lookup"><span data-stu-id="67b33-134">Manually update remote devices</span></span>

<span data-ttu-id="67b33-135">当您使用管理中心更新一个或多个设备时，您可以决定是立即更新设备还是安排未来日期和时间的更新。</span><span class="sxs-lookup"><span data-stu-id="67b33-135">When you update one or more devices using the admin center, you can decide whether to update the devices immediately or schedule an update for a future date and time.</span></span>

<span data-ttu-id="67b33-136">若要手动更新远程设备，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="67b33-136">To manually update remote devices, do the following:</span></span>

1. <span data-ttu-id="67b33-137">通过访问登录到 Microsoft 团队管理中心https://admin.teams.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="67b33-137">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com</span></span>
2. <span data-ttu-id="67b33-138">导航**设备**  >  **电话**或**协作栏**</span><span class="sxs-lookup"><span data-stu-id="67b33-138">Navigate  **Devices** > **Phones** or **Collaboration bars**</span></span>
3. <span data-ttu-id="67b33-139">选择一个或多个设备，然后选择 "**更新**"</span><span class="sxs-lookup"><span data-stu-id="67b33-139">Select one or more devices and then select **Update**</span></span>
4. <span data-ttu-id="67b33-140">在 "**手动更新**" 下，如果想要计划更新未来日期和时间，请选择 "**计划**"。</span><span class="sxs-lookup"><span data-stu-id="67b33-140">Under **Manual updates**, select **Schedule** if you want to schedule the update for a future date and time.</span></span> <span data-ttu-id="67b33-141">将在 "**时区**" 中选择的时区中的日期和时间应用更新。</span><span class="sxs-lookup"><span data-stu-id="67b33-141">The updates are applied at the date and time in the timezone selected in **Timezone**.</span></span>

<span data-ttu-id="67b33-142">你将看到的内容取决于你是否选择了一个或多个设备。</span><span class="sxs-lookup"><span data-stu-id="67b33-142">What you'll see depends on whether you have one, or multiple, devices selected.</span></span> <span data-ttu-id="67b33-143">下面的左图显示了选定的多个设备，而右侧的图像显示选定的单个设备。</span><span class="sxs-lookup"><span data-stu-id="67b33-143">The left image below shows multiple devices selected while the image on the right shows a single device selected.</span></span>

:::image type="content" source="../media/device-update-status.png" alt-text="设备更新状态窗格中的单个和多个设备视图":::

<span data-ttu-id="67b33-145">选择多个设备时，可以选择要对每个选定设备应用的更新类型。</span><span class="sxs-lookup"><span data-stu-id="67b33-145">When you select multiple devices, you can choose which update types to apply to each selected device.</span></span> <span data-ttu-id="67b33-146">选择要应用的更新类型，然后选择 "**更新**"。</span><span class="sxs-lookup"><span data-stu-id="67b33-146">Select the update types you want to apply and select **Update**.</span></span>

<span data-ttu-id="67b33-147">选择单个设备时，将显示适用于该设备的更新。</span><span class="sxs-lookup"><span data-stu-id="67b33-147">When you select a single device, updates that are available for the device are shown.</span></span> <span data-ttu-id="67b33-148">如果有多个更新类型可用于设备，请选择要应用的每个更新类型。</span><span class="sxs-lookup"><span data-stu-id="67b33-148">If multiple update types are available for the device, select each update type to apply.</span></span> <span data-ttu-id="67b33-149">你可以查看在设备上应用的**当前版本**以及将应用的**新版本**。</span><span class="sxs-lookup"><span data-stu-id="67b33-149">You can view the **Current version** applied on the device and the **New version** that will be applied.</span></span> <span data-ttu-id="67b33-150">选择要应用的更新，然后选择 "**更新**"。</span><span class="sxs-lookup"><span data-stu-id="67b33-150">Select the update(s) you want to apply and select **Update**.</span></span>

<span data-ttu-id="67b33-151">选择 "**更新**" 后，如果你计划更新，将在你选择的日期和时间将更新应用到你的设备。</span><span class="sxs-lookup"><span data-stu-id="67b33-151">After you select **Update**, updates are applied to your devices at the date and time you selected if you scheduled an update.</span></span> <span data-ttu-id="67b33-152">如果您没有选择将来的日期和时间，则在几分钟内将更新应用到您的设备。</span><span class="sxs-lookup"><span data-stu-id="67b33-152">If you didn't select a future date and time, updates are applied to your devices within a few minutes.</span></span>
