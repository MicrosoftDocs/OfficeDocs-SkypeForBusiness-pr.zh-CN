---
title: 转换规则中的Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
description: 了解呼叫中的转换规则和拨号字符串Skype for Business Server 企业语音。
ms.openlocfilehash: 1ad2434a0f57e57f6d86b8bda0c9c2e7af6c3de9
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60841004"
---
# <a name="translation-rules-in-skype-for-business-server"></a>转换规则中的Skype for Business Server

了解呼叫中的转换规则和拨号字符串Skype for Business Server 企业语音。

 企业语音要求所有拨号串规范化为 E.164 格式，以便执行 RNL (反向号码) 。 被叫号码和呼叫号码均支持转换规则。 中继对等 (，即关联网关、专用交换机 (PBX) 或 SIP 中继) 可能要求号码采用本地拨号格式。 要将 E.164 格式的号码转换为本地拨号格式，可以在将其路由至中继对等方之前，定义一个或多个转换规则以处理请求 URI。 例如，可以编写用于删除拨号串开头的 +44 并将其替换为 0144 的转换规则。

通过在服务器上执行出站路由转换，可以降低每个单独中继对等方上的配置要求，以便将电话号码转换为本地拨号格式。 在规划要与特定中介服务器群集关联的网关和网关数时，将具有类似本地拨号要求的中继对等方分组可能很有用。 这可减少所需的转换规则数和编写转换规则所需的时间。

> [!IMPORTANT]
> 将一个或多个转换规则与企业语音中继配置相关联，作为在中继对等方上配置转换规则的替代方法。 如果在中继对等方上配置了转换规则，则不要将转换规则与企业语音中继配置关联，因为这两个规则可能会发生冲突。

## <a name="example-translation-rules"></a>示例转换规则

以下示例转换规则说明了如何在服务器上开发将号码由 E.164 格式转换为适用于中继对等方的本地格式的规则。

有关如何实施转换规则的详细信息，请参阅部署文档中的[Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules)。

|**说明**|**起始数字**|**长度**|**要删除的数字**|**要添加的数字**|**匹配模式**|**翻译**|**示例**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|美国常规长途拨号  <br/>  (去除"+")   <br/> |+1  <br/> |正好 12 位  <br/> |1  <br/> |0  <br/> |^\+ (1\d {10}) $  <br/> |$1  <br/> |+14255551010 变为 14255551010  <br/> |
|美国国际长途拨号  <br/>  ("+"，然后添加 011)   <br/> |+  <br/> |至少 11 位  <br/> |1  <br/> |011  <br/> |^\+ (\d {9} \d+) $  <br/> |011$1  <br/> |+441235551010 变为 011441235551010  <br/> |