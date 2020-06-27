---
title: 在 Skype for Business Server 中评价我的呼叫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c4e0c905-33a1-49d8-9276-1b338f94d085
description: 摘要：了解在 Skype for business Server 中如何评价我的呼叫功能。
ms.openlocfilehash: 15f2bcbcf75690baaa350541f5f1da134fb32025
ms.sourcegitcommit: a73df97a06ea860bfaf5387e0acbf3c724697e14
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "44902216"
---
# <a name="rate-my-call-in-skype-for-business-server"></a>在 Skype for Business Server 中评价我的呼叫

**摘要：** 了解在 Skype for business Server 中如何评价我的呼叫功能。

评价我的呼叫是 Skype for business 2015 和2016客户端在 Windows 中的一项新功能，它为企业提供了一种从最终用户获得反馈的方法。

"汇率我的呼叫" 窗口为音频和视频呼叫提供 "星形" 分级系统和预定义令牌。 此外，管理员还可以启用自定义字段以提供反馈。

收集的速率我的呼叫数据当前不包含在任何现有监控报告中，但它具有单独的监控报告。 可以通过运行 SQL 查询来访问 SQL 表中收集的数据。

## <a name="rate-my-call-prerequisites"></a>评价我的呼叫先决条件

在 Skype for Business Server 部署中的用户可以访问我的呼叫功能之前，必须部署和配置以下组件集：

-  您必须已安装 Skype for Business Server （版本9160或更高版本）。

- 让你的用户安装并更新到最新版本的 Skype for Business，并让他们使用 Skype for Business UI。

- 用户必须驻留在 Skype for Business Server 前端池上。

- 您必须已部署 Skype for Business Server monitoring 数据库并将其与 Skype for business Server 池相关联。

- 建议部署呼叫质量仪表板（CQD）。

## <a name="configure-rate-my-call"></a>配置呼叫评分

默认情况下，在客户端策略中启用了 "我的呼叫" 功能，具有以下设置：

- 评价我的呼叫显示百分比-10%

- 评价我的呼叫允许自定义用户反馈-已禁用

但如果您想要启用基本功能，则无需执行任何操作，但如果您想要进行自定义反馈，则需要单独启用它。 以下 Windows PowerShell cmdlet 是一个启用自定义最终用户反馈并将时间间隔从10% 更改为80% 的示例。

```PowerShell
Set-CSClientPolicy -Identity <PolicyIdentity> -RateMyCallDisplayPercentage 80 -RateMyCallAllowCustomUserFeedback $true 
```

## <a name="accessing-rate-my-call-data"></a>访问呼叫数据的速率

用户的数据在监视数据库的两个表中收集。

 **[QoeMetrics]。[dbo]。[CallQualityFeedbackToken]**-此表包含最终用户对令牌进行轮询的结果。

 **[QoeMetrics]。[dbo]。[CallQualityFeedbackTokenDef]**-此表包含令牌定义。

令牌定义的编码方式如下所示：

|||
|:-----|:-----|
|1   <br/> |DistortedSpeech  <br/> |
|2   <br/> | ElectronicFeedback <br/> |
|3   <br/> | BackgroundNoise <br/> |
|4   <br/> |MuffledSpeech  <br/> |
|5   <br/> |回声  <br/> |
| 21  <br/> | FrozenVideo <br/> |
|22  <br/> | PixelatedVideo <br/> |
|上午  <br/> | BlurryImage <br/> |
|24  <br/> | PoorColor <br/> |
|word  <br/> | DarkVideo <br/> |
|101  <br/> |Audio_SilentLocal  <br/> |
|102  <br/> |Audio_SilentRemote  <br/> |
|103  <br/> |Audio_Echo  <br/> |
|104  <br/> |Audio_BackgroundNoise  <br/> |
|105  <br/> |Audio_LowSound  <br/> |
|106  <br/> |Audio_Dropped  <br/> |
|107  <br/> |Audio_DistortedSpeech  <br/> |
|108  <br/> |Audio_Interrupted  <br/> |
|109  <br/> |Audio_Other  <br/> |
|201  <br/> |Video_NoLocalVideo  <br/> |
|202  <br/> |Video_NoRemoteVideo  <br/> |
|203  <br/> |Video_LowQuality  <br/> |
|204  <br/> |Video_FrozenVideo  <br/> |
|205  <br/> |Video_StoppedUnexpectedly  <br/> |
|206  <br/> |Video_DarkVideo  <br/> |
|207  <br/> |Video_NoAudioSync  <br/> |
|208  <br/> |Video_Other  <br/> |
|301  <br/> |Pstn_DialPad  <br/> |
|401  <br/> |SS_NoContentLocal  <br/> |
|402  <br/> |SS_NoContentRemote  <br/> |
|403  <br/> |SS_CantPresent  <br/> |
|404  <br/> |SS_LowQuality  <br/> |
|405  <br/> |SS_Freezing  <br/> |
|406  <br/> |SS_StoppedUnexpectedly  <br/> |
|407  <br/> |SS_LargeDelay  <br/> |
|408  <br/> |SS_Other  <br/> |
|501  <br/> |Reliabilty_Join  <br/> |
|502  <br/> |Reliabilty_Invite  <br/> |

 **[QoeMetrics]。[dbo]。[CallQualityFeedback]** 此表包含来自 "星" 投票的轮询结果和客户反馈（如果已启用）。

可以使用**select \* from [Table.Name]** 查询或使用 Microsoft SQL Server Management Studio 调用表中的数据。

可以使用以下 SQL 查询：

 **音频**

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

 **Video**

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

## <a name="updating-token-definitions"></a>更新令牌定义

最新的 Skype for Business 客户端报告 \> 了您的 [QoeMetrics] 中可能不存在的新问题令牌 id （100）。 [dbo]。[CallQualityFeedbackTokenDef] 表。 若要使用最新的标记定义更新数据库表，可使用 Microsoft SQL Server Management Studio 在监控数据库上运行下面的 SQL 命令。 此命令将替换 [QoeMetrics] 中的所有条目。[dbo]。[CallQualityFeedbackTokenDef] 表。

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


