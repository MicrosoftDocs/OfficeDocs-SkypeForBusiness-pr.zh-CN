---
title: 'Lync Server 2013: 创建公告'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create an announcement
ms:assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412783(v=OCS.15)
ms:contentKeyID: 48185005
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b80210787a8261d122fa7508807ab995279c7d0e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830849"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-an-announcement-in-lync-server-2013"></a><span data-ttu-id="94368-102">在 Lync Server 2013 中创建公告</span><span class="sxs-lookup"><span data-stu-id="94368-102">Create an announcement in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94368-103">_**主题上次修改时间:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="94368-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="94368-104">要创建新的通知，您需要执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="94368-104">To create a new announcement, you need to perform the following steps:</span></span>

1.  <span data-ttu-id="94368-105">对于音频提示，使用喜欢的音频录制应用程序来录制音频文件。</span><span class="sxs-lookup"><span data-stu-id="94368-105">For audio prompts, record the audio file by using your favorite audio recording application.</span></span>

2.  <span data-ttu-id="94368-106">对于音频提示，运行 **Import-CsAnnouncementFile** cmdlet 将音频文件的内容导入文件存储。</span><span class="sxs-lookup"><span data-stu-id="94368-106">For audio prompts, run the **Import-CsAnnouncementFile** cmdlet to import the contents of the audio file to File Store.</span></span>

3.  <span data-ttu-id="94368-107">运行  **New-CsAnnouncement** cmdlet 创建并命名通知。</span><span class="sxs-lookup"><span data-stu-id="94368-107">Run the **New-CsAnnouncement** cmdlet to create and name the announcement.</span></span> <span data-ttu-id="94368-108">执行此步骤，以创建具有音频提示、文本到语音转换 (TTS) 提示或无提示的通知。</span><span class="sxs-lookup"><span data-stu-id="94368-108">Perform this step to create announcements with an audio prompt, a text-to-speech (TTS) prompt, or no prompt.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="94368-109">您可能要创建无提示的通知（例如，要在不播放消息的情况下将呼叫转接到指定目标时）。</span><span class="sxs-lookup"><span data-stu-id="94368-109">You might want to create an announcement with no prompt (for example, if you want to transfer calls to a specific destination without playing a message).</span></span>

    
    </div>

4.  <span data-ttu-id="94368-110">将新通知分配给未分配号码表中的号码范围。</span><span class="sxs-lookup"><span data-stu-id="94368-110">Assign the new announcement to a number range in the unassigned number table.</span></span>

<span data-ttu-id="94368-111">本主题介绍如何导入和创建通知。</span><span class="sxs-lookup"><span data-stu-id="94368-111">This topic describes how to import and create announcements.</span></span> <span data-ttu-id="94368-112">有关在 "未分配的号码" 表中分配公告的详细信息, 请参阅[在 Lync Server 2013 中配置 "未分配号码" 表](lync-server-2013-configure-the-unassigned-number-table.md)。</span><span class="sxs-lookup"><span data-stu-id="94368-112">For details about assigning announcements in the unassigned number table, see [Configure the unassigned number table in Lync Server 2013](lync-server-2013-configure-the-unassigned-number-table.md).</span></span>

<div>

## <a name="to-create-a-new-announcement"></a><span data-ttu-id="94368-113">创建新通知</span><span class="sxs-lookup"><span data-stu-id="94368-113">To create a new announcement</span></span>

1.  <span data-ttu-id="94368-114">对于音频提示，创建音频文件。</span><span class="sxs-lookup"><span data-stu-id="94368-114">For audio prompts, create the audio file.</span></span>

2.  <span data-ttu-id="94368-115">以 RTCUniversalServerAdmins 组成员的身份或必要的用户权限登录到安装了 Lync Server 管理外壳的计算机, 如在[Lync Server 2013 中的 "委派设置权限](lync-server-2013-delegate-setup-permissions.md)" 中所述。</span><span class="sxs-lookup"><span data-stu-id="94368-115">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

3.  <span data-ttu-id="94368-116">启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="94368-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="94368-117">对于音频提示，运行：</span><span class="sxs-lookup"><span data-stu-id="94368-117">For audio prompts, run:</span></span>
    
        Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]

5.  <span data-ttu-id="94368-118">运行：</span><span class="sxs-lookup"><span data-stu-id="94368-118">Run:</span></span>
    
        New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
    
    <span data-ttu-id="94368-p103">要将呼叫转接到语音邮件，请键入 sip:username@domainname;opaque=app:voicemail 格式的 SIPAddress（例如 sip:bob@contoso.com;opaque=app:voicemail）。要将呼叫转接到电话号码，请键入 sip:number@domainname;user=phone 格式的 SIPAddress（例如 sip:+ 14255550121@contoso.com;user=phone）。</span><span class="sxs-lookup"><span data-stu-id="94368-p103">For transferring calls to voice mail, type SIPAddress in the format sip:username@domainname;opaque=app:voicemail (for example, sip:bob@contoso.com;opaque=app:voicemail). For transferring calls to a phone number, type SIPAddress in the format sip:number@domainname;user=phone (for example, sip:+ 14255550121@contoso.com;user=phone).</span></span>
    
    <span data-ttu-id="94368-121">例如，要指定音频提示，请运行：</span><span class="sxs-lookup"><span data-stu-id="94368-121">For example, to specify an audio prompt:</span></span>
    
        $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
        Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
    
    <span data-ttu-id="94368-122">例如，要指定 TTS 提示，请运行：</span><span class="sxs-lookup"><span data-stu-id="94368-122">For example, to specify a TTS prompt:</span></span>
    
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
    
    <span data-ttu-id="94368-123">有关这些 cmdlet 的更多详细信息, 以及要查看在**TextToSpeechPrompt**参数中使用的语言代码的列表, 请参阅[CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement)。</span><span class="sxs-lookup"><span data-stu-id="94368-123">For more detail about these cmdlets, and to see a list of the language codes to use in the **TextToSpeechPrompt** parameter, see [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="94368-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="94368-124">See Also</span></span>


[<span data-ttu-id="94368-125">Import-CsAnnouncementFile</span><span class="sxs-lookup"><span data-stu-id="94368-125">Import-CsAnnouncementFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsAnnouncementFile)  
[<span data-ttu-id="94368-126">新-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="94368-126">New-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement)  
[<span data-ttu-id="94368-127">在 Lync Server 2013 中配置未分配号码表</span><span class="sxs-lookup"><span data-stu-id="94368-127">Configure the unassigned number table in Lync Server 2013</span></span>](lync-server-2013-configure-the-unassigned-number-table.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

