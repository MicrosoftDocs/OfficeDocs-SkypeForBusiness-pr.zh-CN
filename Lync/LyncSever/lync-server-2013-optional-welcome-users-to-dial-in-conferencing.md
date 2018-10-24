---
title: Lync Server 2013：（可选）欢迎用户参加电话拨入式会议
TOCTitle: （可选）欢迎用户参加电话拨入式会议
ms:assetid: caa4fd61-f506-4c09-bb5b-1aa260d7a720
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398846(v=OCS.15)
ms:contentKeyID: 49314238
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# （可选）在 Lync Server 2013 中欢迎用户参加电话拨入式会议

 

_**上一次修改主题：** 2012-09-30_

配置电话拨入式会议并进行测试以验证其是否正常工作后，应为用户设置初始个人标识号 (PIN) 并通知用户功能是否可用，包括介绍性说明，如初始 PIN 以及指向“电话拨入式会议设置”网页的链接。此步骤是可选的。通常使用 **Set-CsClientPin** cmdlet 来重置 PIN，但是，首次发送包含 PIN 信息的欢迎电子邮件时，可以使用本主题中的过程。如果不想发送电子邮件，则可以改用 **Set-CsClientPin**。

可以使用 **Set-CsPinSendCAWelcomeMail** 脚本来设置 PIN 并向单个用户发送欢迎电子邮件。默认情况下，该脚本不重置已设置的 PIN，但是可以使用 **Force** 参数强制重置 PIN。电子邮件使用简单邮件传输协议 (SMTP) 发送。

可以创建反复运行 **Set-CsPinSendCAWelcomeMail** 脚本的脚本以设置 PIN 并向用户组发送电子邮件。可以修改电子邮件模板（即 **CAWelcomeEmailTemplate.html** 文件）以将更多链接添加到 Intranet 网页或者修改电子邮件文本。

## 设置初始 PIN 并发送欢迎电子邮件

1.  以 RTCUniversalServerAdmins 组成员的身份登录。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  在命令提示符下，运行以下内容：
    
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
    
    **SmtpServer** 默认情况下，脚本会为此参数使用保留环境变量 **$PSEmailServer** 的值。如果未设置 **$PSEmailServer** 变量，则必须指定此参数。
    
    **Credential** 默认情况下，脚本会使用当前用户的凭据。如果当前用户没有权限代表指定的发件人地址发送电子邮件，则必须指定此参数。一般而言，如果没有将电子邮件地址指定为发件人地址，则需指定此参数。
    
    例如：
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com"
    
    此示例创建一个新的 PIN，然后从 Marco 向 Bob 发送欢迎电子邮件。此示例使用默认模板中的电子邮件文本，并创建 HTML 格式的电子邮件。默认主题为“欢迎参加电话拨入式会议”。
    
    另一个示例：
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
        -Pin "383042650" -Force
        -Credential Admin@contoso.com -UseSsl
    
    此示例强制为 Bob 使用值为“383042650”的新 PIN （即使 Bob 已有一个 PIN），然后从 Marco 向 Bob 发送欢迎电子邮件。由于已指定 Credential 参数，因此系统会提示运行命令的人员输入密码。电子邮件使用安全套接字层 (SSL) 发送。

