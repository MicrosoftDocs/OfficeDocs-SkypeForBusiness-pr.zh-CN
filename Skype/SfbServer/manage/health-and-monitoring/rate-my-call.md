---
title: 在 Skype for Business Server 2015 中评价我的呼叫
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/13/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c4e0c905-33a1-49d8-9276-1b338f94d085
description: 摘要： 了解的业务服务器 2015年的 Skype 的速率我调用功能。
ms.openlocfilehash: 1e0088c563f38be59bda0fad10dbd367ea0646e9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="rate-my-call-in-skype-for-business-server-2015"></a><span data-ttu-id="509fe-103">在 Skype for Business Server 2015 中评价我的呼叫</span><span class="sxs-lookup"><span data-stu-id="509fe-103">Rate my Call in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="509fe-104">**摘要：**了解业务服务器 2015年的 Skype 的速率我调用功能。</span><span class="sxs-lookup"><span data-stu-id="509fe-104">**Summary:** Learn about the Rate My Call feature in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="509fe-105">速度我调用是 Skype 业务 2015年和 2016年上为企业提供从最终用户获得反馈的方法的 Windows 的客户端中的新功能。</span><span class="sxs-lookup"><span data-stu-id="509fe-105">Rate My Call is a new feature in Skype for Business 2015 and 2016 clients on Windows that provides enterprises a way to get feedback from their end-users.</span></span>
  
<span data-ttu-id="509fe-106">速度我调用窗口提供"星级"系统和音频和视频呼叫的预定义的标记。</span><span class="sxs-lookup"><span data-stu-id="509fe-106">The Rate My Call window offers a "star" rating system and predefined tokens for audio and video calls.</span></span> <span data-ttu-id="509fe-107">此外，管理员可以启用自定义字段来提供反馈。</span><span class="sxs-lookup"><span data-stu-id="509fe-107">In addition, administrators can enable a custom field to provide feedback.</span></span>
  
<span data-ttu-id="509fe-108">收集的“评价我的呼叫”数据当前不包含在现有监控报告中，但其具有单独的监控报告。</span><span class="sxs-lookup"><span data-stu-id="509fe-108">Collected Rate My Call data is not currently included in any existing monitoring report, but it has a separate monitoring report.</span></span> <span data-ttu-id="509fe-109">可以通过运行 SQL 查询的 SQL 表中收集数据。</span><span class="sxs-lookup"><span data-stu-id="509fe-109">Data is collected in SQL tables that can be accessed by running SQL queries.</span></span>
  
## <a name="rate-my-call-prerequisites"></a><span data-ttu-id="509fe-110">评价我呼叫系统必备组件</span><span class="sxs-lookup"><span data-stu-id="509fe-110">Rate my Call Prerequisites</span></span>

<span data-ttu-id="509fe-111">您 Skype 业务服务器部署中的用户可以访问率我呼叫功能之前，必须部署和配置以下组件组：</span><span class="sxs-lookup"><span data-stu-id="509fe-111">Before the users in your Skype for Business Server deployment can access Rate My Call functionality, the following set of components must be deployed and configured:</span></span>
  
-  <span data-ttu-id="509fe-112">您必须有 Skype 业务服务器安装 （9160 或更高版本）。</span><span class="sxs-lookup"><span data-stu-id="509fe-112">You must have Skype for Business Server installed (version 9160 or higher).</span></span>
    
- <span data-ttu-id="509fe-113">让您的用户安装并更新到最新版本的 Skype 业务中，还要求他们对业务用户界面使用 Skype。</span><span class="sxs-lookup"><span data-stu-id="509fe-113">Have your users install and update to the latest version of Skype for Business and also ask them to use the Skype for Business UI.</span></span>
    
- <span data-ttu-id="509fe-114">用户必须被驻留在业务前端服务器池 Skype 上。</span><span class="sxs-lookup"><span data-stu-id="509fe-114">Users must be homed on the Skype for Business Server Front End pool.</span></span>
    
- <span data-ttu-id="509fe-115">您必须有 Skype 的业务服务器监视数据库部署并与您 Skype 业务服务器池相关联。</span><span class="sxs-lookup"><span data-stu-id="509fe-115">You must have a Skype for Business Server monitoring database deployed and associated to your Skype for Business Server pools.</span></span>
    
- <span data-ttu-id="509fe-116">我们建议部署呼叫质量仪表板 (CQD)。</span><span class="sxs-lookup"><span data-stu-id="509fe-116">We recommend deploying Call Quality Dashboard (CQD).</span></span>
    
## <a name="configure-rate-my-call"></a><span data-ttu-id="509fe-117">配置率我调用</span><span class="sxs-lookup"><span data-stu-id="509fe-117">Configure Rate my Call</span></span>

<span data-ttu-id="509fe-118">默认情况下，具有以下设置的客户端策略中启用了率我调用功能：</span><span class="sxs-lookup"><span data-stu-id="509fe-118">The Rate My Call feature is enabled by default in the Client policy with the following settings:</span></span>
  
- <span data-ttu-id="509fe-119">评价我呼叫显示百分比-10%</span><span class="sxs-lookup"><span data-stu-id="509fe-119">Rate My Call Display Percentage - 10%</span></span>
    
- <span data-ttu-id="509fe-120">评价我调用允许自定义用户反馈-禁用</span><span class="sxs-lookup"><span data-stu-id="509fe-120">Rate My Call Allow Custom User Feedback - disabled</span></span>
    
<span data-ttu-id="509fe-121">启用基本的特征，但是所需的任何操作，但如果您希望自定义反馈您需要单独启用它。</span><span class="sxs-lookup"><span data-stu-id="509fe-121">There is no action required to enable the base feature, however but if you want custom feedback you will need to enable it separately.</span></span> <span data-ttu-id="509fe-122">下面的 Windows PowerShell cmdlet 是一种启用自定义最终用户反馈和更改的时间间隔从 10%到 80%。</span><span class="sxs-lookup"><span data-stu-id="509fe-122">The following Windows PowerShell cmdlet is an example of enabling custom end user feedback and changing the interval from 10% to 80%.</span></span>
  
```
Set-CSClientPolicy -Identity <PolicyIdentity> -RateMyCallDisplayPercentage 80 - RateMyCallAllowCustomUserFeedback $true 

```

## <a name="accessing-rate-my-call-data"></a><span data-ttu-id="509fe-123">我呼叫数据的访问速度</span><span class="sxs-lookup"><span data-stu-id="509fe-123">Accessing Rate My Call Data</span></span>

<span data-ttu-id="509fe-124">监视数据库中两个表中收集来自用户的数据。</span><span class="sxs-lookup"><span data-stu-id="509fe-124">Data from users is collected in two tables in the monitoring database.</span></span>
  
 <span data-ttu-id="509fe-125">**[QoeMetrics]。[dbo]。[CallQualityFeedbackToken]**-此表包含最终用户的令牌轮询的结果。</span><span class="sxs-lookup"><span data-stu-id="509fe-125">**[QoeMetrics].[dbo].[CallQualityFeedbackToken]** - this table contains results of token polling by end users.</span></span>
  
 <span data-ttu-id="509fe-126">**[QoeMetrics]。[dbo]。[CallQualityFeedbackTokenDef]**-此表包含标记的定义。</span><span class="sxs-lookup"><span data-stu-id="509fe-126">**[QoeMetrics].[dbo].[CallQualityFeedbackTokenDef]** - this table contains token definitions.</span></span>
  
<span data-ttu-id="509fe-127">标记定义经过编码，如下所示：</span><span class="sxs-lookup"><span data-stu-id="509fe-127">Token definitions are coded as follows:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="509fe-128">1</span><span class="sxs-lookup"><span data-stu-id="509fe-128">1</span></span>  <br/> |<span data-ttu-id="509fe-129">DistortedSpeech</span><span class="sxs-lookup"><span data-stu-id="509fe-129">DistortedSpeech</span></span>  <br/> |
|<span data-ttu-id="509fe-130">2</span><span class="sxs-lookup"><span data-stu-id="509fe-130">2</span></span>  <br/> | <span data-ttu-id="509fe-131">ElectronicFeedback</span><span class="sxs-lookup"><span data-stu-id="509fe-131">ElectronicFeedback</span></span> <br/> |
|<span data-ttu-id="509fe-132">3</span><span class="sxs-lookup"><span data-stu-id="509fe-132">3</span></span>  <br/> | <span data-ttu-id="509fe-133">BackgroundNoise</span><span class="sxs-lookup"><span data-stu-id="509fe-133">BackgroundNoise</span></span> <br/> |
|<span data-ttu-id="509fe-134">4</span><span class="sxs-lookup"><span data-stu-id="509fe-134">4</span></span>  <br/> |<span data-ttu-id="509fe-135">MuffledSpeech</span><span class="sxs-lookup"><span data-stu-id="509fe-135">MuffledSpeech</span></span>  <br/> |
|<span data-ttu-id="509fe-136">5</span><span class="sxs-lookup"><span data-stu-id="509fe-136">5</span></span>  <br/> |<span data-ttu-id="509fe-137">回声</span><span class="sxs-lookup"><span data-stu-id="509fe-137">Echo</span></span>  <br/> |
|<span data-ttu-id="509fe-138">21</span><span class="sxs-lookup"><span data-stu-id="509fe-138">21</span></span>  <br/> | <span data-ttu-id="509fe-139">FrozenVideo</span><span class="sxs-lookup"><span data-stu-id="509fe-139">FrozenVideo</span></span> <br/> |
|<span data-ttu-id="509fe-140">22</span><span class="sxs-lookup"><span data-stu-id="509fe-140">22</span></span>  <br/> | <span data-ttu-id="509fe-141">PixelatedVideo</span><span class="sxs-lookup"><span data-stu-id="509fe-141">PixelatedVideo</span></span> <br/> |
|<span data-ttu-id="509fe-142">23</span><span class="sxs-lookup"><span data-stu-id="509fe-142">23</span></span>  <br/> | <span data-ttu-id="509fe-143">BlurryImage</span><span class="sxs-lookup"><span data-stu-id="509fe-143">BlurryImage</span></span> <br/> |
|<span data-ttu-id="509fe-144">24</span><span class="sxs-lookup"><span data-stu-id="509fe-144">24</span></span>  <br/> | <span data-ttu-id="509fe-145">PoorColor</span><span class="sxs-lookup"><span data-stu-id="509fe-145">PoorColor</span></span> <br/> |
|<span data-ttu-id="509fe-146">25</span><span class="sxs-lookup"><span data-stu-id="509fe-146">25</span></span>  <br/> | <span data-ttu-id="509fe-147">DarkVideo</span><span class="sxs-lookup"><span data-stu-id="509fe-147">DarkVideo</span></span> <br/> |
|<span data-ttu-id="509fe-148">101</span><span class="sxs-lookup"><span data-stu-id="509fe-148">101</span></span>  <br/> |<span data-ttu-id="509fe-149">Audio_SilentLocal</span><span class="sxs-lookup"><span data-stu-id="509fe-149">Audio_SilentLocal</span></span>  <br/> |
|<span data-ttu-id="509fe-150">102</span><span class="sxs-lookup"><span data-stu-id="509fe-150">102</span></span>  <br/> |<span data-ttu-id="509fe-151">Audio_SilentRemote</span><span class="sxs-lookup"><span data-stu-id="509fe-151">Audio_SilentRemote</span></span>  <br/> |
|<span data-ttu-id="509fe-152">103</span><span class="sxs-lookup"><span data-stu-id="509fe-152">103</span></span>  <br/> |<span data-ttu-id="509fe-153">Audio_Echo</span><span class="sxs-lookup"><span data-stu-id="509fe-153">Audio_Echo</span></span>  <br/> |
|<span data-ttu-id="509fe-154">104</span><span class="sxs-lookup"><span data-stu-id="509fe-154">104</span></span>  <br/> |<span data-ttu-id="509fe-155">Audio_BackgroundNoise</span><span class="sxs-lookup"><span data-stu-id="509fe-155">Audio_BackgroundNoise</span></span>  <br/> |
|<span data-ttu-id="509fe-156">105</span><span class="sxs-lookup"><span data-stu-id="509fe-156">105</span></span>  <br/> |<span data-ttu-id="509fe-157">Audio_LowSound</span><span class="sxs-lookup"><span data-stu-id="509fe-157">Audio_LowSound</span></span>  <br/> |
|<span data-ttu-id="509fe-158">106</span><span class="sxs-lookup"><span data-stu-id="509fe-158">106</span></span>  <br/> |<span data-ttu-id="509fe-159">Audio_Dropped</span><span class="sxs-lookup"><span data-stu-id="509fe-159">Audio_Dropped</span></span>  <br/> |
|<span data-ttu-id="509fe-160">107</span><span class="sxs-lookup"><span data-stu-id="509fe-160">107</span></span>  <br/> |<span data-ttu-id="509fe-161">Audio_DistortedSpeech</span><span class="sxs-lookup"><span data-stu-id="509fe-161">Audio_DistortedSpeech</span></span>  <br/> |
|<span data-ttu-id="509fe-162">108</span><span class="sxs-lookup"><span data-stu-id="509fe-162">108</span></span>  <br/> |<span data-ttu-id="509fe-163">Audio_Interrupted</span><span class="sxs-lookup"><span data-stu-id="509fe-163">Audio_Interrupted</span></span>  <br/> |
|<span data-ttu-id="509fe-164">109</span><span class="sxs-lookup"><span data-stu-id="509fe-164">109</span></span>  <br/> |<span data-ttu-id="509fe-165">Audio_Other</span><span class="sxs-lookup"><span data-stu-id="509fe-165">Audio_Other</span></span>  <br/> |
|<span data-ttu-id="509fe-166">201</span><span class="sxs-lookup"><span data-stu-id="509fe-166">201</span></span>  <br/> |<span data-ttu-id="509fe-167">Video_NoLocalVideo</span><span class="sxs-lookup"><span data-stu-id="509fe-167">Video_NoLocalVideo</span></span>  <br/> |
|<span data-ttu-id="509fe-168">202</span><span class="sxs-lookup"><span data-stu-id="509fe-168">202</span></span>  <br/> |<span data-ttu-id="509fe-169">Video_NoRemoteVideo</span><span class="sxs-lookup"><span data-stu-id="509fe-169">Video_NoRemoteVideo</span></span>  <br/> |
|<span data-ttu-id="509fe-170">203</span><span class="sxs-lookup"><span data-stu-id="509fe-170">203</span></span>  <br/> |<span data-ttu-id="509fe-171">Video_LowQuality</span><span class="sxs-lookup"><span data-stu-id="509fe-171">Video_LowQuality</span></span>  <br/> |
|<span data-ttu-id="509fe-172">204</span><span class="sxs-lookup"><span data-stu-id="509fe-172">204</span></span>  <br/> |<span data-ttu-id="509fe-173">Video_FrozenVideo</span><span class="sxs-lookup"><span data-stu-id="509fe-173">Video_FrozenVideo</span></span>  <br/> |
|<span data-ttu-id="509fe-174">205</span><span class="sxs-lookup"><span data-stu-id="509fe-174">205</span></span>  <br/> |<span data-ttu-id="509fe-175">Video_StoppedUnexpectedly</span><span class="sxs-lookup"><span data-stu-id="509fe-175">Video_StoppedUnexpectedly</span></span>  <br/> |
|<span data-ttu-id="509fe-176">206</span><span class="sxs-lookup"><span data-stu-id="509fe-176">206</span></span>  <br/> |<span data-ttu-id="509fe-177">Video_DarkVideo</span><span class="sxs-lookup"><span data-stu-id="509fe-177">Video_DarkVideo</span></span>  <br/> |
|<span data-ttu-id="509fe-178">207</span><span class="sxs-lookup"><span data-stu-id="509fe-178">207</span></span>  <br/> |<span data-ttu-id="509fe-179">Video_NoAudioSync</span><span class="sxs-lookup"><span data-stu-id="509fe-179">Video_NoAudioSync</span></span>  <br/> |
|<span data-ttu-id="509fe-180">208</span><span class="sxs-lookup"><span data-stu-id="509fe-180">208</span></span>  <br/> |<span data-ttu-id="509fe-181">Video_Other</span><span class="sxs-lookup"><span data-stu-id="509fe-181">Video_Other</span></span>  <br/> |
|<span data-ttu-id="509fe-182">301</span><span class="sxs-lookup"><span data-stu-id="509fe-182">301</span></span>  <br/> |<span data-ttu-id="509fe-183">Pstn_DialPad</span><span class="sxs-lookup"><span data-stu-id="509fe-183">Pstn_DialPad</span></span>  <br/> |
|<span data-ttu-id="509fe-184">401</span><span class="sxs-lookup"><span data-stu-id="509fe-184">401</span></span>  <br/> |<span data-ttu-id="509fe-185">SS_NoContentLocal</span><span class="sxs-lookup"><span data-stu-id="509fe-185">SS_NoContentLocal</span></span>  <br/> |
|<span data-ttu-id="509fe-186">402</span><span class="sxs-lookup"><span data-stu-id="509fe-186">402</span></span>  <br/> |<span data-ttu-id="509fe-187">SS_NoContentRemote</span><span class="sxs-lookup"><span data-stu-id="509fe-187">SS_NoContentRemote</span></span>  <br/> |
|<span data-ttu-id="509fe-188">403</span><span class="sxs-lookup"><span data-stu-id="509fe-188">403</span></span>  <br/> |<span data-ttu-id="509fe-189">SS_CantPresent</span><span class="sxs-lookup"><span data-stu-id="509fe-189">SS_CantPresent</span></span>  <br/> |
|<span data-ttu-id="509fe-190">404</span><span class="sxs-lookup"><span data-stu-id="509fe-190">404</span></span>  <br/> |<span data-ttu-id="509fe-191">SS_LowQuality</span><span class="sxs-lookup"><span data-stu-id="509fe-191">SS_LowQuality</span></span>  <br/> |
|<span data-ttu-id="509fe-192">405</span><span class="sxs-lookup"><span data-stu-id="509fe-192">405</span></span>  <br/> |<span data-ttu-id="509fe-193">SS_Freezing</span><span class="sxs-lookup"><span data-stu-id="509fe-193">SS_Freezing</span></span>  <br/> |
|<span data-ttu-id="509fe-194">406</span><span class="sxs-lookup"><span data-stu-id="509fe-194">406</span></span>  <br/> |<span data-ttu-id="509fe-195">SS_StoppedUnexpectedly</span><span class="sxs-lookup"><span data-stu-id="509fe-195">SS_StoppedUnexpectedly</span></span>  <br/> |
|<span data-ttu-id="509fe-196">407</span><span class="sxs-lookup"><span data-stu-id="509fe-196">407</span></span>  <br/> |<span data-ttu-id="509fe-197">SS_LargeDelay</span><span class="sxs-lookup"><span data-stu-id="509fe-197">SS_LargeDelay</span></span>  <br/> |
|<span data-ttu-id="509fe-198">408</span><span class="sxs-lookup"><span data-stu-id="509fe-198">408</span></span>  <br/> |<span data-ttu-id="509fe-199">SS_Other</span><span class="sxs-lookup"><span data-stu-id="509fe-199">SS_Other</span></span>  <br/> |
|<span data-ttu-id="509fe-200">501</span><span class="sxs-lookup"><span data-stu-id="509fe-200">501</span></span>  <br/> |<span data-ttu-id="509fe-201">Reliabilty_Join</span><span class="sxs-lookup"><span data-stu-id="509fe-201">Reliabilty_Join</span></span>  <br/> |
|<span data-ttu-id="509fe-202">502</span><span class="sxs-lookup"><span data-stu-id="509fe-202">502</span></span>  <br/> |<span data-ttu-id="509fe-203">Reliabilty_Invite</span><span class="sxs-lookup"><span data-stu-id="509fe-203">Reliabilty_Invite</span></span>  <br/> |
   
 <span data-ttu-id="509fe-204">**[QoeMetrics]。[dbo]。[CallQualityFeedback]**如果启用，此表将包含来自"星型"投票和客户反馈的轮询结果。</span><span class="sxs-lookup"><span data-stu-id="509fe-204">**[QoeMetrics].[dbo].[CallQualityFeedback]** This table contains polling results from "Star" voting and customer feedback if enabled.</span></span>
  
<span data-ttu-id="509fe-205">表中的数据可以通过调用**选择\*[Table.Name] 从**查询或通过使用 Microsoft SQL Server 管理 Studio。</span><span class="sxs-lookup"><span data-stu-id="509fe-205">Data from tables can be called by using a **select \* from [Table.Name]** query or by using Microsoft SQL Server Management Studio.</span></span>
  
<span data-ttu-id="509fe-206">可以用下面的 SQL 查询：</span><span class="sxs-lookup"><span data-stu-id="509fe-206">The following SQL queries can be used:</span></span>
  
 <span data-ttu-id="509fe-207">**音频**</span><span class="sxs-lookup"><span data-stu-id="509fe-207">**Audio**</span></span>
  
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

 <span data-ttu-id="509fe-208">**视频**</span><span class="sxs-lookup"><span data-stu-id="509fe-208">**Video**</span></span>
  
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

## <a name="updating-token-definitions"></a><span data-ttu-id="509fe-209">更新标记定义</span><span class="sxs-lookup"><span data-stu-id="509fe-209">Updating Token Definitions</span></span>

<span data-ttu-id="509fe-210">业务客户端最新 Skype 报告新问题标记 Id (\> 100)，可能不会显示在您 [QoeMetrics]。[dbo]。[CallQualityFeedbackTokenDef] 表。</span><span class="sxs-lookup"><span data-stu-id="509fe-210">The latest Skype for Business clients report new problem token IDs (\> 100) that may not be present in your [QoeMetrics].[dbo].[CallQualityFeedbackTokenDef] table.</span></span> <span data-ttu-id="509fe-211">若要更新数据库表中的最新的标记定义以下 SQL 命令可以运行使用 Microsoft SQL Server 管理 Studio 的监视数据库。</span><span class="sxs-lookup"><span data-stu-id="509fe-211">To update the database table with the latest token definitions, the below SQL command can be run on the monitoring database using Microsoft SQL Server Management Studio.</span></span> <span data-ttu-id="509fe-212">此命令将替换 [QoeMetrics] 中的所有条目。[dbo]。[CallQualityFeedbackTokenDef] 表。</span><span class="sxs-lookup"><span data-stu-id="509fe-212">This command will replace all entries in the [QoeMetrics].[dbo].[CallQualityFeedbackTokenDef] table.</span></span>
  
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


