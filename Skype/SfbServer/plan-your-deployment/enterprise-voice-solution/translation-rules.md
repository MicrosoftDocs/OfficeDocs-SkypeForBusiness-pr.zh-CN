---
title: Skype for Business Server 2015 中的转换规则
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
description: 了解有关转换规则和拨号字符串正常化在 Skype 的业务服务器企业语音。
ms.openlocfilehash: ff3718e89d152a2b6c7d1c78ccaaa055d00ffcdb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="translation-rules-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的转换规则
 
了解有关转换规则和拨号字符串正常化在 Skype 的业务服务器企业语音。
  
 企业语音要求所有拨号字符串被都正常化为 E.164 格式以便执行反向号码查询 (RNL)。 转换规则支持拨电话号码和呼叫的号码。 Thetrunk 等 （即关联的网关、 专用分组交换机 (PBX) 或 SIP 中继） 可能要求数字都以本地拨号的格式。 要将 E.164 格式的号码转换为本地拨号格式，可以在将其路由至中继对等方之前，定义一个或多个转换规则以处理请求 URI。 例如，可以编写用于删除拨号串开头的 +44 并将其替换为 0144 的转换规则。
  
通过在服务器上执行出站路由转换，可以降低每个单独中继对等方上的配置要求，以便将电话号码转换为本地拨号格式。 规划的网关和多少网关与一个特定的中介服务器群集时可能很有用到组干线对等方具有类似本地拨号要求。 这可减少所需的转换规则数和编写转换规则所需的时间。
  
> [!IMPORTANT]
> 应作为对干线等配置转换规则的另一种方法将一个或多个转换规则与企业语音中继配置相关联。 不关联转换规则与企业语音中继配置如果您已配置转换规则对干线等，因为那两个规则可能发生冲突。 
  
## <a name="example-translation-rules"></a>示例转换规则

以下示例转换规则说明了如何在服务器上开发将号码由 E.164 格式转换为适用于中继对等方的本地格式的规则。
  
有关如何实现转换规则的详细信息，请参阅部署文档中[定义的转换规则](http://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)。
  
|**说明**|**起始位**|**长度**|**删除位**|**若要添加的数字**|**匹配模式**|**转换**|**示例**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|美国常规长途拨号  <br/> (去除 +)  <br/> |+ 1  <br/> |正好 12 位  <br/> |1  <br/> |0  <br/> |^\+(1\d {10}) $  <br/> |$1  <br/> |+14255551010 变为 14255551010  <br/> |
|美国国际长途拨号  <br/> (去除 +，并添加 011)  <br/> |+  <br/> |至少 11 位  <br/> |1  <br/> |011  <br/> |^\+(\d{9}\d+)$  <br/> |011$1  <br/> |+441235551010 变为 011441235551010  <br/> |
   

