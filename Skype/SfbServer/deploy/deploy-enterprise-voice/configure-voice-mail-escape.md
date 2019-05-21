---
title: 在 Skype for Business 中配置语音邮件转义
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: '摘要: 了解如何使用 Skype for business Server 命令行管理程序在 Skype for Business 服务器中配置语音邮件转义。'
ms.openlocfilehash: 89c449f538fee2f5230cb66a664317cada723220
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289081"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a>在 Skype for Business 中配置语音邮件转义

**摘要:** 了解如何使用 Skype for business Server 命令行管理程序在 Skype for Business 服务器中配置语音邮件转义。

当用户配置与移动电话的同时拨打时, 如果移动电话已关闭、电池电量不足或超出范围, 呼叫者通常会被路由到用户的个人语音邮件。 使用 Skype for Business 服务器, 用户可以选择将与业务相关的呼叫路由到其企业语音邮件系统。 具体而言, 可以配置计时器, 并且如果运营商的语音邮件在定义的时间范围内由该运营商的语音邮件应答, 则 Skype for business 服务器将断开与运营商的语音邮件系统 (和用户的个人语音邮件) 的连接, 而用户的公司系统中的剩余终结点继续拨打。 这样, 呼叫者将自动路由到用户的公司语音邮件。

使用以下参数, 在语音策略级别使用 Skype for Business Server Management Shell cmdlet ( **CsVoicePolicy**) 执行此配置。

### <a name="to-configure-voice-mail-escape"></a>配置语音邮件转义

1. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。

2. 指定 **Set-CsVoicePolicy** 的以下参数：

   - **EnableVoicemailEscapeTimer** - 启用或禁用转义计时器。

   - **PSTNVoicemailEscapeTimer** - 指定超时值（以毫秒为单位）。默认值为 1500 毫秒，该值的范围可介于 0 到 8000 毫秒之间。

## <a name="example"></a>示例

```
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a>另请参阅

[Configuring Voice Policies and PSTN Usage Records to Authorize Calling Features and Privileges](https://technet.microsoft.com/library/63f22010-a3d7-4cbd-86e8-6fc0e13c2b84.aspx)

