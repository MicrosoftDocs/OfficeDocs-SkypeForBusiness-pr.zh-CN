---
title: Lync Server 2013：（可选）欢迎用户参加电话拨入式会议
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
ms.openlocfilehash: 27abf5da520f1c5befd3a477783bc3f9ae67e1b5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755656"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-welcome-users-to-dial-in-conferencing-in-lync-server-2013"></a>（可选）在 Lync Server 2013 中欢迎用户参加电话拨入式会议

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-30_

在配置电话拨入式会议并测试以验证其是否正常运行后，应为用户设置初始个人识别码（Pin）并通知用户有关功能的可用性，包括介绍性说明（如作为初始引脚和指向电话拨入式会议设置网页的链接。 此步骤是可选的。 通常，你可以使用**CsClientPin** cmdlet 重置 pin，但如果你想要发送包含信息的欢迎电子邮件，第一次可以使用本主题中的过程。 如果不想发送电子邮件，则可以改用 **Set-CsClientPin**。

可以使用 **Set-CsPinSendCAWelcomeMail** 脚本来设置 PIN 并向单个用户发送欢迎电子邮件。 默认情况下，脚本不会重置 PIN （如果已设置），但你可以使用**force**参数强制重置 pin。 电子邮件使用简单邮件传输协议 (SMTP) 发送。

可以创建反复运行 **Set-CsPinSendCAWelcomeMail** 脚本的脚本以设置 PIN 并向用户组发送电子邮件。 你可以修改电子邮件模板（即**CAWelcomeEmailTemplate**文件）以添加更多 intranet 页面链接或修改电子邮件文本。

<div>

## <a name="to-set-an-initial-pin-and-send-welcome-email"></a>设置初始 PIN 并发送欢迎电子邮件

1.  以 RTCUniversalServerAdmins 组成员的身份登录。

2.  启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。

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
    
    **SmtpServer**   默认情况下，脚本将为此参数使用 reserved 环境变量的值 **$PSEmailServer** 。 如果未设置 **$PSEmailServer**变量，则必须指定此参数。
    
    **凭据**   默认情况下，脚本使用当前用户的凭据。 如果当前用户没有代表指定的发件人地址发送电子邮件的权限，则必须指定此参数。 作为一般规则，如果您不将电子邮件地址指定为 "发件人" 地址，请指定此参数。
    
    例如：
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com"
    
    此示例创建一个新的 PIN 码，然后将欢迎电子邮件从宏发送给 Bob。 此示例使用默认模板中的电子邮件文本，并创建 HTML 格式的电子邮件。 默认主题为 "欢迎使用电话拨入式会议"。
    
    另一个示例：
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
        -Pin "383042650" -Force
        -Credential Admin@contoso.com -UseSsl
    
    此示例为 Bob 强制使用值为 "383042650" 的新 PIN，即使 Bob 有现有的 PIN，然后将欢迎电子邮件从宏发送到 Bob。 由于已指定 Credential 参数，因此系统会提示运行命令的人员输入密码。 电子邮件通过使用安全套接字层（SSL）发送。

</div>

</div>

<span> </span>

</div>

</div>

</div>

