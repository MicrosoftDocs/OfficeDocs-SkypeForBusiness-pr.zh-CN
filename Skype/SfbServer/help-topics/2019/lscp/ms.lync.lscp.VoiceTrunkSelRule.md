---
title: 选择转换规则
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceTrunkSelRule
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 55776a94-4888-4436-a3b6-0e6f8252e392
ROBOTS: NOINDEX, NOFOLLOW
description: 企业语音要求所有拨号字符串规范化为 E.164 格式，以便执行 RNL (反向) 。 中继对等方（即，关联网关、PBX 或 SIP 中继）可能要求号码采用本地拨号格式。 要将 E.164 格式的号码转换为本地拨号格式，可以在将其路由至中继对等方之前，选择定义一个或多个转换规则以处理请求 URI。 例如，可以编写用于删除拨号串开头的 +44 并将其替换为 0144 的转换规则。
ms.openlocfilehash: 033cfca7fcbb9cde12b585b7086dd7a8bf8d4de8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801312"
---
# <a name="select-translation-rules"></a>选择转换规则
 
 企业语音要求所有拨号字符串规范化为 E.164 格式，以便执行 RNL (反向) 。 中继对等方（即，关联网关、PBX 或 SIP 中继）可能要求号码采用本地拨号格式。 要将 E.164 格式的号码转换为本地拨号格式，可以在将其路由至中继对等方之前，选择定义一个或多个转换规则以处理请求 URI。 例如，可以编写用于删除拨号串开头的 +44 并将其替换为 0144 的转换规则。
  
> [!IMPORTANT]
> 将一个或多个转换规则与企业语音中继配置进行关联的功能可用作在中继对等方上配置转换规则的备选方法。 如果已在中继对等方上配置转换规则，则不要将任何转换规则与企业语音中继配置相关联，因为这两个规则可能会发生冲突。 
  
要使用现有的转换规则，请单击列表中的某个规则，然后单击“确定”。
  
 
  

