---
title: 在 Skype for Business Server 创建或删除通知
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
description: Create or delete announcements for Announcement application in Skype for Business Server 企业语音. 这会影响如何处理对未分配号码的呼叫。
ms.openlocfilehash: 571dce52366430c0e13f442de4917a2c51ed056f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093280"
---
# <a name="create-or-delete-an-announcement-in-skype-for-business-server"></a>在 Skype for Business Server 创建或删除通知

Create or delete announcements for Announcement application in Skype for Business Server 企业语音. 这会影响如何处理对未分配号码的呼叫。

配置通知的同时，实际也配置了对未分配号码的呼叫的处理方式。可以播放提示（可以是音频文件或文本到语音转换 (TTS) 文件），或者在不播放提示的情况下直接将呼叫转接到指定目标。

在您定义未分配的数字表前需要创建通知。您需要为使用音频提示、TTS 提示或无提示的所有公告执行此步骤。

本主题介绍如何导入和创建通知。 有关在未分配号码表中分配通知的详细信息，请参阅配置未 [分配号码表](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-unassigned-number-table)。

## <a name="create-a-new-announcement-for-unassigned-numbers"></a>为未分配号码创建新通知

若要创建新通知，需要执行以下步骤：

1. 对于音频提示，使用最喜爱的音频录制应用程序录制音频文件。

2. 对于音频提示，请运行 **Import-CsAnnouncementFile** cmdlet 将音频文件的内容导入文件存储。

3. 运行 **New-CsAnnouncement** cmdlet 以创建通知并命名通知。 执行此步骤可创建具有音频提示、文本到语音 (TTS) 或无提示通知。

    > [!TIP]
    > 例如，如果要将呼叫转接到特定目标而不播放消息 (，可能需要创建无提示) 。

4. 将新通知分配给未分配号码表中的号码范围。

### <a name="to-create-a-new-announcement"></a>创建新通知

1. 对于音频提示，请创建音频文件。

2. 以 RTCUniversalServerAdmins 组的成员或委派安装权限中所述的必要用户权限登录到安装了 Skype for Business Server 命令行管理程序 **的计算机**。

3. 启动 Skype for Business Server命令行管理程序：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**

4. 对于音频提示，请运行：

   ```powershell
   Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]
   ```

5. 运行：

   ```powershell
   New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
   ```

    若要将呼叫转接到语音邮件，请以 sip：username@domainname;opaque=app：voicemail (格式键入 SIPAddress，例如 sip：bob@contoso.com;opaque=app：voicemail) 。 若要将呼叫转接到电话号码，请以 sip：number@domainname;user=phone (格式键入 SIPAddress，例如 sip：+ 14255550121@contoso.com;user=phone) 。

    例如，若要指定音频提示：

   ```powershell
   $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
   Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
   ```

    例如，若要指定 TTS 提示：

   ```powershell
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
   ```

   有关这些 cmdlet 的详细信息，以及要用于 **TextToSpeechPrompt** 参数的语言代码的列表，请参阅 [New-CsAnnouncement。](/powershell/module/skype/new-csannouncement?view=skype-ps)

## <a name="delete-an-announcement-for-unassigned-numbers"></a>删除未分配号码通知

### <a name="to-delete-an-announcement"></a>删除通知

1. 以 RTCUniversalServerAdmins 组的成员或委派安装权限中所述的必要用户权限登录到安装了 Skype for Business Server 命令行管理程序 **的计算机**。

2. 启动 Skype for Business Server命令行管理程序：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**

3. 列出组织中的所有通知。在命令行运行：

   ```powershell
   Get-CsAnnouncement
   ```

4. 在结果列表中，找到要删除的通知，并复制 GUID。然后，在命令行运行：

   ```powershell
   Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
   ```

    例如：

   ```powershell
   Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
   ```

    > [!NOTE]
    > 有关更多选项的详细信息，请参阅[Get-CsAnnouncement](/powershell/module/skype/get-csannouncement?view=skype-ps)和[Remove-CsAnnouncement。](/powershell/module/skype/remove-csannouncement?view=skype-ps)

## <a name="see-also"></a>另请参阅

[在 Skype for Business Server 创建或删除通知](create-an-announcement.md)

[Import-CsAnnouncementFile](/powershell/module/skype/import-csannouncementfile?view=skype-ps)

[New-CsAnnouncement](/powershell/module/skype/new-csannouncement?view=skype-ps)

[Remove-CsAnnouncement](/powershell/module/skype/remove-csannouncement?view=skype-ps)

[Get-CsAnnouncement](/powershell/module/skype/get-csannouncement?view=skype-ps)