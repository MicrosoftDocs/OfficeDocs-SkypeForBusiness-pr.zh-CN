---
title: 设置 Microsoft Teams 的云视频互操作性
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: srividhc
f1.keywords:
- NOCSH
description: 本文介绍如何为组织中的用户规划和设置云视频互操作。
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a1f45967b3e2737f6e2df74c505932ea69afe37f
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582629"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a><span data-ttu-id="b1859-103">设置 Microsoft Teams 的云视频互操作性</span><span class="sxs-lookup"><span data-stu-id="b1859-103">Set up Cloud Video Interop for Microsoft Teams</span></span>

<span data-ttu-id="b1859-104">[选择你的云视频互操作伙伴 (s) ](cloud-video-interop.md)后，你需要规划部署、使用预配详细信息和合作伙伴租户密钥进行设置，并同意你的组织中的视频互操作应用。</span><span class="sxs-lookup"><span data-stu-id="b1859-104">After you have [chosen your Cloud Video Interop partner(s)](cloud-video-interop.md), you will need to plan your deployment, get set up with provisioning details and partner tenant key, and consent to the video interop app in your organization.</span></span> <span data-ttu-id="b1859-105">下图概括介绍了该过程。</span><span class="sxs-lookup"><span data-stu-id="b1859-105">The following diagram outlines the process.</span></span> 

![在组织中部署 CVI](media/deploying-cvi.png)

## <a name="plan"></a><span data-ttu-id="b1859-107">规划</span><span class="sxs-lookup"><span data-stu-id="b1859-107">Plan</span></span>

<span data-ttu-id="b1859-108">有关如何确定要在组织中使用的合作伙伴或合作伙伴的信息，请参阅[Microsoft 团队的云视频互操作](cloud-video-interop.md)。</span><span class="sxs-lookup"><span data-stu-id="b1859-108">See [Cloud Video Interop for Microsoft Teams](cloud-video-interop.md) for information about identifying a partner or partners to use in your organization.</span></span> 

<span data-ttu-id="b1859-109">规划基于用户的/并行/网站范围的支持：</span><span class="sxs-lookup"><span data-stu-id="b1859-109">To plan for user based/concurrent/site wide enablement:</span></span> 

- <span data-ttu-id="b1859-110">选择部署模型/托管模型供你使用</span><span class="sxs-lookup"><span data-stu-id="b1859-110">Pick a deployment model/hosted model for your use</span></span>
- <span data-ttu-id="b1859-111">选择适用于你的组织的许可证计划。</span><span class="sxs-lookup"><span data-stu-id="b1859-111">Select the license plan ideal for your organization.</span></span> 
- <span data-ttu-id="b1859-112">对虚拟机的容量进行规划是您托管的视频基础结构。</span><span class="sxs-lookup"><span data-stu-id="b1859-112">Plan for capacity of VMs is you are hosting your video infrastructure.</span></span>

## <a name="configure"></a><span data-ttu-id="b1859-113">配置</span><span class="sxs-lookup"><span data-stu-id="b1859-113">Configure</span></span> 

<span data-ttu-id="b1859-114">若要配置云视频互操作，请按照下列步骤操作。</span><span class="sxs-lookup"><span data-stu-id="b1859-114">To configure Cloud Video Interop, follow these steps.</span></span> 

1. <span data-ttu-id="b1859-115">从你选择的合作伙伴/合作伙伴那里获取配置信息 (租户密钥 appIds ) 。</span><span class="sxs-lookup"><span data-stu-id="b1859-115">Obtain configuration info from the partner/partners you have chosen (tenant key, appIds…).</span></span> <span data-ttu-id="b1859-116">你可以使用你的组织中的一个或多个视频互操作合作伙伴</span><span class="sxs-lookup"><span data-stu-id="b1859-116">You can use one or more video interop partners in your organization</span></span> 

2. <span data-ttu-id="b1859-117">确保您的网络配置正确。</span><span class="sxs-lookup"><span data-stu-id="b1859-117">Ensure that your network is configured correctly.</span></span> <span data-ttu-id="b1859-118">为支持的外围网络遍历配置基于标准的视频防火墙。</span><span class="sxs-lookup"><span data-stu-id="b1859-118">Configure your standards-based video firewall for perimeter network traversal to support.</span></span> <span data-ttu-id="b1859-119">例如：</span><span class="sxs-lookup"><span data-stu-id="b1859-119">For example:</span></span> 
    - <span data-ttu-id="b1859-120">Cisco VCS-e</span><span class="sxs-lookup"><span data-stu-id="b1859-120">Cisco VCS-e</span></span>                  
    - <span data-ttu-id="b1859-121">Polycom RPAD</span><span class="sxs-lookup"><span data-stu-id="b1859-121">Polycom RPAD</span></span>

3. <span data-ttu-id="b1859-122">通过 exchange 和 OTD 配置集成会议室。</span><span class="sxs-lookup"><span data-stu-id="b1859-122">Configure integrated rooms with exchange and OTD.</span></span> <span data-ttu-id="b1859-123">在大多数情况下，需要在你的环境中设置和配置其他中继。</span><span class="sxs-lookup"><span data-stu-id="b1859-123">In most cases, additional relay would need to be set up and configured in your environment.</span></span>


## <a name="provision"></a><span data-ttu-id="b1859-124">提供</span><span class="sxs-lookup"><span data-stu-id="b1859-124">Provision</span></span>
 
<span data-ttu-id="b1859-125">租户密钥将是向合作伙伴服务拨出的电话。</span><span class="sxs-lookup"><span data-stu-id="b1859-125">The tenant key will be the dial out to the partner service.</span></span> <span data-ttu-id="b1859-126">在以下示例中，813878896@t.plcm.vc 是租户密钥。</span><span class="sxs-lookup"><span data-stu-id="b1859-126">In the following example, 813878896@t.plcm.vc is the tenant key.</span></span> 

![租户密钥示例](media/tenant-key-example.png) 

<span data-ttu-id="b1859-128">你将需要执行以下 cmdlet 来设置租户密钥，还可以启用选择用户或整个组织以使用视频互操作坐标创建会议。</span><span class="sxs-lookup"><span data-stu-id="b1859-128">You will need to execute the following cmdlets to provision the tenant key, and also enable select users or your whole organization to create meetings with video interop coordinates.</span></span>

 
- <span data-ttu-id="b1859-129">\*\* [CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsvideointeropservicepolicy)：\*\* Microsoft 为每个受支持的合作伙伴提供预构建的策略，允许你指定哪些合作伙伴 (s) 用于云视频互操作。</span><span class="sxs-lookup"><span data-stu-id="b1859-129">**[Get-CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft provides pre-constructed policies for each of our supported partners that allow you to designate which partner(s) to use for cloud video interop.</span></span>

    <span data-ttu-id="b1859-130">此 cmdlet 允许你标识可在你的组织中使用的预构建的策略。</span><span class="sxs-lookup"><span data-stu-id="b1859-130">This cmdlet allows you to identify the pre-constructed policies that you can use in your organization.</span></span> <span data-ttu-id="b1859-131">你可以利用 CsTeamsVideoInteropServicePolicy cmdlet 将此策略分配给一个或多个用户。</span><span class="sxs-lookup"><span data-stu-id="b1859-131">You can assign this policy to one or more of your users leveraging the Grant-CsTeamsVideoInteropServicePolicy cmdlet.</span></span>
 
- <span data-ttu-id="b1859-132">**[授权-CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsvideointeropservicepolicy)：** CsTeamsVideoInteropServicePolicy cmdlet 允许你分配一个预构建的策略以供在你的组织中使用，或将策略分配给特定用户。</span><span class="sxs-lookup"><span data-stu-id="b1859-132">**[Grant-CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** The Grant-CsTeamsVideoInteropServicePolicy cmdlet allows you to assign a pre-constructed policy for use in your organization or assign the policy to specific users.</span></span>
 
- <span data-ttu-id="b1859-133">**[新-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/new-csvideointeropserviceprovider)：** 使用 New-CsVideoInteropServiceProvider 指定你的组织要使用的受支持的 CVI 合作伙伴的相关信息。</span><span class="sxs-lookup"><span data-stu-id="b1859-133">**[New-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/new-csvideointeropserviceprovider):** Use the New-CsVideoInteropServiceProvider to specify information about a supported CVI partner your organization would like to use.</span></span>
 
- <span data-ttu-id="b1859-134">\*\* [Set-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/set-csvideointeropserviceprovider)：\*\* 使用 CsVideoInteropServiceProvider 更新你的组织使用的受支持的 CVI 合作伙伴的相关信息。</span><span class="sxs-lookup"><span data-stu-id="b1859-134">**[Set-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/set-csvideointeropserviceprovider):** Use the Set-CsVideoInteropServiceProvider to update information about a supported CVI partner your organization uses.</span></span>
 
- <span data-ttu-id="b1859-135">\*\* [CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/get-csvideointeropserviceprovider)：\*\* 获取已配置为在组织内使用的所有提供商。</span><span class="sxs-lookup"><span data-stu-id="b1859-135">**[Get-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/get-csvideointeropserviceprovider):** Get all of the providers that have been configured for use within the organization.</span></span>
 
- <span data-ttu-id="b1859-136">\*\* [Remove-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/remove-csvideointeropserviceprovider)：\*\* 使用 Remove-CsVideoInteropServiceProvider 删除有关你的组织不再使用的提供程序的所有提供程序信息。</span><span class="sxs-lookup"><span data-stu-id="b1859-136">**[Remove-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/remove-csvideointeropserviceprovider):** Use Remove-CsVideoInteropServiceProvider to remove all provider information about a provider that your organization no longer uses.</span></span>  
 
## <a name="consent"></a><span data-ttu-id="b1859-137">即</span><span class="sxs-lookup"><span data-stu-id="b1859-137">Consent</span></span>

<span data-ttu-id="b1859-138">你将需要为视频 teleconferencing 设备提供权限同意， (VTCs) 通过合作伙伴服务加入组织会议。</span><span class="sxs-lookup"><span data-stu-id="b1859-138">You will need to provide permission consent for the video teleconferencing devices (VTCs) to join your organizations meetings via the partner service.</span></span> <span data-ttu-id="b1859-139">您的合作伙伴也将提供此同意链接。</span><span class="sxs-lookup"><span data-stu-id="b1859-139">This consent link will also be provided by your partner.</span></span>  
 
<span data-ttu-id="b1859-140">完成这些步骤后，通过上述授权 cmdlet 单独启用的用户或组织中的所有用户（如果启用了租户）将在其计划的所有团队会议中具有 VTC 坐标。</span><span class="sxs-lookup"><span data-stu-id="b1859-140">When these steps are complete, the users who are individually enabled via the Grant cmdlet above, or all of the users in the organization if the tenant is enabled, will have VTC coordinates in all the Teams meetings that they schedule.</span></span> <span data-ttu-id="b1859-141">任何 VTC 都可以通过这些坐标加入这些会议。</span><span class="sxs-lookup"><span data-stu-id="b1859-141">Any VTC can join these meetings via those coordinates.</span></span>


|<span data-ttu-id="b1859-142">名称</span><span class="sxs-lookup"><span data-stu-id="b1859-142">Name</span></span>|<span data-ttu-id="b1859-143">应用程序权限简短说明</span><span class="sxs-lookup"><span data-stu-id="b1859-143">Application Permission Short Description</span></span>| <span data-ttu-id="b1859-144">说明</span><span class="sxs-lookup"><span data-stu-id="b1859-144">Description</span></span>|
|--|--|---|
|<span data-ttu-id="b1859-145">JoinGroupCall</span><span class="sxs-lookup"><span data-stu-id="b1859-145">Calls.JoinGroupCall.All</span></span>|<span data-ttu-id="b1859-146">将组呼叫和会议作为应用加入 (预览) </span><span class="sxs-lookup"><span data-stu-id="b1859-146">Join Group Calls and Meetings as an app (preview)</span></span>|<span data-ttu-id="b1859-147">允许应用在你的组织中加入群组通话和计划会议，无需登录用户。</span><span class="sxs-lookup"><span data-stu-id="b1859-147">Allows the app to join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="b1859-148">应用将使用目录用户的权限加入租户中的会议。</span><span class="sxs-lookup"><span data-stu-id="b1859-148">The app will be joined with the privileges of a directory user to meetings in your tenant.</span></span>|
|<span data-ttu-id="b1859-149">JoinGroupCallasGuest</span><span class="sxs-lookup"><span data-stu-id="b1859-149">Calls.JoinGroupCallasGuest.All</span></span>|<span data-ttu-id="b1859-150">以来宾用户身份加入群组呼叫和会议 (预览) </span><span class="sxs-lookup"><span data-stu-id="b1859-150">Join Group Calls and Meetings as a guest user (preview)</span></span>|<span data-ttu-id="b1859-151">允许应用在没有登录用户的情况下匿名加入组织中的群组通话和计划会议。</span><span class="sxs-lookup"><span data-stu-id="b1859-151">Allows the app to anonymously join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="b1859-152">该应用将作为来宾加入到租户中的会议。</span><span class="sxs-lookup"><span data-stu-id="b1859-152">The app will be joined as a guest to meetings in your tenant.</span></span>|
|<span data-ttu-id="b1859-153">AccessMedia</span><span class="sxs-lookup"><span data-stu-id="b1859-153">Calls.AccessMedia.All</span></span>|<span data-ttu-id="b1859-154">将呼叫中的媒体流作为应用 (预览) 中访问</span><span class="sxs-lookup"><span data-stu-id="b1859-154">Access media streams in a call as an app (preview)</span></span>|<span data-ttu-id="b1859-155">允许应用无需登录用户即可直接访问呼叫中的媒体流。</span><span class="sxs-lookup"><span data-stu-id="b1859-155">Allows the app to get direct access to media streams in a call, without a signed-in user.</span></span>|
|<span data-ttu-id="b1859-156">OnlineMeetings 已读。所有</span><span class="sxs-lookup"><span data-stu-id="b1859-156">OnlineMeetings.Read.All</span></span>|<span data-ttu-id="b1859-157"> (预览) 阅读联机会议详细信息</span><span class="sxs-lookup"><span data-stu-id="b1859-157">Read Online Meeting details (preview)</span></span>|<span data-ttu-id="b1859-158">允许应用在没有登录用户的情况下阅读您的组织中的联机会议详细信息。</span><span class="sxs-lookup"><span data-stu-id="b1859-158">Allows the app to read Online Meeting details in your organization, without a signed-in user.</span></span>|

## <a name="schedule"></a><span data-ttu-id="b1859-159">安排</span><span class="sxs-lookup"><span data-stu-id="b1859-159">Schedule</span></span>

<span data-ttu-id="b1859-160">接下来，用视频互操作坐标安排团队会议。</span><span class="sxs-lookup"><span data-stu-id="b1859-160">Next, schedule Teams meeting with video interop coordinates.</span></span> <span data-ttu-id="b1859-161">已启用的用户可以通过以下方式安排团队会议：</span><span class="sxs-lookup"><span data-stu-id="b1859-161">The enabled user can schedule teams meetings via:</span></span>
- [<span data-ttu-id="b1859-162">适用于 Outlook 的团队会议外接程序</span><span class="sxs-lookup"><span data-stu-id="b1859-162">Teams Meeting add-in for Outlook</span></span>](teams-add-in-for-outlook.md)
- <span data-ttu-id="b1859-163">团队客户端桌面和移动版</span><span class="sxs-lookup"><span data-stu-id="b1859-163">Teams client desktop and mobile</span></span>


## <a name="join"></a><span data-ttu-id="b1859-164">Join</span><span class="sxs-lookup"><span data-stu-id="b1859-164">Join</span></span>

<span data-ttu-id="b1859-165">你可以通过以下方式与你的 VTC 设备加入团队会议：</span><span class="sxs-lookup"><span data-stu-id="b1859-165">You can join Teams meetings with your VTC devices in the following ways:</span></span>
 
- <span data-ttu-id="b1859-166">IVR (交互式语音回复) </span><span class="sxs-lookup"><span data-stu-id="b1859-166">IVR (Interactive voice Response)</span></span>
    - <span data-ttu-id="b1859-167">您可以使用 tenantkey@domain 拨入合作伙伴的 IVR。</span><span class="sxs-lookup"><span data-stu-id="b1859-167">You can dial in to the partner's IVR using the tenantkey@domain.</span></span> 
    - <span data-ttu-id="b1859-168">在合作伙伴 IVR 中，系统将提示你输入 VTC conferenceId，然后该将把你连接到团队会议。</span><span class="sxs-lookup"><span data-stu-id="b1859-168">Once you are in the partner IVR, you will be prompted to enter the VTC conferenceId, which will then connect you to the Teams meeting.</span></span>
- <span data-ttu-id="b1859-169">直接拨号</span><span class="sxs-lookup"><span data-stu-id="b1859-169">Direct dial</span></span>
    - <span data-ttu-id="b1859-170">通过使用直接拨号功能 tenantkey 的完整字符串，您可以直接拨入团队会议，而无需使用直接拨号功能与合作伙伴的 IVR 进行交互。VTC ConferenceId@domain。</span><span class="sxs-lookup"><span data-stu-id="b1859-170">You can directly dial into the Teams meeting without interacting with the partner’s IVR by using the direct dial feature using the full string of tenantkey.VTC ConferenceId@domain.</span></span>
- <span data-ttu-id="b1859-171">单点触控拨号</span><span class="sxs-lookup"><span data-stu-id="b1859-171">One-touch dial</span></span>
    - <span data-ttu-id="b1859-172">如果您有一个集成的团队聊天室，则可以使用合作伙伴 (提供的一种触摸式拨号功能，而无需键入任何拨号字符串) 。</span><span class="sxs-lookup"><span data-stu-id="b1859-172">If you have an integrated Teams room, you can use the one-touch dial capabilities offered by your partner (without needing to type any dial string).</span></span>

<span data-ttu-id="b1859-173">最后，在会议中使用音频、视频和内容共享与团队用户接洽。</span><span class="sxs-lookup"><span data-stu-id="b1859-173">Finally, engage with Teams users in your meetings using audio, video, and content sharing.</span></span> 
