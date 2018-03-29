---
title: 选择转换规则
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceTrunkSelRule
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 55776a94-4888-4436-a3b6-0e6f8252e392
description: 企业语音要求所有拨号字符串被都正常化为 E.164 格式以便执行反向号码查询 (RNL)。 中继对等方（即，关联网关、PBX 或 SIP 中继）可能要求号码采用本地拨号格式。 要将 E.164 格式的号码转换为本地拨号格式，可以在将其路由至中继对等方之前，选择定义一个或多个转换规则以处理请求 URI。 例如，可以编写用于删除拨号串开头的 +44 并将其替换为 0144 的转换规则。
ms.openlocfilehash: ab2a39442ce41f96769668d19de0694d4a464a4b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="select-translation-rules"></a>选择转换规则
 
 企业语音要求所有拨号字符串被都正常化为 E.164 格式以便执行反向号码查询 (RNL)。 中继对等方（即，关联网关、PBX 或 SIP 中继）可能要求号码采用本地拨号格式。 要将 E.164 格式的号码转换为本地拨号格式，可以在将其路由至中继对等方之前，选择定义一个或多个转换规则以处理请求 URI。 例如，可以编写用于删除拨号串开头的 +44 并将其替换为 0144 的转换规则。
  
> [!IMPORTANT]
> 将一个或多个转换规则与企业语音中继配置相关联的功能旨在用作对干线等配置转换规则的一种替代方法。 不关联翻译规则与企业语音中继配置如果您已配置对干线等转换规则，因为那两个规则可能发生冲突。 
  
要使用现有的转换规则，请单击列表中的某个规则，然后单击“**确定**”。
  
您还可以通过 Skype 业务服务器控件面板的不同过程的详细信息，请参阅[管理的业务服务器 2015年的 Skype](../../manage/manage.md)。
  

