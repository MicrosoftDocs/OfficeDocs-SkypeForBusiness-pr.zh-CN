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
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a> (可选) Skype for Business 中验证呼叫等待部署
 
验证 Skype for Business Server 企业语音 中的呼叫企业语音。 
  
安装和配置呼叫库后，需要验证配置以确保呼叫的停叫和取回按预期方式工作。 至少必须验证以下内容：
  
- 呼叫已启用呼叫管理的用户，并让用户呼叫。
    
    > [!NOTE]
    > 如果你在执行此测试之前在语音策略中启用了呼叫等待，则等待呼叫的用户需要注销 Skype for Business，然后重新登录，才能在转接呼叫列表中看到呼叫等待选项。 
  
- 拨打通道号码以取回此呼叫。
    
- 寄存其他呼叫，使之前寄存的呼叫超时，并且不接听回拨。验证超时的呼叫是否正确路由到为 **OnTimeoutURI** 指定的回退目标。
    

