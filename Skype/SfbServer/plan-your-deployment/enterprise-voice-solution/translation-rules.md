---
title: Skype for Business 服务器中的翻译规则
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
description: 了解有关翻译规则和在 Skype for Business Server 企业语音中拨打字符串规范化的信息。
ms.openlocfilehash: c82b925c9ef168d8a5f5e7ac730a93a53a432e2d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802392"
---
# <a name="translation-rules-in-skype-for-business-server"></a>Skype for Business 服务器中的翻译规则

了解有关翻译规则和在 Skype for Business Server 企业语音中拨打字符串规范化的信息。

 对于执行反向数字查找（RNL），企业语音要求将所有拨号字符串正常化为 E-164 格式。 同时支持被呼叫号码和通话号码的翻译规则。 Thetrunk 对等（即关联网关、专用分支交换（PBX）或 SIP 干线）可能要求数字采用本地拨号格式。 要将 E.164 格式的号码转换为本地拨号格式，可以在将其路由至中继对等方之前，定义一个或多个转换规则以处理请求 URI。 例如，可以编写用于删除拨号串开头的 +44 并将其替换为 0144 的转换规则。

通过在服务器上执行出站路由转换，可以降低每个单独中继对等方上的配置要求，以便将电话号码转换为本地拨号格式。 在规划要与特定中介服务器群集关联的网关和多少个网关时，使用类似的本地拨号要求对干线对等进行分组可能非常有用。 这可减少所需的转换规则数和编写转换规则所需的时间。

> [!IMPORTANT]
> 将一个或多个翻译规则与企业语音中继配置相关联应用作在中继对等上配置翻译规则的替代方法。 如果你已在中继对等上配置了转换规则，请不要将翻译规则与企业语音中继配置相关联，因为这两个规则可能会发生冲突。

## <a name="example-translation-rules"></a>示例转换规则

以下示例转换规则说明了如何在服务器上开发将号码由 E.164 格式转换为适用于中继对等方的本地格式的规则。

有关如何实施转换规则的详细信息，请参阅部署文档中的 [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)。

|**说明**|**起始数字**|**长度**|**要删除的数字**|**要添加的数字**|**匹配模式**|**转换**|**示例**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|美国常规长途拨号  <br/> （去掉 "+"）  <br/> |+1  <br/> |正好 12 位  <br/> |1  <br/> |0  <br/> |^\+（1 \ d{10}） $  <br/> |$1  <br/> |+14255551010 变为 14255551010  <br/> |
|美国国际长途拨号  <br/> （去掉 "+" 并添加011）  <br/> |+  <br/> |至少 11 位  <br/> |1  <br/> |011  <br/> |^\+（\d{9}\d +） $  <br/> |011$1  <br/> |+441235551010 变为 011441235551010  <br/> |


