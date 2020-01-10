---
title: 在 Skype for Business 服务器中创建或删除公告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
description: 在 Skype for Business Server Enterprise Voice 中创建或删除公告应用程序的公告。 这将影响如何处理打给未分配号码的呼叫。
ms.openlocfilehash: 50a55908e238dfc1e3ce3d9979d554c7115576a2
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001192"
---
# <a name="create-or-delete-an-announcement-in-skype-for-business-server"></a>在 Skype for Business 服务器中创建或删除公告

在 Skype for Business Server Enterprise Voice 中创建或删除公告应用程序的公告。 这将影响如何处理打给未分配号码的呼叫。

配置通知的同时，实际也配置了对未分配号码的呼叫的处理方式。可以播放提示（可以是音频文件或文本到语音转换 (TTS) 文件），或者在不播放提示的情况下直接将呼叫转接到指定目标。

在您定义未分配的数字表前需要创建通知。您需要为使用音频提示、TTS 提示或无提示的所有公告执行此步骤。

本主题介绍如何导入和创建通知。有关在未分配号码表中分配通知的详细信息，请参阅 [Configure the Unassigned Number Table](https://technet.microsoft.com/library/eaa01986-e92f-4328-acf6-4e46c4306a04.aspx)。

## <a name="create-a-new-announcement-for-unassigned-numbers"></a>创建未分配号码的新通知

要创建新的通知，您需要执行以下步骤：

1. 对于音频提示，使用喜欢的音频录制应用程序来录制音频文件。

2. 对于音频提示，运行 **Import-CsAnnouncementFile** cmdlet 将音频文件的内容导入文件存储。

3. 运行  **New-CsAnnouncement** cmdlet 创建并命名通知。 执行此步骤，以创建具有音频提示、文本到语音转换 (TTS) 提示或无提示的通知。

    > [!TIP]
    > 您可能要创建无提示的通知（例如，要在不播放消息的情况下将呼叫转接到指定目标时）。

4. 将新通知分配给未分配号码表中的号码范围。

### <a name="to-create-a-new-announcement"></a>创建新通知

1. 对于音频提示，创建音频文件。

2. 登录到将 Skype for Business Server Management Shell 作为 RTCUniversalServerAdmins 组的成员或必要的用户权限（如 "**委派设置权限**" 中所述）进行安装的计算机。

3. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。

4. 对于音频提示，运行：

   ```powershell
   Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]
   ```

5. 运行：

   ```powershell
   New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
   ```

    要将呼叫转接到语音邮件，请键入 sip:username@domainname;opaque=app:voicemail 格式的 SIPAddress（例如 sip:bob@contoso.com;opaque=app:voicemail）。要将呼叫转接到电话号码，请键入 sip:number@domainname;user=phone 格式的 SIPAddress（例如 sip:+ 14255550121@contoso.com;user=phone）。

    例如，要指定音频提示，请运行：

   ```powershell
   $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
   Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
   ```

    例如，要指定 TTS 提示，请运行：

   ```powershell
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
   ```

   有关这些 cmdlet 的更多详细信息，以及要查看在**TextToSpeechPrompt**参数中使用的语言代码的列表，请参阅[CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps)。

## <a name="delete-an-announcement-for-unassigned-numbers"></a>删除未分配号码的通知

### <a name="to-delete-an-announcement"></a>删除通知

1. 登录到将 Skype for Business Server Management Shell 作为 RTCUniversalServerAdmins 组的成员或必要的用户权限（如 "**委派设置权限**" 中所述）进行安装的计算机。

2. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。

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
    > 有关更多选项的详细信息，请参阅[CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps)和[Remove-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps)。

## <a name="see-also"></a>另请参阅

[在 Skype for Business 服务器中创建或删除公告](create-an-announcement.md)

[Import-CsAnnouncementFile](https://docs.microsoft.com/powershell/module/skype/import-csannouncementfile?view=skype-ps)

[新-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps)

[Remove-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps)

[CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps)

