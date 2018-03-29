---
title: 在 Skype for Business 2015 中配置呼叫寄存设置
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
description: 修改业务服务器企业语音在 Skype 呼叫公园设置。
ms.openlocfilehash: 56b0e2508fda61bddc94a6f8813708e8186c99c7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-call-park-settings-in-skype-for-business-2015"></a><span data-ttu-id="458b5-103">在 Skype for Business 2015 中配置呼叫寄存设置</span><span class="sxs-lookup"><span data-stu-id="458b5-103">Configure Call Park settings in Skype for Business 2015</span></span>
 
<span data-ttu-id="458b5-104">修改业务服务器企业语音在 Skype 呼叫公园设置。</span><span class="sxs-lookup"><span data-stu-id="458b5-104">Modify Call Park settings in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="458b5-105">如果您不想使用默认调用公园设置，您可以自定义它们。</span><span class="sxs-lookup"><span data-stu-id="458b5-105">If you don't want to use default Call Park settings, you can customize them.</span></span> <span data-ttu-id="458b5-106">调用公园应用程序安装时，默认情况下配置全局设置。</span><span class="sxs-lookup"><span data-stu-id="458b5-106">When you install the Call Park application, global settings are configured by default.</span></span> <span data-ttu-id="458b5-107">您可以修改全局设置，也可以指定特定于站点的设置。</span><span class="sxs-lookup"><span data-stu-id="458b5-107">You can modify the global settings, and you can also specify site-specific settings.</span></span> <span data-ttu-id="458b5-108">使用**New CsCpsConfiguration** cmdlet 来创建新的特定于站点的设置。</span><span class="sxs-lookup"><span data-stu-id="458b5-108">Use the **New-CsCpsConfiguration** cmdlet to create new site-specific settings.</span></span> <span data-ttu-id="458b5-109">使用**一组 CsCpsConfiguration** cmdlet 来修改现有的设置。</span><span class="sxs-lookup"><span data-stu-id="458b5-109">Use the **Set-CsCpsConfiguration** cmdlet to modify existing settings.</span></span>
  
> [!NOTE]
> <span data-ttu-id="458b5-110">寄存呼叫超时且回拨失败时，我们建议您至少为要使用的回退目标配置 **OnTimeoutURI** 选项。</span><span class="sxs-lookup"><span data-stu-id="458b5-110">At a minimum, we recommend that you configure the **OnTimeoutURI** option for the fallback destination to use when a parked call times out and ringback fails.</span></span>
  
<span data-ttu-id="458b5-111">使用**New CsCpsConfiguration** cmdlet 或**设置 CsCpsConfiguration** cmdlet 以配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="458b5-111">Use **New-CsCpsConfiguration** cmdlet or the **Set-CsCpsConfiguration** cmdlet to configure any of the following settings:</span></span>
  
|<span data-ttu-id="458b5-112">**这一选项：**</span><span class="sxs-lookup"><span data-stu-id="458b5-112">**This option:**</span></span>|<span data-ttu-id="458b5-113">**指定此：**</span><span class="sxs-lookup"><span data-stu-id="458b5-113">**Specifies this:**</span></span>|
|:-----|:-----|
|<span data-ttu-id="458b5-114">**CallPickupTimeoutThreshold**</span><span class="sxs-lookup"><span data-stu-id="458b5-114">**CallPickupTimeoutThreshold**</span></span> <br/> |<span data-ttu-id="458b5-115">呼叫寄存后到回拨此前应答呼叫的电话之前等待的时间。</span><span class="sxs-lookup"><span data-stu-id="458b5-115">The amount of time that elapses after a call has been parked before it rings back to the phone where the call was answered.</span></span>  <br/> <span data-ttu-id="458b5-p102">该值必须采用 hh:mm:ss 的格式输入，以便指定小时数、分钟数和秒数。最小值为 10 秒，最大值为 10 分钟。默认值为 00:01:30。</span><span class="sxs-lookup"><span data-stu-id="458b5-p102">The value must be entered in the format hh:mm:ss to specify the hours, minutes, and seconds. The minimum value is 10 seconds, and the maximum value is 10 minutes. The default is 00:01:30.</span></span>  <br/> |
|<span data-ttu-id="458b5-119">**EnableMusicOnHold**</span><span class="sxs-lookup"><span data-stu-id="458b5-119">**EnableMusicOnHold**</span></span> <br/> |<span data-ttu-id="458b5-120">寄存呼叫时是否向呼叫者播放音乐。</span><span class="sxs-lookup"><span data-stu-id="458b5-120">Whether music plays for a caller while a call is parked.</span></span>  <br/> <span data-ttu-id="458b5-p103">值为 True 或 False。默认值为 True。</span><span class="sxs-lookup"><span data-stu-id="458b5-p103">Values are True or False. The default is True.</span></span>  <br/> |
|<span data-ttu-id="458b5-123">**MaxCallPickupAttempts**</span><span class="sxs-lookup"><span data-stu-id="458b5-123">**MaxCallPickupAttempts**</span></span> <br/> |<span data-ttu-id="458b5-p104">在将寄存呼叫转接到为 **OnTimeoutURI** 指定的回退统一资源标识符 (URI) 之前该寄存呼叫回拨应答电话的次数。默认值为 1。</span><span class="sxs-lookup"><span data-stu-id="458b5-p104">The number of times a parked call rings back to the answering phone before it is forwarded to the fallback Uniform Resource Identifier (URI) that is specified for **OnTimeoutURI**. The default is 1.  </span></span><br/> |
|<span data-ttu-id="458b5-126">**OnTimeoutURI**</span><span class="sxs-lookup"><span data-stu-id="458b5-126">**OnTimeoutURI**</span></span> <br/> |<span data-ttu-id="458b5-127">超出 **MaxCallPickupAttempts** 时未应答的寄存呼叫将路由到的用户或响应组的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="458b5-127">The SIP address of the user or response group to which an unanswered parked call is routed when **MaxCallPickupAttempts** is exceeded.</span></span> <br/> <span data-ttu-id="458b5-p105">值必须为以字符串 sip: 开头的 SIP URI。例如，sip:bob@contoso.com。默认情况下没有转接地址。</span><span class="sxs-lookup"><span data-stu-id="458b5-p105">Value must be a SIP URI beginning with the string sip:. For example, sip:bob@contoso.com. The default is no forwarding address.  </span></span><br/> |
   
### <a name="to-configure-call-park-settings"></a><span data-ttu-id="458b5-130">若要配置呼叫公园设置</span><span class="sxs-lookup"><span data-stu-id="458b5-130">To configure Call Park settings</span></span>

1. <span data-ttu-id="458b5-131">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="458b5-131">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="458b5-132">运行：</span><span class="sxs-lookup"><span data-stu-id="458b5-132">Run:</span></span>
    
   ```
   New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
   ```

   > [!TIP]
   > <span data-ttu-id="458b5-133">使用**Get CsSite** cmdlet 来标识网站。</span><span class="sxs-lookup"><span data-stu-id="458b5-133">Use the **Get-CsSite** cmdlet to identify the site.</span></span> <span data-ttu-id="458b5-134">有关详细信息，请参阅 Lync 服务器管理外壳程序文档。</span><span class="sxs-lookup"><span data-stu-id="458b5-134">For details, see Lync Server Management Shell documentation.</span></span>
  
    <span data-ttu-id="458b5-135">例如：</span><span class="sxs-lookup"><span data-stu-id="458b5-135">For example:</span></span>
    
   ```
   New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com
   ```

## <a name="see-also"></a><span data-ttu-id="458b5-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="458b5-136">See also</span></span>

#### 

[<span data-ttu-id="458b5-137">自定义业务 2015年的封存 inSkype 上的调用公园音乐</span><span class="sxs-lookup"><span data-stu-id="458b5-137">Customize Call Park music on hold inSkype for Business 2015</span></span>](customize-call-park-music-on-hold.md)
#### 

[<span data-ttu-id="458b5-138">新 CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="458b5-138">New-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscpsconfiguration?view=skype-ps)
  
[<span data-ttu-id="458b5-139">一组 CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="458b5-139">Set-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscpsconfiguration?view=skype-ps)
  
[<span data-ttu-id="458b5-140">获得 CsSite</span><span class="sxs-lookup"><span data-stu-id="458b5-140">Get-CsSite</span></span>](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps)

