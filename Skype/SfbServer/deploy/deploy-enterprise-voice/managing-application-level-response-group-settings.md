---
title: 在 Skype for Business 中管理应用程序级响应组设置
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
ms.assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
description: 在 Skype for Business Server 企业语音 中管理应用程序级响应组设置，如保持音乐设置和回企业语音。
ms.openlocfilehash: d41211b83e5ce0c27bb9efe1d3d15a6289ae38fe
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830782"
---
# <a name="managing-application-level-response-group-settings-in-skype-for-business"></a><span data-ttu-id="6d085-103">在 Skype for Business 中管理应用程序级响应组设置</span><span class="sxs-lookup"><span data-stu-id="6d085-103">Managing application-level Response Group settings in Skype for Business</span></span>
 
<span data-ttu-id="6d085-104">在 Skype for Business Server 企业语音 中管理应用程序级响应组设置，如保持音乐设置和回企业语音。</span><span class="sxs-lookup"><span data-stu-id="6d085-104">Managing application-level Response Group settings, such as music-on-hold and ringback settings, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="6d085-105">响应组应用程序的应用程序级别设置包括默认的保持音乐配置、默认的保持音乐音频文件、代理回响宽限期和呼叫上下文配置。</span><span class="sxs-lookup"><span data-stu-id="6d085-105">Application-level settings for Response Group application include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="6d085-106">您只能针对每个池定义一组应用程序级别设置。</span><span class="sxs-lookup"><span data-stu-id="6d085-106">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="6d085-107">要查看应用程序级别设置，请使用 **Get-CsRgsConfiguration** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6d085-107">To view application-level settings, use the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="6d085-108">要修改应用程序级别设置，请使用 **Set-CsRgsConfiguration** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6d085-108">To modify the application-level settings, use the **Set-CsRgsConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="6d085-p102">只有未定义任何自定义保持音乐时，才会在呼叫处于呼叫等待状态时播放默认保持音乐。呼叫上下文仅适用于分配给互动工作流的队列。如果启用呼叫上下文，则代理可以在收到呼叫时查看呼叫者等待时间或工作流问题和解答等信息。</span><span class="sxs-lookup"><span data-stu-id="6d085-p102">The default music on hold is played when a call is placed on hold only if no custom music on hold is defined. Call context is available only for queues assigned to interactive workflows. If call context is enabled, an agent can see information such as caller wait time or workflow questions and answers when the call is received.</span></span>
  
### <a name="to-modify-response-group-application-level-settings"></a><span data-ttu-id="6d085-112">修改响应组应用程序级设置</span><span class="sxs-lookup"><span data-stu-id="6d085-112">To modify Response Group application-level settings</span></span>

1. <span data-ttu-id="6d085-113">以 RTCUniversalServerAdmins 组的成员或支持响应组的预定义管理角色之一的成员登录。</span><span class="sxs-lookup"><span data-stu-id="6d085-113">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="6d085-114">启动 Skype for Business Server命令行管理程序：单击"开始"，**单击"所有** 程序"，再单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="6d085-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="6d085-115">在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="6d085-115">At the command line, run:</span></span>
    
   ```powershell
   Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
   ```

    <span data-ttu-id="6d085-116">例如：</span><span class="sxs-lookup"><span data-stu-id="6d085-116">For example:</span></span>
    
   ```powershell
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
   ```

    <span data-ttu-id="6d085-p103">要指定一个音频文件以用作默认的保持音乐，您需要首先导入该音频文件。例如：</span><span class="sxs-lookup"><span data-stu-id="6d085-p103">To specify an audio file to use as the default music on hold, you need to import the audio file first. For example:</span></span>
    
   ```powershell
   $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>
   ```

## <a name="see-also"></a><span data-ttu-id="6d085-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6d085-119">See also</span></span>

[<span data-ttu-id="6d085-120">Get-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="6d085-120">Get-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csrgsconfiguration?view=skype-ps)
  
[<span data-ttu-id="6d085-121">Set-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="6d085-121">Set-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csrgsconfiguration?view=skype-ps)
  
[<span data-ttu-id="6d085-122">Import-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="6d085-122">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
