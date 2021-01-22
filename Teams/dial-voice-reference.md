---
title: 自动助理和呼叫队列拨号和语音识别参考
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.autoattendants.overview
- Phone System
- seo-marvel-apr2020
description: 了解 Teams 中的自动助理和呼叫队列拨号和语音识别选项。
ms.openlocfilehash: 1cb8da2d2e6625de5a1471d1051c1ca51f11bbae
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918958"
---
# <a name="auto-attendant-and-call-queue-dialing-and-voice-recognition-reference"></a>自动助理和呼叫队列拨号和语音识别参考

按名字拨叫是自动助理的一项功能，也称为目录搜索。 它使呼叫自动助理的人能够使用语音 (语音识别) 或电话键盘 (DTMF) 响应输入完整或部分名称以搜索公司的目录、查找人员，然后将呼叫转接给他们。 在自动助理中配置呼叫流设置时 [，按姓名设置拨号](create-a-phone-system-auto-attendant.md#call-flow)。

## <a name="searching-for-users"></a>搜索用户

希望使用"按名字拨叫"定位和联系的用户无需拥有电话号码或为其分配通话计划，但必须为 **Skype for Business Server** 企业语音启用呼叫计划。 "按名称拨叫"甚至能够查找和转移呼叫在不同国家/地区或区域为多个国家/地区托管的 Microsoft Teams 用户。 根据所涉及的先决条件，在自动助理中显式启用按名字拨叫。

按分机拨叫是自动助理的一项功能，也是目录搜索的一部分。 它使呼叫自动助理的用户能够使用语音 (语音识别) 或电话键盘 (DTMF) 响应输入他们尝试联系的用户的电话分机，然后将呼叫转接给他们。 希望使用"按分机拨叫"定位和联系的用户不需要拥有电话号码或为其分配了呼叫计划，但必须为  **Skype for Business Server** 企业语音启用呼叫计划。 你还需要为用户设置适当配置的拨号计划。 通过分机拨叫甚至能够查找并转接到在多个国家/地区为多个国家/地区托管的 Microsoft Teams 用户。 根据所涉及的先决条件，在自动助理中显式启用"按分机拨叫"。

### <a name="maximum-directory-size"></a>目录最大大小

当呼叫者搜索特定人员时，Active Directory 用户按名字拨叫和按分机拨叫可以支持的数量没有限制。 调用方可以在名字 + 姓氏 (输入部分或全名，也可以输入姓氏 +) 名，但需要完整的分机号码。 单个自动助理可以使用语音识别支持的最大名称列表大小是 80，000 个用户。
  
|输入类型|搜索格式|组织中的最大用户数|
|:-----|:-----|:-----|
|DTMF（键盘输入） |部分  <br/> 名字 + 姓氏  <br/> 姓氏 + 名字 |无限制  |
|语音（语音识别） |FirstName  <br/> LastName  <br/> 名字 + 姓氏  <br/> 姓氏 + 名字  | 80，000 个用户 |

> [!NOTE]
> 如果通过语音识别使用按名字拨叫，但组织的 Active Directory 大于 80，000 个用户，并且未使用"按名字拨叫"功能限制"按名字拨叫"的范围，则按名字拨叫仍适用于使用电话键盘的呼叫者，语音输入可用于所有其他方案。 你可以使用"拨号范围"功能，通过更改按名字拨叫的范围，减少可以呼叫的姓名，以找到特定自动助理。
  
## <a name="dial-by-name---keypad-dtmf-entry"></a>按名字拨叫 - 键盘 (DTMF) 输入
呼叫进入的用户可以通过指定用户尝试联系的联系人的完整或部分姓名，使用按名字拨叫来联系用户。 输入名称时可以使用多种格式。

搜索组织目录时，用户可以使用"0"（零）键来表示名字与姓氏之间或姓氏与名字之间的空格。 输入姓名时，会要求他们使用 # 键终止键盘输入。 例如，"在你输入要联系的用户姓名后，请按 # 号"。 如果找到多个姓名，会向呼叫者提供姓名列表，供其从中选择。
  
用户可以在电话键盘上使用以下搜索格式搜索组织中的姓名：
  
|姓名格式|搜索类型|示例|搜索结果|
|:-----|:-----|:-----|:-----|
|名字 + 姓氏 |完整  |Amos0Marble# |Amos Marble |
|姓氏 + 名字 |完整 |Marble0Amos#  |Amos Marble |
|FirstName  |完整   |Amos#   |按 1 选择 Amos Marble  <br/> 按 2 选择 Amos Marcus |
|LastName |完整 |Marble#  |按 1 选择 Amos Marble  <br/> 按 2 选择 Mary Marble |
|名字或姓氏 |部分 |Mar# |按 1 选择 Mary Marble  <br/> 按 2 选择 Mary Jones  <br/> 按 3 选择 Amos Marcus |
|名字 + 姓氏 |部分 |Amos0Mar# |按 1 选择 Amos Marble  <br/> 按 2 选择 Amos Marcus |
|姓氏 + 名字 |部分 |Mar0Am# |按 1 选择 Amos Marble  <br/> 按 2 选择 Amos Marcus |

使用电话键盘搜索用户时可以使用多种特殊字符。 例如，将要求该人员使用井号键 (#) ，而零 (0) 键用于姓名之间的空格。 按星号键 (*) 将重复与该用户匹配的姓名列表。
  
|特殊电话键盘字符|含义|
|:-----|:-----|
|#   |输入姓名时的结束字符。 |
|0   |姓名中间的空格。 |
|*    |重复姓名匹配列表。 |

### <a name="dial-by-name---name-recognition-with-speech"></a>按名字拨叫 - 使用语音识别姓名

用户可以使用语音和语音识别功能搜索 (中的) 。 他们还可以通过说出要查找的联系人的完整或部分名称来联系 Active Directory 中的任何人。 使用语音输入可以识别各种格式的名称，包括名字、姓氏、名字 + 姓氏或姓氏 + 名字。
  
你可以为自动助理启用语音识别，但电话键盘输入 (DTMF) 未禁用。 即使自动助理上启用了语音识别，也随时都可以使用电话键盘输入。
  
与电话键盘输入一样，如果找到多个姓名，呼叫者将听到要选择的姓名列表。
  
调用方可以使用以下格式说出姓名：
  
|使用语音命名|搜索类型|示例|搜索结果|
|:-----|:-----|:-----|:-----|
|名字 + 姓氏 |完整 |Amos Marble |Amos Marble |
|姓氏 + 名字 |完整  |Marble Amos |Amos Marble |
|FirstName |完整 |Amos |按或报 1 选择 Amos Marble  <br/> 按或报 2 选择 Amos Jones |
|LastName |完整 |Marble |按或报 1 选择 Amos Marble  <br/> 按或报 2 选择 Ben Marble |
|名字或姓氏 |部分 |3 月 |按或报 1 选择 Mary Marble  <br/> 按或报 2 选择 Mary Jones  <br/> 按或报 3 选择 Amos Marcus |
|名字 + 姓氏 |部分 |Amos Mar |按或报 1 选择 Amos Marble  <br/> 按或报 2 选择 Amos Marcus |


> [!NOTE]
> 由于 Active Directory 复制延迟，新用户可能需要最多 36 小时才能在"按名字拨叫"目录中列出其姓名和语音识别。
  
## <a name="language-support"></a>语言支持

以下语言适用于与传出提示一起使用的文本到语音：
  
|-|-|-|
|:-----|:-----|:-----|
|阿拉伯语 (EG)  |英语 (NZ)  |韩语 (KO)  |
|中文 (HK)  |英语 (UK) |挪威语 (NO)  |
|中文 (TW) |英语 (US) |波兰语 (PL)  |
|中文 (ZH) |芬兰语 (FI) |葡萄牙语 (BR) |
|丹麦语 (DA)  |法语 (CA)  |葡萄牙语 (PT) |
|荷兰语 (NL)   |法语 (FR)  |俄语 (RU) |
|英语 (AU)  |德语 (DE) |西班牙语 (ES)  |
|英语 (CA)  |意大利语 (IT) |西班牙语 (MX)|
|英语 (IN)  |日语 (JP) |瑞典语 (SV)|

自动助理的语音识别输入以下列语言提供：
  
|-|-|
|:-----|:-----|
|中文 (ZH)  |法语 (FR)  |
|英语 (AU)  |德语 (DE)  |
|英语 (CA)  |意大利语 (IT)  |
|英语 (IN)  |日语 (JP)  |
|英语 (UK)  |葡萄牙语 (BR)  |
|英语 (US)  |西班牙语 (ES)  |
|法语 (CA)   |西班牙语 (MX)  |

以下语音命令在语音识别支持的 14 种语言中可用：
  
|语音命令| 对应于 |
|:-----|:-----|
|是 | 按 1 表示是。 |
|否 | 按 2 表示"否"。 |
|重复 |重复选项列表。 按键盘上的 *重复选项列表。 |
|接线员 | 按 0 作为"运算符" |
|主菜单  |为呼叫者返回到自动助理的主菜单。 |
|零 | 默认情况下按 0 (，与"运算符"相同) 。|
|一 | 按 1。 |
|二 | 按 2。 |
|三| 按 3。|
|四 | 按 4。 |
|五 | 按 5。 |
|六  | 按 6。 |
|七 | 按 7。|
|八 |按 8。|
|九  |按 9。|

## <a name="related-topics"></a>相关主题

[电话系统的功能](here-s-what-you-get-with-phone-system.md)

[获取 Skype for Business 和 Microsoft Teams 的服务电话号码](/microsoftteams/getting-service-phone-numbers)

[音频会议和通话套餐的国家/地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
