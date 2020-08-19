---
title: 通过 Microsoft 团队聊天室和 Surface Hub 设置协调的会议
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
description: 配置团队室设备和 Surface Hub，以便在一个设备或其他设备加入会议时加入会议。
ms.openlocfilehash: cfd8bd423d8f7765a973d55e42d64773a06bba32
ms.sourcegitcommit: bd13aecbb25c14e17d1b64343df6d80c90b2aa45
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2020
ms.locfileid: "46803934"
---
# <a name="set-up-coordinated-meetings-with-microsoft-teams-rooms-and-surface-hub"></a><span data-ttu-id="a50eb-103">通过 Microsoft 团队聊天室和 Surface Hub 设置协调的会议</span><span class="sxs-lookup"><span data-stu-id="a50eb-103">Set up Coordinated Meetings with Microsoft Teams Rooms and Surface Hub</span></span>

<span data-ttu-id="a50eb-104">如果您在会议室中有一个或多个 Microsoft 团队聊天室设备或 Surface Hub，则可以设置协调的会议。</span><span class="sxs-lookup"><span data-stu-id="a50eb-104">If you have one or more Microsoft Teams Rooms devices or Surface Hubs in a meeting room, you can set up Coordinated Meetings.</span></span> <span data-ttu-id="a50eb-105">使用协调的会议，你可以设置团队房间设备和 Surface Hub，以便在一个设备上加入会议时，会议室中的其他设备也会加入同一会议。</span><span class="sxs-lookup"><span data-stu-id="a50eb-105">Coordinated Meetings lets you set up your Teams Rooms devices and Surface Hubs so that when you join a meeting on one device, the other devices in the room are also joined to the same meeting.</span></span> <span data-ttu-id="a50eb-106">你可以配置你的相机、扬声器和麦克风，以便允许参与者获得最佳体验的人在其他人禁用时启用。</span><span class="sxs-lookup"><span data-stu-id="a50eb-106">You can configure your cameras, speakers, and microphones so that the ones that give participants the best experience are enabled while others are disabled.</span></span> <span data-ttu-id="a50eb-107">这样就避免了令人可怕的回音和反馈噪音参与者在向会议添加多个设备时可能会遇到的情况。</span><span class="sxs-lookup"><span data-stu-id="a50eb-107">This avoids the dreaded echo and feedback noise participants can experience when adding multiple devices to a meeting.</span></span>

<span data-ttu-id="a50eb-108">若要设置协调的会议，你需要确保你的团队聊天室设备和 Surface Hub 已正确配置为参与会议。</span><span class="sxs-lookup"><span data-stu-id="a50eb-108">To set up Coordinated Meetings, you need to make sure your Teams Rooms devices and Surface Hubs are already correctly configured to participate in meetings.</span></span> <span data-ttu-id="a50eb-109">最重要的是，每个设备都需要有自己的 Exchange 会议室邮箱。</span><span class="sxs-lookup"><span data-stu-id="a50eb-109">Most importantly, each device needs to have its own Exchange room mailbox.</span></span> <span data-ttu-id="a50eb-110">有关如何设置它们的信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="a50eb-110">For information on how to set them up, see the following articles:</span></span>

- [<span data-ttu-id="a50eb-111">部署 Microsoft Teams 会议室</span><span class="sxs-lookup"><span data-stu-id="a50eb-111">Deploy Microsoft Teams Rooms</span></span>](../rooms/rooms-deploy.md)
- [<span data-ttu-id="a50eb-112">创建 Surface Hub 2 设备帐户</span><span class="sxs-lookup"><span data-stu-id="a50eb-112">Create Surface Hub 2S device account</span></span>](https://docs.microsoft.com/surface-hub/surface-hub-2s-account)

<span data-ttu-id="a50eb-113">在您确认团队聊天室设备和 Surface Hub 可以自动接受会议并成功加入会议后，您可以设置协调的会议。</span><span class="sxs-lookup"><span data-stu-id="a50eb-113">After you've confirmed that your Teams Rooms devices and Surface Hubs can automatically accept meetings and join them successfully, you can set up Coordinated Meetings.</span></span>

<span data-ttu-id="a50eb-114">应为每个会议室单独完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="a50eb-114">The following steps should be completed for each meeting room separately.</span></span> <span data-ttu-id="a50eb-115">一个会议室中的设备不应设置为与其他会议室中的设备进行协调的会议。</span><span class="sxs-lookup"><span data-stu-id="a50eb-115">Devices in one meeting room shouldn't be set up for Coordinated Meetings with devices in other meeting rooms.</span></span>

## <a name="step-1-plan-your-coordinated-meeting-experience"></a><span data-ttu-id="a50eb-116">步骤1：规划您的协调会议体验</span><span class="sxs-lookup"><span data-stu-id="a50eb-116">Step 1: Plan your Coordinated Meeting experience</span></span>

<span data-ttu-id="a50eb-117">在进行任何配置更改之前，你需要确定哪些设备将在每个会议室中执行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="a50eb-117">Before you make any configuration changes, you need to decide which devices will do what in each meeting room.</span></span> <span data-ttu-id="a50eb-118">也就是说，对于给定的会议室，你需要确定哪些设备将具有 "活动麦克风"、"照相机" 和 "白板"。</span><span class="sxs-lookup"><span data-stu-id="a50eb-118">That is, for a given meeting room, you need to decide which device will have the active microphone, camera, and whiteboard.</span></span> <span data-ttu-id="a50eb-119">配置设备的方式取决于你的特定环境，但以下是一些一般建议：</span><span class="sxs-lookup"><span data-stu-id="a50eb-119">How you configure your devices depends on your specific environment, but here are some general recommendations to start with:</span></span>

- <span data-ttu-id="a50eb-120">**麦克风** 团队聊天室设备</span><span class="sxs-lookup"><span data-stu-id="a50eb-120">**Microphone** Teams Rooms device</span></span>
- <span data-ttu-id="a50eb-121">**相机** 默认情况下，团队聊天室设备 (默认情况下) 和 Surface Hub (关闭，但允许参与者启用) </span><span class="sxs-lookup"><span data-stu-id="a50eb-121">**Camera** Teams Rooms device (on by default) and Surface Hub (off by default, but allowed to be turned on by participants)</span></span>
- <span data-ttu-id="a50eb-122">**白板** Surface Hub</span><span class="sxs-lookup"><span data-stu-id="a50eb-122">**Whiteboard** Surface Hub</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a50eb-123">请确保仅在一台设备上启用麦克风。</span><span class="sxs-lookup"><span data-stu-id="a50eb-123">Make sure you enable the microphone only on one device.</span></span> <span data-ttu-id="a50eb-124">如果在多台设备上启用它，将体验音频回声和反馈。</span><span class="sxs-lookup"><span data-stu-id="a50eb-124">If you enable it on more than one device, you'll experience audio echo and feedback.</span></span>

## <a name="step-2-get-your-devices-upns"></a><span data-ttu-id="a50eb-125">步骤2：获取你的设备的 Upn</span><span class="sxs-lookup"><span data-stu-id="a50eb-125">Step 2: Get your devices' UPNs</span></span>

<span data-ttu-id="a50eb-126">在会议室中设置协调的会议体验时，你需要将团队聊天室设备和 Surface Hub 告知在该房间内要与之协调的设备。</span><span class="sxs-lookup"><span data-stu-id="a50eb-126">When you set up a Coordinated Meeting experience in a meeting room, you need to tell the Teams Rooms devices and Surface Hubs in that room which devices to coordinate with.</span></span> <span data-ttu-id="a50eb-127">这是通过将用户主体名称添加到其与其配置配合的设备 (UPN) 来完成的。</span><span class="sxs-lookup"><span data-stu-id="a50eb-127">This is done by adding the user principal name (UPN) of the devices it should coordinate with to its configuration.</span></span> <span data-ttu-id="a50eb-128">如果你不知道要为协调会议设置的每个设备的 Upn，则可以使用 Microsoft 365 管理中心找到它们。</span><span class="sxs-lookup"><span data-stu-id="a50eb-128">If you don't know the UPNs for each of the devices you want to set up for Coordinated Meetings, you can find them using the Microsoft 365 admin center.</span></span> 

<span data-ttu-id="a50eb-129">您需要分配管理员角色才能访问 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="a50eb-129">You need to be assigned an admin role to access the Microsoft 365 admin center.</span></span> <span data-ttu-id="a50eb-130">有关详细信息，请参阅 [关于管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="a50eb-130">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="a50eb-131">若要获取团队聊天室设备和 Surface Hub 的 Upn，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="a50eb-131">To get the UPNs of your Teams Rooms devices and Surface Hubs, do the following:</span></span>

1. <span data-ttu-id="a50eb-132">通过访问登录到 Microsoft 365 管理中心 https://admin.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="a50eb-132">Sign in to the Microsoft 365 admin center by visiting https://admin.microsoft.com.</span></span>
2. <span data-ttu-id="a50eb-133">转到 "**用户**  >  **活动用户**"。</span><span class="sxs-lookup"><span data-stu-id="a50eb-133">Go to **Users** > **Active users**.</span></span>
3. <span data-ttu-id="a50eb-134">在 " **显示名称** " 列中查找团队聊天室设备或 Surface Hub 的名称 (如果有多个用户) ，则可以使用 " **搜索** " 框。</span><span class="sxs-lookup"><span data-stu-id="a50eb-134">Find the name of your Teams Rooms device or Surface Hub in the **Display name** column (you can use the **Search** box if you have many users).</span></span>
4. <span data-ttu-id="a50eb-135">在 " **用户名** " 列中查找 UPN， (它将以 alias@contoso.com 或 alias@contoso.onmicrosoft.com) 的形式显示。</span><span class="sxs-lookup"><span data-stu-id="a50eb-135">Find the UPN in the **Username** column (it'll look something like alias@contoso.com or alias@contoso.onmicrosoft.com).</span></span>
5. <span data-ttu-id="a50eb-136">对将参与协调会议的每个设备重复此操作。</span><span class="sxs-lookup"><span data-stu-id="a50eb-136">Repeat this for each device that will participate in Coordinated Meetings.</span></span>

## <a name="step-3-create-a-deployment-worksheet"></a><span data-ttu-id="a50eb-137">步骤3：创建部署工作表</span><span class="sxs-lookup"><span data-stu-id="a50eb-137">Step 3: Create a deployment worksheet</span></span>

<span data-ttu-id="a50eb-138">在规划了您的协调会议体验并收集了设备 Upn 的列表后，最好创建一个部署工作表。</span><span class="sxs-lookup"><span data-stu-id="a50eb-138">After you've planned your Coordinated Meeting experience and gathered a list of your devices' UPNs, it's a good idea to create a deployment worksheet.</span></span> <span data-ttu-id="a50eb-139">部署工作表可帮助你可视化要在所有设备上设置的配置，使你可以验证你的选择并检查错误。</span><span class="sxs-lookup"><span data-stu-id="a50eb-139">A deployment worksheet will help you visualize the configuration you want to set across all of your devices, allowing you to validate your choices and check for errors.</span></span>

<span data-ttu-id="a50eb-140">在电子表格应用中，在第一列中为以下内容添加行：</span><span class="sxs-lookup"><span data-stu-id="a50eb-140">In a spreadsheet app, add rows for the following in the first column:</span></span>

| <span data-ttu-id="a50eb-141">设置</span><span class="sxs-lookup"><span data-stu-id="a50eb-141">Setting</span></span>                | <span data-ttu-id="a50eb-142">说明</span><span class="sxs-lookup"><span data-stu-id="a50eb-142">Description</span></span>      |
|------------------------|-----------------|
| <span data-ttu-id="a50eb-143">**音频默认值**</span><span class="sxs-lookup"><span data-stu-id="a50eb-143">**Audio default**</span></span>      | <span data-ttu-id="a50eb-144">确定当会议启动时，麦克风将处于活动状态的设备。</span><span class="sxs-lookup"><span data-stu-id="a50eb-144">Determines on which device the microphone will be active when a meeting starts.</span></span> <span data-ttu-id="a50eb-145">只有一台设备 (通常是团队会议室设备) 可以将此字段设置为 "， `true` 而其余设备必须将此字段设置为" `false` ，以避免音频回声和反馈。</span><span class="sxs-lookup"><span data-stu-id="a50eb-145">Only one device (typically a Teams Rooms device) can have this field set to `true` while the rest of the devices must have this field set to `false` to avoid audio echo and feedback.</span></span>          |
| <span data-ttu-id="a50eb-146">**启用音频**</span><span class="sxs-lookup"><span data-stu-id="a50eb-146">**Audio enabled**</span></span>      | <span data-ttu-id="a50eb-147">确定会议中的参与者是否可以打开或关闭麦克风。</span><span class="sxs-lookup"><span data-stu-id="a50eb-147">Determines whether participants in a meeting can toggle the microphone on or off.</span></span> <span data-ttu-id="a50eb-148">将 **音频默认** 设置为 `false` 应将此设置设置为的设备， `false` 以便参与者无法意外打开麦克风并导致音频回声或反馈。</span><span class="sxs-lookup"><span data-stu-id="a50eb-148">Devices on which **Audio default** is set to `false` should have this setting set to `false` so that participants can't accidentally turn on a microphone and cause audio echo or feedback.</span></span><p><span data-ttu-id="a50eb-149">如果 " **音频默认值** " 设置为 `true` ""，将忽略此设置，并且参与者可以将麦克风设为静音或取消静音。</span><span class="sxs-lookup"><span data-stu-id="a50eb-149">If **Audio default** is set to `true`, this setting is ignored and participants can mute or unmute the microphone.</span></span>          |
| <span data-ttu-id="a50eb-150">**视频默认值**</span><span class="sxs-lookup"><span data-stu-id="a50eb-150">**Video default**</span></span>      | <span data-ttu-id="a50eb-151">确定会议启动时相机将处于活动状态的设备。</span><span class="sxs-lookup"><span data-stu-id="a50eb-151">Determines on which device the camera will be active when a meeting starts.</span></span> <span data-ttu-id="a50eb-152">为了获得最佳体验，我们建议仅将团队聊天室设备设置为， `true` 同时将所有其他设备设置为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="a50eb-152">For the best experience, we recommend that only the Teams Rooms device be set to `true` while all other devices are set to `false`.</span></span>          |
| <span data-ttu-id="a50eb-153">**视频已启用**</span><span class="sxs-lookup"><span data-stu-id="a50eb-153">**Video enabled**</span></span>      | <span data-ttu-id="a50eb-154">确定会议中的参与者是否可以打开或关闭摄像头。</span><span class="sxs-lookup"><span data-stu-id="a50eb-154">Determines whether participants in a meeting can toggle the camera on or off.</span></span> <span data-ttu-id="a50eb-155">你可以将此项设置为 `true` 在事件参与者中的任何其他设备上，希望共享不同的视频透视 (例如，如果参与者使用 Surface Hub 白板) 。</span><span class="sxs-lookup"><span data-stu-id="a50eb-155">You can set this to `true` on any other devices in the event participants want to share different video perspectives (such as if a participant is using the Surface Hub whiteboard).</span></span> <span data-ttu-id="a50eb-156">如果不希望参与者在设备上打开或关闭摄像头，请将此设置为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="a50eb-156">If you don't want participants to turn a camera on or off on a device, set this to `false`.</span></span><p> <span data-ttu-id="a50eb-157">如果 " **视频默认值** " 设置为 `true` ""，则会忽略此设置，并且参与者可以打开或关闭摄像头。</span><span class="sxs-lookup"><span data-stu-id="a50eb-157">If **Video default** is set to `true`, this setting is ignored and participants can turn the camera on or off.</span></span>         |
| <span data-ttu-id="a50eb-158">**白板默认设置**</span><span class="sxs-lookup"><span data-stu-id="a50eb-158">**Whiteboard default**</span></span> | <span data-ttu-id="a50eb-159">确定团队间设备是否将显示由某个会议参与者共享的白板。</span><span class="sxs-lookup"><span data-stu-id="a50eb-159">Determines whether the Teams Rooms device will display a whiteboard shared by one of the meeting participants.</span></span> <span data-ttu-id="a50eb-160">我们建议你将其设置为 `false` 如果你有 Surface Hub，并且你没有 Surface Hub `true` 。</span><span class="sxs-lookup"><span data-stu-id="a50eb-160">We recommend that you set this to `false` if you have a Surface Hub and `true` if you don't have one.</span></span> <span data-ttu-id="a50eb-161">此设置对 Surface Hub 没有影响。</span><span class="sxs-lookup"><span data-stu-id="a50eb-161">This setting has no effect on Surface Hubs.</span></span> <span data-ttu-id="a50eb-162">Surface Hub 将始终显示由会议参与者共享的白板。</span><span class="sxs-lookup"><span data-stu-id="a50eb-162">Surface Hubs will always display a whiteboard shared by meeting participants.</span></span>         |
| <span data-ttu-id="a50eb-163">**白板已启用**</span><span class="sxs-lookup"><span data-stu-id="a50eb-163">**Whiteboard enabled**</span></span> | <span data-ttu-id="a50eb-164">确定会议中的参与者是否可以打开或关闭白板。</span><span class="sxs-lookup"><span data-stu-id="a50eb-164">Determines whether participants in a meeting can toggle the whiteboard on or off.</span></span> <span data-ttu-id="a50eb-165">如果不希望参与者在设备上打开或关闭白板，请将此设置为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="a50eb-165">If you don't want participants to turn the whiteboard on or off on a device, set this to `false`.</span></span> <p><span data-ttu-id="a50eb-166">如果 " **白板默认值** " 设置为 `true` ""，则忽略此设置，参与者可以打开或关闭白板。</span><span class="sxs-lookup"><span data-stu-id="a50eb-166">If **Whiteboard default** is set to `true`, this setting is ignored and participants can turn the whiteboard on or off.</span></span>
| <span data-ttu-id="a50eb-167">**受信任帐户**</span><span class="sxs-lookup"><span data-stu-id="a50eb-167">**Trusted accounts**</span></span>   | <span data-ttu-id="a50eb-168">这是一个逗号分隔的 Upn 列表，用于表示设备应接受会议加入请求的每个团队房间设备或 Surface Hub，或应发送到哪些会议加入请求。</span><span class="sxs-lookup"><span data-stu-id="a50eb-168">This is a comma-separated list of UPNs for each Teams Room device or Surface Hub that the device should accept meeting join requests from, or to which meeting join requests should be sent.</span></span> |

<span data-ttu-id="a50eb-169">在后续列中，添加每个团队聊天室设备和 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="a50eb-169">In subsequent columns, add each of your Teams Rooms devices and Surface Hubs.</span></span> <span data-ttu-id="a50eb-170">在每列中，填写与你希望的会议室的体验相对应的值。</span><span class="sxs-lookup"><span data-stu-id="a50eb-170">In each column, fill out the values that correspond to the experience you want for the meeting room.</span></span> <span data-ttu-id="a50eb-171">下面是一个团队聊天室设备和一个 Surface Hub 的示例：</span><span class="sxs-lookup"><span data-stu-id="a50eb-171">Here's an example with one Teams Rooms device and one Surface Hub:</span></span>

- <span data-ttu-id="a50eb-172">团队设备</span><span class="sxs-lookup"><span data-stu-id="a50eb-172">Teams device</span></span>
  - <span data-ttu-id="a50eb-173">当会议启动时，音频和 **视频处于打开** 状态。</span><span class="sxs-lookup"><span data-stu-id="a50eb-173">Audio and video are turned **on** when a meeting starts.</span></span> <span data-ttu-id="a50eb-174">参与者 **可以** 打开或关闭音频和视频。</span><span class="sxs-lookup"><span data-stu-id="a50eb-174">Participants **can** toggle audio and video on or off.</span></span>
  - <span data-ttu-id="a50eb-175">显示共享白板功能已关闭。</span><span class="sxs-lookup"><span data-stu-id="a50eb-175">Displaying a shared whiteboard is turned off.</span></span>
- <span data-ttu-id="a50eb-176">Surface Hub</span><span class="sxs-lookup"><span data-stu-id="a50eb-176">Surface Hub</span></span>
  - <span data-ttu-id="a50eb-177">会议启动时，音频处于 **关闭** 状态。</span><span class="sxs-lookup"><span data-stu-id="a50eb-177">Audio is turned **off** when a meeting starts.</span></span> <span data-ttu-id="a50eb-178">参与者 **无法** 打开或关闭音频。</span><span class="sxs-lookup"><span data-stu-id="a50eb-178">Participants **can't** toggle audio on or off.</span></span>
  - <span data-ttu-id="a50eb-179">会议启动时，视频处于 **关闭** 状态。</span><span class="sxs-lookup"><span data-stu-id="a50eb-179">Video is turned **off** when a meeting starts.</span></span> <span data-ttu-id="a50eb-180">参与者 **可以** 打开或关闭视频。</span><span class="sxs-lookup"><span data-stu-id="a50eb-180">Participants **can** toggle video on or off.</span></span>

| <span data-ttu-id="a50eb-181">设置</span><span class="sxs-lookup"><span data-stu-id="a50eb-181">Setting</span></span>                | <span data-ttu-id="a50eb-182">团队聊天室</span><span class="sxs-lookup"><span data-stu-id="a50eb-182">Teams Room</span></span>      | <span data-ttu-id="a50eb-183">Surface Hub</span><span class="sxs-lookup"><span data-stu-id="a50eb-183">Surface Hub</span></span>      |
|------------------------|-----------------|------------------|
| <span data-ttu-id="a50eb-184">**音频默认值**</span><span class="sxs-lookup"><span data-stu-id="a50eb-184">**Audio default**</span></span>      | `true`          | `false`          |
| <span data-ttu-id="a50eb-185">**启用音频**</span><span class="sxs-lookup"><span data-stu-id="a50eb-185">**Audio enabled**</span></span>      | `true`          | `false`          |
| <span data-ttu-id="a50eb-186">**视频默认值**</span><span class="sxs-lookup"><span data-stu-id="a50eb-186">**Video default**</span></span>      | `true`          | `false`          |
| <span data-ttu-id="a50eb-187">**视频已启用**</span><span class="sxs-lookup"><span data-stu-id="a50eb-187">**Video enabled**</span></span>      | `true`          | `true`           |
| <span data-ttu-id="a50eb-188">**白板默认设置**</span><span class="sxs-lookup"><span data-stu-id="a50eb-188">**Whiteboard default**</span></span> | `false`         | `false`          |
| <span data-ttu-id="a50eb-189">**受信任帐户**</span><span class="sxs-lookup"><span data-stu-id="a50eb-189">**Trusted accounts**</span></span>   | <span data-ttu-id="a50eb-190">hub@contoso.com</span><span class="sxs-lookup"><span data-stu-id="a50eb-190">hub@contoso.com</span></span> | <span data-ttu-id="a50eb-191">room@contoso.com</span><span class="sxs-lookup"><span data-stu-id="a50eb-191">room@contoso.com</span></span> |

## <a name="step-4-configure-teams-rooms-device"></a><span data-ttu-id="a50eb-192">步骤4：配置团队聊天室设备</span><span class="sxs-lookup"><span data-stu-id="a50eb-192">Step 4: Configure Teams Rooms device</span></span>

<span data-ttu-id="a50eb-193">你可以使用设备的触摸屏在团队聊天室设备上设置协调的会议，或者，如果需要设置多个设备并希望从中心位置执行此操作，则可以使用 XML 配置文件。</span><span class="sxs-lookup"><span data-stu-id="a50eb-193">You can either set up Coordinated Meetings on a Teams Rooms device using the device's touch screen or, if you need to set up many devices and want to do so from a central location, you can use an XML configuration file.</span></span>

<span data-ttu-id="a50eb-194">使用您在上一步中创建的工作表来帮助您设置设备。</span><span class="sxs-lookup"><span data-stu-id="a50eb-194">Use the worksheet you created in the previous step to help you set up your devices.</span></span>

### <a name="use-the-teams-rooms-devices-touch-screen"></a><span data-ttu-id="a50eb-195">使用团队聊天室设备的触摸屏幕</span><span class="sxs-lookup"><span data-stu-id="a50eb-195">Use the Teams Rooms device's touch screen</span></span>

<span data-ttu-id="a50eb-196">若要在设备上设置协调的会议，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="a50eb-196">To set up Coordinated Meetings on a device, do the following:</span></span>

1. <span data-ttu-id="a50eb-197">选择 **.。。更多**  >  **设置**。</span><span class="sxs-lookup"><span data-stu-id="a50eb-197">Select **... More** > **Settings**.</span></span>
2. <span data-ttu-id="a50eb-198">输入管理员密码，然后选择 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="a50eb-198">Enter the Administrator password and select **Yes**.</span></span>
3. <span data-ttu-id="a50eb-199">选择 " **协调的会议**"。</span><span class="sxs-lookup"><span data-stu-id="a50eb-199">Select **Coordinated Meetings**.</span></span>
4. <span data-ttu-id="a50eb-200">在 " **选项**" 下，将 " **协调会议** " 设置为 _"开"_。</span><span class="sxs-lookup"><span data-stu-id="a50eb-200">Under **Options**, set **Coordinated Meeting** to _on_.</span></span>
5. <span data-ttu-id="a50eb-201">如果工作表中的 **音频默认值** 为 `true` ，请将 **此设备的麦克风** 设置为 "打开"，否则将其 _关闭_。</span><span class="sxs-lookup"><span data-stu-id="a50eb-201">If **Audio default** in your worksheet is `true`, set **Turn on this device's microphone** to on, otherwise leave it _off_.</span></span>
6. <span data-ttu-id="a50eb-202">如果工作表中**已启用音频** `true` ，请选择 "**打开此设备的麦克风**" 下的 "在**加入会议时允许用户启用**"。</span><span class="sxs-lookup"><span data-stu-id="a50eb-202">If **Audio enabled** in your worksheet is `true`, select **Let people enable when joining a meeting** under **Turn on this device's microphone**.</span></span> <span data-ttu-id="a50eb-203">如果 **"打开此设备的麦克风** " 设置为 "打开"，则不能关闭此选项。</span><span class="sxs-lookup"><span data-stu-id="a50eb-203">This option can't be turned off if **Turn on this device's microphone** is set to on.</span></span>
7. <span data-ttu-id="a50eb-204">如果工作表中的 **视频默认值** 为 `true` "启用"，则将 **此设备的摄像头** 设置为 "开"，否则将其 _关闭_。</span><span class="sxs-lookup"><span data-stu-id="a50eb-204">If **Video default** in your worksheet is `true`, set **Turn on this device's camera** to on, otherwise leave it _off_.</span></span>
8. <span data-ttu-id="a50eb-205">如果工作表中**启用**了视频 `true` ，请选择 "在**此设备的相机上**启用**加入会议时允许用户启用**"。</span><span class="sxs-lookup"><span data-stu-id="a50eb-205">If **Video enabled** in your worksheet is `true`, select **Let people enable when joining a meeting** under **Turn on this device's camera**.</span></span> <span data-ttu-id="a50eb-206">如果将 **此设备的相机** 设置为 _"_ 打开"，则无法关闭此选项。</span><span class="sxs-lookup"><span data-stu-id="a50eb-206">This option can't be turned off if **Turn on this device's camera** is set to _on_.</span></span>
9. <span data-ttu-id="a50eb-207">如果工作表中的 **白板默认值** 为 `true` "打开"，请将 **此设备** 上的 whiteboarding 设置为 _"_ 打开"，否则将其 _关闭_。</span><span class="sxs-lookup"><span data-stu-id="a50eb-207">If **Whiteboard default** in your worksheet is `true`, set **Turn on whiteboarding on this device** to _on_, otherwise leave it _off_.</span></span>
10. <span data-ttu-id="a50eb-208">在 " **受信任的设备帐户**" 下，在工作表中键入 " **受信任帐户** " 中列出的所有 UPN</span><span class="sxs-lookup"><span data-stu-id="a50eb-208">Under **Trusted device accounts**, type each UPN listed in **Trusted accounts** in your worksheet.</span></span> <span data-ttu-id="a50eb-209">用逗号分隔多个 Upn。</span><span class="sxs-lookup"><span data-stu-id="a50eb-209">Separate multiple UPNs with commas.</span></span>
11. <span data-ttu-id="a50eb-210">选择 " **保存并退出**"。</span><span class="sxs-lookup"><span data-stu-id="a50eb-210">Select **Save and exit**.</span></span>

<span data-ttu-id="a50eb-211">选择 " **保存并退出**" 后，设备将重新启动，并准备好参与协调的会议。</span><span class="sxs-lookup"><span data-stu-id="a50eb-211">After you select **Save and exit**, the device will restart and it'll be ready to participate in Coordinated Meetings.</span></span>

### <a name="use-the-teams-rooms-xml-configuration-file"></a><span data-ttu-id="a50eb-212">使用团队聊天室 XML 配置文件</span><span class="sxs-lookup"><span data-stu-id="a50eb-212">Use the Teams Rooms XML configuration file</span></span>

<span data-ttu-id="a50eb-213">可以使用团队聊天室设备的 `SkypeSettings.xml` XML 配置文件设置协调的会议。</span><span class="sxs-lookup"><span data-stu-id="a50eb-213">Coordinated Meetings can be set up using the Teams Rooms device's `SkypeSettings.xml` XML configuration file.</span></span> <span data-ttu-id="a50eb-214">`SkypeSettings.xml`文件不是静态文件。</span><span class="sxs-lookup"><span data-stu-id="a50eb-214">The `SkypeSettings.xml` file isn't a static file.</span></span> <span data-ttu-id="a50eb-215">当团队房间设备启动时，它将签入 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` 一个名为的文件 `SkypeSettings.xml` 。</span><span class="sxs-lookup"><span data-stu-id="a50eb-215">When the Teams Rooms device start, it checks in `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` for a file named `SkypeSettings.xml`.</span></span> <span data-ttu-id="a50eb-216">如果文件存在，设备将读取并应用文件中指定的配置。</span><span class="sxs-lookup"><span data-stu-id="a50eb-216">If the file exists, the device reads and applies the configuration specified in the file.</span></span> <span data-ttu-id="a50eb-217">完成应用配置后，文件将被删除。</span><span class="sxs-lookup"><span data-stu-id="a50eb-217">After it's done applying the configuration, the file is deleted.</span></span> <span data-ttu-id="a50eb-218">有关文件的详细信息 `SkypeSettings.xml` ，请参阅 [使用 XML 配置文件管理控制台设置](../rooms/xml-config-file.md#manage-console-settings-with-an-xml-configuration-file)。</span><span class="sxs-lookup"><span data-stu-id="a50eb-218">For more information about the `SkypeSettings.xml` file, see [Manage console settings with an XML configuration file](../rooms/xml-config-file.md#manage-console-settings-with-an-xml-configuration-file).</span></span>

<span data-ttu-id="a50eb-219">以下是配置文件中协调的会议设置的语法：</span><span class="sxs-lookup"><span data-stu-id="a50eb-219">The following is the syntax of the Coordinated Meetings settings in the configuration file:</span></span>

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

<span data-ttu-id="a50eb-220">若要在设备上设置协调的会议，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="a50eb-220">To set up Coordinated Meetings on a device, do the following:</span></span>

1. <span data-ttu-id="a50eb-221">在文本文件编辑器（如 Visual Studio 代码或记事本）中，将上面的 XML 粘贴到新文件中。</span><span class="sxs-lookup"><span data-stu-id="a50eb-221">In a text file editor, such as Visual Studio Code or Notepad, paste the above XML into a new file.</span></span>

2. <span data-ttu-id="a50eb-222">将每个 XML 元素设置为 `true` `false` 电子表格中的相应值或值。</span><span class="sxs-lookup"><span data-stu-id="a50eb-222">Set each of the XML elements to the corresponding `true` or `false` value in your spreadsheet.</span></span> <span data-ttu-id="a50eb-223">例如，如果 **音频默认值** 为 `true` ，则设置 `<Audio default="true">` 。</span><span class="sxs-lookup"><span data-stu-id="a50eb-223">For example, if **Audio default** is `true`, set `<Audio default="true">`.</span></span>

3. <span data-ttu-id="a50eb-224">请确保更改 `TrustedAccounts` 为 upn 列表。</span><span class="sxs-lookup"><span data-stu-id="a50eb-224">Be sure to change `TrustedAccounts` to your list of UPNs.</span></span>

4. <span data-ttu-id="a50eb-225">将文件保存为名称 `SkypeSettings.xml` 。</span><span class="sxs-lookup"><span data-stu-id="a50eb-225">Save the file with the name `SkypeSettings.xml`.</span></span>

5. <span data-ttu-id="a50eb-226">将文件放在团队聊天室设备的 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="a50eb-226">Place the file in the Teams Rooms device's `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` folder.</span></span> <span data-ttu-id="a50eb-227">你可以通过以下几种方式执行此操作：</span><span class="sxs-lookup"><span data-stu-id="a50eb-227">You can do this a few ways:</span></span>

    - <span data-ttu-id="a50eb-228">**将文件复制到团队聊天室设备** 在将文件复制到你的设备之前，你需要启用文件共享并创建网络共享。</span><span class="sxs-lookup"><span data-stu-id="a50eb-228">**Copy the file to your Teams Rooms device** You'll need to enable file sharing and create a network share before you can copy files to your device.</span></span> <span data-ttu-id="a50eb-229">执行此操作后，您可以连接到网络共享并将文件复制到设备。</span><span class="sxs-lookup"><span data-stu-id="a50eb-229">After you do that, you can connect to network share and copy the file to the device.</span></span> <span data-ttu-id="a50eb-230">有关详细信息，请参阅 [Microsoft 团队会议室维护和操作](../rooms/rooms-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="a50eb-230">For more information, see [Microsoft Teams Rooms maintenance and operations](../rooms/rooms-operations.md).</span></span>
    - <span data-ttu-id="a50eb-231">**使用组策略** 创建组策略以将文件复制到设备。</span><span class="sxs-lookup"><span data-stu-id="a50eb-231">**Use a Group Policy** Create a group policy to copy the file to device.</span></span> <span data-ttu-id="a50eb-232">有关详细信息，请参阅 [组策略概述](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="a50eb-232">For more information, see [Group Policy Overview](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11)).</span></span>
    - <span data-ttu-id="a50eb-233">**在团队聊天室设备上下载文件** 你可以使用管理员模式登录到设备，然后从网络共享或 USB 驱动器将文件复制到设备。</span><span class="sxs-lookup"><span data-stu-id="a50eb-233">**Download the file on the Teams Rooms device** You can log into the device using Admin mode and then copy the file to the device from a network share or USB drive.</span></span> <span data-ttu-id="a50eb-234">有关详细信息，请参阅 [切换到 "管理员模式](../rooms/rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)"。</span><span class="sxs-lookup"><span data-stu-id="a50eb-234">For more information, see [Switching to Admin mode](../rooms/rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running).</span></span>
    
6. <span data-ttu-id="a50eb-235">重启设备。</span><span class="sxs-lookup"><span data-stu-id="a50eb-235">Restart the device.</span></span> <span data-ttu-id="a50eb-236">你可以通过以下几种方式执行此操作：</span><span class="sxs-lookup"><span data-stu-id="a50eb-236">You can do this a couple ways:</span></span>

    - <span data-ttu-id="a50eb-237">**远程 PowerShell** 你可以使用远程 PowerShell 在设备上运行 Shutdown 命令。</span><span class="sxs-lookup"><span data-stu-id="a50eb-237">**Remote PowerShell** You can run the Shutdown command on the device using Remote PowerShell.</span></span> <span data-ttu-id="a50eb-238">有关详细信息，请参阅 [使用 PowerShell 进行远程管理](../rooms/rooms-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="a50eb-238">For more information, see [Remote Management using PowerShell](../rooms/rooms-operations.md).</span></span>
    - <span data-ttu-id="a50eb-239">**运行重启-计算机** 你可以 `Restart-Computer` 在本地计算机上运行 cmdlet，并指定要重新启动的设备的计算机名。</span><span class="sxs-lookup"><span data-stu-id="a50eb-239">**Run Restart-Computer** You can run the `Restart-Computer` cmdlet on your local computer and specify the computer name of the device you want to restart.</span></span> <span data-ttu-id="a50eb-240">有关详细信息，请参阅 [重新启动计算机](https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-7)。</span><span class="sxs-lookup"><span data-stu-id="a50eb-240">For more information, see [Restart-Computer](https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-7).</span></span>

## <a name="step-5-configure-surface-hub"></a><span data-ttu-id="a50eb-241">步骤5：配置 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="a50eb-241">Step 5: Configure Surface Hub</span></span>

<span data-ttu-id="a50eb-242">你可以使用 Windows 配置设计器创建预配包，你可以使用它将协调会议设置应用于 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="a50eb-242">You can use Windows Configuration Designer to create a provisioning package that you can use to apply Coordinating Meetings settings to your Surface Hubs.</span></span> <span data-ttu-id="a50eb-243">你将在上面创建的 XML 文件粘贴到 Windows 配置设计器以创建预配包。</span><span class="sxs-lookup"><span data-stu-id="a50eb-243">You'll paste the XML file you created above into Windows Configuration Designer to create the provisioning package.</span></span>

### <a name="create-coordinated-meetings-xml-configuration-file-for-surface-hub"></a><span data-ttu-id="a50eb-244">创建 Surface Hub 的协调会议 XML 配置文件</span><span class="sxs-lookup"><span data-stu-id="a50eb-244">Create Coordinated Meetings XML configuration file for Surface Hub</span></span>

<span data-ttu-id="a50eb-245">Windows 配置设计器和 Microsoft Intune 都用于将协调的会议配置应用于 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="a50eb-245">Both Windows Configuration Designer and Microsoft Intune are used to apply the Coordinated Meetings configuration to your Surface Hubs.</span></span> <span data-ttu-id="a50eb-246">配置是使用 XML 定义的。</span><span class="sxs-lookup"><span data-stu-id="a50eb-246">The configuration is defined using XML.</span></span> <span data-ttu-id="a50eb-247">在继续操作之前，你需要创建将应用的 XML。</span><span class="sxs-lookup"><span data-stu-id="a50eb-247">Before you go further, you need to create the XML that will be applied.</span></span>

<span data-ttu-id="a50eb-248">下面是 "协调的会议" XML 配置文件的语法。</span><span class="sxs-lookup"><span data-stu-id="a50eb-248">The following is the syntax of the Coordinated Meetings XML configuration file.</span></span>

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

<span data-ttu-id="a50eb-249">执行以下操作以准备适用于 Windows 配置设计器或 Microsoft Intune 的 XML：</span><span class="sxs-lookup"><span data-stu-id="a50eb-249">Do the following to prepare the XML for Windows Configuration Designer or Microsoft Intune:</span></span>

1. <span data-ttu-id="a50eb-250">在文本文件编辑器（如 Visual Studio 代码或记事本）中，将上面的 XML 粘贴到新文件中。</span><span class="sxs-lookup"><span data-stu-id="a50eb-250">In a text file editor, such as Visual Studio Code or Notepad, paste the above XML into a new file.</span></span>

2. <span data-ttu-id="a50eb-251">将每个 XML 元素设置为 `true` `false` 电子表格中的相应值或值。</span><span class="sxs-lookup"><span data-stu-id="a50eb-251">Set each of the XML elements to the corresponding `true` or `false` value in your spreadsheet.</span></span> <span data-ttu-id="a50eb-252">例如，如果 **音频默认值** 为 `true` ，则设置 `<Audio default="true">` 。</span><span class="sxs-lookup"><span data-stu-id="a50eb-252">For example, if **Audio default** is `true`, set `<Audio default="true">`.</span></span>

3. <span data-ttu-id="a50eb-253">请确保更改 `TrustedAccounts` 为 upn 列表。</span><span class="sxs-lookup"><span data-stu-id="a50eb-253">Be sure to change `TrustedAccounts` to your list of UPNs.</span></span>

4. <span data-ttu-id="a50eb-254">Windows 配置设计器要求 XML 位于单个行上。</span><span class="sxs-lookup"><span data-stu-id="a50eb-254">Windows Configuration Designer requires that the XML be on a single line.</span></span> <span data-ttu-id="a50eb-255">删除每行之间的所有换行符，以使 XML 如下所示：</span><span class="sxs-lookup"><span data-stu-id="a50eb-255">Remove all the line breaks between each line so that the XML looks like the following:</span></span>

    ```xml
    <SurfaceHubSettings><BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>...
    ```

5. <span data-ttu-id="a50eb-256">将文件保存在您的计算机上。</span><span class="sxs-lookup"><span data-stu-id="a50eb-256">Save the file on your computer.</span></span>

<span data-ttu-id="a50eb-257">创建 XML 配置文件后，请使用 " [管理 Microsoft 团队中的 Microsoft 团队设置](surface-hub-manage-config.md) " 中的步骤将其应用于 surface hub。</span><span class="sxs-lookup"><span data-stu-id="a50eb-257">After you've created your XML configuration file, use the steps in [Manage Microsoft Teams settings on Surface Hub](surface-hub-manage-config.md) to apply it to your Surface Hubs.</span></span>
