---
title: 自动助理和呼叫队列拨号和语音识别参考
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.autoattendants.overview
- Phone System
- seo-marvel-apr2020
description: 了解自动助理和呼叫队列拨号和语音识别选项，Teams。
ms.openlocfilehash: 7ea18f5ca1f9fba619fe00f28e93e245a7a8f074
ms.sourcegitcommit: 38a4d2f41270633479afb3412c749365922554e5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2021
ms.locfileid: "61410673"
---
# <a name="auto-attendant-and-call-queue-dialing-and-voice-recognition-reference"></a>自动助理和呼叫队列拨号和语音识别参考

按姓名或分机拨叫是一项自动助理功能，使呼叫者能够联系Teams呼叫者。 使用语音或电话键盘呼叫者可以说出或输入要联系的联系人的完整或部分姓名或分机号。 自动助理将搜索公司目录，找到人员，然后将呼叫者转接给他们。  "按姓名拨叫"或"按分机拨叫"是当您在自动助理 中配置呼叫流设置 [时设置的选项](create-a-phone-system-auto-attendant.md#call-flow)。


## <a name="searching-for-users"></a>搜索用户

Teams **企业语音"** 按姓名拨叫"联系的用户不需要拥有电话号码或为其分配了呼叫计划，但必须为 Skype for Business Server 用户启用呼叫计划。 对于多个国家/地区组织，"按名称拨叫"将查找呼叫者，Microsoft Teams呼叫者转接到不同国家/地区的用户。

Teams分机号码联系的用户不需要拥有电话号码或为其分配了呼叫计划，但必须为企业语音启用Skype for Business Server **用户**。 还需要为用户配置适当的拨号计划。 对于多个国家/地区组织，"按分机拨叫"将查找呼叫者，Microsoft Teams呼叫者转接到不同国家/地区的用户。 

根据相关先决条件，配置自动助理时必须显式启用"按姓名拨叫"或"分机号码"。

### <a name="maximum-directory-size"></a>目录最大大小

当呼叫者搜索特定人员时，Active Directory 用户"按姓名拨叫"和"按分机拨叫"可以支持的数量没有限制。 调用方可以在 FirstName + LastName (输入部分或全名，也可以输入姓氏 + 名字) ，但需要完整的分机号码。 单个自动助理可以使用语音识别支持的最大名称列表大小是 80，000 个用户。
  
|输入类型|搜索格式|组织中的最大用户数|
|:-----|:-----|:-----|
|DTMF（键盘输入） |部分  <br/> 名字 + 姓氏  <br/> 姓氏 + 名字 |无限制  |
|语音（语音识别） |FirstName  <br/> LastName  <br/> 名字 + 姓氏  <br/> 姓氏 + 名字  | 80，000 个用户 |

> [!NOTE]
> 如果通过语音识别使用"按姓名拨叫"，但组织的 Active Directory 大于 80，000 个用户，并且尚未使用"按名字拨叫范围"功能限制[](create-a-phone-system-auto-attendant.md#dial-scope)范围，则按姓名拨叫仍适用于使用电话键盘的呼叫者，语音输入可用于所有其他方案。 你可以使用"拨号范围"功能，通过更改按名字拨叫的范围，减少可以呼叫的姓名，以找到特定自动助理。
 
### <a name="search-considerations"></a>搜索注意事项 
按名称拨叫搜索组织的目录，然后针对任何已配置的"拨号范围包括"或"排除"列表筛选结果。 如果初始搜索返回超过 100 个用户，将不会应用"拨号范围"列表，搜索将失败，并且呼叫者将被告知找到的名称过多。
 
 
## <a name="dial-by-name---keypad-dtmf-entry"></a>按名字拨叫 - 键盘 (DTMF) 输入
呼叫者可以通过指定尝试联系的用户的完整或部分姓名，使用"按姓名拨叫"来联系用户。 输入名称时可以使用多种格式。

搜索组织目录时，用户可以使用"0"（零）键来表示名字与姓氏之间或姓氏与名字之间的空格。 输入姓名时，会要求他们使用 # 键终止键盘输入。 例如，"在你输入要联系的用户姓名后，请按 # 号"。 如果找到多个姓名，会向呼叫者提供姓名列表，供其从中选择。

> [!NOTE]
> 如果在应用任何"拨号范围包括"或"排除"列表后仍保留超过 5 个姓名，搜索将失败，并且呼叫者将被告知找到的名称过多。 
  
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

使用电话键盘搜索用户时可以使用多种特殊字符。 例如，将要求人员使用井号键 (#) ，而零 (0) 键用于姓名之间的空格。 按星号键 (*) 将重复与该用户匹配的姓名列表。
  
|特殊电话键盘字符|含义|
|:-----|:-----|
|#   |输入姓名时的结束字符。 |
|0   |姓名中间的空格。 |
|*    |重复姓名匹配列表。 |

### <a name="dial-by-name---name-recognition-with-speech"></a>按名字拨叫 - 使用语音识别姓名

用户可以使用语音和语音识别功能搜索 (组织) 。 他们还可以通过说出要查找的人的完整或部分姓名来联系 Active Directory 中的任何人。 使用语音输入可以识别各种格式的名称，包括名字、姓氏、名字 + 姓氏或姓氏 + 名字。
  
你可以为自动助理启用语音识别，但是未禁用 (DTMF) 键盘输入。 电话自动助理上启用了语音识别，也随时都可以使用键盘输入。
  
与电话键盘输入一样，如果找到多个姓名，呼叫者将听到要选择的姓名列表。

> [!NOTE]
> 如果在应用任何"拨号范围包括"或"排除"列表后仍保留超过 5 个姓名，搜索将失败，并且呼叫者将被告知找到的名称过多。 
  
调用方可以使用以下格式说出姓名：
  
|具有语音的名称|搜索类型|示例|搜索结果|
|:-----|:-----|:-----|:-----|
|名字 + 姓氏 |完整 |Amos Marble |Amos Marble |
|姓氏 + 名字 |完整  |Marble Amos |Amos Marble |
|FirstName |完整 |Amos |按或报 1 选择 Amos Marble  <br/> 按或报 2 选择 Amos Jones |
|LastName |完整 |Marble |按或报 1 选择 Amos Marble  <br/> 按或报 2 选择 Ben Marble |
|名字或姓氏 |部分 |3 月 |按或说出 1 表示 Mary Marble  <br/> 按或报 2 表示 Mary Jones  <br/> 按或报 3 表示 Amos Marcus |
|名字 + 姓氏 |部分 |Amos Mar |按或报 1 选择 Amos Marble  <br/> 按或报 2 表示 Amos Marcus |


> [!NOTE]
> 由于 Active Directory 复制延迟，新用户可能需要最多 36 小时才能在"按名称拨叫"目录中列出其姓名并识别语音识别。
  
## <a name="language-support"></a>语言支持

这些支持的语言提供对文本到语音和语音识别 [的语言支持](create-a-phone-system-auto-attendant-languages.md)。

以下语音命令可用于语音识别： 
  
|语音命令| 对应于 |
|:-----|:-----|
|是 | 按 1 表示"是"。 |
|否 | 按 2 表示"否"。 |
|重复 |重复选项列表。 按键盘上的 *重复选项列表。 |
|接线员 | 按 0 表示"运算符" |
|主菜单  |为呼叫者返回到自动助理的主菜单。 |
|零 | 默认情况下按 0 (，与"运算符") 。|
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

[获取 Skype for Business 和 Microsoft Teams 的服务电话号码](./getting-service-phone-numbers.md)

[音频会议和通话套餐的国家/地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
