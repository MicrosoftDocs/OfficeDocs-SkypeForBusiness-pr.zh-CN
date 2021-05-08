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
description: 本文介绍如何为组织中用户计划和设置云视频互操作。
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 64d790e775ac0d76de48a71de8d165656f2e6927
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102598"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a><span data-ttu-id="17def-103">设置 Microsoft Teams 的云视频互操作性</span><span class="sxs-lookup"><span data-stu-id="17def-103">Set up Cloud Video Interop for Microsoft Teams</span></span>

<span data-ttu-id="17def-104">选择云视频[](cloud-video-interop.md)互操作合作伙伴 () 后，需要规划部署、设置预配详细信息和合作伙伴租户密钥，并同意组织中视频互操作应用。</span><span class="sxs-lookup"><span data-stu-id="17def-104">After you have [chosen your Cloud Video Interop partner(s)](cloud-video-interop.md), you will need to plan your deployment, get set up with provisioning details and partner tenant key, and consent to the video interop app in your organization.</span></span> <span data-ttu-id="17def-105">下图概述了该过程。</span><span class="sxs-lookup"><span data-stu-id="17def-105">The following diagram outlines the process.</span></span> 

![在组织中部署 CVI](media/deploying-cvi.png)

## <a name="plan"></a><span data-ttu-id="17def-107">规划</span><span class="sxs-lookup"><span data-stu-id="17def-107">Plan</span></span>

<span data-ttu-id="17def-108">有关[确定组织Microsoft Teams](cloud-video-interop.md)合作伙伴的信息，请参阅 Cloud Video Interop for Microsoft Teams for your organization（云视频互操作）。</span><span class="sxs-lookup"><span data-stu-id="17def-108">See [Cloud Video Interop for Microsoft Teams](cloud-video-interop.md) for information about identifying a partner or partners to use in your organization.</span></span> 

<span data-ttu-id="17def-109">规划基于用户/并发/站点范围的启用：</span><span class="sxs-lookup"><span data-stu-id="17def-109">To plan for user based/concurrent/site wide enablement:</span></span> 

- <span data-ttu-id="17def-110">选择一个部署模型/托管模型供你使用</span><span class="sxs-lookup"><span data-stu-id="17def-110">Pick a deployment model/hosted model for your use</span></span>
- <span data-ttu-id="17def-111">选择最适合组织的许可证计划。</span><span class="sxs-lookup"><span data-stu-id="17def-111">Select the license plan ideal for your organization.</span></span> 
- <span data-ttu-id="17def-112">VM 容量规划是托管视频基础结构。</span><span class="sxs-lookup"><span data-stu-id="17def-112">Plan for capacity of VMs is you are hosting your video infrastructure.</span></span>

## <a name="configure"></a><span data-ttu-id="17def-113">配置</span><span class="sxs-lookup"><span data-stu-id="17def-113">Configure</span></span> 

<span data-ttu-id="17def-114">若要配置云视频互操作，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="17def-114">To configure Cloud Video Interop, follow these steps.</span></span> 

1. <span data-ttu-id="17def-115">从所选合作伙伴/合作伙伴获取配置信息 (租户密钥 appIds...) 。</span><span class="sxs-lookup"><span data-stu-id="17def-115">Obtain configuration info from the partner/partners you have chosen (tenant key, appIds…).</span></span> <span data-ttu-id="17def-116">可以在组织中使用一个或多个视频互操作合作伙伴</span><span class="sxs-lookup"><span data-stu-id="17def-116">You can use one or more video interop partners in your organization</span></span> 

2. <span data-ttu-id="17def-117">确保网络配置正确。</span><span class="sxs-lookup"><span data-stu-id="17def-117">Ensure that your network is configured correctly.</span></span> <span data-ttu-id="17def-118">为外围网络遍历配置基于标准的视频防火墙以支持。</span><span class="sxs-lookup"><span data-stu-id="17def-118">Configure your standards-based video firewall for perimeter network traversal to support.</span></span> <span data-ttu-id="17def-119">例如：</span><span class="sxs-lookup"><span data-stu-id="17def-119">For example:</span></span> 
    - <span data-ttu-id="17def-120">Cisco VCS-e</span><span class="sxs-lookup"><span data-stu-id="17def-120">Cisco VCS-e</span></span>                  
    - <span data-ttu-id="17def-121">Polycom RPAD</span><span class="sxs-lookup"><span data-stu-id="17def-121">Polycom RPAD</span></span>

3. <span data-ttu-id="17def-122">使用 Exchange 和 OTD 配置集成房间。</span><span class="sxs-lookup"><span data-stu-id="17def-122">Configure integrated rooms with exchange and OTD.</span></span> <span data-ttu-id="17def-123">在大多数情况下，需要在环境中设置和配置其他中继。</span><span class="sxs-lookup"><span data-stu-id="17def-123">In most cases, additional relay would need to be set up and configured in your environment.</span></span>


## <a name="provision"></a><span data-ttu-id="17def-124">预配</span><span class="sxs-lookup"><span data-stu-id="17def-124">Provision</span></span>
 
<span data-ttu-id="17def-125">租户密钥将是向合作伙伴服务拨出。</span><span class="sxs-lookup"><span data-stu-id="17def-125">The tenant key will be the dial out to the partner service.</span></span> <span data-ttu-id="17def-126">在下面的示例中，813878896@t.plcm.vc 租户密钥。</span><span class="sxs-lookup"><span data-stu-id="17def-126">In the following example, 813878896@t.plcm.vc is the tenant key.</span></span> 

![租户密钥示例](media/tenant-key-example.png) 

<span data-ttu-id="17def-128">需要执行以下 cmdlet 来预配租户密钥，同时允许选择用户或整个组织使用视频互操作坐标创建会议。</span><span class="sxs-lookup"><span data-stu-id="17def-128">You will need to execute the following cmdlets to provision the tenant key, and also enable select users or your whole organization to create meetings with video interop coordinates.</span></span>

 
- <span data-ttu-id="17def-129">**[Get-CsTeamsVideoInteropServicepolicy：](/powershell/module/skype/get-csteamsvideointeropservicepolicy)** Microsoft 为每个支持的合作伙伴提供预构建的策略，允许指定 (合作伙伴) 云视频互操作。</span><span class="sxs-lookup"><span data-stu-id="17def-129">**[Get-CsTeamsVideoInteropServicepolicy](/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft provides pre-constructed policies for each of our supported partners that allow you to designate which partner(s) to use for cloud video interop.</span></span>

    <span data-ttu-id="17def-130">使用此 cmdlet 可以标识可在组织中使用的预构建策略。</span><span class="sxs-lookup"><span data-stu-id="17def-130">This cmdlet allows you to identify the pre-constructed policies that you can use in your organization.</span></span> <span data-ttu-id="17def-131">可以将此策略分配给利用 Grant-CsTeamsVideoInteropServicePolicy cmdlet 的一个或多个用户。</span><span class="sxs-lookup"><span data-stu-id="17def-131">You can assign this policy to one or more of your users leveraging the Grant-CsTeamsVideoInteropServicePolicy cmdlet.</span></span>
 
- <span data-ttu-id="17def-132">**[Grant-CsTeamsVideoInteropServicePolicy：](/powershell/module/skype/grant-csteamsvideointeropservicepolicy)** 使用 Grant-CsTeamsVideoInteropServicePolicy cmdlet 可分配预构造的策略，以在组织中使用，或将策略分配给特定用户。</span><span class="sxs-lookup"><span data-stu-id="17def-132">**[Grant-CsTeamsVideoInteropServicePolicy](/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** The Grant-CsTeamsVideoInteropServicePolicy cmdlet allows you to assign a pre-constructed policy for use in your organization or assign the policy to specific users.</span></span>
 
- <span data-ttu-id="17def-133">**[New-CsVideoInteropServiceProvider：](/powershell/module/skype/new-csvideointeropserviceprovider)** 使用New-CsVideoInteropServiceProvider指定有关组织希望使用的受支持 CVI 合作伙伴的信息。</span><span class="sxs-lookup"><span data-stu-id="17def-133">**[New-CsVideoInteropServiceProvider](/powershell/module/skype/new-csvideointeropserviceprovider):** Use the New-CsVideoInteropServiceProvider to specify information about a supported CVI partner your organization would like to use.</span></span>
 
- <span data-ttu-id="17def-134">**[Set-CsVideoInteropServiceProvider：](/powershell/module/skype/set-csvideointeropserviceprovider)** 使用Set-CsVideoInteropServiceProvider更新有关组织使用的受支持 CVI 合作伙伴的信息。</span><span class="sxs-lookup"><span data-stu-id="17def-134">**[Set-CsVideoInteropServiceProvider](/powershell/module/skype/set-csvideointeropserviceprovider):** Use the Set-CsVideoInteropServiceProvider to update information about a supported CVI partner your organization uses.</span></span>
 
- <span data-ttu-id="17def-135">**[Get-CsVideoInteropServiceProvider：](/powershell/module/skype/get-csvideointeropserviceprovider)** 获取已配置为在组织中使用的所有提供程序。</span><span class="sxs-lookup"><span data-stu-id="17def-135">**[Get-CsVideoInteropServiceProvider](/powershell/module/skype/get-csvideointeropserviceprovider):** Get all of the providers that have been configured for use within the organization.</span></span>
 
- <span data-ttu-id="17def-136">**[Remove-CsVideoInteropServiceProvider：](/powershell/module/skype/remove-csvideointeropserviceprovider)** 使用Remove-CsVideoInteropServiceProvider删除有关组织不再使用的提供商的所有提供商信息。</span><span class="sxs-lookup"><span data-stu-id="17def-136">**[Remove-CsVideoInteropServiceProvider](/powershell/module/skype/remove-csvideointeropserviceprovider):** Use Remove-CsVideoInteropServiceProvider to remove all provider information about a provider that your organization no longer uses.</span></span>  
 
## <a name="consent"></a><span data-ttu-id="17def-137">同意</span><span class="sxs-lookup"><span data-stu-id="17def-137">Consent</span></span>

<span data-ttu-id="17def-138">你需要向 VTC 发送视频电话会议设备 (许可) 合作伙伴服务加入组织会议。</span><span class="sxs-lookup"><span data-stu-id="17def-138">You will need to provide permission consent for the video teleconferencing devices (VTCs) to join your organizations meetings via the partner service.</span></span> <span data-ttu-id="17def-139">此许可链接也将由合作伙伴提供。</span><span class="sxs-lookup"><span data-stu-id="17def-139">This consent link will also be provided by your partner.</span></span>  
 
<span data-ttu-id="17def-140">完成这些步骤后，通过上述 Grant cmdlet 单独启用的用户或组织中所有用户（如果已启用租户）将在他们安排的所有 Teams 会议中具有 VTC 坐标。</span><span class="sxs-lookup"><span data-stu-id="17def-140">When these steps are complete, the users who are individually enabled via the Grant cmdlet above, or all of the users in the organization if the tenant is enabled, will have VTC coordinates in all the Teams meetings that they schedule.</span></span> <span data-ttu-id="17def-141">任何 VTC 都可以通过这些坐标加入这些会议。</span><span class="sxs-lookup"><span data-stu-id="17def-141">Any VTC can join these meetings via those coordinates.</span></span>


|<span data-ttu-id="17def-142">名称</span><span class="sxs-lookup"><span data-stu-id="17def-142">Name</span></span>|<span data-ttu-id="17def-143">应用程序权限简短说明</span><span class="sxs-lookup"><span data-stu-id="17def-143">Application Permission Short Description</span></span>| <span data-ttu-id="17def-144">说明</span><span class="sxs-lookup"><span data-stu-id="17def-144">Description</span></span>|
|--|--|---|
|<span data-ttu-id="17def-145">Calls.JoinGroupCall.All</span><span class="sxs-lookup"><span data-stu-id="17def-145">Calls.JoinGroupCall.All</span></span>|<span data-ttu-id="17def-146">将群组通话和会议作为应用加入 (预览版) </span><span class="sxs-lookup"><span data-stu-id="17def-146">Join Group Calls and Meetings as an app (preview)</span></span>|<span data-ttu-id="17def-147">允许应用在组织中加入群组通话和计划会议，而无需登录用户。</span><span class="sxs-lookup"><span data-stu-id="17def-147">Allows the app to join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="17def-148">应用将具有目录用户的权限加入租户中的会议。</span><span class="sxs-lookup"><span data-stu-id="17def-148">The app will be joined with the privileges of a directory user to meetings in your tenant.</span></span>|
|<span data-ttu-id="17def-149">Calls.JoinGroupCallasGuest.All</span><span class="sxs-lookup"><span data-stu-id="17def-149">Calls.JoinGroupCallasGuest.All</span></span>|<span data-ttu-id="17def-150">作为来宾用户加入群组通话和会议 (预览版) </span><span class="sxs-lookup"><span data-stu-id="17def-150">Join Group Calls and Meetings as a guest user (preview)</span></span>|<span data-ttu-id="17def-151">允许应用在组织中匿名加入群组通话和安排的会议，而无需登录用户。</span><span class="sxs-lookup"><span data-stu-id="17def-151">Allows the app to anonymously join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="17def-152">该应用将作为来宾加入租户中的会议。</span><span class="sxs-lookup"><span data-stu-id="17def-152">The app will be joined as a guest to meetings in your tenant.</span></span>|
|<span data-ttu-id="17def-153">Calls.AccessMedia.All</span><span class="sxs-lookup"><span data-stu-id="17def-153">Calls.AccessMedia.All</span></span>|<span data-ttu-id="17def-154">在通话中以应用或预览版 (媒体) </span><span class="sxs-lookup"><span data-stu-id="17def-154">Access media streams in a call as an app (preview)</span></span>|<span data-ttu-id="17def-155">允许应用在通话中直接访问媒体流，而无需登录用户。</span><span class="sxs-lookup"><span data-stu-id="17def-155">Allows the app to get direct access to media streams in a call, without a signed-in user.</span></span>|
|<span data-ttu-id="17def-156">OnlineMeetings.Read.All</span><span class="sxs-lookup"><span data-stu-id="17def-156">OnlineMeetings.Read.All</span></span>|<span data-ttu-id="17def-157">阅读联机会议详细信息 (预览) </span><span class="sxs-lookup"><span data-stu-id="17def-157">Read Online Meeting details (preview)</span></span>|<span data-ttu-id="17def-158">允许应用在组织中阅读联机会议详细信息，而无需登录用户。</span><span class="sxs-lookup"><span data-stu-id="17def-158">Allows the app to read Online Meeting details in your organization, without a signed-in user.</span></span>|

## <a name="schedule"></a><span data-ttu-id="17def-159">计划</span><span class="sxs-lookup"><span data-stu-id="17def-159">Schedule</span></span>

<span data-ttu-id="17def-160">接下来，使用Teams互操作坐标安排会议。</span><span class="sxs-lookup"><span data-stu-id="17def-160">Next, schedule Teams meeting with video interop coordinates.</span></span> <span data-ttu-id="17def-161">启用的用户可以通过以下方式安排团队会议：</span><span class="sxs-lookup"><span data-stu-id="17def-161">The enabled user can schedule teams meetings via:</span></span>
- [<span data-ttu-id="17def-162">Teams适用于会议的会议Outlook</span><span class="sxs-lookup"><span data-stu-id="17def-162">Teams Meeting add-in for Outlook</span></span>](teams-add-in-for-outlook.md)
- <span data-ttu-id="17def-163">Teams客户端桌面和移动版</span><span class="sxs-lookup"><span data-stu-id="17def-163">Teams client desktop and mobile</span></span>


## <a name="join"></a><span data-ttu-id="17def-164">Join</span><span class="sxs-lookup"><span data-stu-id="17def-164">Join</span></span>

<span data-ttu-id="17def-165">可以通过以下Teams与 VTC 设备一起加入会议：</span><span class="sxs-lookup"><span data-stu-id="17def-165">You can join Teams meetings with your VTC devices in the following ways:</span></span>
 
- <span data-ttu-id="17def-166">IVR (交互式语音响应) </span><span class="sxs-lookup"><span data-stu-id="17def-166">IVR (Interactive voice Response)</span></span>
    - <span data-ttu-id="17def-167">可以使用设备拨入合作伙伴的 IVR tenantkey@domain。</span><span class="sxs-lookup"><span data-stu-id="17def-167">You can dial in to the partner's IVR using the tenantkey@domain.</span></span> 
    - <span data-ttu-id="17def-168">进入合作伙伴 IVR 后，系统会提示输入 VTC conferenceId，然后它将你连接到 Teams 会议。</span><span class="sxs-lookup"><span data-stu-id="17def-168">Once you are in the partner IVR, you will be prompted to enter the VTC conferenceId, which will then connect you to the Teams meeting.</span></span>
- <span data-ttu-id="17def-169">直接拨号</span><span class="sxs-lookup"><span data-stu-id="17def-169">Direct dial</span></span>
    - <span data-ttu-id="17def-170">通过使用 tenantkey 的完整Teams直接拨号功能，可以直接拨入 Teams 会议，而无需与合作伙伴的 IVR 交互。VTC ConferenceId@domain。</span><span class="sxs-lookup"><span data-stu-id="17def-170">You can directly dial into the Teams meeting without interacting with the partner’s IVR by using the direct dial feature using the full string of tenantkey.VTC ConferenceId@domain.</span></span>
- <span data-ttu-id="17def-171">一键式拨号</span><span class="sxs-lookup"><span data-stu-id="17def-171">One-touch dial</span></span>
    - <span data-ttu-id="17def-172">如果您有集成的Teams会议室，您可以使用合作伙伴合作伙伴提供的一键式拨号功能 (无需键入任何拨号字符串) 。</span><span class="sxs-lookup"><span data-stu-id="17def-172">If you have an integrated Teams room, you can use the one-touch dial capabilities offered by your partner (without needing to type any dial string).</span></span>

<span data-ttu-id="17def-173">最后，使用Teams、视频和内容共享与会议中的用户互动。</span><span class="sxs-lookup"><span data-stu-id="17def-173">Finally, engage with Teams users in your meetings using audio, video, and content sharing.</span></span>