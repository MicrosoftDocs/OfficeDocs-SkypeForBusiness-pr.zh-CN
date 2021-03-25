---
title: 在 Skype for Business 中配置语音邮件转义
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
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: 摘要：了解如何使用 Skype for Business Server 命令行管理程序在 Skype for Business Server 中配置语音邮件转义。
ms.openlocfilehash: c74142cf3b0f6c9d5a871e116d8e163a095ad3cd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106368"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a><span data-ttu-id="db78c-103">在 Skype for Business 中配置语音邮件转义</span><span class="sxs-lookup"><span data-stu-id="db78c-103">Configure voice mail escape in Skype for Business</span></span>

<span data-ttu-id="db78c-104">**摘要：** 了解如何使用 Skype for Business Server 命令行管理程序在 Skype for Business Server 中配置语音邮件转义。</span><span class="sxs-lookup"><span data-stu-id="db78c-104">**Summary:** Learn how to configure voice mail escape in Skype for Business Server by using the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="db78c-105">当用户配置移动电话的同时响铃时，如果移动电话已关闭、电池电量不足或范围外，呼叫者通常会路由到用户的个人语音邮件。</span><span class="sxs-lookup"><span data-stu-id="db78c-105">When a user configures simultaneous ringing to a mobile phone, a caller will typically be routed to the user's personal voice mail if the mobile phone is turned off, out of battery power, or out of range.</span></span> <span data-ttu-id="db78c-106">使用 Skype for Business Server，用户可以选择将业务相关的呼叫路由到其公司语音邮件系统。</span><span class="sxs-lookup"><span data-stu-id="db78c-106">With Skype for Business Server , users can opt to have business-related calls routed to their corporate voice mail system.</span></span> <span data-ttu-id="db78c-107">具体而言，可以配置计时器，如果运营商的语音邮件在定义的时间范围内应答呼叫，Skype for Business Server 将断开与运营商的语音邮件系统 (和用户的个人语音邮件) 的连接，同时企业系统中用户的剩余终结点将继续响铃。</span><span class="sxs-lookup"><span data-stu-id="db78c-107">Specifically, a timer can be configured, and if the call is answered by the carrier's voice mail within the range of time defined, Skype for Business Server will disconnect from the carrier's voice mail system (and the user's personal voice mail), while the user's remaining endpoints in the corporate system continue to ring.</span></span> <span data-ttu-id="db78c-108">这样，呼叫者会自动路由到用户的企业语音邮件。</span><span class="sxs-lookup"><span data-stu-id="db78c-108">This way, the caller is automatically routed to the user's corporate voice mail.</span></span>

<span data-ttu-id="db78c-109">此配置在语音策略级别使用 Skype for Business Server 命令行管理程序 cmdlet **Set-CsVoicePolicy** 执行，并具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="db78c-109">This configuration is performed using the Skype for Business Server Management Shell cmdlet, **Set-CsVoicePolicy**, at the voice policy level, with the following parameters.</span></span>

### <a name="to-configure-voice-mail-escape"></a><span data-ttu-id="db78c-110">配置语音邮件转义</span><span class="sxs-lookup"><span data-stu-id="db78c-110">To configure voice mail escape</span></span>

1. <span data-ttu-id="db78c-111">启动 Skype for Business Server命令行管理程序：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="db78c-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="db78c-112">指定 **Set-CsVoicePolicy** 的以下参数：</span><span class="sxs-lookup"><span data-stu-id="db78c-112">Specify the following parameters to **Set-CsVoicePolicy**:</span></span>

   - <span data-ttu-id="db78c-113">**EnableVoicemailEscapeTimer** - 启用或禁用转义计时器。</span><span class="sxs-lookup"><span data-stu-id="db78c-113">**EnableVoicemailEscapeTimer** - Enables or disables the escape timer.</span></span>

   - <span data-ttu-id="db78c-p102">**PSTNVoicemailEscapeTimer** - 指定超时值（以毫秒为单位）。默认值为 1500 毫秒，该值的范围可介于 0 到 8000 毫秒之间。</span><span class="sxs-lookup"><span data-stu-id="db78c-p102">**PSTNVoicemailEscapeTimer** - Specifies the timeout value in milliseconds. The default value is 1500 milliseconds, and the value can range from 0 milliseconds to 8000 milliseconds.</span></span>

## <a name="example"></a><span data-ttu-id="db78c-116">示例</span><span class="sxs-lookup"><span data-stu-id="db78c-116">Example</span></span>

```powershell
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a><span data-ttu-id="db78c-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="db78c-117">See also</span></span>

[<span data-ttu-id="db78c-118">配置语音策略和 PSTN 用法记录以授权呼叫功能和权限</span><span class="sxs-lookup"><span data-stu-id="db78c-118">Configuring Voice Policies and PSTN Usage Records to Authorize Calling Features and Privileges</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges)