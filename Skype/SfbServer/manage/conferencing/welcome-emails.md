---
title: 在 Skype for Business Server 2015 中将欢迎电子邮件发送给电话拨入用户
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5507827b-6f8d-4ea4-94e6-1cf72c1d38eb
description: 摘要： 了解如何在 Skype 的用户拨入会议欢迎业务服务器 2015年的。
ms.openlocfilehash: 0aa939e2ef742c554339967e31204461bca52b6f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="send-welcome-email-to-dial-in-users-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中将欢迎电子邮件发送给电话拨入用户
 
**摘要：**了解如何在 Skype 的用户拨入会议欢迎业务服务器 2015年的。
  
配置电话拨入式会议并进行测试以验证其是否正常工作后，应为用户设置初始个人标识号 (PIN) 并通知用户功能是否可用。 可以包括介绍性说明，如初始 PIN 以及指向“电话拨入式会议设置”网页的链接。 
  
通常情况下，使用**集 CsClientPin** cmdlet 来重置 Pin，但如果您想要发送介绍性欢迎电子邮件的 PIN 信息可以在本主题中使用步骤。 如果不想发送电子邮件，则可以改用 **Set-CsClientPin**。
  
可以使用 **Set-CsPinSendCAWelcomeMail** 脚本来设置 PIN 并向单个用户发送欢迎电子邮件。默认情况下，该脚本不重置已设置的 PIN，但是可以使用 Force 参数强制重置 PIN。电子邮件使用简单邮件传输协议 (SMTP) 发送。
  
可以创建反复运行 **Set-CsPinSendCAWelcomeMail** 脚本的脚本以设置 PIN 并向用户组发送电子邮件。可以修改电子邮件模板（即 CAWelcomeEmailTemplate.html 文件）以将更多链接添加到 Intranet 网页或者修改电子邮件文本。
  
## 

### <a name="set-an-initial-pin-and-send-welcome-email"></a>设置初始 PIN 并发送欢迎电子邮件

1. 以 RTCUniversalServerAdmins 组成员的身份登录。
    
2. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
3. 在命令提示符下，运行以下内容：
    
  ```
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

**SmtpServer**默认情况下，脚本使用此参数保留的环境变量**$PSEmailServer**的值。 如果未设置**$PSEmailServer**变量，您必须指定此参数。
    
**凭据**默认情况下，脚本使用当前用户的凭据。 如果当前用户没有权限发送电子邮件，代表指定发件人地址，则必须指定此参数。 作为一般规则，指定该参数，如果未指定电子邮件地址作为源地址。
    
下面的示例创建一个新的 PIN，然后从 Marco 向 Bob 发送欢迎电子邮件。此示例使用默认模板中的电子邮件文本，并创建 HTML 格式的电子邮件。默认主题为“欢迎参加电话拨入式会议”：
  
```
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com"
```

下一个示例强制为 Bob 使用值为“383042650”的新 PIN（即使 Bob 已有一个 PIN），然后从 Marco 向 Bob 发送欢迎电子邮件。由于已指定 Credential 参数，因此系统会提示运行命令的人员输入密码。电子邮件使用安全套接字层 (SSL) 发送：
  
```
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
-Pin "383042650" -Force
-Credential Admin@contoso.com -UseSsl
```