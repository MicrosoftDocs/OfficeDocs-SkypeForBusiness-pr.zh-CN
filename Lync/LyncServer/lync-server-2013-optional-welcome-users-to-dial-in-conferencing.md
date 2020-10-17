---
title: Lync Server 2013： (可选) 欢迎用户加入电话拨入式会议
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Welcome users to dial-in conferencing
ms:assetid: caa4fd61-f506-4c09-bb5b-1aa260d7a720
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398846(v=OCS.15)
ms:contentKeyID: 48185443
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fde04364faf306983f5008539c2ccc6f248955bf
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522249"
---
# <a name="optional-welcome-users-to-dial-in-conferencing-in-lync-server-2013"></a>在 Lync Server 2013 中 (欢迎用户加入电话拨入式会议的可选) 

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-30_

配置电话拨入式会议并进行测试以验证其是否正常工作后，应为用户设置初始个人标识号 (PIN) 并通知用户功能是否可用，包括介绍性说明，如初始 PIN 以及指向“电话拨入式会议设置”网页的链接。 此步骤是可选的。 通常使用 **Set-CsClientPin** cmdlet 来重置 PIN，但是，首次发送包含 PIN 信息的欢迎电子邮件时，可以使用本主题中的过程。 如果不想发送电子邮件，则可以改用 **Set-CsClientPin**。

可以使用 **Set-CsPinSendCAWelcomeMail** 脚本来设置 PIN 并向单个用户发送欢迎电子邮件。 默认情况下，该脚本不重置已设置的 PIN，但是可以使用 **Force** 参数强制重置 PIN。 电子邮件使用简单邮件传输协议 (SMTP) 发送。

可以创建反复运行 **Set-CsPinSendCAWelcomeMail** 脚本的脚本以设置 PIN 并向用户组发送电子邮件。 可以修改电子邮件模板（即 **CAWelcomeEmailTemplate.html** 文件）以将更多链接添加到 Intranet 网页或者修改电子邮件文本。

<div>

## <a name="to-set-an-initial-pin-and-send-welcome-email"></a>设置初始 PIN 并发送欢迎电子邮件

1.  以 RTCUniversalServerAdmins 组成员的身份登录。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

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
    
    **SmtpServer**    默认情况下，该脚本使用此参数的 reserved 环境变量的值 **$PSEmailServer** 。 如果未设置 **$PSEmailServer** 变量，则必须指定此参数。
    
    **凭据**    默认情况下，此脚本使用当前用户的凭据。 如果当前用户不具有代表指定发件人地址发送电子邮件的权限，则必须指定此参数。 作为一般规则，如果您未将电子邮件地址指定为 "发件人" 地址，则指定此参数。
    
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

</div>

</div>

<span> </span>

</div>

</div>

</div>

