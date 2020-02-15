---
title: Lync Server 2013：管理应用程序级响应组设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing application-level Response Group settings
ms:assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721843(v=OCS.15)
ms:contentKeyID: 49733776
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1dccc404350e10b61ea0917c0bd6b6d7e44b333
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045344"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-application-level-response-group-settings-in-lync-server-2013"></a><span data-ttu-id="6aca2-102">在 Lync Server 2013 中管理应用程序级响应组设置</span><span class="sxs-lookup"><span data-stu-id="6aca2-102">Managing application-level Response Group settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6aca2-103">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="6aca2-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="6aca2-104">响应组应用程序的应用程序级别设置包括默认的保持音乐配置、默认的保持音乐音频文件、代理回拨宽限期和呼叫上下文配置。</span><span class="sxs-lookup"><span data-stu-id="6aca2-104">Application-level settings for Response Group application include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="6aca2-105">您只能针对每个池定义一组应用程序级别设置。</span><span class="sxs-lookup"><span data-stu-id="6aca2-105">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="6aca2-106">要查看应用程序级别设置，请使用 **Get-CsRgsConfiguration** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6aca2-106">To view application-level settings, use the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="6aca2-107">要修改应用程序级别设置，请使用 **Set-CsRgsConfiguration** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6aca2-107">To modify the application-level settings, use the **Set-CsRgsConfiguration** cmdlet.</span></span>

<span data-ttu-id="6aca2-p102">只有未定义任何自定义保持音乐时，才会在呼叫处于呼叫等待状态时播放默认保持音乐。呼叫上下文仅适用于分配给互动工作流的队列。如果启用呼叫上下文，则代理可以在收到呼叫时查看呼叫者等待时间或工作流问题和解答等信息。</span><span class="sxs-lookup"><span data-stu-id="6aca2-p102">The default music on hold is played when a call is placed on hold only if no custom music on hold is defined. Call context is available only for queues assigned to interactive workflows. If call context is enabled, an agent can see information such as caller wait time or workflow questions and answers when the call is received.</span></span>

<div>

## <a name="to-modify-response-group-application-level-settings"></a><span data-ttu-id="6aca2-111">修改响应组应用程序级别设置</span><span class="sxs-lookup"><span data-stu-id="6aca2-111">To modify Response Group application-level settings</span></span>

1.  <span data-ttu-id="6aca2-112">以 RTCUniversalServerAdmins 组成员的身份登录，或以支持响应组的预定义管理角色之一的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="6aca2-112">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="6aca2-113">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6aca2-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="6aca2-114">在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="6aca2-114">At the command line, run:</span></span>
    
        Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
    
    <span data-ttu-id="6aca2-115">例如：</span><span class="sxs-lookup"><span data-stu-id="6aca2-115">For example:</span></span>
    
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
    
    <span data-ttu-id="6aca2-p103">要指定一个音频文件以用作默认的保持音乐，您需要首先导入该音频文件。例如：</span><span class="sxs-lookup"><span data-stu-id="6aca2-p103">To specify an audio file to use as the default music on hold, you need to import the audio file first. For example:</span></span>
    
        $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6aca2-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6aca2-118">See Also</span></span>


[<span data-ttu-id="6aca2-119">CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="6aca2-119">Get-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration)  
[<span data-ttu-id="6aca2-120">CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="6aca2-120">Set-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsConfiguration)  
[<span data-ttu-id="6aca2-121">Import-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="6aca2-121">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

