---
title: Lync Server 2013：创建通知
TOCTitle: 创建通知
ms:assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412783(v=OCS.15)
ms:contentKeyID: 49313845
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中创建通知

 

_**上一次修改主题：** 2012-11-01_

要创建新的通知，您需要执行以下步骤：

1.  对于音频提示，使用喜欢的音频录制应用程序来录制音频文件。

2.  对于音频提示，运行 **Import-CsAnnouncementFile** cmdlet 将音频文件的内容导入文件存储。

3.  运行 **New-CsAnnouncement** cmdlet 创建并命名通知。执行此步骤，以创建具有音频提示、文本到语音转换 (TTS) 提示或无提示的通知。
    
    > [!TIP]
    > 您可能要创建无提示的通知（例如，要在不播放消息的情况下将呼叫转接到指定目标时）。


4.  将新通知分配给未分配号码表中的号码范围。

本主题介绍如何导入和创建通知。有关在未分配号码表中分配通知的详细信息，请参阅 [在 Lync Server 2013 中配置未分配号码表](lync-server-2013-configure-the-unassigned-number-table.md)。

## 创建新通知

1.  对于音频提示，创建音频文件。

2.  以 RTCUniversalServerAdmins 组成员的身份或利用[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)中所述的必要用户权限登录安装了 Lync Server 命令行管理程序的计算机。

3.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

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
    
    有关这些 cmdlet 的更多详细信息，以及查看要在 **TextToSpeechPrompt** 参数中使用的语言代码的列表，请参阅 [New-CsAnnouncement](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsAnnouncement)。

## 另请参阅

#### 其他资源

[Import-CsAnnouncementFile](https://docs.microsoft.com/en-us/powershell/module/skype/Import-CsAnnouncementFile)  
[New-CsAnnouncement](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsAnnouncement)  
[在 Lync Server 2013 中配置未分配号码表](lync-server-2013-configure-the-unassigned-number-table.md)

