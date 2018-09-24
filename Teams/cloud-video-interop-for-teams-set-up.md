---
title: 设置 Microsoft 团队的云视频互操作
author: lolaj
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: srividhc
description: 本文介绍如何规划和在您的组织中设置用户云视频互操作。
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 92fe72b8352e9a2152361f410f9e39f1f296a3c8
ms.sourcegitcommit: 2d76fad92b6d6c5d1bd223a717fd6c534ecaa5be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2018
ms.locfileid: "24974428"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a><span data-ttu-id="57bfa-103">设置 Microsoft 团队的云视频互操作</span><span class="sxs-lookup"><span data-stu-id="57bfa-103">Set up Cloud Video Interop for Microsoft Teams</span></span>

<span data-ttu-id="57bfa-104">[选择上您云视频互操作的合作伙伴](cloud-video-interop.md)后，您需要规划您的部署，提供设置的详细信息和合作伙伴租户密钥和同意您的组织中的视频互操作应用程序获取设置。</span><span class="sxs-lookup"><span data-stu-id="57bfa-104">After you have [chosen on your Cloud Video Interop partner(s)](cloud-video-interop.md), you will need to plan your deployment, get set up with provisioning details and partner tenant key, and consent to the video interop app in your organization.</span></span> <span data-ttu-id="57bfa-105">下图概述的过程。</span><span class="sxs-lookup"><span data-stu-id="57bfa-105">The following diagram outlines the process.</span></span> 

![组织中部署 CVI](media/deploying-cvi.png)

## <a name="plan"></a><span data-ttu-id="57bfa-107">规划</span><span class="sxs-lookup"><span data-stu-id="57bfa-107">Plan</span></span>

<span data-ttu-id="57bfa-108">关于标识合作伙伴在组织中使用的信息，请参阅[Microsoft 团队的云视频互操作](cloud-video-interop.md)。</span><span class="sxs-lookup"><span data-stu-id="57bfa-108">See [Cloud Video Interop for Microsoft Teams](cloud-video-interop.md) for information about identifying a partner or partners to use in your organization.</span></span> 

<span data-ttu-id="57bfa-109">若要规划用户基于/并发/网站范围启用：</span><span class="sxs-lookup"><span data-stu-id="57bfa-109">To plan for user based/concurrent/site wide enablement:</span></span> 

- <span data-ttu-id="57bfa-110">选取您使用的部署模型/承载模型</span><span class="sxs-lookup"><span data-stu-id="57bfa-110">Pick a deployment model/hosted model for your use</span></span>
- <span data-ttu-id="57bfa-111">选择适合您的组织的许可计划。</span><span class="sxs-lookup"><span data-stu-id="57bfa-111">Select the license plan ideal for your organization.</span></span> 
- <span data-ttu-id="57bfa-112">虚拟机的容量规划是将承载视频基础结构。</span><span class="sxs-lookup"><span data-stu-id="57bfa-112">Plan for capacity of VMs is you are hosting your video infrastructure.</span></span>

## <a name="configure"></a><span data-ttu-id="57bfa-113">配置</span><span class="sxs-lookup"><span data-stu-id="57bfa-113">Configure</span></span> 

<span data-ttu-id="57bfa-114">若要配置云视频互操作，请按照下列步骤。</span><span class="sxs-lookup"><span data-stu-id="57bfa-114">To configure Cloud Video Interop, follow these steps.</span></span> 

1. <span data-ttu-id="57bfa-115">从合作伙伴/合作伙伴必须获取所选 （租户密钥、 appIds...） 的配置信息。</span><span class="sxs-lookup"><span data-stu-id="57bfa-115">Obtain configuration info from the partner/partners you have chosen (tenant key, appIds…).</span></span> <span data-ttu-id="57bfa-116">您可以使用一个或多个视频互操作的合作伙伴组织</span><span class="sxs-lookup"><span data-stu-id="57bfa-116">You can use one or more video interop partners in your organization</span></span> 

2. <span data-ttu-id="57bfa-117">确保您的网络配置正确。</span><span class="sxs-lookup"><span data-stu-id="57bfa-117">Ensure that your network is configured correctly.</span></span> <span data-ttu-id="57bfa-118">配置基于标准的视频防火墙的外围网络遍历支持。</span><span class="sxs-lookup"><span data-stu-id="57bfa-118">Configure your standards-based video firewall for perimeter network traversal to support.</span></span> <span data-ttu-id="57bfa-119">例如：</span><span class="sxs-lookup"><span data-stu-id="57bfa-119">For example:</span></span> 
    - <span data-ttu-id="57bfa-120">Cisco VCS-e</span><span class="sxs-lookup"><span data-stu-id="57bfa-120">Cisco VCS-e</span></span>                  
    - <span data-ttu-id="57bfa-121">Polycom RPAD</span><span class="sxs-lookup"><span data-stu-id="57bfa-121">Polycom RPAD</span></span>

3. <span data-ttu-id="57bfa-122">配置 exchange 和 OTD 集成的聊天室。</span><span class="sxs-lookup"><span data-stu-id="57bfa-122">Configure integrated rooms with exchange and OTD.</span></span> <span data-ttu-id="57bfa-123">在大多数情况下，其他中继需要设置和配置您的环境中。</span><span class="sxs-lookup"><span data-stu-id="57bfa-123">In most cases, additional relay would need to be set up and configured in your environment.</span></span>


## <a name="provision"></a><span data-ttu-id="57bfa-124">设置</span><span class="sxs-lookup"><span data-stu-id="57bfa-124">Provision</span></span>
 
<span data-ttu-id="57bfa-125">租户密钥将与合作伙伴服务的拨出。</span><span class="sxs-lookup"><span data-stu-id="57bfa-125">The tenant key will be the dial out to the partner service.</span></span> <span data-ttu-id="57bfa-126">以下示例中，在 813878896@t.plcm.vc 是租户密钥。</span><span class="sxs-lookup"><span data-stu-id="57bfa-126">In the following example, 813878896@t.plcm.vc is the tenant key.</span></span> 

![租户密钥示例](media/tenant-key-example.png) 

<span data-ttu-id="57bfa-128">您需要执行以下 cmdlet 设置的租户密钥，并还允许选择用户或整个组织使用视频互操作性坐标创建会议。</span><span class="sxs-lookup"><span data-stu-id="57bfa-128">You will need to execute the following cmdlets to provision the tenant key, and also enable select users or your whole organization to create meetings with video interop coordinates.</span></span>

 
- <span data-ttu-id="57bfa-129">\*\* [Get CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/en-us/powershell/module/skype/get-csteamsvideointeropservicepolicy):\*\* Microsoft 提供的预构建的策略用于每个允许您指定其中合作伙伴用于云视频互操作的支持合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="57bfa-129">**[Get-CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/en-us/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft provides pre-constructed policies for each of our supported partners that allow you to designate which partner(s) to use for cloud video interop.</span></span>

    <span data-ttu-id="57bfa-130">此 cmdlet，可以确定可以在组织中使用的预构建的策略。</span><span class="sxs-lookup"><span data-stu-id="57bfa-130">This cmdlet allows you to identify the pre-constructed policies that you can use in your organization.</span></span> <span data-ttu-id="57bfa-131">您可以将此策略分配给一个或多个用户利用授予 CsTeamsVideoInteropServicePolicy cmdlet。</span><span class="sxs-lookup"><span data-stu-id="57bfa-131">You can assign this policy to one or more of your users leveraging the Grant-CsTeamsVideoInteropServicePolicy cmdlet.</span></span>
 
- <span data-ttu-id="57bfa-132">**[授予 CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** 授予 CsTeamsVideoInteropServicePolicy cmdlet 可以分配组织中使用的预构建的策略或将策略分配给特定用户。</span><span class="sxs-lookup"><span data-stu-id="57bfa-132">**[Grant-CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** The Grant-CsTeamsVideoInteropServicePolicy cmdlet allows you to assign a pre-constructed policy for use in your organization or assign the policy to specific users.</span></span>
 
- <span data-ttu-id="57bfa-133">**[新 CsVideoInteropServiceProvider](https://docs.microsoft.com/en-us/powershell/module/skype/new-csvideointeropserviceprovider):** 新建 CsVideoInteropServiceProvider 用于指定有关支持 CVI 合作伙伴组织希望使用的信息。</span><span class="sxs-lookup"><span data-stu-id="57bfa-133">**[New-CsVideoInteropServiceProvider](https://docs.microsoft.com/en-us/powershell/module/skype/new-csvideointeropserviceprovider):** Use the New-CsVideoInteropServiceProvider to specify information about a supported CVI partner your organization would like to use.</span></span>
 
- <span data-ttu-id="57bfa-134">**[集 CsVideoInteropServiceProvider](https://docs.microsoft.com/en-us/powershell/module/skype/set-csvideointeropserviceprovider):** 使用组 CsVideoInteropServiceProvider 更新您的组织使用的支持 CVI 合作伙伴的信息。</span><span class="sxs-lookup"><span data-stu-id="57bfa-134">**[Set-CsVideoInteropServiceProvider](https://docs.microsoft.com/en-us/powershell/module/skype/set-csvideointeropserviceprovider):** Use the Set-CsVideoInteropServiceProvider to update information about a supported CVI partner your organization uses.</span></span>
 
- <span data-ttu-id="57bfa-135">\*\* [Get CsVideoInteropServiceProvider](https://docs.microsoft.com/en-us/powershell/module/skype/get-csvideointeropserviceprovider):\*\* 获取组织中使用的所有已配置提供程序。</span><span class="sxs-lookup"><span data-stu-id="57bfa-135">**[Get-CsVideoInteropServiceProvider](https://docs.microsoft.com/en-us/powershell/module/skype/get-csvideointeropserviceprovider):** Get all of the providers that have been configured for use within the organization.</span></span>
 
- <span data-ttu-id="57bfa-136">**[删除 CsVideoInteropServiceProvider](https://docs.microsoft.com/en-us/powershell/module/skype/remove-csvideointeropserviceprovider):** 使用删除 CsVideoInteropServiceProvider 删除有关您的组织不再使用的提供程序的所有提供商信息。</span><span class="sxs-lookup"><span data-stu-id="57bfa-136">**[Remove-CsVideoInteropServiceProvider](https://docs.microsoft.com/en-us/powershell/module/skype/remove-csvideointeropserviceprovider):** Use Remove-CsVideoInteropServiceProvider to remove all provider information about a provider that your organization no longer uses.</span></span>  
 
## <a name="consent"></a><span data-ttu-id="57bfa-137">同意</span><span class="sxs-lookup"><span data-stu-id="57bfa-137">Consent</span></span>

<span data-ttu-id="57bfa-138">您需要为远程视频会议设备 (VTCs) 加入您的组织会议，通过合作伙伴服务提供权限同意。</span><span class="sxs-lookup"><span data-stu-id="57bfa-138">You will need to provide permission consent for the video teleconferencing devices (VTCs) to join your organizations meetings via the partner service.</span></span> <span data-ttu-id="57bfa-139">此外将由您的合作伙伴提供此同意链接。</span><span class="sxs-lookup"><span data-stu-id="57bfa-139">This consent link will also be provided by your partner.</span></span>  
 
<span data-ttu-id="57bfa-140">完成这些步骤后，如果已启用租户，单独启用通过授予 cmdlet，或在组织中的用户的所有用户将他们安排的团队会议中具有 VTC 坐标。</span><span class="sxs-lookup"><span data-stu-id="57bfa-140">When these steps are complete, the users who are individually enabled via the Grant cmdlet above, or all of the users in the organization if the tenant is enabled, will have VTC coordinates in all the Teams meetings that they schedule.</span></span> <span data-ttu-id="57bfa-141">任何 VTC 可以加入这些会议，通过这些坐标。</span><span class="sxs-lookup"><span data-stu-id="57bfa-141">Any VTC can join these meetings via those coordinates.</span></span>


|<span data-ttu-id="57bfa-142">名称</span><span class="sxs-lookup"><span data-stu-id="57bfa-142">Name</span></span>|<span data-ttu-id="57bfa-143">应用程序权限的简短说明</span><span class="sxs-lookup"><span data-stu-id="57bfa-143">Application Permission Short Description</span></span>| <span data-ttu-id="57bfa-144">说明</span><span class="sxs-lookup"><span data-stu-id="57bfa-144">Description</span></span>|
|--|--|---|
|<span data-ttu-id="57bfa-145">Calls.JoinGroupCall.All</span><span class="sxs-lookup"><span data-stu-id="57bfa-145">Calls.JoinGroupCall.All</span></span>|<span data-ttu-id="57bfa-146">加入组呼叫和会议作为应用程序 （预览）</span><span class="sxs-lookup"><span data-stu-id="57bfa-146">Join Group Calls and Meetings as an app (preview)</span></span>|<span data-ttu-id="57bfa-147">允许应用程序以在组织中，已登录的用户的情况下加入组呼叫和计划的会议。</span><span class="sxs-lookup"><span data-stu-id="57bfa-147">Allows the app to join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="57bfa-148">应用程序将被加入的会议在您的租户中的目录用户权限。</span><span class="sxs-lookup"><span data-stu-id="57bfa-148">The app will be joined with the privileges of a directory user to meetings in your tenant.</span></span>|
|<span data-ttu-id="57bfa-149">Calls.JoinGroupCallasGuest.All</span><span class="sxs-lookup"><span data-stu-id="57bfa-149">Calls.JoinGroupCallasGuest.All</span></span>|<span data-ttu-id="57bfa-150">作为来宾用户 （预览） 加入组呼叫和会议</span><span class="sxs-lookup"><span data-stu-id="57bfa-150">Join Group Calls and Meetings as a guest user (preview)</span></span>|<span data-ttu-id="57bfa-151">允许应用程序以匿名方式加入您的组织，没有已登录的用户组呼叫和计划的会议。</span><span class="sxs-lookup"><span data-stu-id="57bfa-151">Allows the app to anonymously join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="57bfa-152">将以来宾身份加入会议租户中加入应用程序。</span><span class="sxs-lookup"><span data-stu-id="57bfa-152">The app will be joined as a guest to meetings in your tenant.</span></span>|
|<span data-ttu-id="57bfa-153">Calls.AccessMedia.All</span><span class="sxs-lookup"><span data-stu-id="57bfa-153">Calls.AccessMedia.All</span></span>|<span data-ttu-id="57bfa-154">访问呼叫作为应用程序 (preview) 中的媒体流</span><span class="sxs-lookup"><span data-stu-id="57bfa-154">Access media streams in a call as an app (preview)</span></span>|<span data-ttu-id="57bfa-155">允许应用程序以获取对媒体流进行通话，已登录的用户的情况下直接访问。</span><span class="sxs-lookup"><span data-stu-id="57bfa-155">Allows the app to get direct access to media streams in a call, without a signed-in user.</span></span>|
|<span data-ttu-id="57bfa-156">OnlineMeetings.Read.All</span><span class="sxs-lookup"><span data-stu-id="57bfa-156">OnlineMeetings.Read.All</span></span>|<span data-ttu-id="57bfa-157">读取联机会议详细信息 （预览）</span><span class="sxs-lookup"><span data-stu-id="57bfa-157">Read Online Meeting details (preview)</span></span>|<span data-ttu-id="57bfa-158">允许应用程序读取登录用户的情况下在组织中的联机会议详细信息。</span><span class="sxs-lookup"><span data-stu-id="57bfa-158">Allows the app to read Online Meeting details in your organization, without a signed-in user.</span></span>|

## <a name="schedule"></a><span data-ttu-id="57bfa-159">计划</span><span class="sxs-lookup"><span data-stu-id="57bfa-159">Schedule</span></span>

<span data-ttu-id="57bfa-160">接下来，安排团队会议视频互操作的坐标。</span><span class="sxs-lookup"><span data-stu-id="57bfa-160">Next, schedule Teams meeting with video interop coordinates.</span></span> <span data-ttu-id="57bfa-161">启用的用户可以安排通过团队会议：</span><span class="sxs-lookup"><span data-stu-id="57bfa-161">The enabled user can schedule teams meetings via:</span></span>
- [<span data-ttu-id="57bfa-162">会议外接程序 Outlook 的团队</span><span class="sxs-lookup"><span data-stu-id="57bfa-162">Teams Meeting add-in for Outlook</span></span>](teams-add-in-for-outlook.md)
- <span data-ttu-id="57bfa-163">桌面和移动的团队客户端</span><span class="sxs-lookup"><span data-stu-id="57bfa-163">Teams client desktop and mobile</span></span>


## <a name="join"></a><span data-ttu-id="57bfa-164">Join</span><span class="sxs-lookup"><span data-stu-id="57bfa-164">Join</span></span>

<span data-ttu-id="57bfa-165">您可以按以下方式与 VTC 设备加入团队会议：</span><span class="sxs-lookup"><span data-stu-id="57bfa-165">You can join Teams meetings with your VTC devices in the following ways:</span></span>
 
- <span data-ttu-id="57bfa-166">IVR （互动语音响应）</span><span class="sxs-lookup"><span data-stu-id="57bfa-166">IVR (Interactive voice Response)</span></span>
    - <span data-ttu-id="57bfa-167">您可以使用 tenantkey@domain 的合作伙伴的 IVR 拨入。</span><span class="sxs-lookup"><span data-stu-id="57bfa-167">You can dial in to the partner's IVR using the tenantkey@domain.</span></span> 
    - <span data-ttu-id="57bfa-168">伙伴 IVR 中后，将提示您输入 VTC conferenceId，其中将然后将您连接到团队会议。</span><span class="sxs-lookup"><span data-stu-id="57bfa-168">Once you are in the partner IVR, you will be prompted to enter the VTC conferenceId, which will then connect you to the Teams meeting.</span></span>
- <span data-ttu-id="57bfa-169">直接拨号</span><span class="sxs-lookup"><span data-stu-id="57bfa-169">Direct dial</span></span>
    - <span data-ttu-id="57bfa-170">可以不使用 tenantkey 的完整字符串的直拨功能与合作伙伴的 IVR 交互直接拨入团队会议。VTC ConferenceId@domain。</span><span class="sxs-lookup"><span data-stu-id="57bfa-170">You can directly dial into the Teams meeting without interacting with the partner’s IVR by using the direct dial feature using the full string of tenantkey.VTC ConferenceId@domain.</span></span>
- <span data-ttu-id="57bfa-171">一站式拨号</span><span class="sxs-lookup"><span data-stu-id="57bfa-171">One-touch dial</span></span>
    - <span data-ttu-id="57bfa-172">如果您有集成的团队会议室，您可以使用 （而无需键入任何拨号串） 由您的合作伙伴提供的一站式拨号功能。</span><span class="sxs-lookup"><span data-stu-id="57bfa-172">If you have an integrated Teams room, you can use the one-touch dial capabilities offered by your partner (without needing to type any dial string).</span></span>

<span data-ttu-id="57bfa-173">最后，engaeg 与团队中使用音频、 视频以及内容共享会议的用户。</span><span class="sxs-lookup"><span data-stu-id="57bfa-173">Finally, engaeg with Teams users in your meetings using audio, video, and content sharing.</span></span> 