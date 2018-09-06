---
title: Skype 业务服务器中的转换规则
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
description: 了解转换规则，并拨号字符串规范化 Skype 中的业务 Server 企业语音。
ms.openlocfilehash: 9372ed2f0ab5f9ba2dcd4a37d54c3ef19300eb45
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2018
ms.locfileid: "23256893"
---
# <a name="translation-rules-in-skype-for-business-server"></a>Skype 业务服务器中的转换规则

了解转换规则，并拨号字符串规范化 Skype 中的业务 Server 企业语音。

 企业语音要求所有拨号串都规范化为 E.164 格式，以便执行反向号码查找 （rnl） 会。 支持呼叫的号码以及呼叫的号码转换规则。 Thetrunk 对等方 （即，关联的网关、 专用交换机 (PBX) 或 SIP 中继） 可能要求号码都本地拨号格式。 要将 E.164 格式的号码转换为本地拨号格式，可以在将其路由至中继对等方之前，定义一个或多个转换规则以处理请求 URI。 例如，可以编写用于删除拨号串开头的 +44 并将其替换为 0144 的转换规则。

通过在服务器上执行出站路由转换，可以降低每个单独中继对等方上的配置要求，以便将电话号码转换为本地拨号格式。 规划的网关和多少网关与特定的中介服务器群集，相关联时可能有用组中继对等方具有类似本地拨号要求。 这可减少所需的转换规则数和编写转换规则所需的时间。

> [!IMPORTANT]
> 将一个或多个转换规则与企业语音中继配置相关联应用作中继对等方上配置转换规则的替代项。 不关联转换规则与企业语音中继配置如果中继对等方上, 配置了转换规则因为这两种规则可能会发生冲突。

## <a name="example-translation-rules"></a>示例转换规则

以下示例转换规则说明了如何在服务器上开发将号码由 E.164 格式转换为适用于中继对等方的本地格式的规则。

有关如何实施转换规则的详细信息，请参阅部署文档中的[Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) 。

|**说明**|**起始数字**|**长度**|**要删除的数字**|**要添加的数字**|**匹配模式**|**转换**|**示例**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|美国常规长途拨号  <br/> (去掉 +)  <br/> |+ 1  <br/> |正好 12 位  <br/> |1  <br/> |0  <br/> |^\+(1\d{10}) $  <br/> |$1  <br/> |+14255551010 变为 14255551010  <br/> |
|美国国际长途拨号  <br/> (去掉 + 并添加 011)  <br/> |+  <br/> |至少 11 位  <br/> |1  <br/> |011  <br/> |^\+(\d{9}\d+)$  <br/> |011$1  <br/> |+441235551010 变为 011441235551010  <br/> |


