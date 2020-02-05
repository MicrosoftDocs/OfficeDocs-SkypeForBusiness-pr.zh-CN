---
title: 可选在 Skype for Business 中验证呼叫寄存部署
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: 在 Skype for Business Server Enterprise Voice 中验证呼叫寄存的部署。
ms.openlocfilehash: 7dfaf916e94db18c3b53fc7e9c9e3b136fa445b8
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767335"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a>可选在 Skype for Business 中验证呼叫寄存部署
 
在 Skype for Business Server Enterprise Voice 中验证呼叫寄存的部署。 
  
安装并配置呼叫寄存后，您需要验证配置，以确保停车和检索呼叫按预期工作。 至少必须验证以下内容：
  
- 呼叫已启用呼叫寄存并让用户寄存呼叫的用户。
    
    > [!NOTE]
    > 如果在执行此测试之前已在语音策略中启用了呼叫寄存，则离开呼叫的用户需要注销 Skype for Business，然后重新登录，以便能够在转接呼叫列表中看到呼叫寄存选项。 
  
- 拨打通道号码以取回此呼叫。
    
- 寄存其他呼叫，使之前寄存的呼叫超时，并且不接听回拨。验证超时的呼叫是否正确路由到为 **OnTimeoutURI** 指定的回退目标。
    

