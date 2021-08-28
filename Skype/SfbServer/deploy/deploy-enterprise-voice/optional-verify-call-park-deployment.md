---
title: " (中) 验证呼叫Skype for Business"
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: 验证呼叫管理中心中的呼叫Skype for Business Server 企业语音。
ms.openlocfilehash: 279f55e058678bdd33616a71642555b134052018
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58579946"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a> (中) 验证呼叫Skype for Business
 
验证呼叫管理中心中的呼叫Skype for Business Server 企业语音。 
  
安装和配置呼叫呼叫库后，需要验证配置以确保呼叫的停叫和取回按预期工作。 至少必须验证以下内容：
  
- 呼叫启用了呼叫管理的用户，并让用户将呼叫进行呼叫。
    
    > [!NOTE]
    > 如果在执行此测试前刚刚在语音策略中启用了呼叫库，则正在呼叫的呼叫被呼叫的用户需要注销 Skype for Business，然后重新登录，才能在转移呼叫列表中看到"呼叫离开"选项。 
  
- 拨打通道号码以取回此呼叫。
    
- 寄存其他呼叫，使之前寄存的呼叫超时，并且不接听回拨。验证超时的呼叫是否正确路由到为 **OnTimeoutURI** 指定的回退目标。
    

