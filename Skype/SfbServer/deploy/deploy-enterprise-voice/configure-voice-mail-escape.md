---
title: 在 Skype for Business Server 2015 中配置语音邮件转义
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: 摘要： 了解如何通过 Skype 业务服务器管理程序，为业务服务器 2015年配置语音邮件转义 Skype。
ms.openlocfilehash: 07586f38127b2831ecdb2900f005ff43b4184292
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-voice-mail-escape-in-skype-for-business-2015"></a>在 Skype for Business Server 2015 中配置语音邮件转义
 
**摘要：**了解如何通过 Skype 业务服务器管理程序，为业务服务器 2015年配置语音邮件转义 Skype。
  
当用户配置并发响铃到移动电话时，呼叫者将通常路由到用户的个人语音邮件，如果移动电话已关闭、 电池电量不足或超出范围。 与 Skype 业务服务器，用户可以选择与业务相关的呼叫路由到其企业的语音邮件系统。 具体来说，可以配置一个计时器，和 Skype 业务服务器的应答是通过运营商的语音邮件，在定义的时间范围内，如果将断开连接从运营商的语音邮件系统 （和用户的个人语音邮件），同时用户的在公司系统中剩余的终结点继续环。 这样，调用方自动路由到用户的企业语音邮件。
  
使用 Skype 业务服务器管理外壳 cmdlet，**集 CsVoicePolicy**，在语音策略级别，使用下面的参数执行此配置。
  
### <a name="to-configure-voice-mail-escape"></a>配置语音邮件转义

1. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
2. 指定 **Set-CsVoicePolicy** 的以下参数：
    
   - **EnableVoicemailEscapeTimer** - 启用或禁用转义计时器。
    
   - **PSTNVoicemailEscapeTimer** - 指定超时值（以毫秒为单位）。默认值为 1500 毫秒，该值的范围可介于 0 到 8000 毫秒之间。
    
## <a name="example"></a>示例

```
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000

Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500

```

## <a name="see-also"></a>另请参阅

#### 

[配置语音策略和 PSTN 使用记录授权调用功能和权限](http://technet.microsoft.com/library/63f22010-a3d7-4cbd-86e8-6fc0e13c2b84.aspx)

