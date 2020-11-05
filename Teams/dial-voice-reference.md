---
title: 自动助理和通话队列拨号和语音识别参考
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
description: 了解团队中的自动助理和通话队列拨号和语音识别选项。
ms.openlocfilehash: b63235409418f7ff05b8d34973d2390e6b18df36
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908701"
---
# <a name="auto-attendant-and-call-queue-dialing-and-voice-recognition-reference"></a>自动助理和通话队列拨号和语音识别参考

按名称拨号是自动助理的一项功能，也称为目录搜索。 它使呼叫您的自动助理的人可以使用语音 (语音识别) 或其电话键盘 (DTMF) 响应输入完整或部分名称以搜索公司的目录，找到该联系人，然后将呼叫转移到他们。 在 [自动助理中配置通话流设置](create-a-phone-system-auto-attendant.md#call-flow)时，按名称设置拨号。

## <a name="searching-for-users"></a>搜索用户

您希望使用 "按名称拨入" 和 "已达到" 状态的用户 **无需具有电话号码或有分配给他们的通话计划，但他们必须具有电话系统许可证（如果他们是联机用户）或为 Skype for Business 服务器用户启用的企业语音** 。 通过名称拨号，您甚至可以找到并将呼叫转移到位于不同国家或地区组织的其他国家或地区的 Microsoft 团队用户。 根据所涉及的先决条件，在自动助理中明确启用 "按名称拨号"。

"通过分机号码拨号" 是自动助理的一项功能，它也是目录搜索的一部分。 它使呼叫您的自动助理的人可以使用语音 (语音识别) 或其电话键盘 (DTMF) 响应输入他们尝试访问的用户的电话分机，然后将呼叫转移到他们。 您希望使用 "通过分机拨入" 和 "已达到" 的用户  **无需具有电话号码或分配给他们的通话计划，但他们必须具有电话系统许可证（如果他们是联机用户）或为 Skype for Business 服务器用户启用的企业语音** 。 您还需要为用户配置适当配置的拨号计划。 通过分机号码进行拨号，甚至可以查找与多国组织的不同国家或地区托管的 Microsoft 团队用户的呼叫和转移呼叫。 根据所涉及的先决条件，你可以显式启用自动助理中的 "通过扩展拨号"。

### <a name="maximum-directory-size"></a>目录最大大小

对按名称拨入的 Active Directory 用户的数量没有限制，并且通过分机支持呼叫者搜索特定人员时可以支持。 呼叫者可以输入姓名 + LastName (部分或全名，也可以输入姓氏 + 名字) ，但需要完整的分机号码。 单个自动助理可以使用语音识别支持的最大名称列表大小是80000用户。
  
|输入类型|搜索格式|组织中的最大用户数|
|:-----|:-----|:-----|
|DTMF（键盘输入） |部分  <br/> 名字 + 姓氏  <br/> 姓氏 + 名字 |无限制  |
|语音（语音识别） |名  <br/> 姓名  <br/> 名字 + 姓氏  <br/> 姓氏 + 名字  | 80000用户 |

> [!NOTE]
> 如果你使用的是使用语音识别的 "按名称拨号"，但你的组织的 Active Directory 大于80000用户，并且你没有通过 "拨号作用域" 功能限制按名称进行拨号的范围，则按名称使用电话键盘仍可使用呼叫者，并且语音输入将可用于所有其他方案。 你可以使用"拨号范围"功能，通过更改按名字拨叫的范围，减少可以呼叫的姓名，以找到特定自动助理。
  
## <a name="dial-by-name---keypad-dtmf-entry"></a>按名字拨叫 - 键盘 (DTMF) 输入
拨入者可以通过指定要访问的人员的全名或部分名称，使用 "按名称拨号" 访问用户。 输入姓名时可以使用不同的格式。

搜索组织目录时，用户可以使用"0"（零）键来表示名字与姓氏之间或姓氏与名字之间的空格。 输入名称时，系统将要求他们用 # 键终止其键盘输入。 例如，"在你输入要联系的用户姓名后，请按 # 号"。 如果找到多个姓名，会向呼叫者提供姓名列表，供其从中选择。
  
用户可以在电话键盘上使用以下搜索格式搜索组织中的姓名：
  
|姓名格式|搜索类型|示例|搜索结果|
|:-----|:-----|:-----|:-----|
|名字 + 姓氏 |完整  |Amos0Marble# |Amos Marble |
|姓氏 + 名字 |完整 |Marble0Amos#  |Amos Marble |
|名  |完整   |Amos#   |按 1 选择 Amos Marble  <br/> 按 2 选择 Amos Marcus |
|姓名 |完整 |Marble#  |按 1 选择 Amos Marble  <br/> 按 2 选择 Mary Marble |
|名字或姓氏 |部分 |Mar# |按 1 选择 Mary Marble  <br/> 按 2 选择 Mary Jones  <br/> 按 3 选择 Amos Marcus |
|名字 + 姓氏 |部分 |Amos0Mar# |按 1 选择 Amos Marble  <br/> 按 2 选择 Amos Marcus |
|姓氏 + 名字 |部分 |Mar0Am# |按 1 选择 Amos Marble  <br/> 按 2 选择 Amos Marcus |

使用电话键盘搜索用户时可以使用多种特殊字符。 例如，将要求人员使用井号键 ( # ) ，而零 (0) 键用于名称间的空格。 按星号键 (*) 将重复与该用户匹配的姓名列表。
  
|特殊电话键盘字符|含义|
|:-----|:-----|
|#   |输入姓名时的结束字符。 |
|0   |姓名中间的空格。 |
|*    |重复姓名匹配列表。 |

### <a name="dial-by-name---name-recognition-with-speech"></a>按名字拨叫 - 使用语音识别姓名

用户可以通过语音 (语音识别) 搜索其组织中的其他人。 他们还可以通过说出您想要查找的人员的全名或部分名称，与 Active Directory 中的任何人联系。 使用语音输入可以识别各种格式的名称，包括 "名字"、"姓氏"、"名字"、"姓氏" 或 "姓氏 + 名字"。
  
你可以启用自动助理的语音识别，但电话键盘条目 (DTMF) 不会禁用。 即使自动助理上已启用语音识别，也可以随时使用电话键盘条目。
  
与电话键盘条目一样，如果找到多个姓名，呼叫者将听到要选择的姓名列表。
  
调用方可以通过以下格式表达名称：
  
|带有语音的名称|搜索类型|示例|搜索结果|
|:-----|:-----|:-----|:-----|
|名字 + 姓氏 |完整 |Amos Marble |Amos Marble |
|姓氏 + 名字 |完整  |Marble Amos |Amos Marble |
|名 |完整 |Amos |按或报 1 选择 Amos Marble  <br/> 按或报 2 选择 Amos Jones |
|姓名 |完整 |Marble |按或报 1 选择 Amos Marble  <br/> 按或报 2 选择 Ben Marble |
|名字或姓氏 |部分 |年 |对 Mary 大理石按下或说出1  <br/> 按或说 "2" 表示 "张薇"  <br/> 对 Amos Marcus 按下或说出3 |
|名字 + 姓氏 |部分 |Amos 三月 |按或报 1 选择 Amos Marble  <br/> 按下或说 Amos Marcus 的2 |


> [!NOTE]
> 由于 Active Directory 复制延迟，新用户可能需要长达36小时才能将其名称列在目录中，以便通过语音识别按名称进行拨号。
  
## <a name="language-support"></a>语言支持

以下语言适用于与传出提示一起使用的文本到语音转换：
  
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

自动助理的语音识别输入适用于以下语言：
  
|-|-|
|:-----|:-----|
|中文 (ZH)  |法语 (FR)  |
|英语 (AU)  |德语 (DE)  |
|英语 (CA)  |意大利语 (IT)  |
|英语 (IN)  |日语 (JP)  |
|英语 (UK)  |葡萄牙语 (BR)  |
|英语 (US)  |西班牙语 (ES)  |
|法语 (CA)   |西班牙语 (MX)  |

以下语音命令在支持语音识别的14种语言中可用：
  
|语音命令| 对应于 |
|:-----|:-----|
|是 | 按1表示 "是"。 |
|否 | 按2键。 |
|重复 |重复选项列表。 按键盘上的 "*" 重复选项列表。 |
|接线员 | 按0表示 "运算符" |
|主菜单  |为呼叫者返回到自动助理的主菜单。 |
|零 | 按 0 (默认情况下，与 "Operator" ) 相同。|
|一 | 按1。 |
|二 | 按2。 |
|三| 按3。|
|四 | 按4。 |
|五 | 按5。 |
|六  | 按6。 |
|七 | 按7。|
|八 |按8。|
|九  |按9。|

## <a name="related-topics"></a>相关主题

[电话系统的功能](here-s-what-you-get-with-phone-system.md)

[获取 Skype for Business 和 Microsoft Teams 的服务电话号码](/microsoftteams/getting-service-phone-numbers)

[音频会议和通话套餐的国家/地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[小型企业示例 - 设置自动助理](/microsoftteams/tutorial-org-aa)
