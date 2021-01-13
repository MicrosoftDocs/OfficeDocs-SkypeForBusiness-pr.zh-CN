---
title: " (可选) Skype for Business 中验证呼叫等待部署"
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
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: 验证 Skype for Business Server 企业语音 中的呼叫企业语音。
ms.openlocfilehash: a7edb9f47610bf7cdae068ca789670ab4048bb9c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830892"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a><span data-ttu-id="d4cd2-103"> (可选) Skype for Business 中验证呼叫等待部署</span><span class="sxs-lookup"><span data-stu-id="d4cd2-103">(Optional) Verify Call Park deployment in Skype for Business</span></span>
 
<span data-ttu-id="d4cd2-104">验证 Skype for Business Server 企业语音 中的呼叫企业语音。</span><span class="sxs-lookup"><span data-stu-id="d4cd2-104">Verifying your deployment of Call Park in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="d4cd2-105">安装和配置呼叫库后，需要验证配置以确保呼叫的停叫和取回按预期方式工作。</span><span class="sxs-lookup"><span data-stu-id="d4cd2-105">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="d4cd2-106">至少必须验证以下内容：</span><span class="sxs-lookup"><span data-stu-id="d4cd2-106">At minimum, verify the following:</span></span>
  
- <span data-ttu-id="d4cd2-107">呼叫已启用呼叫管理的用户，并让用户呼叫。</span><span class="sxs-lookup"><span data-stu-id="d4cd2-107">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d4cd2-108">如果你在执行此测试之前在语音策略中启用了呼叫等待，则等待呼叫的用户需要注销 Skype for Business，然后重新登录，才能在转接呼叫列表中看到呼叫等待选项。</span><span class="sxs-lookup"><span data-stu-id="d4cd2-108">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Skype for Business, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span> 
  
- <span data-ttu-id="d4cd2-109">拨打通道号码以取回此呼叫。</span><span class="sxs-lookup"><span data-stu-id="d4cd2-109">Dial the orbit number to retrieve the call.</span></span>
    
- <span data-ttu-id="d4cd2-p102">寄存其他呼叫，使之前寄存的呼叫超时，并且不接听回拨。验证超时的呼叫是否正确路由到为 **OnTimeoutURI** 指定的回退目标。</span><span class="sxs-lookup"><span data-stu-id="d4cd2-p102">Park another call, let the parked call time out, and do not pick up the ringback. Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>
    

