---
title: 创建或删除业务服务器 2015年中 Skype 通知
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
description: 创建或删除 Skype 中为 Business Server 企业语音的通知应用程序的通知。 这将影响如何处理打给未分配号码的呼叫。
ms.openlocfilehash: 5e635ec066ee5a3b76f0d3d9f25d095f57a8bf2e
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2018
ms.locfileid: "19500710"
---
# <a name="create-or-delete-an-announcement-in-skype-for-business-server-2015"></a><span data-ttu-id="6ae24-104">创建或删除业务服务器 2015年中 Skype 通知</span><span class="sxs-lookup"><span data-stu-id="6ae24-104">Create or delete an announcement in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="6ae24-105">创建或删除 Skype 中为 Business Server 企业语音的通知应用程序的通知。</span><span class="sxs-lookup"><span data-stu-id="6ae24-105">Create or delete announcements for Announcement application in Skype for Business Server Enterprise Voice.</span></span> <span data-ttu-id="6ae24-106">这将影响如何处理打给未分配号码的呼叫。</span><span class="sxs-lookup"><span data-stu-id="6ae24-106">This affects how calls to unassigned numbers are handled.</span></span>
  
<span data-ttu-id="6ae24-p103">配置通知的同时，实际也配置了对未分配号码的呼叫的处理方式。可以播放提示（可以是音频文件或文本到语音转换 (TTS) 文件），或者在不播放提示的情况下直接将呼叫转接到指定目标。</span><span class="sxs-lookup"><span data-stu-id="6ae24-p103">When you configure announcements, you are really configuring how you want calls to unassigned numbers to be handled. You can play a prompt, which can be an audio file or a text-to-speech (TTS) file, or you can just transfer the call to a specified destination without playing a prompt.</span></span>
  
<span data-ttu-id="6ae24-p104">在您定义未分配的数字表前需要创建通知。您需要为使用音频提示、TTS 提示或无提示的所有公告执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="6ae24-p104">You need to create announcements before you define the unassigned number table. You need to perform this step for all announcements that use an audio prompt, a TTS prompt, or no prompt.</span></span>
  
<span data-ttu-id="6ae24-111">本主题介绍如何导入和创建通知。</span><span class="sxs-lookup"><span data-stu-id="6ae24-111">This topic describes how to import and create announcements.</span></span> <span data-ttu-id="6ae24-112">有关分配未分配号码表中的通知的详细信息，请参阅[配置未分配号码表](http://technet.microsoft.com/library/eaa01986-e92f-4328-acf6-4e46c4306a04.aspx)。</span><span class="sxs-lookup"><span data-stu-id="6ae24-112">For details about assigning announcements in the unassigned number table, see [Configure the Unassigned Number Table](http://technet.microsoft.com/library/eaa01986-e92f-4328-acf6-4e46c4306a04.aspx).</span></span>
  
## <a name="create-a-new-announcement-for-unassigned-numbers"></a><span data-ttu-id="6ae24-113">创建未分配号码的新通知</span><span class="sxs-lookup"><span data-stu-id="6ae24-113">Create a new announcement for unassigned numbers</span></span>

<span data-ttu-id="6ae24-114">要创建新的通知，您需要执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="6ae24-114">To create a new announcement, you need to perform the following steps:</span></span> 
  
1. <span data-ttu-id="6ae24-115">对于音频提示，使用喜欢的音频录制应用程序来录制音频文件。</span><span class="sxs-lookup"><span data-stu-id="6ae24-115">For audio prompts, record the audio file by using your favorite audio recording application.</span></span>
    
2. <span data-ttu-id="6ae24-116">对于音频提示，运行**Import-csannouncementfile** cmdlet 导入文件存储的音频文件的内容。</span><span class="sxs-lookup"><span data-stu-id="6ae24-116">For audio prompts, run the **Import-CsAnnouncementFile** cmdlet to import the contents of the audio file to File Store.</span></span>
    
3. <span data-ttu-id="6ae24-117">运行**New-csannouncement** cmdlet 可以创建和命名通知。</span><span class="sxs-lookup"><span data-stu-id="6ae24-117">Run the **New-CsAnnouncement** cmdlet to create and name the announcement.</span></span> <span data-ttu-id="6ae24-118">执行此步骤，以创建具有音频提示、文本到语音转换 (TTS) 提示或无提示的通知。</span><span class="sxs-lookup"><span data-stu-id="6ae24-118">Perform this step to create announcements with an audio prompt, a text-to-speech (TTS) prompt, or no prompt.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="6ae24-119">您可能要创建无提示的通知（例如，要在不播放消息的情况下将呼叫转接到指定目标时）。</span><span class="sxs-lookup"><span data-stu-id="6ae24-119">You might want to create an announcement with no prompt (for example, if you want to transfer calls to a specific destination without playing a message).</span></span> 
  
4. <span data-ttu-id="6ae24-120">将新通知分配给未分配号码表中的号码范围。</span><span class="sxs-lookup"><span data-stu-id="6ae24-120">Assign the new announcement to a number range in the unassigned number table.</span></span>
    
### <a name="to-create-a-new-announcement"></a><span data-ttu-id="6ae24-121">创建新通知</span><span class="sxs-lookup"><span data-stu-id="6ae24-121">To create a new announcement</span></span>

1. <span data-ttu-id="6ae24-122">对于音频提示，创建音频文件。</span><span class="sxs-lookup"><span data-stu-id="6ae24-122">For audio prompts, create the audio file.</span></span>
    
2. <span data-ttu-id="6ae24-123">登录到计算机的业务 Server Management Shell 的 Skype 或使用**Delegate Setup Permissions**中所述的必要用户权限的 RTCUniversalServerAdmins 组成员身份的安装。</span><span class="sxs-lookup"><span data-stu-id="6ae24-123">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
3. <span data-ttu-id="6ae24-124">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="6ae24-124">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
4. <span data-ttu-id="6ae24-125">对于音频提示，运行：</span><span class="sxs-lookup"><span data-stu-id="6ae24-125">For audio prompts, run:</span></span>
    
   ```
   Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]
   ```

5. <span data-ttu-id="6ae24-126">运行：</span><span class="sxs-lookup"><span data-stu-id="6ae24-126">Run:</span></span>
    
   ```
   New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
   ```

    <span data-ttu-id="6ae24-p107">要将呼叫转接到语音邮件，请键入 sip:username@domainname;opaque=app:voicemail 格式的 SIPAddress（例如 sip:bob@contoso.com;opaque=app:voicemail）。要将呼叫转接到电话号码，请键入 sip:number@domainname;user=phone 格式的 SIPAddress（例如 sip:+ 14255550121@contoso.com;user=phone）。</span><span class="sxs-lookup"><span data-stu-id="6ae24-p107">For transferring calls to voice mail, type SIPAddress in the format sip:username@domainname;opaque=app:voicemail (for example, sip:bob@contoso.com;opaque=app:voicemail). For transferring calls to a phone number, type SIPAddress in the format sip:number@domainname;user=phone (for example, sip:+ 14255550121@contoso.com;user=phone).</span></span>
    
    <span data-ttu-id="6ae24-129">例如，要指定音频提示，请运行：</span><span class="sxs-lookup"><span data-stu-id="6ae24-129">For example, to specify an audio prompt:</span></span>
    
   ```
   $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
   Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
   ```

    <span data-ttu-id="6ae24-130">例如，要指定 TTS 提示，请运行：</span><span class="sxs-lookup"><span data-stu-id="6ae24-130">For example, to specify a TTS prompt:</span></span>
    
   ```
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
   ```

  <span data-ttu-id="6ae24-131">有关这些 cmdlet，以及查看要在**TextToSpeechPrompt**参数中使用的语言代码的列表的详细信息，请参阅[New-csannouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="6ae24-131">For more detail about these cmdlets, and to see a list of the language codes to use in the **TextToSpeechPrompt** parameter, see [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps).</span></span>
    
## <a name="delete-an-announcement-for-unassigned-numbers"></a><span data-ttu-id="6ae24-132">删除未分配号码的通知</span><span class="sxs-lookup"><span data-stu-id="6ae24-132">Delete an announcement for unassigned numbers</span></span>

### <a name="to-delete-an-announcement"></a><span data-ttu-id="6ae24-133">删除通知</span><span class="sxs-lookup"><span data-stu-id="6ae24-133">To delete an announcement</span></span>

1. <span data-ttu-id="6ae24-134">登录到计算机的业务 Server Management Shell 的 Skype 或使用**Delegate Setup Permissions**中所述的必要用户权限的 RTCUniversalServerAdmins 组成员身份的安装。</span><span class="sxs-lookup"><span data-stu-id="6ae24-134">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="6ae24-135">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="6ae24-135">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="6ae24-p108">列出组织中的所有通知。在命令行运行：</span><span class="sxs-lookup"><span data-stu-id="6ae24-p108">List all the announcements in your organization. At the command line, run:</span></span>
     
   ```
   Get-CsAnnouncement
   ```

4. <span data-ttu-id="6ae24-p109">在结果列表中，找到要删除的通知，并复制 GUID。然后，在命令行运行：</span><span class="sxs-lookup"><span data-stu-id="6ae24-p109">In the resulting list, locate the announcement you want to delete, and copy the GUID. Then, at the command line, run:</span></span>
    
   ```
   Remove-CsAnnouncement -Identity "<Service:service ID/guid>" 
   ```

    <span data-ttu-id="6ae24-140">例如：</span><span class="sxs-lookup"><span data-stu-id="6ae24-140">For example:</span></span>
    
   ```
   Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
   ```

    > [!NOTE]
    > <span data-ttu-id="6ae24-141">有关更多选项的详细信息，请参阅[Get-csannouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps)和[Remove-csannouncement](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="6ae24-141">For details about more options, see [Get-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps) and [Remove-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="6ae24-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6ae24-142">See also</span></span>

[<span data-ttu-id="6ae24-143">创建或删除业务服务器 2015年中 Skype 通知</span><span class="sxs-lookup"><span data-stu-id="6ae24-143">Create or delete an announcement in Skype for Business Server 2015</span></span>](create-an-announcement.md)

[<span data-ttu-id="6ae24-144">Import-csannouncementfile</span><span class="sxs-lookup"><span data-stu-id="6ae24-144">Import-CsAnnouncementFile</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csannouncementfile?view=skype-ps)
  
[<span data-ttu-id="6ae24-145">新 CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="6ae24-145">New-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps)
  
[<span data-ttu-id="6ae24-146">Remove-csannouncement</span><span class="sxs-lookup"><span data-stu-id="6ae24-146">Remove-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps)
  
[<span data-ttu-id="6ae24-147">Get-csannouncement</span><span class="sxs-lookup"><span data-stu-id="6ae24-147">Get-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps)