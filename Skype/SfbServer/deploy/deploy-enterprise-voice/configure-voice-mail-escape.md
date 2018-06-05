---
title: 在 Skype for Business Server 2015 中配置语音邮件转义
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: 摘要： 了解如何使用 Skype 业务 Server 命令行管理程序，为业务服务器 2015年配置语音邮件转义 Skype。
ms.openlocfilehash: 2f8cf7549fd91c8153803a42f5dfb3b78a311e56
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568288"
---
# <a name="configure-voice-mail-escape-in-skype-for-business-2015"></a>在 Skype for Business Server 2015 中配置语音邮件转义
 
**摘要：** 了解如何使用 Skype 业务 Server 命令行管理程序，为业务服务器 2015年配置语音邮件转义 Skype。
  
当用户配置到移动电话同时响铃时，呼叫者将通常路由到用户的个人语音邮件，如果移动电话处于关闭、 电池供电不足或超出范围。 与业务服务器 Skype，用户可以选择使与业务相关的呼叫路由至其企业语音邮件系统。 具体而言，可以配置计时器，并且 Skype 业务服务器如果通过定义的时间范围内的运营商的语音邮件应答呼叫时，将断开连接从运营商的语音邮件系统 （和用户的个人语音邮件），当用户企业系统中的其余终结点继续响铃。 这种方式，呼叫者会自动传送到用户的企业语音邮件。
  
Skype 用于业务 Server Management Shell cmdlet **Set-csvoicepolicy**，在语音策略级别，使用以下参数执行此配置。
  
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

[配置语音策略和 PSTN 用法记录以授权呼叫功能和权限](http://technet.microsoft.com/library/63f22010-a3d7-4cbd-86e8-6fc0e13c2b84.aspx)