---
title: 使用会议和会议设置Microsoft Teams 会议室Surface Hub
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
description: 配置Teams 会议室设备，Surface Hub一台设备加入会议时加入会议。
ms.openlocfilehash: b81d6fca5c263bb8ba1dcd07e80167425bd42fc0
ms.sourcegitcommit: 3704577b1424c063fd925a58a6f6d0b3ff2c8148
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2021
ms.locfileid: "53278675"
---
# <a name="set-up-coordinated-meetings-with-microsoft-teams-rooms-and-surface-hub"></a><span data-ttu-id="1a2c7-103">使用会议设置协调Microsoft Teams 会议室Surface Hub</span><span class="sxs-lookup"><span data-stu-id="1a2c7-103">Set up Coordinated Meetings with Microsoft Teams Rooms and Surface Hub</span></span>

<span data-ttu-id="1a2c7-104">如果您在会议室中拥有一Microsoft Teams 会议室或 Surface Hub，您可以设置协调会议。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-104">If you have one or more Microsoft Teams Rooms devices or Surface Hubs in a meeting room, you can set up Coordinated Meetings.</span></span> <span data-ttu-id="1a2c7-105">协调会议允许您设置 Teams 会议室 设备和 Surface Hub，以便当您在一台设备上加入会议时，会议室的其他设备也加入同一会议。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-105">Coordinated Meetings lets you set up your Teams Rooms devices and Surface Hubs so that when you join a meeting on one device, the other devices in the room are also joined to the same meeting.</span></span> <span data-ttu-id="1a2c7-106">您可以配置摄像机、扬声器和麦克风，以便启用为参与者提供最佳体验的摄像机，同时禁用其他设备。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-106">You can configure your cameras, speakers, and microphones so that the ones that give participants the best experience are enabled while others are disabled.</span></span> <span data-ttu-id="1a2c7-107">这可以避免参与者在将多个设备添加到会议时可能体验到的干扰回声和反馈噪音。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-107">This avoids the dreaded echo and feedback noise participants can experience when adding multiple devices to a meeting.</span></span>

<span data-ttu-id="1a2c7-108">若要设置协调会议，你需要确保你的 Teams 会议室 设备和 Surface Hub 已正确配置为参加会议。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-108">To set up Coordinated Meetings, you need to make sure your Teams Rooms devices and Surface Hubs are already correctly configured to participate in meetings.</span></span> <span data-ttu-id="1a2c7-109">最重要的是，每台设备需要有自己的会议室Exchange邮箱。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-109">Most importantly, each device needs to have its own Exchange room mailbox.</span></span> <span data-ttu-id="1a2c7-110">若要了解如何设置它们，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="1a2c7-110">For information on how to set them up, see the following articles:</span></span>

- [<span data-ttu-id="1a2c7-111">部署 Microsoft Teams 会议室</span><span class="sxs-lookup"><span data-stu-id="1a2c7-111">Deploy Microsoft Teams Rooms</span></span>](../rooms/rooms-deploy.md)
- [<span data-ttu-id="1a2c7-112">创建 Surface Hub 2S 设备帐户</span><span class="sxs-lookup"><span data-stu-id="1a2c7-112">Create Surface Hub 2S device account</span></span>](/surface-hub/surface-hub-2s-account)

<span data-ttu-id="1a2c7-113">确认你的设备和 Surface Hub Teams 会议室自动接受会议并成功加入会议后，可以设置协调会议。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-113">After you've confirmed that your Teams Rooms devices and Surface Hubs can automatically accept meetings and join them successfully, you can set up Coordinated Meetings.</span></span>

<span data-ttu-id="1a2c7-114">应分别针对每个会议室完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-114">The following steps should be completed for each meeting room separately.</span></span> <span data-ttu-id="1a2c7-115">不应将一个会议室中的设备设置为与其他会议室中的设备协调会议。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-115">Devices in one meeting room shouldn't be set up for Coordinated Meetings with devices in other meeting rooms.</span></span>

## <a name="step-1-plan-your-coordinated-meeting-experience"></a><span data-ttu-id="1a2c7-116">步骤 1：规划协调会议体验</span><span class="sxs-lookup"><span data-stu-id="1a2c7-116">Step 1: Plan your Coordinated Meeting experience</span></span>

<span data-ttu-id="1a2c7-117">在做出任何配置更改之前，您需要确定哪些设备将在每个会议室中执行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-117">Before you make any configuration changes, you need to decide which devices will do what in each meeting room.</span></span> <span data-ttu-id="1a2c7-118">也就是说，对于给定的会议室，你需要确定哪个设备将具有活动的麦克风、摄像头和白板。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-118">That is, for a given meeting room, you need to decide which device will have the active microphone, camera, and whiteboard.</span></span> <span data-ttu-id="1a2c7-119">配置设备的方式取决于特定的环境，但以下是一些一般建议：一开始建议：</span><span class="sxs-lookup"><span data-stu-id="1a2c7-119">How you configure your devices depends on your specific environment, but here are some general recommendations to start with:</span></span>

- <span data-ttu-id="1a2c7-120">**麦克风** Teams 会议室设备</span><span class="sxs-lookup"><span data-stu-id="1a2c7-120">**Microphone** Teams Rooms device</span></span>
- <span data-ttu-id="1a2c7-121">**相机** Teams 会议室默认 (打开，) Surface Hub (关闭，但参与者或参与者) </span><span class="sxs-lookup"><span data-stu-id="1a2c7-121">**Camera** Teams Rooms device (on by default) and Surface Hub (off by default, but allowed to be turned on by participants)</span></span>
- <span data-ttu-id="1a2c7-122">**白板Surface Hub**</span><span class="sxs-lookup"><span data-stu-id="1a2c7-122">**Whiteboard** Surface Hub</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1a2c7-123">请确保仅在一台设备上启用麦克风。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-123">Make sure you enable the microphone only on one device.</span></span> <span data-ttu-id="1a2c7-124">如果你在多台设备上启用它，你将体验到音频回声和反馈。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-124">If you enable it on more than one device, you'll experience audio echo and feedback.</span></span>

## <a name="step-2-get-your-devices-upns"></a><span data-ttu-id="1a2c7-125">步骤 2：获取设备的 UPN</span><span class="sxs-lookup"><span data-stu-id="1a2c7-125">Step 2: Get your devices' UPNs</span></span>

<span data-ttu-id="1a2c7-126">当您在会议室中设置协调会议体验时，您需要告知Teams 会议室会议室中的设备和 Surface Hub 要协调哪些设备。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-126">When you set up a Coordinated Meeting experience in a meeting room, you need to tell the Teams Rooms devices and Surface Hubs in that room which devices to coordinate with.</span></span> <span data-ttu-id="1a2c7-127">为此，将用户主体名称 (UPN) 应协调到其配置的设备中。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-127">This is done by adding the user principal name (UPN) of the devices it should coordinate with to its configuration.</span></span> <span data-ttu-id="1a2c7-128">如果不知道要为协调会议设置的每个设备的 UPN，可以使用Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-128">If you don't know the UPNs for each of the devices you want to set up for Coordinated Meetings, you can find them using the Microsoft 365 admin center.</span></span> 

<span data-ttu-id="1a2c7-129">需要分配管理员角色才能访问Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-129">You need to be assigned an admin role to access the Microsoft 365 admin center.</span></span> <span data-ttu-id="1a2c7-130">有关详细信息，请参阅 [关于管理员角色](/microsoft-365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-130">For more information, see [About admin roles](/microsoft-365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="1a2c7-131">若要获取 Teams 会议室 和 Surface Hub 的 UPN，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="1a2c7-131">To get the UPNs of your Teams Rooms devices and Surface Hubs, do the following:</span></span>

1. <span data-ttu-id="1a2c7-132">访问 登录到 https://admin.microsoft.com Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-132">Sign in to the Microsoft 365 admin center by visiting https://admin.microsoft.com.</span></span>
2. <span data-ttu-id="1a2c7-133">转到"**用户**  >  **""活动用户"。**</span><span class="sxs-lookup"><span data-stu-id="1a2c7-133">Go to **Users** > **Active users**.</span></span>
3. <span data-ttu-id="1a2c7-134">在"显示名称"Teams 会议室或Surface Hub"名称"列中 ("搜索"框，如果有许多用户) 。 </span><span class="sxs-lookup"><span data-stu-id="1a2c7-134">Find the name of your Teams Rooms device or Surface Hub in the **Display name** column (you can use the **Search** box if you have many users).</span></span>
4. <span data-ttu-id="1a2c7-135">在"用户名"列中找到UPN (该 UPN 的外观与 alias@contoso.com 或 alias@contoso.onmicrosoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-135">Find the UPN in the **Username** column (it'll look something like alias@contoso.com or alias@contoso.onmicrosoft.com).</span></span>
5. <span data-ttu-id="1a2c7-136">对将参与协调会议的每个设备重复此操作。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-136">Repeat this for each device that will participate in Coordinated Meetings.</span></span>

## <a name="step-3-create-a-deployment-worksheet"></a><span data-ttu-id="1a2c7-137">步骤 3：创建部署工作表</span><span class="sxs-lookup"><span data-stu-id="1a2c7-137">Step 3: Create a deployment worksheet</span></span>

<span data-ttu-id="1a2c7-138">规划协调会议体验并收集设备的 UPN 列表后，建议创建部署工作表。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-138">After you've planned your Coordinated Meeting experience and gathered a list of your devices' UPNs, it's a good idea to create a deployment worksheet.</span></span> <span data-ttu-id="1a2c7-139">部署工作表将帮助你可视化要在所有设备上设置的配置，从而验证选择并检查错误。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-139">A deployment worksheet will help you visualize the configuration you want to set across all of your devices, allowing you to validate your choices and check for errors.</span></span>

<span data-ttu-id="1a2c7-140">在电子表格应用中，添加第一列中以下内容的行：</span><span class="sxs-lookup"><span data-stu-id="1a2c7-140">In a spreadsheet app, add rows for the following in the first column:</span></span>

| <span data-ttu-id="1a2c7-141">设置</span><span class="sxs-lookup"><span data-stu-id="1a2c7-141">Setting</span></span>                | <span data-ttu-id="1a2c7-142">说明</span><span class="sxs-lookup"><span data-stu-id="1a2c7-142">Description</span></span>      |
|------------------------|-----------------|
| <span data-ttu-id="1a2c7-143">**音频默认值**</span><span class="sxs-lookup"><span data-stu-id="1a2c7-143">**Audio default**</span></span>      | <span data-ttu-id="1a2c7-144">确定在会议开始时麦克风将处于活动状态的设备。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-144">Determines on which device the microphone will be active when a meeting starts.</span></span> <span data-ttu-id="1a2c7-145">只有一 (设备Teams 会议室设备) 可以将此字段设置为 ，而其余设备必须将此字段设置为 以避免音频回声和 `true` `false` 反馈。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-145">Only one device (typically a Teams Rooms device) can have this field set to `true` while the rest of the devices must have this field set to `false` to avoid audio echo and feedback.</span></span>          |
| <span data-ttu-id="1a2c7-146">**已启用音频**</span><span class="sxs-lookup"><span data-stu-id="1a2c7-146">**Audio enabled**</span></span>      | <span data-ttu-id="1a2c7-147">确定会议参与者是否可以打开或关闭麦克风。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-147">Determines whether participants in a meeting can toggle the microphone on or off.</span></span> <span data-ttu-id="1a2c7-148">将 **"音频默认值** "设置为 的设备应将此设置设置为 ，以便参与者不会意外打开麦克风并 `false` `false` 引发音频回声或反馈。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-148">Devices on which **Audio default** is set to `false` should have this setting set to `false` so that participants can't accidentally turn on a microphone and cause audio echo or feedback.</span></span><p><span data-ttu-id="1a2c7-149">如果 **"音频** 默认值"设置为 `true` ，则忽略此设置，参与者可以将麦克风设为静音或取消静音。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-149">If **Audio default** is set to `true`, this setting is ignored and participants can mute or unmute the microphone.</span></span>          |
| <span data-ttu-id="1a2c7-150">**视频默认值**</span><span class="sxs-lookup"><span data-stu-id="1a2c7-150">**Video default**</span></span>      | <span data-ttu-id="1a2c7-151">确定在会议开始时相机将在哪个设备上处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-151">Determines on which device the camera will be active when a meeting starts.</span></span> <span data-ttu-id="1a2c7-152">为获得最佳体验，建议仅将Teams 会议室设置为 ，而所有其他 `true` 设备都设置为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-152">For the best experience, we recommend that only the Teams Rooms device be set to `true` while all other devices are set to `false`.</span></span>          |
| <span data-ttu-id="1a2c7-153">**视频已启用**</span><span class="sxs-lookup"><span data-stu-id="1a2c7-153">**Video enabled**</span></span>      | <span data-ttu-id="1a2c7-154">确定会议参与者是否可以打开或关闭摄像机。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-154">Determines whether participants in a meeting can toggle the camera on or off.</span></span> <span data-ttu-id="1a2c7-155">您可以在事件参与者想要共享不同视频透视图的其他任何设备上 (，例如，如果参与者正在使用 Surface Hub `true` 白板) 。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-155">You can set this to `true` on any other devices in the event participants want to share different video perspectives (such as if a participant is using the Surface Hub whiteboard).</span></span> <span data-ttu-id="1a2c7-156">如果不希望参与者在设备上打开或关闭摄像机，请将其设置为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-156">If you don't want participants to turn a camera on or off on a device, set this to `false`.</span></span><p> <span data-ttu-id="1a2c7-157">如果 **"视频** 默认值"设置为 `true` ，则忽略此设置，参与者可以打开或关闭摄像机。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-157">If **Video default** is set to `true`, this setting is ignored and participants can turn the camera on or off.</span></span>         |
| <span data-ttu-id="1a2c7-158">**白板默认值**</span><span class="sxs-lookup"><span data-stu-id="1a2c7-158">**Whiteboard default**</span></span> | <span data-ttu-id="1a2c7-159">确定Teams 会议室设备是否显示由其中一个会议参与者共享的白板。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-159">Determines whether the Teams Rooms device will display a whiteboard shared by one of the meeting participants.</span></span> <span data-ttu-id="1a2c7-160">如果你拥有一个Surface Hub并且没有，我们建议你对此进行 `false` `true` 设置。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-160">We recommend that you set this to `false` if you have a Surface Hub and `true` if you don't have one.</span></span> <span data-ttu-id="1a2c7-161">此设置对 Surface Hub 没有影响。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-161">This setting has no effect on Surface Hubs.</span></span> <span data-ttu-id="1a2c7-162">Surface Hub 将始终显示会议参与者共享的白板。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-162">Surface Hubs will always display a whiteboard shared by meeting participants.</span></span>         |
| <span data-ttu-id="1a2c7-163">**已启用 Whiteboard**</span><span class="sxs-lookup"><span data-stu-id="1a2c7-163">**Whiteboard enabled**</span></span> | <span data-ttu-id="1a2c7-164">确定会议参与者是否可以打开或关闭白板。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-164">Determines whether participants in a meeting can toggle the whiteboard on or off.</span></span> <span data-ttu-id="1a2c7-165">如果不希望参与者在设备上打开或关闭白板，请将其设置为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-165">If you don't want participants to turn the whiteboard on or off on a device, set this to `false`.</span></span> <p><span data-ttu-id="1a2c7-166">如果 **Whiteboard 默认值** 设置为 `true` ，则忽略此设置，参与者可以打开或关闭白板。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-166">If **Whiteboard default** is set to `true`, this setting is ignored and participants can turn the whiteboard on or off.</span></span>
| <span data-ttu-id="1a2c7-167">**受信任的帐户**</span><span class="sxs-lookup"><span data-stu-id="1a2c7-167">**Trusted accounts**</span></span>   | <span data-ttu-id="1a2c7-168">这是每个 Teams 会议室设备或设备的 UPN 的逗号分隔列表Surface Hub设备应接受会议加入请求，或者应发送到哪些会议加入请求。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-168">This is a comma-separated list of UPNs for each Teams Room device or Surface Hub that the device should accept meeting join requests from, or to which meeting join requests should be sent.</span></span> |

<span data-ttu-id="1a2c7-169">在后续列中，添加每个Teams 会议室和 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-169">In subsequent columns, add each of your Teams Rooms devices and Surface Hubs.</span></span> <span data-ttu-id="1a2c7-170">在每个列中，填写与想要用于会议室的体验对应的值。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-170">In each column, fill out the values that correspond to the experience you want for the meeting room.</span></span> <span data-ttu-id="1a2c7-171">下面是一个示例，其中一个设备Teams 会议室一个Surface Hub：</span><span class="sxs-lookup"><span data-stu-id="1a2c7-171">Here's an example with one Teams Rooms device and one Surface Hub:</span></span>

- <span data-ttu-id="1a2c7-172">Teams设备</span><span class="sxs-lookup"><span data-stu-id="1a2c7-172">Teams device</span></span>
  - <span data-ttu-id="1a2c7-173">音频和视频在会议 **开始时** 打开。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-173">Audio and video are turned **on** when a meeting starts.</span></span> <span data-ttu-id="1a2c7-174">参与者 **可以** 打开或关闭音频和视频。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-174">Participants **can** toggle audio and video on or off.</span></span>
  - <span data-ttu-id="1a2c7-175">显示共享白板已关闭。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-175">Displaying a shared whiteboard is turned off.</span></span>
- <span data-ttu-id="1a2c7-176">Surface Hub</span><span class="sxs-lookup"><span data-stu-id="1a2c7-176">Surface Hub</span></span>
  - <span data-ttu-id="1a2c7-177">会议开始时 **，** 音频已关闭。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-177">Audio is turned **off** when a meeting starts.</span></span> <span data-ttu-id="1a2c7-178">参与者 **无法打开** 或关闭音频。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-178">Participants **can't** toggle audio on or off.</span></span>
  - <span data-ttu-id="1a2c7-179">会议开始时 **，** 视频已关闭。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-179">Video is turned **off** when a meeting starts.</span></span> <span data-ttu-id="1a2c7-180">参与者 **可以** 打开或关闭视频。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-180">Participants **can** toggle video on or off.</span></span>

| <span data-ttu-id="1a2c7-181">设置</span><span class="sxs-lookup"><span data-stu-id="1a2c7-181">Setting</span></span>                | <span data-ttu-id="1a2c7-182">Teams会议室</span><span class="sxs-lookup"><span data-stu-id="1a2c7-182">Teams Room</span></span>      | <span data-ttu-id="1a2c7-183">Surface Hub</span><span class="sxs-lookup"><span data-stu-id="1a2c7-183">Surface Hub</span></span>      |
|------------------------|-----------------|------------------|
| <span data-ttu-id="1a2c7-184">**音频默认值**</span><span class="sxs-lookup"><span data-stu-id="1a2c7-184">**Audio default**</span></span>      | `true`          | `false`          |
| <span data-ttu-id="1a2c7-185">**已启用音频**</span><span class="sxs-lookup"><span data-stu-id="1a2c7-185">**Audio enabled**</span></span>      | `true`          | `false`          |
| <span data-ttu-id="1a2c7-186">**视频默认值**</span><span class="sxs-lookup"><span data-stu-id="1a2c7-186">**Video default**</span></span>      | `true`          | `false`          |
| <span data-ttu-id="1a2c7-187">**视频已启用**</span><span class="sxs-lookup"><span data-stu-id="1a2c7-187">**Video enabled**</span></span>      | `true`          | `true`           |
| <span data-ttu-id="1a2c7-188">**白板默认值**</span><span class="sxs-lookup"><span data-stu-id="1a2c7-188">**Whiteboard default**</span></span> | `false`         | `false`          |
| <span data-ttu-id="1a2c7-189">**受信任的帐户**</span><span class="sxs-lookup"><span data-stu-id="1a2c7-189">**Trusted accounts**</span></span>   | <span data-ttu-id="1a2c7-190">hub@contoso.com</span><span class="sxs-lookup"><span data-stu-id="1a2c7-190">hub@contoso.com</span></span> | <span data-ttu-id="1a2c7-191">room@contoso.com</span><span class="sxs-lookup"><span data-stu-id="1a2c7-191">room@contoso.com</span></span> |

## <a name="step-4-configure-teams-rooms-device"></a><span data-ttu-id="1a2c7-192">步骤 4：配置Teams 会议室设备</span><span class="sxs-lookup"><span data-stu-id="1a2c7-192">Step 4: Configure Teams Rooms device</span></span>

<span data-ttu-id="1a2c7-193">可以使用设备的触摸屏在 Teams 会议室 设备上设置协调会议，或者，如果需要设置许多设备，并且想要从一个中心位置设置协调会议，可以使用 XML 配置文件。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-193">You can either set up Coordinated Meetings on a Teams Rooms device using the device's touch screen or, if you need to set up many devices and want to do so from a central location, you can use an XML configuration file.</span></span>

<span data-ttu-id="1a2c7-194">使用在上一步中创建的工作表来帮助设置设备。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-194">Use the worksheet you created in the previous step to help you set up your devices.</span></span>

### <a name="use-the-teams-rooms-devices-touch-screen"></a><span data-ttu-id="1a2c7-195">使用Teams 会议室设备的触摸屏</span><span class="sxs-lookup"><span data-stu-id="1a2c7-195">Use the Teams Rooms device's touch screen</span></span>

<span data-ttu-id="1a2c7-196">若要在设备上设置协调会议，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="1a2c7-196">To set up Coordinated Meetings on a device, do the following:</span></span>

1. <span data-ttu-id="1a2c7-197">选择 **...。更多**  >  **设置。**</span><span class="sxs-lookup"><span data-stu-id="1a2c7-197">Select **... More** > **Settings**.</span></span>
2. <span data-ttu-id="1a2c7-198">输入管理员密码，然后选择"**是"。**</span><span class="sxs-lookup"><span data-stu-id="1a2c7-198">Enter the Administrator password and select **Yes**.</span></span>
3. <span data-ttu-id="1a2c7-199">选择 **"协调会议"。**</span><span class="sxs-lookup"><span data-stu-id="1a2c7-199">Select **Coordinated Meetings**.</span></span>
4. <span data-ttu-id="1a2c7-200">在 **"选项"** 下，将 **"协调会议"** 设置为 _on。_</span><span class="sxs-lookup"><span data-stu-id="1a2c7-200">Under **Options**, set **Coordinated Meeting** to _on_.</span></span>
5. <span data-ttu-id="1a2c7-201">如果 **工作表中的**"音频"默认为 ，将"打开此设备的麦克风"设置为"打开"， `true` 否则将其 _关闭_。 </span><span class="sxs-lookup"><span data-stu-id="1a2c7-201">If **Audio default** in your worksheet is `true`, set **Turn on this device's microphone** to on, otherwise leave it _off_.</span></span>
6. <span data-ttu-id="1a2c7-202">如果 **工作表中已启用**"音频"，请在"打开此设备的麦克风"下选择"允许用户在加入会议 `true` **时启用"。** </span><span class="sxs-lookup"><span data-stu-id="1a2c7-202">If **Audio enabled** in your worksheet is `true`, select **Let people enable when joining a meeting** under **Turn on this device's microphone**.</span></span> <span data-ttu-id="1a2c7-203">如果"打开此设备的麦克风"设置为"打开 **"，则不能** 关闭此选项。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-203">This option can't be turned off if **Turn on this device's microphone** is set to on.</span></span>
7. <span data-ttu-id="1a2c7-204">如果 **工作表中的"** 视频"默认为 `true` ，将 **"打开此设备的** 相机"设置为"打开"，否则请将其 _关闭_。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-204">If **Video default** in your worksheet is `true`, set **Turn on this device's camera** to on, otherwise leave it _off_.</span></span>
8. <span data-ttu-id="1a2c7-205">如果 **工作表中** 已启用"视频"，请在"打开此设备的相机"下选择"允许用户在加入会议 `true` **时启用"。** </span><span class="sxs-lookup"><span data-stu-id="1a2c7-205">If **Video enabled** in your worksheet is `true`, select **Let people enable when joining a meeting** under **Turn on this device's camera**.</span></span> <span data-ttu-id="1a2c7-206">如果"打开此设备的相机"设置为"开"，则不能 _关闭此选项_。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-206">This option can't be turned off if **Turn on this device's camera** is set to _on_.</span></span>
9. <span data-ttu-id="1a2c7-207">如果 **工作表中的 Whiteboard** 默认值为 `true` ，将 **"在此设备上打开白板** "设置为 _"打开_"，否则将其 _关闭_。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-207">If **Whiteboard default** in your worksheet is `true`, set **Turn on whiteboarding on this device** to _on_, otherwise leave it _off_.</span></span>
10. <span data-ttu-id="1a2c7-208">在 **"受信任的设备帐户"下**，键入工作表中" **受信任的帐户"中列出的** 每个 UPN。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-208">Under **Trusted device accounts**, type each UPN listed in **Trusted accounts** in your worksheet.</span></span> <span data-ttu-id="1a2c7-209">使用逗号分隔多个 UPN。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-209">Separate multiple UPNs with commas.</span></span>
11. <span data-ttu-id="1a2c7-210">选择 **"保存并退出"。**</span><span class="sxs-lookup"><span data-stu-id="1a2c7-210">Select **Save and exit**.</span></span>

<span data-ttu-id="1a2c7-211">选择" **保存并退出"** 后，设备将重新启动，并准备好参与协调会议。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-211">After you select **Save and exit**, the device will restart and it'll be ready to participate in Coordinated Meetings.</span></span>

### <a name="use-the-teams-rooms-xml-configuration-file"></a><span data-ttu-id="1a2c7-212">使用 Teams 会议室 XML 配置文件</span><span class="sxs-lookup"><span data-stu-id="1a2c7-212">Use the Teams Rooms XML configuration file</span></span>

<span data-ttu-id="1a2c7-213">可以使用设备 XML 配置文件Teams 会议室协调 `SkypeSettings.xml` 会议。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-213">Coordinated Meetings can be set up using the Teams Rooms device's `SkypeSettings.xml` XML configuration file.</span></span> <span data-ttu-id="1a2c7-214">`SkypeSettings.xml`该文件不是静态文件。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-214">The `SkypeSettings.xml` file isn't a static file.</span></span> <span data-ttu-id="1a2c7-215">当Teams 会议室启动时，它将检查 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` 名为 的文件 `SkypeSettings.xml` 。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-215">When the Teams Rooms device start, it checks in `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` for a file named `SkypeSettings.xml`.</span></span> <span data-ttu-id="1a2c7-216">如果文件存在，设备将读取并应用文件中指定的配置。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-216">If the file exists, the device reads and applies the configuration specified in the file.</span></span> <span data-ttu-id="1a2c7-217">应用完配置后，将删除该文件。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-217">After it's done applying the configuration, the file is deleted.</span></span> <span data-ttu-id="1a2c7-218">有关文件详细信息 `SkypeSettings.xml` ，请参阅 [使用 XML 配置文件管理控制台设置](../rooms/xml-config-file.md#manage-console-settings-with-an-xml-configuration-file)。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-218">For more information about the `SkypeSettings.xml` file, see [Manage console settings with an XML configuration file](../rooms/xml-config-file.md#manage-console-settings-with-an-xml-configuration-file).</span></span>

<span data-ttu-id="1a2c7-219">下面是配置文件中协调会议设置的语法：</span><span class="sxs-lookup"><span data-stu-id="1a2c7-219">The following is the syntax of the Coordinated Meetings settings in the configuration file:</span></span>

```xml
<CoordinatedMeetings enabled="true">
    <Settings>
        <Audio default="true" enabled="true"/>
        <Video default="true" enabled="true"/>
        <Whiteboard default="false" enabled="false"/>
    </Settings>
    <TrustedAccounts>hub@contoso.com</TrustedAccounts>
</CoordinatedMeetings>
```

<span data-ttu-id="1a2c7-220">若要在设备上设置协调会议，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="1a2c7-220">To set up Coordinated Meetings on a device, do the following:</span></span>

1. <span data-ttu-id="1a2c7-221">在文本文件编辑器（如Visual Studio Code或记事本）中，将上述 XML 粘贴到新文件中。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-221">In a text file editor, such as Visual Studio Code or Notepad, paste the above XML into a new file.</span></span>

2. <span data-ttu-id="1a2c7-222">将每个 XML 元素设置为电子表格 `true` 中的对应 `false` 或值。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-222">Set each of the XML elements to the corresponding `true` or `false` value in your spreadsheet.</span></span> <span data-ttu-id="1a2c7-223">例如，如果 **"音频默认值"为** `true` ，则设置 `<Audio default="true">` 。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-223">For example, if **Audio default** is `true`, set `<Audio default="true">`.</span></span>

3. <span data-ttu-id="1a2c7-224">请务必更改为 `TrustedAccounts` UPN 列表。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-224">Be sure to change `TrustedAccounts` to your list of UPNs.</span></span>

4. <span data-ttu-id="1a2c7-225">保存名称为 的文件 `SkypeSettings.xml` 。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-225">Save the file with the name `SkypeSettings.xml`.</span></span>

5. <span data-ttu-id="1a2c7-226">将文件Teams 会议室设备的 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-226">Place the file in the Teams Rooms device's `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` folder.</span></span> <span data-ttu-id="1a2c7-227">可通过多种方式实现此要求：</span><span class="sxs-lookup"><span data-stu-id="1a2c7-227">You can do this a few ways:</span></span>

    - <span data-ttu-id="1a2c7-228">**将文件复制到 Teams 会议室 设备** 需要先启用文件共享并创建网络共享，然后才能将文件复制到设备。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-228">**Copy the file to your Teams Rooms device** You'll need to enable file sharing and create a network share before you can copy files to your device.</span></span> <span data-ttu-id="1a2c7-229">完成操作后，可以连接到网络共享，将文件复制到设备。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-229">After you do that, you can connect to network share and copy the file to the device.</span></span> <span data-ttu-id="1a2c7-230">有关详细信息，请参阅Microsoft Teams 会议室[和操作](../rooms/rooms-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-230">For more information, see [Microsoft Teams Rooms maintenance and operations](../rooms/rooms-operations.md).</span></span>
    - <span data-ttu-id="1a2c7-231">**使用组策略** 创建组策略，将文件复制到设备。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-231">**Use a Group Policy** Create a group policy to copy the file to device.</span></span> <span data-ttu-id="1a2c7-232">有关详细信息，请参阅组 [策略概述](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-232">For more information, see [Group Policy Overview](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11)).</span></span>
    - <span data-ttu-id="1a2c7-233">**在设备上下载Teams 会议室文件** 可以使用管理模式登录到设备，然后将文件从网络共享或 U 盘复制到设备。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-233">**Download the file on the Teams Rooms device** You can log into the device using Admin mode and then copy the file to the device from a network share or USB drive.</span></span> <span data-ttu-id="1a2c7-234">有关详细信息，请参阅 [切换到管理模式](../rooms/rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-234">For more information, see [Switching to Admin mode](../rooms/rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running).</span></span>
    
6. <span data-ttu-id="1a2c7-235">重启设备。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-235">Restart the device.</span></span> <span data-ttu-id="1a2c7-236">可通过多种方式实现此要求：</span><span class="sxs-lookup"><span data-stu-id="1a2c7-236">You can do this a couple ways:</span></span>

    - <span data-ttu-id="1a2c7-237">**远程 PowerShell** 可以使用远程 PowerShell 在设备上运行"关闭"命令。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-237">**Remote PowerShell** You can run the Shutdown command on the device using Remote PowerShell.</span></span> <span data-ttu-id="1a2c7-238">有关详细信息，请参阅使用 [PowerShell 进行远程管理](../rooms/rooms-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-238">For more information, see [Remote Management using PowerShell](../rooms/rooms-operations.md).</span></span>
    - <span data-ttu-id="1a2c7-239">**运行 Restart-Computer** 可以在本地 `Restart-Computer` 计算机上运行 cmdlet，并指定要重启的设备的计算机名称。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-239">**Run Restart-Computer** You can run the `Restart-Computer` cmdlet on your local computer and specify the computer name of the device you want to restart.</span></span> <span data-ttu-id="1a2c7-240">有关详细信息，请参阅 [Restart-Computer](/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-7)。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-240">For more information, see [Restart-Computer](/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-7).</span></span>

## <a name="step-5-configure-surface-hub"></a><span data-ttu-id="1a2c7-241">步骤 5：配置Surface Hub</span><span class="sxs-lookup"><span data-stu-id="1a2c7-241">Step 5: Configure Surface Hub</span></span>

<span data-ttu-id="1a2c7-242">可以使用Windows设计器创建可用于将协调会议设置应用到 Surface Hub 的预配包。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-242">You can use Windows Configuration Designer to create a provisioning package that you can use to apply Coordinating Meetings settings to your Surface Hubs.</span></span> <span data-ttu-id="1a2c7-243">将上面创建的 XML 文件粘贴到Windows设计器以创建预配包。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-243">You'll paste the XML file you created above into Windows Configuration Designer to create the provisioning package.</span></span>

### <a name="create-coordinated-meetings-xml-configuration-file-for-surface-hub"></a><span data-ttu-id="1a2c7-244">为会议创建协调会议 XML 配置文件Surface Hub</span><span class="sxs-lookup"><span data-stu-id="1a2c7-244">Create Coordinated Meetings XML configuration file for Surface Hub</span></span>

<span data-ttu-id="1a2c7-245">配置Windows设计器和Microsoft Intune用于将协调会议配置应用到 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-245">Both Windows Configuration Designer and Microsoft Intune are used to apply the Coordinated Meetings configuration to your Surface Hubs.</span></span> <span data-ttu-id="1a2c7-246">配置是使用 XML 定义的。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-246">The configuration is defined using XML.</span></span> <span data-ttu-id="1a2c7-247">在进一步操作之前，需要创建要应用的 XML。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-247">Before you go further, you need to create the XML that will be applied.</span></span>

<span data-ttu-id="1a2c7-248">下面是协调会议 XML 配置文件的语法。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-248">The following is the syntax of the Coordinated Meetings XML configuration file.</span></span>

```xml
<SurfaceHubSettings>
    <BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>
    <AutoAcceptProximateMeetingInvitations>true</AutoAcceptProximateMeetingInvitations>
    <CoordinatedMeetings enabled="true"> 
        <TrustedAccounts>room@contoso.com</TrustedAccounts>
        <Settings> 
            <Audio default="false" enabled="false" />
            <Video default="false" enabled="true" /> 
        </Settings> 
    </CoordinatedMeetings>
</SurfaceHubSettings>
```

<span data-ttu-id="1a2c7-249">执行以下操作，为配置设计器或Windows准备 Microsoft Intune XML：</span><span class="sxs-lookup"><span data-stu-id="1a2c7-249">Do the following to prepare the XML for Windows Configuration Designer or Microsoft Intune:</span></span>

1. <span data-ttu-id="1a2c7-250">在文本文件编辑器（如Visual Studio Code或记事本）中，将上述 XML 粘贴到新文件中。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-250">In a text file editor, such as Visual Studio Code or Notepad, paste the above XML into a new file.</span></span>

2. <span data-ttu-id="1a2c7-251">将每个 XML 元素设置为电子表格 `true` 中的对应 `false` 或值。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-251">Set each of the XML elements to the corresponding `true` or `false` value in your spreadsheet.</span></span> <span data-ttu-id="1a2c7-252">例如，如果 **"音频默认值"为** `true` ，则设置 `<Audio default="true">` 。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-252">For example, if **Audio default** is `true`, set `<Audio default="true">`.</span></span>

3. <span data-ttu-id="1a2c7-253">请务必更改为 `TrustedAccounts` UPN 列表。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-253">Be sure to change `TrustedAccounts` to your list of UPNs.</span></span>

4. <span data-ttu-id="1a2c7-254">Windows配置设计器要求 XML 位于单行中。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-254">Windows Configuration Designer requires that the XML be on a single line.</span></span> <span data-ttu-id="1a2c7-255">删除每行之间的所有换行符，使 XML 如下所示：</span><span class="sxs-lookup"><span data-stu-id="1a2c7-255">Remove all the line breaks between each line so that the XML looks like the following:</span></span>

    ```xml
    <SurfaceHubSettings><BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>...
    ```

5. <span data-ttu-id="1a2c7-256">在计算机上保存文件。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-256">Save the file on your computer.</span></span>

<span data-ttu-id="1a2c7-257">创建 XML 配置文件后，使用 Microsoft Teams 上的管理[](surface-hub-manage-config.md)Microsoft Teams 设置中的步骤Surface Hub Surface Hub 应用它。</span><span class="sxs-lookup"><span data-stu-id="1a2c7-257">After you've created your XML configuration file, use the steps in [Manage Microsoft Teams settings on Surface Hub](surface-hub-manage-config.md) to apply it to your Surface Hubs.</span></span>