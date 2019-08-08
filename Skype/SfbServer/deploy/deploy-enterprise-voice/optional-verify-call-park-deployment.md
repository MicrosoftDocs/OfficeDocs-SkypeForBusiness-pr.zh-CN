---
title: 可选在 Skype for Business 中验证呼叫寄存部署
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: 在 Skype for Business Server Enterprise Voice 中验证呼叫寄存的部署。
ms.openlocfilehash: d698bf46f0a36a86729856c388fde09514288253
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240433"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a><span data-ttu-id="58575-103">可选在 Skype for Business 中验证呼叫寄存部署</span><span class="sxs-lookup"><span data-stu-id="58575-103">(Optional) Verify Call Park deployment in Skype for Business</span></span>
 
<span data-ttu-id="58575-104">在 Skype for Business Server Enterprise Voice 中验证呼叫寄存的部署。</span><span class="sxs-lookup"><span data-stu-id="58575-104">Verifying your deployment of Call Park in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="58575-105">安装并配置呼叫寄存后, 您需要验证配置, 以确保停车和检索呼叫按预期工作。</span><span class="sxs-lookup"><span data-stu-id="58575-105">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="58575-106">至少必须验证以下内容：</span><span class="sxs-lookup"><span data-stu-id="58575-106">At minimum, verify the following:</span></span>
  
- <span data-ttu-id="58575-107">呼叫已启用呼叫寄存并让用户寄存呼叫的用户。</span><span class="sxs-lookup"><span data-stu-id="58575-107">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="58575-108">如果在执行此测试之前已在语音策略中启用了呼叫寄存, 则离开呼叫的用户需要注销 Skype for Business, 然后重新登录, 以便能够在转接呼叫列表中看到呼叫寄存选项。</span><span class="sxs-lookup"><span data-stu-id="58575-108">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Skype for Business, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span> 
  
- <span data-ttu-id="58575-109">拨打通道号码以取回此呼叫。</span><span class="sxs-lookup"><span data-stu-id="58575-109">Dial the orbit number to retrieve the call.</span></span>
    
- <span data-ttu-id="58575-p102">寄存其他呼叫，使之前寄存的呼叫超时，并且不接听回拨。验证超时的呼叫是否正确路由到为 **OnTimeoutURI** 指定的回退目标。</span><span class="sxs-lookup"><span data-stu-id="58575-p102">Park another call, let the parked call time out, and do not pick up the ringback. Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>
    

