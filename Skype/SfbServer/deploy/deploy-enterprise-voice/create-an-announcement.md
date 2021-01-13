---
title: 在 Skype for Business Server 中创建或删除通知
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
description: 在 Skype for Business Server 应用程序中创建或删除通知企业语音。 这会影响如何处理对未分配号码的呼叫。
ms.openlocfilehash: 9f2b4fcda8e98d4b939b6b443da875dbe153546c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824902"
---
# <a name="create-or-delete-an-announcement-in-skype-for-business-server"></a><span data-ttu-id="a429a-104">在 Skype for Business Server 中创建或删除通知</span><span class="sxs-lookup"><span data-stu-id="a429a-104">Create or delete an announcement in Skype for Business Server</span></span>

<span data-ttu-id="a429a-105">在 Skype for Business Server 应用程序中创建或删除通知企业语音。</span><span class="sxs-lookup"><span data-stu-id="a429a-105">Create or delete announcements for Announcement application in Skype for Business Server Enterprise Voice.</span></span> <span data-ttu-id="a429a-106">这会影响如何处理对未分配号码的呼叫。</span><span class="sxs-lookup"><span data-stu-id="a429a-106">This affects how calls to unassigned numbers are handled.</span></span>

<span data-ttu-id="a429a-p103">配置通知的同时，实际也配置了对未分配号码的呼叫的处理方式。可以播放提示（可以是音频文件或文本到语音转换 (TTS) 文件），或者在不播放提示的情况下直接将呼叫转接到指定目标。</span><span class="sxs-lookup"><span data-stu-id="a429a-p103">When you configure announcements, you are really configuring how you want calls to unassigned numbers to be handled. You can play a prompt, which can be an audio file or a text-to-speech (TTS) file, or you can just transfer the call to a specified destination without playing a prompt.</span></span>

<span data-ttu-id="a429a-p104">在您定义未分配的数字表前需要创建通知。您需要为使用音频提示、TTS 提示或无提示的所有公告执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="a429a-p104">You need to create announcements before you define the unassigned number table. You need to perform this step for all announcements that use an audio prompt, a TTS prompt, or no prompt.</span></span>

<span data-ttu-id="a429a-111">本主题介绍如何导入和创建通知。</span><span class="sxs-lookup"><span data-stu-id="a429a-111">This topic describes how to import and create announcements.</span></span> <span data-ttu-id="a429a-112">有关在未分配号码表中分配通知的详细信息，请参阅"[配置未分配号码表"。](https://technet.microsoft.com/library/eaa01986-e92f-4328-acf6-4e46c4306a04.aspx)</span><span class="sxs-lookup"><span data-stu-id="a429a-112">For details about assigning announcements in the unassigned number table, see [Configure the Unassigned Number Table](https://technet.microsoft.com/library/eaa01986-e92f-4328-acf6-4e46c4306a04.aspx).</span></span>

## <a name="create-a-new-announcement-for-unassigned-numbers"></a><span data-ttu-id="a429a-113">为未分配号码创建新通知</span><span class="sxs-lookup"><span data-stu-id="a429a-113">Create a new announcement for unassigned numbers</span></span>

<span data-ttu-id="a429a-114">若要创建新通知，需要执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="a429a-114">To create a new announcement, you need to perform the following steps:</span></span>

1. <span data-ttu-id="a429a-115">对于音频提示，使用你最喜爱的音频录制应用程序录制音频文件。</span><span class="sxs-lookup"><span data-stu-id="a429a-115">For audio prompts, record the audio file by using your favorite audio recording application.</span></span>

2. <span data-ttu-id="a429a-116">对于音频提示，请运行 **Import-CsAnnouncementFile** cmdlet 将音频文件的内容导入文件存储。</span><span class="sxs-lookup"><span data-stu-id="a429a-116">For audio prompts, run the **Import-CsAnnouncementFile** cmdlet to import the contents of the audio file to File Store.</span></span>

3. <span data-ttu-id="a429a-117">运行 **New-CsAnnouncement** cmdlet 以创建通知并命名通知。</span><span class="sxs-lookup"><span data-stu-id="a429a-117">Run the **New-CsAnnouncement** cmdlet to create and name the announcement.</span></span> <span data-ttu-id="a429a-118">执行此步骤可创建具有音频提示、文本到语音 (TTS) 或无提示通知。</span><span class="sxs-lookup"><span data-stu-id="a429a-118">Perform this step to create announcements with an audio prompt, a text-to-speech (TTS) prompt, or no prompt.</span></span>

    > [!TIP]
    > <span data-ttu-id="a429a-119">例如，如果要在不播放消息 (将呼叫转接到特定目标，可能需要创建无提示通知) 。</span><span class="sxs-lookup"><span data-stu-id="a429a-119">You might want to create an announcement with no prompt (for example, if you want to transfer calls to a specific destination without playing a message).</span></span>

4. <span data-ttu-id="a429a-120">将新通知分配给未分配号码表中的号码范围。</span><span class="sxs-lookup"><span data-stu-id="a429a-120">Assign the new announcement to a number range in the unassigned number table.</span></span>

### <a name="to-create-a-new-announcement"></a><span data-ttu-id="a429a-121">创建新通知</span><span class="sxs-lookup"><span data-stu-id="a429a-121">To create a new announcement</span></span>

1. <span data-ttu-id="a429a-122">对于音频提示，创建音频文件。</span><span class="sxs-lookup"><span data-stu-id="a429a-122">For audio prompts, create the audio file.</span></span>

2. <span data-ttu-id="a429a-123">以 RTCUniversalServerAdmins 组的成员或委派安装权限中所述的必要用户权限登录到安装了 Skype for Business Server 命令行管理程序 的计算机 **。**</span><span class="sxs-lookup"><span data-stu-id="a429a-123">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

3. <span data-ttu-id="a429a-124">启动 Skype for Business Server命令行管理程序：单击"开始"，**单击"所有** 程序"，再单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="a429a-124">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

4. <span data-ttu-id="a429a-125">对于音频提示，请运行：</span><span class="sxs-lookup"><span data-stu-id="a429a-125">For audio prompts, run:</span></span>

   ```powershell
   Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]
   ```

5. <span data-ttu-id="a429a-126">运行：</span><span class="sxs-lookup"><span data-stu-id="a429a-126">Run:</span></span>

   ```powershell
   New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
   ```

    <span data-ttu-id="a429a-127">若要将呼叫转接到语音邮件，请键入 sip：username@domainname;opaque=app：voicemail (格式的 SIPAddress，例如 sip：bob@contoso.com;opaque=app：voicemail) 。</span><span class="sxs-lookup"><span data-stu-id="a429a-127">For transferring calls to voice mail, type SIPAddress in the format sip:username@domainname;opaque=app:voicemail (for example, sip:bob@contoso.com;opaque=app:voicemail).</span></span> <span data-ttu-id="a429a-128">若要将呼叫转接到电话号码，请键入 sip：number@domainname;user=phone (格式的 SIPAddress，例如 sip：+ 14255550121@contoso.com;user=phone) 。</span><span class="sxs-lookup"><span data-stu-id="a429a-128">For transferring calls to a phone number, type SIPAddress in the format sip:number@domainname;user=phone (for example, sip:+ 14255550121@contoso.com;user=phone).</span></span>

    <span data-ttu-id="a429a-129">例如，若要指定音频提示：</span><span class="sxs-lookup"><span data-stu-id="a429a-129">For example, to specify an audio prompt:</span></span>

   ```powershell
   $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
   Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
   ```

    <span data-ttu-id="a429a-130">例如，若要指定 TTS 提示：</span><span class="sxs-lookup"><span data-stu-id="a429a-130">For example, to specify a TTS prompt:</span></span>

   ```powershell
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
   ```

   <span data-ttu-id="a429a-131">有关这些 cmdlet 的更多详细信息，以及要用于 **TextToSpeechPrompt** 参数的语言代码的列表，请参阅 [New-CsAnnouncement。](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="a429a-131">For more detail about these cmdlets, and to see a list of the language codes to use in the **TextToSpeechPrompt** parameter, see [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps).</span></span>

## <a name="delete-an-announcement-for-unassigned-numbers"></a><span data-ttu-id="a429a-132">删除未分配号码通知</span><span class="sxs-lookup"><span data-stu-id="a429a-132">Delete an announcement for unassigned numbers</span></span>

### <a name="to-delete-an-announcement"></a><span data-ttu-id="a429a-133">删除通知</span><span class="sxs-lookup"><span data-stu-id="a429a-133">To delete an announcement</span></span>

1. <span data-ttu-id="a429a-134">以 RTCUniversalServerAdmins 组的成员或委派安装权限中所述的必要用户权限登录到安装了 Skype for Business Server 命令行管理程序 的计算机 **。**</span><span class="sxs-lookup"><span data-stu-id="a429a-134">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="a429a-135">启动 Skype for Business Server命令行管理程序：单击"开始"，**单击"所有** 程序"，再单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="a429a-135">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="a429a-p108">列出组织中的所有通知。在命令行运行：</span><span class="sxs-lookup"><span data-stu-id="a429a-p108">List all the announcements in your organization. At the command line, run:</span></span>

   ```powershell
   Get-CsAnnouncement
   ```

4. <span data-ttu-id="a429a-p109">在结果列表中，找到要删除的通知，并复制 GUID。然后，在命令行运行：</span><span class="sxs-lookup"><span data-stu-id="a429a-p109">In the resulting list, locate the announcement you want to delete, and copy the GUID. Then, at the command line, run:</span></span>

   ```powershell
   Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
   ```

    <span data-ttu-id="a429a-140">例如：</span><span class="sxs-lookup"><span data-stu-id="a429a-140">For example:</span></span>

   ```powershell
   Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
   ```

    > [!NOTE]
    > <span data-ttu-id="a429a-141">有关更多选项的详细信息，请参阅[Get-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps)和[Remove-CsAnnouncement。](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="a429a-141">For details about more options, see [Get-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps) and [Remove-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps).</span></span>

## <a name="see-also"></a><span data-ttu-id="a429a-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a429a-142">See also</span></span>

[<span data-ttu-id="a429a-143">在 Skype for Business Server 中创建或删除通知</span><span class="sxs-lookup"><span data-stu-id="a429a-143">Create or delete an announcement in Skype for Business Server</span></span>](create-an-announcement.md)

[<span data-ttu-id="a429a-144">Import-CsAnnouncementFile</span><span class="sxs-lookup"><span data-stu-id="a429a-144">Import-CsAnnouncementFile</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csannouncementfile?view=skype-ps)

[<span data-ttu-id="a429a-145">New-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="a429a-145">New-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps)

[<span data-ttu-id="a429a-146">Remove-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="a429a-146">Remove-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps)

[<span data-ttu-id="a429a-147">Get-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="a429a-147">Get-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps)

