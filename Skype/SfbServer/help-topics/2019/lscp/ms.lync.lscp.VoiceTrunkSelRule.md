---
title: 选择转换规则
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceTrunkSelRule
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 55776a94-4888-4436-a3b6-0e6f8252e392
ROBOTS: NOINDEX, NOFOLLOW
description: 企业语音需要将所有拨号串规范化为 E.164 格式，以便执行 RNL (反向号码) 。 中继对等方（即，关联网关、PBX 或 SIP 中继）可能要求号码采用本地拨号格式。 要将 E.164 格式的号码转换为本地拨号格式，可以在将其路由至中继对等方之前，选择定义一个或多个转换规则以处理请求 URI。 例如，可以编写用于删除拨号串开头的 +44 并将其替换为 0144 的转换规则。
ms.openlocfilehash: 164986f47dbbc7bbe14e9612f0091448ba1f9364
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60859469"
---
# <a name="select-translation-rules"></a>选择转换规则
 
 企业语音需要将所有拨号串规范化为 E.164 格式，以便执行 RNL (反向号码) 。 中继对等方（即，关联网关、PBX 或 SIP 中继）可能要求号码采用本地拨号格式。 要将 E.164 格式的号码转换为本地拨号格式，可以在将其路由至中继对等方之前，选择定义一个或多个转换规则以处理请求 URI。 例如，可以编写用于删除拨号串开头的 +44 并将其替换为 0144 的转换规则。
  
> [!IMPORTANT]
> 将一个或多个转换规则与企业语音中继配置进行关联的功能可用作在中继对等方上配置转换规则的备选方法。如果已在中继对等方上配置转换规则，则不要将任何转换规则与企业语音中继配置相关联，因为这两个规则可能会发生冲突。 
  
要使用现有的转换规则，请单击列表中的某个规则，然后单击“确定”。
  
 
  

