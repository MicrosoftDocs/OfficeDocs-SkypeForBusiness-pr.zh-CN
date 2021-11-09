---
title: 配置语音邮件转义Skype for Business
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: 摘要：了解如何使用命令行管理程序在 Skype for Business Server 中配置Skype for Business Server转义。
ms.openlocfilehash: 7bd18056362fc4ed6ffdede31515b6eb41d8b134
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60865319"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a>配置语音邮件转义Skype for Business

**摘要：** 了解如何使用命令行管理程序在 Skype for Business Server 中配置Skype for Business Server转义。

当用户配置移动电话的同时响铃时，如果移动电话已关闭、没有电池电源或范围外，呼叫者通常会路由到用户的个人语音邮件。 使用 Skype for Business Server，用户可以选择将业务相关的呼叫路由到其公司语音邮件系统。 具体而言，可以配置计时器，如果运营商的语音邮件在定义的时间范围内应答呼叫，Skype for Business Server 将断开与运营商的语音邮件系统 (和用户的个人语音邮件) 的连接，同时企业系统中用户的剩余终结点将继续响铃。 这样，呼叫者会自动路由到用户的企业语音邮件。

此配置在语音策略级别Skype for Business Server命令行管理程序 cmdlet **Set-CsVoicePolicy，** 并具有以下参数。

### <a name="to-configure-voice-mail-escape"></a>配置语音邮件转义

1. 启动命令行Skype for Business Server：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击"Skype for Business Server **命令行管理程序"。**

2. 指定 **Set-CsVoicePolicy** 的以下参数：

   - **EnableVoicemailEscapeTimer** - 启用或禁用转义计时器。

   - **PSTNVoicemailEscapeTimer** - 指定超时值（以毫秒为单位）。默认值为 1500 毫秒，该值的范围可介于 0 到 8000 毫秒之间。

## <a name="example"></a>示例

```powershell
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a>另请参阅

[配置语音策略和 PSTN 用法记录以授权呼叫功能和权限](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges)