---
title: （可选）在 Skype for Business 2015 中验证呼叫寄存部署
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: 正在验证业务服务器企业语音的部署在 Skype 呼叫公园。
ms.openlocfilehash: e8b3b0abd06ab8dc69bbe1fbcc5f091dd1350966
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business-2015"></a>（可选）在 Skype for Business 2015 中验证呼叫寄存部署
 
正在验证业务服务器企业语音的部署在 Skype 呼叫公园。 
  
安装和配置呼叫公园后，您需要验证配置以确保停车和检索调用能够如预期的那样工作。 至少必须验证以下内容：
  
- 调用具有调用公园启用的用户，并使用户公园呼叫。
    
    > [!NOTE]
    > 如果在进行这项测试之前在语音策略启用呼叫公园，停车呼叫的用户需要登录 Skype 的业务，并重新登录，以便能够查看呼叫清单显示的通话公园选项在传输中。 
  
- 拨打通道号码以取回此呼叫。
    
- 寄存其他呼叫，使之前寄存的呼叫超时，并且不接听回拨。验证超时的呼叫是否正确路由到为 **OnTimeoutURI** 指定的回退目标。
    

