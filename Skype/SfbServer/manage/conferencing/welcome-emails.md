---
title: 发送欢迎电子邮件以电话拨入式 Skype 业务服务器中的用户
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5507827b-6f8d-4ea4-94e6-1cf72c1d38eb
description: 摘要： 了解如何为业务服务器中 Skype 欢迎用户参加电话拨入式会议。
ms.openlocfilehash: 4cf05349e7539a4bd5d1551a19a59f839feb41f8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924911"
---
# <a name="send-welcome-email-to-dial-in-users-in-skype-for-business-server"></a><span data-ttu-id="84815-103">发送欢迎电子邮件以电话拨入式 Skype 业务服务器中的用户</span><span class="sxs-lookup"><span data-stu-id="84815-103">Send welcome email to dial-in users in Skype for Business Server</span></span>
 
<span data-ttu-id="84815-104">**摘要：** 了解如何为业务服务器中 Skype 欢迎用户参加电话拨入式会议。</span><span class="sxs-lookup"><span data-stu-id="84815-104">**Summary:** Learn how to welcome users to dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="84815-105">配置电话拨入式会议并进行测试以验证其是否正常工作后，应为用户设置初始个人标识号 (PIN) 并通知用户功能是否可用。</span><span class="sxs-lookup"><span data-stu-id="84815-105">After you configure dial-in conferencing and test to verify that it is functioning properly, you should set initial personal identification numbers (PINs) for users and notify users about the availability of the feature.</span></span> <span data-ttu-id="84815-106">可以包括介绍性说明，如初始 PIN 以及指向“电话拨入式会议设置”网页的链接。</span><span class="sxs-lookup"><span data-stu-id="84815-106">You can include introductory instructions such as the initial PIN and the link to the Dial-in Conferencing Settings web page.</span></span> 
  
<span data-ttu-id="84815-107">通常，使用**Set-CsClientPin** cmdlet 可重置 Pin，但您可以使用本主题中的过程，如果您想要发送的 PIN 信息介绍性欢迎电子邮件。</span><span class="sxs-lookup"><span data-stu-id="84815-107">Typically, you use the **Set-CsClientPin** cmdlet to reset PINs, but you can use the procedure in this topic if you want to send an introductory welcome email with the PIN information.</span></span> <span data-ttu-id="84815-108">如果不想发送电子邮件，则可以改用 **Set-CsClientPin**。</span><span class="sxs-lookup"><span data-stu-id="84815-108">If you do not want to send the email, you can use **Set-CsClientPin** instead.</span></span>
  
<span data-ttu-id="84815-p103">可以使用 **Set-CsPinSendCAWelcomeMail** 脚本来设置 PIN 并向单个用户发送欢迎电子邮件。默认情况下，该脚本不重置已设置的 PIN，但是可以使用 Force 参数强制重置 PIN。电子邮件使用简单邮件传输协议 (SMTP) 发送。</span><span class="sxs-lookup"><span data-stu-id="84815-p103">You can use the **Set-CsPinSendCAWelcomeMail** script to set the PIN and send a welcome email to a single user. By default, the script does not reset a PIN if it is already set, but you can use the Force parameter to force reset a PIN. The email message is sent using Simple Mail Transfer Protocol (SMTP).</span></span>
  
<span data-ttu-id="84815-p104">可以创建反复运行 **Set-CsPinSendCAWelcomeMail** 脚本的脚本以设置 PIN 并向用户组发送电子邮件。可以修改电子邮件模板（即 CAWelcomeEmailTemplate.html 文件）以将更多链接添加到 Intranet 网页或者修改电子邮件文本。</span><span class="sxs-lookup"><span data-stu-id="84815-p104">You can create a script that runs the **Set-CsPinSendCAWelcomeMail** script iteratively to set PINs and send email to a group of users. You can modify the email template (that is, the CAWelcomeEmailTemplate.html file) to add more links to intranet pages or modify the email text.</span></span>
  


## <a name="set-an-initial-pin-and-send-welcome-email"></a><span data-ttu-id="84815-114">设置初始 PIN 并发送欢迎电子邮件</span><span class="sxs-lookup"><span data-stu-id="84815-114">Set an initial PIN and send welcome email</span></span>

1. <span data-ttu-id="84815-115">以 RTCUniversalServerAdmins 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="84815-115">Log on as a member of the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="84815-116">启动 Skype for Business Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\* 和“Skype for Business 2015”\*\*\*\*，然后单击“Skype for Business Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="84815-116">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="84815-117">在命令提示符下，运行以下内容：</span><span class="sxs-lookup"><span data-stu-id="84815-117">Run the following at the command prompt:</span></span>
    
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

<span data-ttu-id="84815-118">**SmtpServer**默认情况下，该脚本为此参数使用保留的环境变量 **$PSEmailServer**的值。</span><span class="sxs-lookup"><span data-stu-id="84815-118">**SmtpServer** By default, the script uses the value of the reserved environment variable **$PSEmailServer** for this parameter.</span></span> <span data-ttu-id="84815-119">如果未设置 **$PSEmailServer**变量，则必须指定此参数。</span><span class="sxs-lookup"><span data-stu-id="84815-119">If the **$PSEmailServer** variable is not set, you must specify this parameter.</span></span>
    
<span data-ttu-id="84815-120">**凭据**默认情况下，脚本将使用当前用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="84815-120">**Credential** By default, the script uses the credentials of the current user.</span></span> <span data-ttu-id="84815-121">如果当前用户没有权限发送代表指定的电子邮件发件人地址，必须指定此参数。</span><span class="sxs-lookup"><span data-stu-id="84815-121">If the current user does not have permission to send email on behalf of the specified From address, you must specify this parameter.</span></span> <span data-ttu-id="84815-122">一般来说，指定此参数，如果您不指定发件人地址作为电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="84815-122">As a general rule, specify this parameter if you do not specify your email address as the From address.</span></span>
    
<span data-ttu-id="84815-p107">下面的示例创建一个新的 PIN，然后从 Marco 向 Bob 发送欢迎电子邮件。此示例使用默认模板中的电子邮件文本，并创建 HTML 格式的电子邮件。默认主题为“欢迎参加电话拨入式会议”：</span><span class="sxs-lookup"><span data-stu-id="84815-p107">The following example creates a new PIN, and then sends a welcome email from Marco to Bob. It uses the email text from the default template and creates the email message in HTML format. The default Subject is "Welcome to Dial In Conferencing":</span></span>
  
```
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com"
```

<span data-ttu-id="84815-p108">下一个示例强制为 Bob 使用值为“383042650”的新 PIN（即使 Bob 已有一个 PIN），然后从 Marco 向 Bob 发送欢迎电子邮件。由于已指定 Credential 参数，因此系统会提示运行命令的人员输入密码。电子邮件使用安全套接字层 (SSL) 发送：</span><span class="sxs-lookup"><span data-stu-id="84815-p108">The next example forces a new PIN with a value of "383042650" for Bob, even though Bob had an existing PIN, and then sends a welcome email from Marco to Bob. Because the Credential parameter is specified, the person running the command is prompted to enter a password. The email is sent by using the Secure Sockets Layer (SSL):</span></span>
  
```
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
-Pin "383042650" -Force
-Credential Admin@contoso.com -UseSsl
```
