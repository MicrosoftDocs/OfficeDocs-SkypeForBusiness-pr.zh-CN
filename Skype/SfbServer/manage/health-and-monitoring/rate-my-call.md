---
title: 在 Skype for Business Server 中评价我的呼叫
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c4e0c905-33a1-49d8-9276-1b338f94d085
description: 摘要：了解 Skype for Business Server 中的"评价我的呼叫"功能。
ms.openlocfilehash: 597a8213576e7aa2316ace68ed91288475df2a0d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814332"
---
# <a name="rate-my-call-in-skype-for-business-server"></a><span data-ttu-id="182af-103">在 Skype for Business Server 中评价我的呼叫</span><span class="sxs-lookup"><span data-stu-id="182af-103">Rate my Call in Skype for Business Server</span></span>

<span data-ttu-id="182af-104">**摘要：** 了解 Skype for Business Server 中的"评价我的呼叫"功能。</span><span class="sxs-lookup"><span data-stu-id="182af-104">**Summary:** Learn about the Rate My Call feature in Skype for Business Server.</span></span>

<span data-ttu-id="182af-105">评价我的呼叫是 Windows 上的 Skype for Business 2015 和 2016 客户端中的一项新功能，可为企业提供一种从最终用户获取反馈的方法。</span><span class="sxs-lookup"><span data-stu-id="182af-105">Rate My Call was a new feature in Skype for Business 2015 and 2016 clients on Windows that provides enterprises a way to get feedback from their end-users.</span></span>

<span data-ttu-id="182af-106">"评价我的呼叫"窗口提供"星形"评级系统和用于音频和视频呼叫的预定义令牌。</span><span class="sxs-lookup"><span data-stu-id="182af-106">The Rate My Call window offers a "star" rating system and predefined tokens for audio and video calls.</span></span> <span data-ttu-id="182af-107">此外，管理员可以启用自定义域以提供反馈。</span><span class="sxs-lookup"><span data-stu-id="182af-107">In addition, administrators can enable a custom field to provide feedback.</span></span>

<span data-ttu-id="182af-108">收集的"评价我的呼叫"数据当前未包含在任何现有监控报告中，但具有单独的监控报告。</span><span class="sxs-lookup"><span data-stu-id="182af-108">Collected Rate My Call data is not currently included in any existing monitoring report, but it has a separate monitoring report.</span></span> <span data-ttu-id="182af-109">数据收集在SQL查询可以访问的SQL表中。</span><span class="sxs-lookup"><span data-stu-id="182af-109">Data is collected in SQL tables that can be accessed by running SQL queries.</span></span>

## <a name="rate-my-call-prerequisites"></a><span data-ttu-id="182af-110">评价我的呼叫先决条件</span><span class="sxs-lookup"><span data-stu-id="182af-110">Rate my Call Prerequisites</span></span>

<span data-ttu-id="182af-111">在 Skype for Business Server 部署中的用户可以访问"评价我的呼叫"功能之前，必须部署和配置以下组件集：</span><span class="sxs-lookup"><span data-stu-id="182af-111">Before the users in your Skype for Business Server deployment can access Rate My Call functionality, the following set of components must be deployed and configured:</span></span>

-  <span data-ttu-id="182af-112">必须在版本 9160 或更高版本 (Skype for Business Server) 。</span><span class="sxs-lookup"><span data-stu-id="182af-112">You must have Skype for Business Server installed (version 9160 or higher).</span></span>

- <span data-ttu-id="182af-113">让用户安装并更新到最新版本的 Skype for Business，并让他们使用 Skype for Business UI。</span><span class="sxs-lookup"><span data-stu-id="182af-113">Have your users install and update to the latest version of Skype for Business and also ask them to use the Skype for Business UI.</span></span>

- <span data-ttu-id="182af-114">用户必须位于 Skype for Business Server 前端池上。</span><span class="sxs-lookup"><span data-stu-id="182af-114">Users must be homed on the Skype for Business Server Front End pool.</span></span>

- <span data-ttu-id="182af-115">你必须已部署 Skype for Business Server 监控数据库，并且该数据库已与 Skype for Business Server 池关联。</span><span class="sxs-lookup"><span data-stu-id="182af-115">You must have a Skype for Business Server monitoring database deployed and associated to your Skype for Business Server pools.</span></span>

- <span data-ttu-id="182af-116">我们建议将通话质量仪表板 (CQD) 。</span><span class="sxs-lookup"><span data-stu-id="182af-116">We recommend deploying Call Quality Dashboard (CQD).</span></span>

## <a name="configure-rate-my-call"></a><span data-ttu-id="182af-117">配置"评价我的呼叫"</span><span class="sxs-lookup"><span data-stu-id="182af-117">Configure Rate my Call</span></span>

<span data-ttu-id="182af-118">"评价我的呼叫"功能默认在具有以下设置的客户端策略中启用：</span><span class="sxs-lookup"><span data-stu-id="182af-118">The Rate My Call feature is enabled by default in the Client policy with the following settings:</span></span>

- <span data-ttu-id="182af-119">评价我的呼叫显示百分比 - 10%</span><span class="sxs-lookup"><span data-stu-id="182af-119">Rate My Call Display Percentage - 10%</span></span>

- <span data-ttu-id="182af-120">评价我的呼叫允许自定义用户反馈 - 已禁用</span><span class="sxs-lookup"><span data-stu-id="182af-120">Rate My Call Allow Custom User Feedback - disabled</span></span>

<span data-ttu-id="182af-121">虽然无需任何操作来启用基本功能，但如果您需要自定义反馈，则需要单独启用它。</span><span class="sxs-lookup"><span data-stu-id="182af-121">There is no action required to enable the base feature, however but if you want custom feedback you will need to enable it separately.</span></span> <span data-ttu-id="182af-122">以下 Windows PowerShell cmdlet 是启用自定义最终用户反馈以及将间隔从 10% 更改到 80% 的示例。</span><span class="sxs-lookup"><span data-stu-id="182af-122">The following Windows PowerShell cmdlet is an example of enabling custom end user feedback and changing the interval from 10% to 80%.</span></span>

```PowerShell
Set-CSClientPolicy -Identity <PolicyIdentity> -RateMyCallDisplayPercentage 80 -RateMyCallAllowCustomUserFeedback $true 
```

## <a name="accessing-rate-my-call-data"></a><span data-ttu-id="182af-123">访问"评价我的呼叫数据"</span><span class="sxs-lookup"><span data-stu-id="182af-123">Accessing Rate My Call Data</span></span>

<span data-ttu-id="182af-124">来自用户的数据收集在监控数据库中的两个表中。</span><span class="sxs-lookup"><span data-stu-id="182af-124">Data from users is collected in two tables in the monitoring database.</span></span>

 <span data-ttu-id="182af-125">**[QoeMetrics]。[dbo]。[CallQualityFeedbackToken]** - 此表包含最终用户的令牌轮询结果。</span><span class="sxs-lookup"><span data-stu-id="182af-125">**[QoeMetrics].[dbo].[CallQualityFeedbackToken]** - this table contains results of token polling by end users.</span></span>

 <span data-ttu-id="182af-126">**[QoeMetrics]。[dbo]。[CallQualityFeedbackTokenDef]** - 此表包含令牌定义。</span><span class="sxs-lookup"><span data-stu-id="182af-126">**[QoeMetrics].[dbo].[CallQualityFeedbackTokenDef]** - this table contains token definitions.</span></span>

<span data-ttu-id="182af-127">令牌定义编码如下：</span><span class="sxs-lookup"><span data-stu-id="182af-127">Token definitions are coded as follows:</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="182af-128">1 </span><span class="sxs-lookup"><span data-stu-id="182af-128">1</span></span>  <br/> |<span data-ttu-id="182af-129">DistortedSpeech</span><span class="sxs-lookup"><span data-stu-id="182af-129">DistortedSpeech</span></span>  <br/> |
|<span data-ttu-id="182af-130">2 </span><span class="sxs-lookup"><span data-stu-id="182af-130">2</span></span>  <br/> | <span data-ttu-id="182af-131">ElectronicFeedback</span><span class="sxs-lookup"><span data-stu-id="182af-131">ElectronicFeedback</span></span> <br/> |
|<span data-ttu-id="182af-132">3 </span><span class="sxs-lookup"><span data-stu-id="182af-132">3</span></span>  <br/> | <span data-ttu-id="182af-133">BackgroundNoise</span><span class="sxs-lookup"><span data-stu-id="182af-133">BackgroundNoise</span></span> <br/> |
|<span data-ttu-id="182af-134">4 </span><span class="sxs-lookup"><span data-stu-id="182af-134">4</span></span>  <br/> |<span data-ttu-id="182af-135">MuffledSpeech</span><span class="sxs-lookup"><span data-stu-id="182af-135">MuffledSpeech</span></span>  <br/> |
|<span data-ttu-id="182af-136">5 </span><span class="sxs-lookup"><span data-stu-id="182af-136">5</span></span>  <br/> |<span data-ttu-id="182af-137">回声</span><span class="sxs-lookup"><span data-stu-id="182af-137">Echo</span></span>  <br/> |
|<span data-ttu-id="182af-138"> 21</span><span class="sxs-lookup"><span data-stu-id="182af-138">21</span></span>  <br/> | <span data-ttu-id="182af-139">FrozenVideo</span><span class="sxs-lookup"><span data-stu-id="182af-139">FrozenVideo</span></span> <br/> |
|<span data-ttu-id="182af-140">22</span><span class="sxs-lookup"><span data-stu-id="182af-140">22</span></span>  <br/> | <span data-ttu-id="182af-141">PixelatedVideo</span><span class="sxs-lookup"><span data-stu-id="182af-141">PixelatedVideo</span></span> <br/> |
|<span data-ttu-id="182af-142">23</span><span class="sxs-lookup"><span data-stu-id="182af-142">23</span></span>  <br/> | <span data-ttu-id="182af-143">BlurryImage</span><span class="sxs-lookup"><span data-stu-id="182af-143">BlurryImage</span></span> <br/> |
|<span data-ttu-id="182af-144">24</span><span class="sxs-lookup"><span data-stu-id="182af-144">24</span></span>  <br/> | <span data-ttu-id="182af-145">PoorColor</span><span class="sxs-lookup"><span data-stu-id="182af-145">PoorColor</span></span> <br/> |
|<span data-ttu-id="182af-146">25</span><span class="sxs-lookup"><span data-stu-id="182af-146">25</span></span>  <br/> | <span data-ttu-id="182af-147">DarkVideo</span><span class="sxs-lookup"><span data-stu-id="182af-147">DarkVideo</span></span> <br/> |
|<span data-ttu-id="182af-148">101</span><span class="sxs-lookup"><span data-stu-id="182af-148">101</span></span>  <br/> |<span data-ttu-id="182af-149">Audio_SilentLocal</span><span class="sxs-lookup"><span data-stu-id="182af-149">Audio_SilentLocal</span></span>  <br/> |
|<span data-ttu-id="182af-150">102</span><span class="sxs-lookup"><span data-stu-id="182af-150">102</span></span>  <br/> |<span data-ttu-id="182af-151">Audio_SilentRemote</span><span class="sxs-lookup"><span data-stu-id="182af-151">Audio_SilentRemote</span></span>  <br/> |
|<span data-ttu-id="182af-152">103</span><span class="sxs-lookup"><span data-stu-id="182af-152">103</span></span>  <br/> |<span data-ttu-id="182af-153">Audio_Echo</span><span class="sxs-lookup"><span data-stu-id="182af-153">Audio_Echo</span></span>  <br/> |
|<span data-ttu-id="182af-154">104</span><span class="sxs-lookup"><span data-stu-id="182af-154">104</span></span>  <br/> |<span data-ttu-id="182af-155">Audio_BackgroundNoise</span><span class="sxs-lookup"><span data-stu-id="182af-155">Audio_BackgroundNoise</span></span>  <br/> |
|<span data-ttu-id="182af-156">105</span><span class="sxs-lookup"><span data-stu-id="182af-156">105</span></span>  <br/> |<span data-ttu-id="182af-157">Audio_LowSound</span><span class="sxs-lookup"><span data-stu-id="182af-157">Audio_LowSound</span></span>  <br/> |
|<span data-ttu-id="182af-158">106</span><span class="sxs-lookup"><span data-stu-id="182af-158">106</span></span>  <br/> |<span data-ttu-id="182af-159">Audio_Dropped</span><span class="sxs-lookup"><span data-stu-id="182af-159">Audio_Dropped</span></span>  <br/> |
|<span data-ttu-id="182af-160">107</span><span class="sxs-lookup"><span data-stu-id="182af-160">107</span></span>  <br/> |<span data-ttu-id="182af-161">Audio_DistortedSpeech</span><span class="sxs-lookup"><span data-stu-id="182af-161">Audio_DistortedSpeech</span></span>  <br/> |
|<span data-ttu-id="182af-162">108</span><span class="sxs-lookup"><span data-stu-id="182af-162">108</span></span>  <br/> |<span data-ttu-id="182af-163">Audio_Interrupted</span><span class="sxs-lookup"><span data-stu-id="182af-163">Audio_Interrupted</span></span>  <br/> |
|<span data-ttu-id="182af-164">109</span><span class="sxs-lookup"><span data-stu-id="182af-164">109</span></span>  <br/> |<span data-ttu-id="182af-165">Audio_Other</span><span class="sxs-lookup"><span data-stu-id="182af-165">Audio_Other</span></span>  <br/> |
|<span data-ttu-id="182af-166">201</span><span class="sxs-lookup"><span data-stu-id="182af-166">201</span></span>  <br/> |<span data-ttu-id="182af-167">Video_NoLocalVideo</span><span class="sxs-lookup"><span data-stu-id="182af-167">Video_NoLocalVideo</span></span>  <br/> |
|<span data-ttu-id="182af-168">202</span><span class="sxs-lookup"><span data-stu-id="182af-168">202</span></span>  <br/> |<span data-ttu-id="182af-169">Video_NoRemoteVideo</span><span class="sxs-lookup"><span data-stu-id="182af-169">Video_NoRemoteVideo</span></span>  <br/> |
|<span data-ttu-id="182af-170">203</span><span class="sxs-lookup"><span data-stu-id="182af-170">203</span></span>  <br/> |<span data-ttu-id="182af-171">Video_LowQuality</span><span class="sxs-lookup"><span data-stu-id="182af-171">Video_LowQuality</span></span>  <br/> |
|<span data-ttu-id="182af-172">204</span><span class="sxs-lookup"><span data-stu-id="182af-172">204</span></span>  <br/> |<span data-ttu-id="182af-173">Video_FrozenVideo</span><span class="sxs-lookup"><span data-stu-id="182af-173">Video_FrozenVideo</span></span>  <br/> |
|<span data-ttu-id="182af-174">205</span><span class="sxs-lookup"><span data-stu-id="182af-174">205</span></span>  <br/> |<span data-ttu-id="182af-175">Video_StoppedUnexpectedly</span><span class="sxs-lookup"><span data-stu-id="182af-175">Video_StoppedUnexpectedly</span></span>  <br/> |
|<span data-ttu-id="182af-176">206</span><span class="sxs-lookup"><span data-stu-id="182af-176">206</span></span>  <br/> |<span data-ttu-id="182af-177">Video_DarkVideo</span><span class="sxs-lookup"><span data-stu-id="182af-177">Video_DarkVideo</span></span>  <br/> |
|<span data-ttu-id="182af-178">207</span><span class="sxs-lookup"><span data-stu-id="182af-178">207</span></span>  <br/> |<span data-ttu-id="182af-179">Video_NoAudioSync</span><span class="sxs-lookup"><span data-stu-id="182af-179">Video_NoAudioSync</span></span>  <br/> |
|<span data-ttu-id="182af-180">208</span><span class="sxs-lookup"><span data-stu-id="182af-180">208</span></span>  <br/> |<span data-ttu-id="182af-181">Video_Other</span><span class="sxs-lookup"><span data-stu-id="182af-181">Video_Other</span></span>  <br/> |
|<span data-ttu-id="182af-182">301</span><span class="sxs-lookup"><span data-stu-id="182af-182">301</span></span>  <br/> |<span data-ttu-id="182af-183">Pstn_DialPad</span><span class="sxs-lookup"><span data-stu-id="182af-183">Pstn_DialPad</span></span>  <br/> |
|<span data-ttu-id="182af-184">401</span><span class="sxs-lookup"><span data-stu-id="182af-184">401</span></span>  <br/> |<span data-ttu-id="182af-185">SS_NoContentLocal</span><span class="sxs-lookup"><span data-stu-id="182af-185">SS_NoContentLocal</span></span>  <br/> |
|<span data-ttu-id="182af-186">402</span><span class="sxs-lookup"><span data-stu-id="182af-186">402</span></span>  <br/> |<span data-ttu-id="182af-187">SS_NoContentRemote</span><span class="sxs-lookup"><span data-stu-id="182af-187">SS_NoContentRemote</span></span>  <br/> |
|<span data-ttu-id="182af-188">403</span><span class="sxs-lookup"><span data-stu-id="182af-188">403</span></span>  <br/> |<span data-ttu-id="182af-189">SS_CantPresent</span><span class="sxs-lookup"><span data-stu-id="182af-189">SS_CantPresent</span></span>  <br/> |
|<span data-ttu-id="182af-190">404</span><span class="sxs-lookup"><span data-stu-id="182af-190">404</span></span>  <br/> |<span data-ttu-id="182af-191">SS_LowQuality</span><span class="sxs-lookup"><span data-stu-id="182af-191">SS_LowQuality</span></span>  <br/> |
|<span data-ttu-id="182af-192">405</span><span class="sxs-lookup"><span data-stu-id="182af-192">405</span></span>  <br/> |<span data-ttu-id="182af-193">SS_Freezing</span><span class="sxs-lookup"><span data-stu-id="182af-193">SS_Freezing</span></span>  <br/> |
|<span data-ttu-id="182af-194">406</span><span class="sxs-lookup"><span data-stu-id="182af-194">406</span></span>  <br/> |<span data-ttu-id="182af-195">SS_StoppedUnexpectedly</span><span class="sxs-lookup"><span data-stu-id="182af-195">SS_StoppedUnexpectedly</span></span>  <br/> |
|<span data-ttu-id="182af-196">407</span><span class="sxs-lookup"><span data-stu-id="182af-196">407</span></span>  <br/> |<span data-ttu-id="182af-197">SS_LargeDelay</span><span class="sxs-lookup"><span data-stu-id="182af-197">SS_LargeDelay</span></span>  <br/> |
|<span data-ttu-id="182af-198">408</span><span class="sxs-lookup"><span data-stu-id="182af-198">408</span></span>  <br/> |<span data-ttu-id="182af-199">SS_Other</span><span class="sxs-lookup"><span data-stu-id="182af-199">SS_Other</span></span>  <br/> |
|<span data-ttu-id="182af-200">501</span><span class="sxs-lookup"><span data-stu-id="182af-200">501</span></span>  <br/> |<span data-ttu-id="182af-201">Reliabilty_Join</span><span class="sxs-lookup"><span data-stu-id="182af-201">Reliabilty_Join</span></span>  <br/> |
|<span data-ttu-id="182af-202">502</span><span class="sxs-lookup"><span data-stu-id="182af-202">502</span></span>  <br/> |<span data-ttu-id="182af-203">Reliabilty_Invite</span><span class="sxs-lookup"><span data-stu-id="182af-203">Reliabilty_Invite</span></span>  <br/> |

 <span data-ttu-id="182af-204">**[QoeMetrics]。[dbo]。[CallQualityFeedback]** 此表包含"星形"投票的轮询结果和客户反馈（如果已启用）。</span><span class="sxs-lookup"><span data-stu-id="182af-204">**[QoeMetrics].[dbo].[CallQualityFeedback]** This table contains polling results from "Star" voting and customer feedback if enabled.</span></span>

<span data-ttu-id="182af-205">可以通过使用 **\* [Table.Name]** 查询中的选择或通过使用 Management Studio Microsoft SQL Server来调用表中的数据。</span><span class="sxs-lookup"><span data-stu-id="182af-205">Data from tables can be called by using a **select \* from [Table.Name]** query or by using Microsoft SQL Server Management Studio.</span></span>

<span data-ttu-id="182af-206">可以使用SQL查询：</span><span class="sxs-lookup"><span data-stu-id="182af-206">The following SQL queries can be used:</span></span>

 <span data-ttu-id="182af-207">**音频**</span><span class="sxs-lookup"><span data-stu-id="182af-207">**Audio**</span></span>

```SQL
SELECT
        s.ConferenceDateTime
        ,Caller.URI as Caller
        ,CallerCqf.FeedbackText 
        ,CallerCqf.Rating
        ,CallerCqfTokenDef.TokenDescription 
        ,CallerCqfToken.TokenValue
    FROM [Session] s WITH (NOLOCK)
        INNER JOIN [MediaLine] AS m WITH (NOLOCK) ON 
            m.ConferenceDateTime = s.ConferenceDateTime
            AND m.SessionSeq = s.SessionSeq                        
        INNER JOIN [AudioStream] AS a WITH (NOLOCK) ON -- only look at Audio related feedback
            a.MediaLineLabel = m.MediaLineLabel    
            and a.ConferenceDateTime = m.ConferenceDateTime 
            and a.SessionSeq = m.SessionSeq
            and a.SenderIsCallerPAI = 1                
        INNER JOIN [CallQualityFeedback] AS CallerCqf WITH (NOLOCK) ON
            CallerCqf.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqf.SessionSeq = s.SessionSeq 
        INNER JOIN [CallQualityFeedbackToken] AS CallerCqfToken WITH (NOLOCK) ON
            CallerCqfToken.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqfToken.SessionSeq = s.SessionSeq
            and
            CallerCqfToken.FromURI = CallerCqf.FromURI
        INNER JOIN [CallQualityFeedbackTokenDef] AS CallerCqfTokenDef WITH (NOLOCK) ON
            CallerCqfTokenDef.TokenId = CallerCqfToken.TokenId
            and
            (CallerCqfToken.TokenId < 20 or (CallerCqfToken.TokenId > 100 and CallerCqfToken.TokenId < 200)) -- only look at Audio related feedback
        INNER JOIN [User] AS Caller WITH (NOLOCK) ON
            Caller.UserKey = CallerCqf.FromURI
```

 <span data-ttu-id="182af-208">**Video**</span><span class="sxs-lookup"><span data-stu-id="182af-208">**Video**</span></span>

```SQL
SELECT
        s.ConferenceDateTime
        ,Caller.URI as Caller
        ,CallerCqf.FeedbackText 
        ,CallerCqf.Rating
        ,CallerCqfTokenDef.TokenDescription 
        ,CallerCqfToken.TokenValue
    FROM [Session] s WITH (NOLOCK)
        INNER JOIN [MediaLine] AS m WITH (NOLOCK) ON 
            m.ConferenceDateTime = s.ConferenceDateTime
            AND m.SessionSeq = s.SessionSeq                        
        INNER JOIN [VideoStream] AS v WITH (NOLOCK) ON -- only look at Video related feedback
            v.MediaLineLabel = m.MediaLineLabel    
            and v.ConferenceDateTime = m.ConferenceDateTime 
            and v.SessionSeq = m.SessionSeq
            and v.SenderIsCallerPAI = 1                
        INNER JOIN [CallQualityFeedback] AS CallerCqf WITH (NOLOCK) ON
            CallerCqf.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqf.SessionSeq = s.SessionSeq 
        INNER JOIN [CallQualityFeedbackToken] AS CallerCqfToken WITH (NOLOCK) ON
            CallerCqfToken.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqfToken.SessionSeq = s.SessionSeq
            and
            CallerCqfToken.FromURI = CallerCqf.FromURI
        INNER JOIN [CallQualityFeedbackTokenDef] AS CallerCqfTokenDef WITH (NOLOCK) ON
            CallerCqfTokenDef.TokenId = CallerCqfToken.TokenId
            and
           ((CallerCqfToken.TokenId > 20 and CallerCqfToken.TokenId < 100) or (CallerCqfToken.TokenId > 200 and CallerCqfToken.TokenId < 300)) -- only look at Video related feedback
        INNER JOIN [User] AS Caller WITH (NOLOCK) ON
            Caller.UserKey = CallerCqf.FromURI
```

## <a name="updating-token-definitions"></a><span data-ttu-id="182af-209">更新令牌定义</span><span class="sxs-lookup"><span data-stu-id="182af-209">Updating Token Definitions</span></span>

<span data-ttu-id="182af-210">最新的 Skype for Business 客户端报告 (100) 中可能不存在的新问题令牌 \> ID[QoeMetrics]。[dbo]。[CallQualityFeedbackTokenDef] 表。</span><span class="sxs-lookup"><span data-stu-id="182af-210">The latest Skype for Business clients report new problem token IDs (\> 100) that may not be present in your [QoeMetrics].[dbo].[CallQualityFeedbackTokenDef] table.</span></span> <span data-ttu-id="182af-211">若要使用最新的令牌定义更新数据库表，可以使用 SQL Management Studio 在监控Microsoft SQL Server运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="182af-211">To update the database table with the latest token definitions, the below SQL command can be run on the monitoring database using Microsoft SQL Server Management Studio.</span></span> <span data-ttu-id="182af-212">此命令将替换 [QoeMetrics] 中的所有条目。[dbo]。[CallQualityFeedbackTokenDef] 表。</span><span class="sxs-lookup"><span data-stu-id="182af-212">This command will replace all entries in the [QoeMetrics].[dbo].[CallQualityFeedbackTokenDef] table.</span></span>

```SQL
DELETE FROM [CallQualityFeedbackTokenDef];
INSERT INTO [CallQualityFeedbackTokenDef] (TokenId, TokenDescription) VALUES
    (1,   N'DistortedSpeech'),
    (2,   N'ElectronicFeedback'),
    (3,   N'BackgroundNoise'),
    (4,   N'MuffledSpeech'),
    (5,   N'Echo'),
    (21,  N'FrozenVideo'),
    (22,  N'PixelatedVideo'),
    (23,  N'BlurryImage'),
    (24,  N'PoorColor'),
    (25,  N'DarkVideo'),
    (101, N'Audio_SilentLocal'),
    (102, N'Audio_SilentRemote'),
    (103, N'Audio_Echo'),
    (104, N'Audio_BackgroundNoise'),
    (105, N'Audio_LowSound'),
    (106, N'Audio_Dropped'),
    (107, N'Audio_DistortedSpeech'),
    (108, N'Audio_Interrupted'),
    (109, N'Audio_Other'),
    (201, N'Video_NoLocalVideo'),
    (202, N'Video_NoRemoteVideo'),
    (203, N'Video_LowQuality'),
    (204, N'Video_FrozenVideo'),
    (205, N'Video_StoppedUnexpectedly'),
    (206, N'Video_DarkVideo'),
    (207, N'Video_NoAudioSync'),
    (208, N'Video_Other'),
    (301, N'Pstn_DialPad'),
    (401, N'SS_NoContentLocal'),
    (402, N'SS_NoContentRemote'),
    (403, N'SS_CantPresent'),
    (404, N'SS_LowQuality'),
    (405, N'SS_Freezing'),
    (406, N'SS_StoppedUnexpectedly'),
    (407, N'SS_LargeDelay'),
    (408, N'SS_Other'),
    (501, N'Reliabilty_Join'),
    (502, N'Reliabilty_Invite');
```


