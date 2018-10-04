---
title: Skype for Business 中配置呼叫寄存设置
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
description: 修改 Skype 中的业务 Server 企业语音的呼叫寄存设置。
ms.openlocfilehash: 4a80b9e60085c3091aacbbf619f0dbe672b64251
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373675"
---
# <a name="configure-call-park-settings-in-skype-for-business"></a><span data-ttu-id="cc8fb-103">Skype for Business 中配置呼叫寄存设置</span><span class="sxs-lookup"><span data-stu-id="cc8fb-103">Configure Call Park settings in Skype for Business</span></span>

<span data-ttu-id="cc8fb-104">修改 Skype 中的业务 Server 企业语音的呼叫寄存设置。</span><span class="sxs-lookup"><span data-stu-id="cc8fb-104">Modify Call Park settings in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="cc8fb-105">如果您不想要使用默认呼叫寄存设置，您可以自定义它们。</span><span class="sxs-lookup"><span data-stu-id="cc8fb-105">If you don't want to use default Call Park settings, you can customize them.</span></span> <span data-ttu-id="cc8fb-106">安装呼叫寄存应用程序时，默认情况下配置全局设置。</span><span class="sxs-lookup"><span data-stu-id="cc8fb-106">When you install the Call Park application, global settings are configured by default.</span></span> <span data-ttu-id="cc8fb-107">您可以修改全局设置，也可以指定特定于站点的设置。</span><span class="sxs-lookup"><span data-stu-id="cc8fb-107">You can modify the global settings, and you can also specify site-specific settings.</span></span> <span data-ttu-id="cc8fb-108">使用**New-cscpsconfiguration** cmdlet 创建新网站特定设置。</span><span class="sxs-lookup"><span data-stu-id="cc8fb-108">Use the **New-CsCpsConfiguration** cmdlet to create new site-specific settings.</span></span> <span data-ttu-id="cc8fb-109">使用**Set-cscpsconfiguration** cmdlet 可修改现有的设置。</span><span class="sxs-lookup"><span data-stu-id="cc8fb-109">Use the **Set-CsCpsConfiguration** cmdlet to modify existing settings.</span></span>

> [!NOTE]
> <span data-ttu-id="cc8fb-110">寄存呼叫超时且回拨失败时，我们建议您至少为要使用的回退目标配置 **OnTimeoutURI** 选项。</span><span class="sxs-lookup"><span data-stu-id="cc8fb-110">At a minimum, we recommend that you configure the **OnTimeoutURI** option for the fallback destination to use when a parked call times out and ringback fails.</span></span>

<span data-ttu-id="cc8fb-111">使用**New-cscpsconfiguration** cmdlet 或**Set-cscpsconfiguration** cmdlet 配置以下设置之一：</span><span class="sxs-lookup"><span data-stu-id="cc8fb-111">Use **New-CsCpsConfiguration** cmdlet or the **Set-CsCpsConfiguration** cmdlet to configure any of the following settings:</span></span>


| <span data-ttu-id="cc8fb-112">**此选项：**</span><span class="sxs-lookup"><span data-stu-id="cc8fb-112">**This option:**</span></span>                     | <span data-ttu-id="cc8fb-113">**指定以下内容：**</span><span class="sxs-lookup"><span data-stu-id="cc8fb-113">**Specifies this:**</span></span>                                                                                                                                                                                                                                                                                                                   |
|:-------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="cc8fb-114">**配置 CallPickupTimeoutThreshold**</span><span class="sxs-lookup"><span data-stu-id="cc8fb-114">**CallPickupTimeoutThreshold**</span></span> <br/> | <span data-ttu-id="cc8fb-115">呼叫寄存后到回拨此前应答呼叫的电话之前等待的时间。</span><span class="sxs-lookup"><span data-stu-id="cc8fb-115">The amount of time that elapses after a call has been parked before it rings back to the phone where the call was answered.</span></span>  <br/> <span data-ttu-id="cc8fb-p102">该值必须采用 hh:mm:ss 的格式输入，以便指定小时数、分钟数和秒数。最小值为 10 秒，最大值为 10 分钟。默认值为 00:01:30。</span><span class="sxs-lookup"><span data-stu-id="cc8fb-p102">The value must be entered in the format hh:mm:ss to specify the hours, minutes, and seconds. The minimum value is 10 seconds, and the maximum value is 10 minutes. The default is 00:01:30.</span></span>  <br/> |
| <span data-ttu-id="cc8fb-119">**配置 EnableMusicOnHold**</span><span class="sxs-lookup"><span data-stu-id="cc8fb-119">**EnableMusicOnHold**</span></span> <br/>          | <span data-ttu-id="cc8fb-120">寄存呼叫时是否向呼叫者播放音乐。</span><span class="sxs-lookup"><span data-stu-id="cc8fb-120">Whether music plays for a caller while a call is parked.</span></span>  <br/> <span data-ttu-id="cc8fb-p103">值为 True 或 False。默认值为 True。</span><span class="sxs-lookup"><span data-stu-id="cc8fb-p103">Values are True or False. The default is True.</span></span>  <br/>                                                                                                                                                                                                                 |
| <span data-ttu-id="cc8fb-123">**MaxCallPickupAttempts**</span><span class="sxs-lookup"><span data-stu-id="cc8fb-123">**MaxCallPickupAttempts**</span></span> <br/>      | <span data-ttu-id="cc8fb-p104">在将寄存呼叫转接到为 **OnTimeoutURI** 指定的回退统一资源标识符 (URI) 之前该寄存呼叫回拨应答电话的次数。默认值为 1。</span><span class="sxs-lookup"><span data-stu-id="cc8fb-p104">The number of times a parked call rings back to the answering phone before it is forwarded to the fallback Uniform Resource Identifier (URI) that is specified for **OnTimeoutURI**. The default is 1.  </span></span><br/>                                                                                                                         |
| <span data-ttu-id="cc8fb-126">**OnTimeoutURI**</span><span class="sxs-lookup"><span data-stu-id="cc8fb-126">**OnTimeoutURI**</span></span> <br/>               | <span data-ttu-id="cc8fb-127">超出 **MaxCallPickupAttempts** 时未应答的寄存呼叫将路由到的用户或响应组的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="cc8fb-127">The SIP address of the user or response group to which an unanswered parked call is routed when **MaxCallPickupAttempts** is exceeded.</span></span> <br/> <span data-ttu-id="cc8fb-p105">值必须为以字符串 sip: 开头的 SIP URI。例如，sip:bob@contoso.com。默认情况下没有转接地址。</span><span class="sxs-lookup"><span data-stu-id="cc8fb-p105">Value must be a SIP URI beginning with the string sip:. For example, sip:bob@contoso.com. The default is no forwarding address.  </span></span><br/>                                                   |

### <a name="to-configure-call-park-settings"></a><span data-ttu-id="cc8fb-131">配置呼叫寄存设置</span><span class="sxs-lookup"><span data-stu-id="cc8fb-131">To configure Call Park settings</span></span>

1. <span data-ttu-id="cc8fb-132">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="cc8fb-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="cc8fb-133">运行：</span><span class="sxs-lookup"><span data-stu-id="cc8fb-133">Run:</span></span>

   ```
   New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
   ```

   > [!TIP]
   > <span data-ttu-id="cc8fb-134">使用**Get-cssite** cmdlet 来标识该网站。</span><span class="sxs-lookup"><span data-stu-id="cc8fb-134">Use the **Get-CsSite** cmdlet to identify the site.</span></span> <span data-ttu-id="cc8fb-135">有关详细信息，请参阅 for Business Server Management Shell 文档的 Skype。</span><span class="sxs-lookup"><span data-stu-id="cc8fb-135">For details, see Skype for Business Server Management Shell documentation.</span></span>

    <span data-ttu-id="cc8fb-136">例如：</span><span class="sxs-lookup"><span data-stu-id="cc8fb-136">For example:</span></span>

   ```
   New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com
   ```

## <a name="see-also"></a><span data-ttu-id="cc8fb-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cc8fb-137">See also</span></span>

[<span data-ttu-id="cc8fb-138">在 Skype for Business 2015 中自定义呼叫寄存保持音乐</span><span class="sxs-lookup"><span data-stu-id="cc8fb-138">Customize Call Park music on hold inSkype for Business 2015</span></span>](customize-call-park-music-on-hold.md)

[<span data-ttu-id="cc8fb-139">新 CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="cc8fb-139">New-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscpsconfiguration?view=skype-ps)

[<span data-ttu-id="cc8fb-140">Set-cscpsconfiguration</span><span class="sxs-lookup"><span data-stu-id="cc8fb-140">Set-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscpsconfiguration?view=skype-ps)

[<span data-ttu-id="cc8fb-141">Get-cssite</span><span class="sxs-lookup"><span data-stu-id="cc8fb-141">Get-CsSite</span></span>](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps)