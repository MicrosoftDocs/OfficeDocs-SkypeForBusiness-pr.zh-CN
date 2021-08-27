---
title: 向电话拨入用户发送欢迎电子邮件Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 5507827b-6f8d-4ea4-94e6-1cf72c1d38eb
description: 摘要：了解如何欢迎用户在 Skype for Business Server 中加入电话拨入式Skype for Business Server。
ms.openlocfilehash: 4304952bbede0f35183a80f789783bbfc4a8cfbd
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58578796"
---
# <a name="send-welcome-email-to-dial-in-users-in-skype-for-business-server"></a>向电话拨入用户发送欢迎电子邮件Skype for Business Server
 
**摘要：** 了解如何欢迎用户使用 Skype for Business Server 中的电话拨入式Skype for Business Server。
  
配置电话拨入式会议并进行测试以验证其是否正常工作后，应为用户设置初始个人标识号 (PIN) 并通知用户该功能的可用性。 你可以包括介绍性说明，如初始 PIN 和指向电话拨入式会议设置的链接。 
  
通常，使用 **Set-CsClientPin** cmdlet 重置 PIN，但如果要发送包含 PIN 信息的介绍性欢迎电子邮件，可以使用本主题中的过程。 如果不想发送电子邮件，则可以改用 **Set-CsClientPin**。
  
可以使用 **Set-CsPinSendCAWelcomeMail** 脚本来设置 PIN 并向单个用户发送欢迎电子邮件。默认情况下，该脚本不重置已设置的 PIN，但是可以使用 Force 参数强制重置 PIN。电子邮件使用简单邮件传输协议 (SMTP) 发送。
  
可以创建反复运行 **Set-CsPinSendCAWelcomeMail** 脚本的脚本以设置 PIN 并向用户组发送电子邮件。可以修改电子邮件模板（即 CAWelcomeEmailTemplate.html 文件）以将更多链接添加到 Intranet 网页或者修改电子邮件文本。
  


## <a name="set-an-initial-pin-and-send-welcome-email"></a>设置初始 PIN 并发送欢迎电子邮件

1. 以 RTCUniversalServerAdmins 组成员的身份登录。
    
2. 启动命令行Skype for Business Server：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击"Skype for Business Server **命令行管理程序"。**
    
3. 在命令提示符下，运行以下内容：
    
   ```PowerShell
   Set-CsPinSendCAWelcomeMail -UserUri <user identifier>
   -From <email address of sender> [-Subject <subject for email message>]
   [-UserEmailAddress <destination email address>]
   [-Cc <email address of recipients who receive copy of email>]
   [-Bcc <email address of recipients who receive blind copies>]
   [-TemplatePath <path for email template>]
   [-SmtpServer] <SMTP server name>]
   [-BodyAsPlainText] [-UseSsl]
   [-Pin <new numeric PIN>] [-Force] `
   [-Credential <SMTP server credentials used to send email with the specified From address>]
   ```

**SmtpServer** 默认情况下，脚本使用此参数的保留 **$PSEmailServer变量的值** 。 如果未 **$PSEmailServer** 变量，则必须指定此参数。
    
**凭据** 默认情况下，脚本使用当前用户的凭据。 如果当前用户无权代表指定的"发送者"地址发送电子邮件，则必须指定此参数。 一般而言，如果不将电子邮件地址指定为"发送地址"，请指定此参数。
    
以下示例创建一个新的 PIN，然后将欢迎电子邮件从一名用户从一名用户发送给 Bob。 此示例使用默认模板中的电子邮件文本，并创建 HTML 格式的电子邮件。 默认主题为"欢迎参加电话拨入式会议"：
  
```PowerShell
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com"
```

下一个示例强制为 Bob 使用值为"383042650"的新 PIN，即使 Bob 已有 PIN，然后从 Bob 向 Bob 发送欢迎电子邮件。 由于已指定 Credential 参数，因此系统会提示运行命令的人员输入密码。 电子邮件使用安全套接字层和 SSL (发送) ：
  
```PowerShell
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
-Pin "383042650" -Force
-Credential Admin@contoso.com -UseSsl
```
