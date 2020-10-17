---
title: Lync Server 2013：创建通知
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
ms.openlocfilehash: 5b704dc3db81c78e187a08ec9ab420f1676f049d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501729"
---
# <a name="create-an-announcement-in-lync-server-2013"></a><span data-ttu-id="903c9-102">在 Lync Server 2013 中创建通知</span><span class="sxs-lookup"><span data-stu-id="903c9-102">Create an announcement in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="903c9-103">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="903c9-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="903c9-104">若要创建新的通知，您需要执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="903c9-104">To create a new announcement, you need to perform the following steps:</span></span>

1.  <span data-ttu-id="903c9-105">对于音频提示，请使用最喜欢的音频录音应用程序录制音频文件。</span><span class="sxs-lookup"><span data-stu-id="903c9-105">For audio prompts, record the audio file by using your favorite audio recording application.</span></span>

2.  <span data-ttu-id="903c9-106">对于音频提示，运行 **CsAnnouncementFile** cmdlet 将音频文件的内容导入到文件存储。</span><span class="sxs-lookup"><span data-stu-id="903c9-106">For audio prompts, run the **Import-CsAnnouncementFile** cmdlet to import the contents of the audio file to File Store.</span></span>

3.  <span data-ttu-id="903c9-107">运行 **CsAnnouncement** cmdlet 以创建并命名通知。</span><span class="sxs-lookup"><span data-stu-id="903c9-107">Run the **New-CsAnnouncement** cmdlet to create and name the announcement.</span></span> <span data-ttu-id="903c9-108">执行此步骤可创建带有音频提示、文本到语音 (TTS) 提示或无提示的通知的通知。</span><span class="sxs-lookup"><span data-stu-id="903c9-108">Perform this step to create announcements with an audio prompt, a text-to-speech (TTS) prompt, or no prompt.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="903c9-109">您可能希望创建无提示的通知 (例如，如果要将呼叫转移到特定目标，而不在) 播放邮件。</span><span class="sxs-lookup"><span data-stu-id="903c9-109">You might want to create an announcement with no prompt (for example, if you want to transfer calls to a specific destination without playing a message).</span></span>

    
    </div>

4.  <span data-ttu-id="903c9-110">将新通知分配到 "未分配号码" 表中的某个号码范围。</span><span class="sxs-lookup"><span data-stu-id="903c9-110">Assign the new announcement to a number range in the unassigned number table.</span></span>

<span data-ttu-id="903c9-111">本主题介绍如何导入和创建通知。</span><span class="sxs-lookup"><span data-stu-id="903c9-111">This topic describes how to import and create announcements.</span></span> <span data-ttu-id="903c9-112">有关在未分配号码表中分配通知的详细信息，请参阅 [在 Lync Server 2013 中配置未分配号码表](lync-server-2013-configure-the-unassigned-number-table.md)。</span><span class="sxs-lookup"><span data-stu-id="903c9-112">For details about assigning announcements in the unassigned number table, see [Configure the unassigned number table in Lync Server 2013](lync-server-2013-configure-the-unassigned-number-table.md).</span></span>

<div>

## <a name="to-create-a-new-announcement"></a><span data-ttu-id="903c9-113">创建新通知</span><span class="sxs-lookup"><span data-stu-id="903c9-113">To create a new announcement</span></span>

1.  <span data-ttu-id="903c9-114">对于音频提示，请创建音频文件。</span><span class="sxs-lookup"><span data-stu-id="903c9-114">For audio prompts, create the audio file.</span></span>

2.  <span data-ttu-id="903c9-115">登录到安装了 Lync Server 命令行管理程序的计算机，作为 RTCUniversalServerAdmins 组的成员或具有必要的用户权限（如在 [Lync Server 2013 中委派安装权限](lync-server-2013-delegate-setup-permissions.md)中所述）。</span><span class="sxs-lookup"><span data-stu-id="903c9-115">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

3.  <span data-ttu-id="903c9-116">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="903c9-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="903c9-117">对于音频提示，请运行：</span><span class="sxs-lookup"><span data-stu-id="903c9-117">For audio prompts, run:</span></span>
    
        Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]

5.  <span data-ttu-id="903c9-118">以</span><span class="sxs-lookup"><span data-stu-id="903c9-118">Run:</span></span>
    
        New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
    
    <span data-ttu-id="903c9-119">若要将呼叫转接到语音邮件，请在 "sip： username@domainname; 不透明 = app：语音 (等格式中键入 SIPAddress。例如，sip： bob@contoso .com; 不透明 = app：语音邮件) 。</span><span class="sxs-lookup"><span data-stu-id="903c9-119">For transferring calls to voice mail, type SIPAddress in the format sip:username@domainname;opaque=app:voicemail (for example, sip:bob@contoso.com;opaque=app:voicemail).</span></span> <span data-ttu-id="903c9-120">若要将呼叫转接到电话号码，请键入 sip： number@domainname; user = phone (例如，sip： + 14255550121@contoso .com; user = phone) ，以 "sip：; user = phone 格式键入 SIPAddress。</span><span class="sxs-lookup"><span data-stu-id="903c9-120">For transferring calls to a phone number, type SIPAddress in the format sip:number@domainname;user=phone (for example, sip:+ 14255550121@contoso.com;user=phone).</span></span>
    
    <span data-ttu-id="903c9-121">例如，若要指定音频提示，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="903c9-121">For example, to specify an audio prompt:</span></span>
    
        $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
        Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
    
    <span data-ttu-id="903c9-122">例如，若要指定 TTS 提示，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="903c9-122">For example, to specify a TTS prompt:</span></span>
    
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
    
    <span data-ttu-id="903c9-123">有关这些 cmdlet 的更多详细信息，以及若要查看在 **TextToSpeechPrompt** 参数中使用的语言代码的列表，请参阅 [CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement)。</span><span class="sxs-lookup"><span data-stu-id="903c9-123">For more detail about these cmdlets, and to see a list of the language codes to use in the **TextToSpeechPrompt** parameter, see [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="903c9-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="903c9-124">See Also</span></span>


[<span data-ttu-id="903c9-125">Import-CsAnnouncementFile</span><span class="sxs-lookup"><span data-stu-id="903c9-125">Import-CsAnnouncementFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsAnnouncementFile)  
[<span data-ttu-id="903c9-126">新 CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="903c9-126">New-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement)  
[<span data-ttu-id="903c9-127">在 Lync Server 2013 中配置未分配号码表</span><span class="sxs-lookup"><span data-stu-id="903c9-127">Configure the unassigned number table in Lync Server 2013</span></span>](lync-server-2013-configure-the-unassigned-number-table.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

