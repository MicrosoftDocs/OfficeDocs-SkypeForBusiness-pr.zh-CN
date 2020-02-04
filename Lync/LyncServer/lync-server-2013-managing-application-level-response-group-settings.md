---
title: Lync Server 2013：管理应用程序级别响应组设置
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
ms.openlocfilehash: ffce659c2c4dc6c91ba4e4935b72c15e4cef4da5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733242"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-application-level-response-group-settings-in-lync-server-2013"></a><span data-ttu-id="49760-102">在 Lync Server 2013 中管理应用程序级别的 "响应" 组设置</span><span class="sxs-lookup"><span data-stu-id="49760-102">Managing application-level Response Group settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49760-103">_**主题上次修改时间：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="49760-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="49760-104">响应组应用程序的应用程序级别设置包括默认的 "保留音乐" 配置、默认的 "保留音乐" 音频文件、代理 ringback 宽限期和 "呼叫上下文配置"。</span><span class="sxs-lookup"><span data-stu-id="49760-104">Application-level settings for Response Group application include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="49760-105">你只能针对每个池定义一组应用程序级别设置。</span><span class="sxs-lookup"><span data-stu-id="49760-105">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="49760-106">若要查看应用程序级别设置，请使用 **Get-CsRgsConfiguration** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="49760-106">To view application-level settings, use the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="49760-107">若要修改应用程序级别设置，请使用 **Set-CsRgsConfiguration** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="49760-107">To modify the application-level settings, use the **Set-CsRgsConfiguration** cmdlet.</span></span>

<span data-ttu-id="49760-p102">只有未定义任何自定义保持音乐时，才会在呼叫处于呼叫等待状态时播放默认保持音乐。呼叫上下文仅适用于分配给互动工作流的队列。如果启用呼叫上下文，则代理可以在收到呼叫时查看呼叫者等待时间或工作流问题和解答等信息。</span><span class="sxs-lookup"><span data-stu-id="49760-p102">The default music on hold is played when a call is placed on hold only if no custom music on hold is defined. Call context is available only for queues assigned to interactive workflows. If call context is enabled, an agent can see information such as caller wait time or workflow questions and answers when the call is received.</span></span>

<div>

## <a name="to-modify-response-group-application-level-settings"></a><span data-ttu-id="49760-111">修改响应组应用程序级别设置</span><span class="sxs-lookup"><span data-stu-id="49760-111">To modify Response Group application-level settings</span></span>

1.  <span data-ttu-id="49760-112">以 RTCUniversalServerAdmins 组成员的身份，或支持响应组的某个预定义管理角色的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="49760-112">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="49760-113">启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="49760-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="49760-114">在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="49760-114">At the command line, run:</span></span>
    
        Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
    
    <span data-ttu-id="49760-115">例如：</span><span class="sxs-lookup"><span data-stu-id="49760-115">For example:</span></span>
    
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
    
    <span data-ttu-id="49760-p103">要指定一个音频文件以用作默认的保持音乐，您需要首先导入该音频文件。例如：</span><span class="sxs-lookup"><span data-stu-id="49760-p103">To specify an audio file to use as the default music on hold, you need to import the audio file first. For example:</span></span>
    
        $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="49760-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="49760-118">See Also</span></span>


[<span data-ttu-id="49760-119">CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="49760-119">Get-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration)  
[<span data-ttu-id="49760-120">Set-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="49760-120">Set-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsConfiguration)  
[<span data-ttu-id="49760-121">Import-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="49760-121">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

