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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225630"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a>（可选）验证呼叫寄存部署中的业务的 Skype
 
验证业务 Server 企业语音的 Skype 中的呼叫寄存部署。 
  
在安装和配置呼叫寄存后，您需要验证配置以确保寄存和取回呼叫能够按预期方式。 至少必须验证以下内容：
  
- 呼叫启用呼叫寄存的用户并使用户寄存此呼叫。
    
    > [!NOTE]
    > 如果执行此测试之前在语音策略中启用呼叫寄存，已寄存呼叫的用户需要注销 Skype for Business，并重新登录，以便能够在传输中的呼叫寄存选项呼叫列表，请参阅。 
  
- 拨打通道号码以取回此呼叫。
    
- 寄存其他呼叫，使之前寄存的呼叫超时，并且不接听回拨。验证超时的呼叫是否正确路由到为 **OnTimeoutURI** 指定的回退目标。
    

