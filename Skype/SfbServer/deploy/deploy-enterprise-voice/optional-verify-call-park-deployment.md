---
title: （可选）验证呼叫寄存部署中的业务的 Skype
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
ms.openlocfilehash: b07b3b3bfb709770a4f30f2f6cb43e5ce5dbcc3a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "21000527"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a>（可选）验证呼叫寄存部署中的业务的 Skype
 
验证业务 Server 企业语音的 Skype 中的呼叫寄存部署。 
  
在安装和配置呼叫寄存后，您需要验证配置以确保寄存和取回呼叫能够按预期方式。 至少必须验证以下内容：
  
- 呼叫启用呼叫寄存的用户并使用户寄存此呼叫。
    
    > [!NOTE]
    > 如果执行此测试之前在语音策略中启用呼叫寄存，已寄存呼叫的用户需要注销 Skype for Business，并重新登录，以便能够在传输中的呼叫寄存选项呼叫列表，请参阅。 
  
- 拨打通道号码以取回此呼叫。
    
- 寄存其他呼叫，使之前寄存的呼叫超时，并且不接听回拨。验证超时的呼叫是否正确路由到为 **OnTimeoutURI** 指定的回退目标。
    

