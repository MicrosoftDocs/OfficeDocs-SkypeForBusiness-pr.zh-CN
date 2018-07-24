---
title: 为业务服务器中 Skype 评价我的呼叫
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c4e0c905-33a1-49d8-9276-1b338f94d085
description: 摘要： 了解业务服务器的 Skype 中的速率我的呼叫功能。
ms.openlocfilehash: 737d6a71f6880139d558d601a14d8f76c61d80f2
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20989061"
---
# <a name="rate-my-call-in-skype-for-business-server"></a><span data-ttu-id="2ae55-103">为业务服务器中 Skype 评价我的呼叫</span><span class="sxs-lookup"><span data-stu-id="2ae55-103">Rate my Call in Skype for Business Server</span></span>
 
<span data-ttu-id="2ae55-104">**摘要：** 了解业务服务器 Skype 中的速率我的呼叫功能。</span><span class="sxs-lookup"><span data-stu-id="2ae55-104">**Summary:** Learn about the Rate My Call feature in Skype for Business Server.</span></span>
  
<span data-ttu-id="2ae55-105">速率我呼叫已 Skype 业务 2015年和 2016年提供一种反馈获得最终用户的企业版的 Windows 上的客户端中的新功能。</span><span class="sxs-lookup"><span data-stu-id="2ae55-105">Rate My Call was a new feature in Skype for Business 2015 and 2016 clients on Windows that provides enterprises a way to get feedback from their end-users.</span></span>
  
<span data-ttu-id="2ae55-106">速率我的呼叫窗口提供"星"评级系统和用于音频和视频呼叫的预定义的令牌。</span><span class="sxs-lookup"><span data-stu-id="2ae55-106">The Rate My Call window offers a "star" rating system and predefined tokens for audio and video calls.</span></span> <span data-ttu-id="2ae55-107">此外，管理员可以使自定义字段提供反馈。</span><span class="sxs-lookup"><span data-stu-id="2ae55-107">In addition, administrators can enable a custom field to provide feedback.</span></span>
  
<span data-ttu-id="2ae55-108">收集的“评价我的呼叫”数据当前不包含在现有监控报告中，但其具有单独的监控报告。</span><span class="sxs-lookup"><span data-stu-id="2ae55-108">Collected Rate My Call data is not currently included in any existing monitoring report, but it has a separate monitoring report.</span></span> <span data-ttu-id="2ae55-109">可通过运行 SQL 查询的 SQL 表中收集数据。</span><span class="sxs-lookup"><span data-stu-id="2ae55-109">Data is collected in SQL tables that can be accessed by running SQL queries.</span></span>
  
## <a name="rate-my-call-prerequisites"></a><span data-ttu-id="2ae55-110">“评价我的呼叫”先决条件</span><span class="sxs-lookup"><span data-stu-id="2ae55-110">Rate my Call Prerequisites</span></span>

<span data-ttu-id="2ae55-111">您 Skype 业务服务器部署中的用户可以访问速率我呼叫功能之前，必须部署以下组件组，并将其配置中：</span><span class="sxs-lookup"><span data-stu-id="2ae55-111">Before the users in your Skype for Business Server deployment can access Rate My Call functionality, the following set of components must be deployed and configured:</span></span>
  
-  <span data-ttu-id="2ae55-112">您必须具有 Skype 业务服务器安装 （9160 或更高版本）。</span><span class="sxs-lookup"><span data-stu-id="2ae55-112">You must have Skype for Business Server installed (version 9160 or higher).</span></span>
    
- <span data-ttu-id="2ae55-113">让您安装，并更新到 for Business 的 Skype 的最新版本，还可以询问他们使用的业务 UI Skype 的用户。</span><span class="sxs-lookup"><span data-stu-id="2ae55-113">Have your users install and update to the latest version of Skype for Business and also ask them to use the Skype for Business UI.</span></span>
    
- <span data-ttu-id="2ae55-114">用户必须驻留在业务 Server 前端池的 Skype。</span><span class="sxs-lookup"><span data-stu-id="2ae55-114">Users must be homed on the Skype for Business Server Front End pool.</span></span>
    
- <span data-ttu-id="2ae55-115">您必须具有业务服务器监控数据库部署和关联到您的业务服务器池的 Skype Skype。</span><span class="sxs-lookup"><span data-stu-id="2ae55-115">You must have a Skype for Business Server monitoring database deployed and associated to your Skype for Business Server pools.</span></span>
    
- <span data-ttu-id="2ae55-116">我们建议部署呼叫质量仪表板 (CQD)。</span><span class="sxs-lookup"><span data-stu-id="2ae55-116">We recommend deploying Call Quality Dashboard (CQD).</span></span>
    
## <a name="configure-rate-my-call"></a><span data-ttu-id="2ae55-117">配置“评价我的呼叫”</span><span class="sxs-lookup"><span data-stu-id="2ae55-117">Configure Rate my Call</span></span>

<span data-ttu-id="2ae55-118">使用以下设置的客户端策略中的默认情况下启用速率我的呼叫功能：</span><span class="sxs-lookup"><span data-stu-id="2ae55-118">The Rate My Call feature is enabled by default in the Client policy with the following settings:</span></span>
  
- <span data-ttu-id="2ae55-119">评价我呼叫显示百分比-10%</span><span class="sxs-lookup"><span data-stu-id="2ae55-119">Rate My Call Display Percentage - 10%</span></span>
    
- <span data-ttu-id="2ae55-120">评价我呼叫允许自定义用户反馈-禁用</span><span class="sxs-lookup"><span data-stu-id="2ae55-120">Rate My Call Allow Custom User Feedback - disabled</span></span>
    
<span data-ttu-id="2ae55-121">若要启用基本功能，但是需执行任何操作，但如果您希望自定义的反馈，您需要单独启用。</span><span class="sxs-lookup"><span data-stu-id="2ae55-121">There is no action required to enable the base feature, however but if you want custom feedback you will need to enable it separately.</span></span> <span data-ttu-id="2ae55-122">以下 Windows PowerShell cmdlet 启用自定义最终用户反馈和更改的时间间隔为 10%为 80%的示例。</span><span class="sxs-lookup"><span data-stu-id="2ae55-122">The following Windows PowerShell cmdlet is an example of enabling custom end user feedback and changing the interval from 10% to 80%.</span></span>
  
```
Set-CSClientPolicy -Identity <PolicyIdentity> -RateMyCallDisplayPercentage 80 - RateMyCallAllowCustomUserFeedback $true 
```

## <a name="accessing-rate-my-call-data"></a><span data-ttu-id="2ae55-123">访问“评价我的呼叫”数据</span><span class="sxs-lookup"><span data-stu-id="2ae55-123">Accessing Rate My Call Data</span></span>

<span data-ttu-id="2ae55-124">来自用户的数据收集监控数据库中的两个表中。</span><span class="sxs-lookup"><span data-stu-id="2ae55-124">Data from users is collected in two tables in the monitoring database.</span></span>
  
 <span data-ttu-id="2ae55-125">**[QoeMetrics]。[dbo]。[CallQualityFeedbackToken]**-此表包含的最终用户的令牌轮询结果。</span><span class="sxs-lookup"><span data-stu-id="2ae55-125">**[QoeMetrics].[dbo].[CallQualityFeedbackToken]** - this table contains results of token polling by end users.</span></span>
  
 <span data-ttu-id="2ae55-126">**[QoeMetrics]。[dbo]。[CallQualityFeedbackTokenDef]**-此表包含令牌的定义。</span><span class="sxs-lookup"><span data-stu-id="2ae55-126">**[QoeMetrics].[dbo].[CallQualityFeedbackTokenDef]** - this table contains token definitions.</span></span>
  
<span data-ttu-id="2ae55-127">令牌定义采用了如下编码：</span><span class="sxs-lookup"><span data-stu-id="2ae55-127">Token definitions are coded as follows:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="2ae55-128">1</span><span class="sxs-lookup"><span data-stu-id="2ae55-128">1</span></span>  <br/> |<span data-ttu-id="2ae55-129">DistortedSpeech</span><span class="sxs-lookup"><span data-stu-id="2ae55-129">DistortedSpeech</span></span>  <br/> |
|<span data-ttu-id="2ae55-130">2</span><span class="sxs-lookup"><span data-stu-id="2ae55-130">2</span></span>  <br/> | <span data-ttu-id="2ae55-131">ElectronicFeedback</span><span class="sxs-lookup"><span data-stu-id="2ae55-131">ElectronicFeedback</span></span> <br/> |
|<span data-ttu-id="2ae55-132">3</span><span class="sxs-lookup"><span data-stu-id="2ae55-132">3</span></span>  <br/> | <span data-ttu-id="2ae55-133">BackgroundNoise</span><span class="sxs-lookup"><span data-stu-id="2ae55-133">BackgroundNoise</span></span> <br/> |
|<span data-ttu-id="2ae55-134">4</span><span class="sxs-lookup"><span data-stu-id="2ae55-134">4</span></span>  <br/> |<span data-ttu-id="2ae55-135">MuffledSpeech</span><span class="sxs-lookup"><span data-stu-id="2ae55-135">MuffledSpeech</span></span>  <br/> |
|<span data-ttu-id="2ae55-136">5</span><span class="sxs-lookup"><span data-stu-id="2ae55-136">5</span></span>  <br/> |<span data-ttu-id="2ae55-137">回声</span><span class="sxs-lookup"><span data-stu-id="2ae55-137">Echo</span></span>  <br/> |
|<span data-ttu-id="2ae55-138">21</span><span class="sxs-lookup"><span data-stu-id="2ae55-138">21</span></span>  <br/> | <span data-ttu-id="2ae55-139">FrozenVideo</span><span class="sxs-lookup"><span data-stu-id="2ae55-139">FrozenVideo</span></span> <br/> |
|<span data-ttu-id="2ae55-140">22</span><span class="sxs-lookup"><span data-stu-id="2ae55-140">22</span></span>  <br/> | <span data-ttu-id="2ae55-141">PixelatedVideo</span><span class="sxs-lookup"><span data-stu-id="2ae55-141">PixelatedVideo</span></span> <br/> |
|<span data-ttu-id="2ae55-142">23</span><span class="sxs-lookup"><span data-stu-id="2ae55-142">23</span></span>  <br/> | <span data-ttu-id="2ae55-143">BlurryImage</span><span class="sxs-lookup"><span data-stu-id="2ae55-143">BlurryImage</span></span> <br/> |
|<span data-ttu-id="2ae55-144">24</span><span class="sxs-lookup"><span data-stu-id="2ae55-144">24</span></span>  <br/> | <span data-ttu-id="2ae55-145">PoorColor</span><span class="sxs-lookup"><span data-stu-id="2ae55-145">PoorColor</span></span> <br/> |
|<span data-ttu-id="2ae55-146">25</span><span class="sxs-lookup"><span data-stu-id="2ae55-146">25</span></span>  <br/> | <span data-ttu-id="2ae55-147">DarkVideo</span><span class="sxs-lookup"><span data-stu-id="2ae55-147">DarkVideo</span></span> <br/> |
|<span data-ttu-id="2ae55-148">101</span><span class="sxs-lookup"><span data-stu-id="2ae55-148">101</span></span>  <br/> |<span data-ttu-id="2ae55-149">Audio_SilentLocal</span><span class="sxs-lookup"><span data-stu-id="2ae55-149">Audio_SilentLocal</span></span>  <br/> |
|<span data-ttu-id="2ae55-150">102</span><span class="sxs-lookup"><span data-stu-id="2ae55-150">102</span></span>  <br/> |<span data-ttu-id="2ae55-151">Audio_SilentRemote</span><span class="sxs-lookup"><span data-stu-id="2ae55-151">Audio_SilentRemote</span></span>  <br/> |
|<span data-ttu-id="2ae55-152">103</span><span class="sxs-lookup"><span data-stu-id="2ae55-152">103</span></span>  <br/> |<span data-ttu-id="2ae55-153">Audio_Echo</span><span class="sxs-lookup"><span data-stu-id="2ae55-153">Audio_Echo</span></span>  <br/> |
|<span data-ttu-id="2ae55-154">104</span><span class="sxs-lookup"><span data-stu-id="2ae55-154">104</span></span>  <br/> |<span data-ttu-id="2ae55-155">Audio_BackgroundNoise</span><span class="sxs-lookup"><span data-stu-id="2ae55-155">Audio_BackgroundNoise</span></span>  <br/> |
|<span data-ttu-id="2ae55-156">105</span><span class="sxs-lookup"><span data-stu-id="2ae55-156">105</span></span>  <br/> |<span data-ttu-id="2ae55-157">Audio_LowSound</span><span class="sxs-lookup"><span data-stu-id="2ae55-157">Audio_LowSound</span></span>  <br/> |
|<span data-ttu-id="2ae55-158">106</span><span class="sxs-lookup"><span data-stu-id="2ae55-158">106</span></span>  <br/> |<span data-ttu-id="2ae55-159">Audio_Dropped</span><span class="sxs-lookup"><span data-stu-id="2ae55-159">Audio_Dropped</span></span>  <br/> |
|<span data-ttu-id="2ae55-160">107</span><span class="sxs-lookup"><span data-stu-id="2ae55-160">107</span></span>  <br/> |<span data-ttu-id="2ae55-161">Audio_DistortedSpeech</span><span class="sxs-lookup"><span data-stu-id="2ae55-161">Audio_DistortedSpeech</span></span>  <br/> |
|<span data-ttu-id="2ae55-162">108</span><span class="sxs-lookup"><span data-stu-id="2ae55-162">108</span></span>  <br/> |<span data-ttu-id="2ae55-163">Audio_Interrupted</span><span class="sxs-lookup"><span data-stu-id="2ae55-163">Audio_Interrupted</span></span>  <br/> |
|<span data-ttu-id="2ae55-164">109</span><span class="sxs-lookup"><span data-stu-id="2ae55-164">109</span></span>  <br/> |<span data-ttu-id="2ae55-165">Audio_Other</span><span class="sxs-lookup"><span data-stu-id="2ae55-165">Audio_Other</span></span>  <br/> |
|<span data-ttu-id="2ae55-166">201</span><span class="sxs-lookup"><span data-stu-id="2ae55-166">201</span></span>  <br/> |<span data-ttu-id="2ae55-167">Video_NoLocalVideo</span><span class="sxs-lookup"><span data-stu-id="2ae55-167">Video_NoLocalVideo</span></span>  <br/> |
|<span data-ttu-id="2ae55-168">202</span><span class="sxs-lookup"><span data-stu-id="2ae55-168">202</span></span>  <br/> |<span data-ttu-id="2ae55-169">Video_NoRemoteVideo</span><span class="sxs-lookup"><span data-stu-id="2ae55-169">Video_NoRemoteVideo</span></span>  <br/> |
|<span data-ttu-id="2ae55-170">203</span><span class="sxs-lookup"><span data-stu-id="2ae55-170">203</span></span>  <br/> |<span data-ttu-id="2ae55-171">Video_LowQuality</span><span class="sxs-lookup"><span data-stu-id="2ae55-171">Video_LowQuality</span></span>  <br/> |
|<span data-ttu-id="2ae55-172">204</span><span class="sxs-lookup"><span data-stu-id="2ae55-172">204</span></span>  <br/> |<span data-ttu-id="2ae55-173">Video_FrozenVideo</span><span class="sxs-lookup"><span data-stu-id="2ae55-173">Video_FrozenVideo</span></span>  <br/> |
|<span data-ttu-id="2ae55-174">205</span><span class="sxs-lookup"><span data-stu-id="2ae55-174">205</span></span>  <br/> |<span data-ttu-id="2ae55-175">Video_StoppedUnexpectedly</span><span class="sxs-lookup"><span data-stu-id="2ae55-175">Video_StoppedUnexpectedly</span></span>  <br/> |
|<span data-ttu-id="2ae55-176">206</span><span class="sxs-lookup"><span data-stu-id="2ae55-176">206</span></span>  <br/> |<span data-ttu-id="2ae55-177">Video_DarkVideo</span><span class="sxs-lookup"><span data-stu-id="2ae55-177">Video_DarkVideo</span></span>  <br/> |
|<span data-ttu-id="2ae55-178">207</span><span class="sxs-lookup"><span data-stu-id="2ae55-178">207</span></span>  <br/> |<span data-ttu-id="2ae55-179">Video_NoAudioSync</span><span class="sxs-lookup"><span data-stu-id="2ae55-179">Video_NoAudioSync</span></span>  <br/> |
|<span data-ttu-id="2ae55-180">208</span><span class="sxs-lookup"><span data-stu-id="2ae55-180">208</span></span>  <br/> |<span data-ttu-id="2ae55-181">Video_Other</span><span class="sxs-lookup"><span data-stu-id="2ae55-181">Video_Other</span></span>  <br/> |
|<span data-ttu-id="2ae55-182">301</span><span class="sxs-lookup"><span data-stu-id="2ae55-182">301</span></span>  <br/> |<span data-ttu-id="2ae55-183">Pstn_DialPad</span><span class="sxs-lookup"><span data-stu-id="2ae55-183">Pstn_DialPad</span></span>  <br/> |
|<span data-ttu-id="2ae55-184">401</span><span class="sxs-lookup"><span data-stu-id="2ae55-184">401</span></span>  <br/> |<span data-ttu-id="2ae55-185">SS_NoContentLocal</span><span class="sxs-lookup"><span data-stu-id="2ae55-185">SS_NoContentLocal</span></span>  <br/> |
|<span data-ttu-id="2ae55-186">402</span><span class="sxs-lookup"><span data-stu-id="2ae55-186">402</span></span>  <br/> |<span data-ttu-id="2ae55-187">SS_NoContentRemote</span><span class="sxs-lookup"><span data-stu-id="2ae55-187">SS_NoContentRemote</span></span>  <br/> |
|<span data-ttu-id="2ae55-188">403</span><span class="sxs-lookup"><span data-stu-id="2ae55-188">403</span></span>  <br/> |<span data-ttu-id="2ae55-189">SS_CantPresent</span><span class="sxs-lookup"><span data-stu-id="2ae55-189">SS_CantPresent</span></span>  <br/> |
|<span data-ttu-id="2ae55-190">404</span><span class="sxs-lookup"><span data-stu-id="2ae55-190">404</span></span>  <br/> |<span data-ttu-id="2ae55-191">SS_LowQuality</span><span class="sxs-lookup"><span data-stu-id="2ae55-191">SS_LowQuality</span></span>  <br/> |
|<span data-ttu-id="2ae55-192">405</span><span class="sxs-lookup"><span data-stu-id="2ae55-192">405</span></span>  <br/> |<span data-ttu-id="2ae55-193">SS_Freezing</span><span class="sxs-lookup"><span data-stu-id="2ae55-193">SS_Freezing</span></span>  <br/> |
|<span data-ttu-id="2ae55-194">406</span><span class="sxs-lookup"><span data-stu-id="2ae55-194">406</span></span>  <br/> |<span data-ttu-id="2ae55-195">SS_StoppedUnexpectedly</span><span class="sxs-lookup"><span data-stu-id="2ae55-195">SS_StoppedUnexpectedly</span></span>  <br/> |
|<span data-ttu-id="2ae55-196">407</span><span class="sxs-lookup"><span data-stu-id="2ae55-196">407</span></span>  <br/> |<span data-ttu-id="2ae55-197">SS_LargeDelay</span><span class="sxs-lookup"><span data-stu-id="2ae55-197">SS_LargeDelay</span></span>  <br/> |
|<span data-ttu-id="2ae55-198">408</span><span class="sxs-lookup"><span data-stu-id="2ae55-198">408</span></span>  <br/> |<span data-ttu-id="2ae55-199">SS_Other</span><span class="sxs-lookup"><span data-stu-id="2ae55-199">SS_Other</span></span>  <br/> |
|<span data-ttu-id="2ae55-200">501</span><span class="sxs-lookup"><span data-stu-id="2ae55-200">501</span></span>  <br/> |<span data-ttu-id="2ae55-201">Reliabilty_Join</span><span class="sxs-lookup"><span data-stu-id="2ae55-201">Reliabilty_Join</span></span>  <br/> |
|<span data-ttu-id="2ae55-202">502</span><span class="sxs-lookup"><span data-stu-id="2ae55-202">502</span></span>  <br/> |<span data-ttu-id="2ae55-203">Reliabilty_Invite</span><span class="sxs-lookup"><span data-stu-id="2ae55-203">Reliabilty_Invite</span></span>  <br/> |
   
 <span data-ttu-id="2ae55-204">**[QoeMetrics]。[dbo]。[CallQualityFeedback]** 如果启用，则此表包含从"Star"投票和客户反馈的投票结果。</span><span class="sxs-lookup"><span data-stu-id="2ae55-204">**[QoeMetrics].[dbo].[CallQualityFeedback]** This table contains polling results from "Star" voting and customer feedback if enabled.</span></span>
  
<span data-ttu-id="2ae55-205">可以通过调用表中的数据**选择\*从 [Table.Name]** 查询或使用 Microsoft SQL Server Management Studio。</span><span class="sxs-lookup"><span data-stu-id="2ae55-205">Data from tables can be called by using a **select \* from [Table.Name]** query or by using Microsoft SQL Server Management Studio.</span></span>
  
<span data-ttu-id="2ae55-206">可使用以下 SQL 查询：</span><span class="sxs-lookup"><span data-stu-id="2ae55-206">The following SQL queries can be used:</span></span>
  
 <span data-ttu-id="2ae55-207">**音频**</span><span class="sxs-lookup"><span data-stu-id="2ae55-207">**Audio**</span></span>
  
```
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

 <span data-ttu-id="2ae55-208">**视频**</span><span class="sxs-lookup"><span data-stu-id="2ae55-208">**Video**</span></span>
  
```
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

## <a name="updating-token-definitions"></a><span data-ttu-id="2ae55-209">更新令牌定义</span><span class="sxs-lookup"><span data-stu-id="2ae55-209">Updating Token Definitions</span></span>

<span data-ttu-id="2ae55-210">业务客户端的最新的 Skype 报告新问题令牌 Id (\> 100) 可能不存在您 [QoeMetrics] 中。[dbo]。[CallQualityFeedbackTokenDef] 表。</span><span class="sxs-lookup"><span data-stu-id="2ae55-210">The latest Skype for Business clients report new problem token IDs (\> 100) that may not be present in your [QoeMetrics].[dbo].[CallQualityFeedbackTokenDef] table.</span></span> <span data-ttu-id="2ae55-211">若要使用的最新的令牌定义，更新的数据库表下方 SQL 命令可以运行使用 Microsoft SQL Server Management Studio 的监控数据库。</span><span class="sxs-lookup"><span data-stu-id="2ae55-211">To update the database table with the latest token definitions, the below SQL command can be run on the monitoring database using Microsoft SQL Server Management Studio.</span></span> <span data-ttu-id="2ae55-212">此命令将替换 [QoeMetrics] 中的所有条目。[dbo]。[CallQualityFeedbackTokenDef] 表。</span><span class="sxs-lookup"><span data-stu-id="2ae55-212">This command will replace all entries in the [QoeMetrics].[dbo].[CallQualityFeedbackTokenDef] table.</span></span>
  
```
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


