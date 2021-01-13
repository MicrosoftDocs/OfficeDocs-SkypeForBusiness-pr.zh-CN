---
title: 在 Skype for Business 中配置语音邮件转义
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: 摘要：了解如何使用 Skype for Business Server 命令行管理程序在 Skype for Business Server 中配置语音邮件转义。
ms.openlocfilehash: c6326360a0e49715feb7e9f9c3c123ec42b9c330
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824922"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a>在 Skype for Business 中配置语音邮件转义

**摘要：** 了解如何使用 Skype for Business Server 命令行管理程序在 Skype for Business Server 中配置语音邮件转义。

当用户将同时响铃配置为移动电话时，如果移动电话已关闭、电池电源不足或范围外，通常会将呼叫者路由到用户的个人语音邮件。 使用 Skype for Business Server，用户可以选择将业务相关的呼叫路由到其公司语音邮件系统。 具体而言，可以配置计时器，如果运营商的语音邮件在定义的时间范围内应答呼叫，Skype for Business Server 将断开与运营商的语音邮件系统 (和用户的个人语音邮件) 的连接，同时企业系统中用户的剩余终结点将继续响铃。 这样，呼叫者会自动路由到用户的公司语音邮件。

此配置使用语音策略级别的 Skype for Business Server 命令行管理程序 cmdlet **Set-CsVoicePolicy** 执行，并具有以下参数。

### <a name="to-configure-voice-mail-escape"></a>配置语音邮件转义

1. 启动 Skype for Business Server命令行管理程序：单击"开始"，**单击"所有** 程序"，再单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**

2. 指定 **Set-CsVoicePolicy** 的以下参数：

   - **EnableVoicemailEscapeTimer** - 启用或禁用转义计时器。

   - **PSTNVoicemailEscapeTimer** - 指定超时值（以毫秒为单位）。默认值为 1500 毫秒，该值的范围可介于 0 到 8000 毫秒之间。

## <a name="example"></a>示例

```powershell
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a>另请参阅

[配置语音策略和 PSTN 用法记录以授权呼叫功能和权限](https://technet.microsoft.com/library/63f22010-a3d7-4cbd-86e8-6fc0e13c2b84.aspx)

