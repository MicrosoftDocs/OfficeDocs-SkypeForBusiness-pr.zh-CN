---
title: Skype for Business 中配置语音邮件转义
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: 摘要： 了解如何使用 Skype 业务 Server Management Shell，业务服务器配置语音邮件转义 Skype。
ms.openlocfilehash: 6c1c6977949eb45c28cce482f98be67295ee4eef
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891865"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a><span data-ttu-id="eff79-103">Skype for Business 中配置语音邮件转义</span><span class="sxs-lookup"><span data-stu-id="eff79-103">Configure voice mail escape in Skype for Business</span></span>

<span data-ttu-id="eff79-104">**摘要：** 了解如何使用 Skype 业务 Server Management Shell，业务服务器配置语音邮件转义 Skype。</span><span class="sxs-lookup"><span data-stu-id="eff79-104">**Summary:** Learn how to configure voice mail escape in Skype for Business Server by using the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="eff79-105">当用户配置到移动电话同时响铃时，呼叫者将通常路由到用户的个人语音邮件，如果移动电话处于关闭、 电池供电不足或超出范围。</span><span class="sxs-lookup"><span data-stu-id="eff79-105">When a user configures simultaneous ringing to a mobile phone, a caller will typically be routed to the user's personal voice mail if the mobile phone is turned off, out of battery power, or out of range.</span></span> <span data-ttu-id="eff79-106">与业务服务器 Skype，用户可以选择使与业务相关的呼叫路由至其企业语音邮件系统。</span><span class="sxs-lookup"><span data-stu-id="eff79-106">With Skype for Business Server , users can opt to have business-related calls routed to their corporate voice mail system.</span></span> <span data-ttu-id="eff79-107">具体而言，可以配置计时器，并且 Skype 业务服务器如果通过定义的时间范围内的运营商的语音邮件应答呼叫时，将断开连接从运营商的语音邮件系统 （和用户的个人语音邮件），当用户企业系统中的其余终结点继续响铃。</span><span class="sxs-lookup"><span data-stu-id="eff79-107">Specifically, a timer can be configured, and if the call is answered by the carrier's voice mail within the range of time defined, Skype for Business Server will disconnect from the carrier's voice mail system (and the user's personal voice mail), while the user's remaining endpoints in the corporate system continue to ring.</span></span> <span data-ttu-id="eff79-108">这种方式，呼叫者会自动传送到用户的企业语音邮件。</span><span class="sxs-lookup"><span data-stu-id="eff79-108">This way, the caller is automatically routed to the user's corporate voice mail.</span></span>

<span data-ttu-id="eff79-109">Skype 用于业务 Server Management Shell cmdlet **Set-csvoicepolicy**，在语音策略级别，使用以下参数执行此配置。</span><span class="sxs-lookup"><span data-stu-id="eff79-109">This configuration is performed using the Skype for Business Server Management Shell cmdlet, **Set-CsVoicePolicy**, at the voice policy level, with the following parameters.</span></span>

### <a name="to-configure-voice-mail-escape"></a><span data-ttu-id="eff79-110">配置语音邮件转义</span><span class="sxs-lookup"><span data-stu-id="eff79-110">To configure voice mail escape</span></span>

1. <span data-ttu-id="eff79-111">启动 Skype for Business Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\* 和“Skype for Business 2015”\*\*\*\*，然后单击“Skype for Business Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="eff79-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="eff79-112">指定 **Set-CsVoicePolicy** 的以下参数：</span><span class="sxs-lookup"><span data-stu-id="eff79-112">Specify the following parameters to **Set-CsVoicePolicy**:</span></span>

   - <span data-ttu-id="eff79-113">**EnableVoicemailEscapeTimer** - 启用或禁用转义计时器。</span><span class="sxs-lookup"><span data-stu-id="eff79-113">**EnableVoicemailEscapeTimer** - Enables or disables the escape timer.</span></span>

   - <span data-ttu-id="eff79-p102">**PSTNVoicemailEscapeTimer** - 指定超时值（以毫秒为单位）。默认值为 1500 毫秒，该值的范围可介于 0 到 8000 毫秒之间。</span><span class="sxs-lookup"><span data-stu-id="eff79-p102">**PSTNVoicemailEscapeTimer** - Specifies the timeout value in milliseconds. The default value is 1500 milliseconds, and the value can range from 0 milliseconds to 8000 milliseconds.</span></span>

## <a name="example"></a><span data-ttu-id="eff79-116">示例</span><span class="sxs-lookup"><span data-stu-id="eff79-116">Example</span></span>

```
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a><span data-ttu-id="eff79-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eff79-117">See also</span></span>

[<span data-ttu-id="eff79-118">Configuring Voice Policies and PSTN Usage Records to Authorize Calling Features and Privileges</span><span class="sxs-lookup"><span data-stu-id="eff79-118">Configuring Voice Policies and PSTN Usage Records to Authorize Calling Features and Privileges</span></span>](https://technet.microsoft.com/library/63f22010-a3d7-4cbd-86e8-6fc0e13c2b84.aspx)

