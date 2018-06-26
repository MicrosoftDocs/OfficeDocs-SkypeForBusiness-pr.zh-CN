---
title: 选择转换规则
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceTrunkSelRule
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 55776a94-4888-4436-a3b6-0e6f8252e392
description: 企业语音要求所有拨号串都规范化为 E.164 格式，以便执行反向号码查找 （rnl） 会。 中继对等方（即，关联网关、PBX 或 SIP 中继）可能要求号码采用本地拨号格式。 要将 E.164 格式的号码转换为本地拨号格式，可以在将其路由至中继对等方之前，选择定义一个或多个转换规则以处理请求 URI。 例如，可以编写用于删除拨号串开头的 +44 并将其替换为 0144 的转换规则。
ms.openlocfilehash: 326d56aea92bf63e9ea813d91d2a3f7c816bce48
ms.sourcegitcommit: b42a6a56a0e1e4be1239174c1c3b4ab86517d043
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2018
ms.locfileid: "20044507"
---
# <a name="select-translation-rules"></a>选择转换规则
 
 企业语音要求所有拨号串都规范化为 E.164 格式，以便执行反向号码查找 （rnl） 会。 中继对等方（即，关联网关、PBX 或 SIP 中继）可能要求号码采用本地拨号格式。 要将 E.164 格式的号码转换为本地拨号格式，可以在将其路由至中继对等方之前，选择定义一个或多个转换规则以处理请求 URI。 例如，可以编写用于删除拨号串开头的 +44 并将其替换为 0144 的转换规则。
  
> [!IMPORTANT]
> 将一个或多个转换规则与企业语音中继配置相关联的功能旨在用作中继对等方上配置转换规则的替代项。 不关联转换规则与企业语音中继配置如果已在中继对等方上配置转换规则，因为这两种规则可能会发生冲突。 
  
要使用现有的转换规则，请单击列表中的某个规则，然后单击“**确定**”。
  
 
  

