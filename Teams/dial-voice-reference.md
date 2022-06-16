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
description: 了解Teams中的自动助理和呼叫队列拨号和语音识别选项。
ms.openlocfilehash: 784dcbf16c5122c165dc1a949fa237769c9837d3
ms.sourcegitcommit: e38dc23e3968f55625e90c8883884045f80d22ee
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2022
ms.locfileid: "66124187"
---
# <a name="auto-attendant-and-call-queue-dialing-and-voice-recognition-reference"></a>自动助理和呼叫队列拨号和语音识别参考

按名称或扩展拨号是一项自动助理功能，使呼叫者能够访问组织中Teams用户。 使用语音或电话键盘呼叫者可以说出或输入要联系的人员的完整或部分姓名或扩展名。 自动助理将搜索公司目录，找到该人员，然后将调用方转移到他们。  按名称拨号或按扩展拨号是在[自动助理中配置呼叫流设置](create-a-phone-system-auto-attendant.md?tabs=call-flow)时设置的选项。

## <a name="searching-for-users"></a>搜索用户

Teams使用“按名称拨号”访问的用户 **不需要有电话号码或分配有呼叫计划，但必须为Skype for Business Server用户启用企业语音**。 对于多国家组织，按名称拨号会查找呼叫者，并将呼叫者转移到位于不同国家或地区的Microsoft Teams用户。

使用“按扩展拨号”联系的Teams用户 **不需要有电话号码或分配有呼叫计划，但必须企业语音为Skype for Business Server用户启用这些用户**。 还需要为用户提供适当配置的拨号计划。 对于多国家组织，按扩展拨号会查找呼叫者，并将呼叫者转移到位于不同国家或地区的Microsoft Teams用户。

根据所涉及的先决条件，在配置自动助理时，必须显式启用按名称或扩展拨号。

### <a name="maximum-directory-size"></a>目录最大大小

当呼叫者搜索特定人员时，Active Directory 用户按名称拨号和按扩展拨号可以支持的数量没有限制。 调用方可以输入部分或全名 (FirstName + LastName，也可以输入 LastName + FirstName) ，但需要完整的扩展号。 使用语音识别，单个自动助理可以支持的最大名称列表大小为 80，000 个用户。
  
|输入类型|搜索格式|组织中的最大用户数|
|:-----|:-----|:-----|
|DTMF（键盘输入） |部分  <br/> 名字 + 姓氏  <br/> 姓氏 + 名字 |无限制  |
|语音（语音识别） |FirstName  <br/> 姓氏  <br/> 名字 + 姓氏  <br/> 姓氏 + 名字  | 80，000 个用户 |

> [!NOTE]
> 如果使用带有语音识别的“按名称拨号”，但组织的 Active Directory 超过 80，000 个用户，并且你没有使用 [拨号范围](create-a-phone-system-auto-attendant.md?tabs=dial-scope) 功能限制按名称拨号的范围，则使用电话键盘按名称拨号仍适用于呼叫者，并且语音输入将适用于所有其他方案。 你可以使用"拨号范围"功能，通过更改按名字拨叫的范围，减少可以呼叫的姓名，以找到特定自动助理。

### <a name="search-considerations"></a>搜索注意事项

在应用已配置的任何拨号范围包括或排除列表之前，按名称拨号首先搜索整个组织的目录。 如果针对整个目录的初始搜索返回超过 100 个用户，则不会应用拨号范围列表，搜索将失败，并且会告知调用方找到的名称太多。

## <a name="dial-by-name---keypad-dtmf-entry"></a>按名字拨叫 - 键盘 (DTMF) 输入

呼叫者可以使用“按名称拨号”来联系用户，方法是指定他们尝试联系的人员的完整或部分姓名。 输入名称时，可以使用各种格式。

搜索组织目录时，用户可以使用"0"（零）键来表示名字与姓氏之间或姓氏与名字之间的空格。 输入名称时，系统会要求他们使用 #键终止其键盘条目。 例如，"在你输入要联系的用户姓名后，请按 # 号"。 如果找到多个姓名，会向呼叫者提供姓名列表，供其从中选择。

> [!NOTE]
> 如果在应用任何“拨号范围包括”或“排除”列表后仍保留超过 5 个名称，搜索将失败，并且会告知调用方找到的名称过多。
  
用户可以在电话键盘上使用以下搜索格式搜索组织中的姓名：
  
|姓名格式|搜索类型|示例|搜索结果|
|:-----|:-----|:-----|:-----|
|名字 + 姓氏 |完整  |Amos0Marble# |Amos Marble |
|姓氏 + 名字 |完整 |Marble0Amos#  |Amos Marble |
|FirstName  |完整   |Amos#   |按 1 选择 Amos Marble  <br/> 按 2 选择 Amos Marcus |
|姓氏 |完整 |Marble#  |按 1 选择 Amos Marble  <br/> 按 2 选择 Mary Marble |
|名字或姓氏 |部分 |Mar# |按 1 选择 Mary Marble  <br/> 按 2 选择 Mary Jones  <br/> 按 3 选择 Amos Marcus |
|名字 + 姓氏 |部分 |Amos0Mar# |按 1 选择 Amos Marble  <br/> 按 2 选择 Amos Marcus |
|姓氏 + 名字 |部分 |Mar0Am# |按 1 选择 Amos Marble  <br/> 按 2 选择 Amos Marcus |

使用电话键盘搜索用户时可以使用多种特殊字符。 例如，将要求用户使用磅键 (#) ，而零 (0) 键用于名称之间的空格。 按星号键 (*) 将重复与该用户匹配的姓名列表。
  
|特殊电话键盘字符|含义|
|:-----|:-----|
|#   |输入姓名时的结束字符。 |
|0   |姓名中间的空格。 |
|*    |重复姓名匹配列表。 |

### <a name="dial-by-name---name-recognition-with-speech"></a>按名字拨叫 - 使用语音识别姓名

用户可以使用语音搜索组织中的其他人 (语音识别) 。 他们还可以通过说出他们试图找到的人员的完整或部分姓名来联系 Active Directory 中的任何人。 使用语音输入可以识别各种格式的名称，包括 FirstName、LastName、FirstName + LastName 或 LastName + FirstName。
  
可以为自动助理启用语音识别，但未禁用 DTMF)  (手机键盘条目。 电话键盘条目可以随时使用，即使在自动助理上启用了语音识别。
  
与电话键盘条目一样，如果找到多个名称，则呼叫者将听到要从中选择的名称列表。

> [!NOTE]
> 如果在应用任何“拨号范围包括”或“排除”列表后仍保留超过 5 个名称，搜索将失败，并且会告知调用方找到的名称过多。
  
调用方可以使用以下格式说出姓名：
  
|带语音的名称|搜索类型|示例|搜索结果|
|:-----|:-----|:-----|:-----|
|名字 + 姓氏 |完整 |Amos Marble |Amos Marble |
|姓氏 + 名字 |完整  |Marble Amos |Amos Marble |
|FirstName |完整 |Amos |按或报 1 选择 Amos Marble  <br/> 按或报 2 选择 Amos Jones |
|姓氏 |完整 |Marble |按或报 1 选择 Amos Marble  <br/> 按或报 2 选择 Ben Marble |
|名字或姓氏 |部分 |三月 |按或说 1 为玛丽大理石  <br/> 按或说 2 为玛丽琼斯  <br/> 按或说 3 为阿莫斯马库斯 |
|名字 + 姓氏 |部分 |Amos Mar |按或报 1 选择 Amos Marble  <br/> 按或说 2 为阿莫斯马库斯 |

> [!NOTE]
> 由于 Active Directory 复制滞后，新用户可能需要长达 36 小时才能将其名称列在具有语音识别的“按名称拨号”目录中。

### <a name="dial-by-extension"></a>按扩展拨号

要用于 **Dial By Extension 的** 用户需要将扩展指定为 Active Directory (中定义的以下电话属性之一，并通过 Azure AD 连接) 或Azure Active Directory进行同步。  (有关详细信息，请参阅 [单独或批量添加用户](/microsoft-365/admin/add-users/add-users) 。) 

- OfficePhone/PhoneNumber (AD 和 Azure AD) 
- HomePhone (AD) 
- Mobile/MobilePhone (AD 和 Azure AD) 
- OtherTelephone (AD) 

在用户电话号码字段中输入扩展所需的格式可以是以下格式之一：

- *+\<phone number>;ext=\<extension>*
- *+\<phone number>X\<extension>*
- *X\<extension>*

- 示例 1：Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber “+15555555678;ext=5678”
- 示例 2：Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber “+1555555678x5678”
- 示例 3：Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber “x5678”

可以在[Microsoft 365 管理中心](https://admin.microsoft.com/)或[Azure Active Directory管理中心](https://aad.portal.azure.com)设置扩展。 最多可能需要 12 小时才能向自动助理和呼叫队列提供更改。

## <a name="language-support"></a>语言支持

这些 [受支持的语言](create-a-phone-system-auto-attendant-languages.md)中提供了对文本转语音和语音识别的语言支持。

以下语音命令可用于语音识别：
  
|语音命令| 对应于 |
|:-----|:-----|
|是 | 按 1 表示是。 |
|否 | 按 2 表示否。 |
|重复 |重复选项列表。 在键盘上按 * 重复选项列表。 |
|接线员 | 按 0 表示“运算符” |
|主菜单  |为呼叫者返回到自动助理的主菜单。 |
|零 | 默认按 0 (，与“运算符”) 相同。|
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
