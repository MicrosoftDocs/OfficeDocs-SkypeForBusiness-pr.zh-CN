---
title: （可选）验证呼叫寄存部署中的业务的 Skype
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: 验证业务 Server 企业语音的 Skype 中的呼叫寄存部署。
ms.openlocfilehash: 514c82590d56a2de16ca31cc892032afe5e7a34c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895095"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a><span data-ttu-id="c68bc-103">（可选）验证呼叫寄存部署中的业务的 Skype</span><span class="sxs-lookup"><span data-stu-id="c68bc-103">(Optional) Verify Call Park deployment in Skype for Business</span></span>
 
<span data-ttu-id="c68bc-104">验证业务 Server 企业语音的 Skype 中的呼叫寄存部署。</span><span class="sxs-lookup"><span data-stu-id="c68bc-104">Verifying your deployment of Call Park in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="c68bc-105">在安装和配置呼叫寄存后，您需要验证配置以确保寄存和取回呼叫能够按预期方式。</span><span class="sxs-lookup"><span data-stu-id="c68bc-105">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="c68bc-106">至少必须验证以下内容：</span><span class="sxs-lookup"><span data-stu-id="c68bc-106">At minimum, verify the following:</span></span>
  
- <span data-ttu-id="c68bc-107">呼叫启用呼叫寄存的用户并使用户寄存此呼叫。</span><span class="sxs-lookup"><span data-stu-id="c68bc-107">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c68bc-108">如果执行此测试之前在语音策略中启用呼叫寄存，已寄存呼叫的用户需要注销 Skype for Business，并重新登录，以便能够在传输中的呼叫寄存选项呼叫列表，请参阅。</span><span class="sxs-lookup"><span data-stu-id="c68bc-108">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Skype for Business, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span> 
  
- <span data-ttu-id="c68bc-109">拨打通道号码以取回此呼叫。</span><span class="sxs-lookup"><span data-stu-id="c68bc-109">Dial the orbit number to retrieve the call.</span></span>
    
- <span data-ttu-id="c68bc-p102">寄存其他呼叫，使之前寄存的呼叫超时，并且不接听回拨。验证超时的呼叫是否正确路由到为 **OnTimeoutURI** 指定的回退目标。</span><span class="sxs-lookup"><span data-stu-id="c68bc-p102">Park another call, let the parked call time out, and do not pick up the ringback. Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>
    

