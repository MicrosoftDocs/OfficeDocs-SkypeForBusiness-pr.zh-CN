---
title: Lync Server 2013：创建公告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create an announcement
ms:assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412783(v=OCS.15)
ms:contentKeyID: 48185005
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cfae1817cb47c769885ca42a7ca3ff6f57f7b669
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726362"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-an-announcement-in-lync-server-2013"></a>在 Lync Server 2013 中创建公告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-11-01_

要创建新的通知，您需要执行以下步骤：

1.  对于音频提示，使用喜欢的音频录制应用程序来录制音频文件。

2.  对于音频提示，运行 **Import-CsAnnouncementFile** cmdlet 将音频文件的内容导入文件存储。

3.  运行  **New-CsAnnouncement** cmdlet 创建并命名通知。 执行此步骤，以创建具有音频提示、文本到语音转换 (TTS) 提示或无提示的通知。
    
    <div>
    

    > [!TIP]  
    > 您可能要创建无提示的通知（例如，要在不播放消息的情况下将呼叫转接到指定目标时）。

    
    </div>

4.  将新通知分配给未分配号码表中的号码范围。

本主题介绍如何导入和创建通知。 有关在 "未分配的号码" 表中分配公告的详细信息，请参阅[在 Lync Server 2013 中配置 "未分配号码" 表](lync-server-2013-configure-the-unassigned-number-table.md)。

<div>

## <a name="to-create-a-new-announcement"></a>创建新通知

1.  对于音频提示，创建音频文件。

2.  以 RTCUniversalServerAdmins 组成员的身份或必要的用户权限登录到安装了 Lync Server 管理外壳的计算机，如在[Lync Server 2013 中的 "委派设置权限](lync-server-2013-delegate-setup-permissions.md)" 中所述。

3.  启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。

4.  对于音频提示，运行：
    
        Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]

5.  运行：
    
        New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
    
    要将呼叫转接到语音邮件，请键入 sip:username@domainname;opaque=app:voicemail 格式的 SIPAddress（例如 sip:bob@contoso.com;opaque=app:voicemail）。要将呼叫转接到电话号码，请键入 sip:number@domainname;user=phone 格式的 SIPAddress（例如 sip:+ 14255550121@contoso.com;user=phone）。
    
    例如，要指定音频提示，请运行：
    
        $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
        Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
    
    例如，要指定 TTS 提示，请运行：
    
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
    
    有关这些 cmdlet 的更多详细信息，以及要查看在**TextToSpeechPrompt**参数中使用的语言代码的列表，请参阅[CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement)。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Import-CsAnnouncementFile](https://docs.microsoft.com/powershell/module/skype/Import-CsAnnouncementFile)  
[新-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement)  
[在 Lync Server 2013 中配置未分配号码表](lync-server-2013-configure-the-unassigned-number-table.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

