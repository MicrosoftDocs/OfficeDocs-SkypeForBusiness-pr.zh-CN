---
title: Lync Server 2013：创建通知
description: Lync Server 2013：创建通知。
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
ms.openlocfilehash: cc064686ef86e04b89951fcaac7abbec28b7257c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562388"
---
# <a name="create-an-announcement-in-lync-server-2013"></a>在 Lync Server 2013 中创建通知

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

若要创建新的通知，您需要执行以下步骤：

1.  对于音频提示，请使用最喜欢的音频录音应用程序录制音频文件。

2.  对于音频提示，运行 **CsAnnouncementFile** cmdlet 将音频文件的内容导入到文件存储。

3.  运行 **CsAnnouncement** cmdlet 以创建并命名通知。 执行此步骤可创建带有音频提示、文本到语音 (TTS) 提示或无提示的通知的通知。
    
    <div>
    

    > [!TIP]  
    > 您可能希望创建无提示的通知 (例如，如果要将呼叫转移到特定目标，而不在) 播放邮件。

    
    </div>

4.  将新通知分配到 "未分配号码" 表中的某个号码范围。

本主题介绍如何导入和创建通知。 有关在未分配号码表中分配通知的详细信息，请参阅 [在 Lync Server 2013 中配置未分配号码表](lync-server-2013-configure-the-unassigned-number-table.md)。

<div>

## <a name="to-create-a-new-announcement"></a>创建新通知

1.  对于音频提示，请创建音频文件。

2.  登录到安装了 Lync Server 命令行管理程序的计算机，作为 RTCUniversalServerAdmins 组的成员或具有必要的用户权限（如在 [Lync Server 2013 中委派安装权限](lync-server-2013-delegate-setup-permissions.md)中所述）。

3.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

4.  对于音频提示，请运行：
    
        Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]

5.  以
    
        New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
    
    若要将呼叫转接到语音邮件，请在 "sip： username@domainname; 不透明 = app：语音 (等格式中键入 SIPAddress。例如，sip： bob@contoso .com; 不透明 = app：语音邮件) 。 若要将呼叫转接到电话号码，请键入 sip： number@domainname; user = phone (例如，sip： + 14255550121@contoso .com; user = phone) ，以 "sip：; user = phone 格式键入 SIPAddress。
    
    例如，若要指定音频提示，请执行以下操作：
    
        $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
        Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
    
    例如，若要指定 TTS 提示，请执行以下操作：
    
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
    
    有关这些 cmdlet 的更多详细信息，以及若要查看在 **TextToSpeechPrompt** 参数中使用的语言代码的列表，请参阅 [CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement)。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Import-CsAnnouncementFile](https://docs.microsoft.com/powershell/module/skype/Import-CsAnnouncementFile)  
[新 CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement)  
[在 Lync Server 2013 中配置未分配号码表](lync-server-2013-configure-the-unassigned-number-table.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

