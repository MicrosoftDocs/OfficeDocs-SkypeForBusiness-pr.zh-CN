---
title: 什么是云自动助理？
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: makolomi
ms.date: 4/2/2019
ms.topic: article
ms.assetid: ab9f05a2-22cb-4692-a585-27f82d1b37c7
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
ROBOTS: NOINDEX, NOFOLLOW
description: 了解云自动助理以及如何使用它们让呼叫者在菜单系统中移动以定位和呼叫用户或部门或者将呼叫转接到用户或部门。
ms.openlocfilehash: c8e5b3f608200036b8c9b9ed5338c558464b32d3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100958"
---
# <a name="what-are-cloud-auto-attendants"></a>什么是云自动助理？

电话系统自动助理，可用于让外部和内部呼叫者在菜单系统中移动，以定位和拨打或转接组织中用户或部门的呼叫。
  
自动助理通常是系统中一个节点，为呼叫者提供一系列他们听到的语音提示或音频文件，而不是人工接线员。 当用户呼叫与自动助理关联的号码时，他们的选择可以将呼叫重定向到某个用户或在您的组织中查找某人，然后连接到该用户。 他们可以使用电话键盘和 DTMF 或语音识别功能， (选择) 与菜单系统交互。 他们所做的选择还可以将呼叫重定向到另一个自动助理或呼叫队列。
  
若要为云自动助理电话系统，请转到[设置云自动助理](create-a-phone-system-auto-attendant.md)。
  
云自动助理具有以下功能：
  
- 提供企业或信息性问候语。
- 提供自定义企业菜单。你可以自定义这些菜单以包含更多级别。
- 它提供目录搜索，使呼叫者能够在组织的目录中搜索姓名。
- 它使呼叫者能够联系或留下组织中人员的消息。
- 它支持多种语言进行提示、文本到语音和语音识别。
- 它支持指定假日和营业时间。
- 它支持将呼叫转接到接线员、其他用户、呼叫队列和自动助理。
- 它支持呼叫者为组织留下消息的共享语音邮件。

> [!NOTE]
> 本文适用于 Microsoft Teams 和 Skype for Business Online。

## <a name="getting-started"></a>入门

要开始使用自动助理，记住以下几点至关重要：

- 需要自动助理才能拥有关联的资源帐户。 有关[资源帐户的详细信息，Teams](manage-resource-accounts.md)管理资源帐户。 <!-- You can either use an existing resource account or create a new resource account as you set up your auto attendant. -->
- 将电话号码分配给自动助理时，严格说来就是将其分配给与该自动助理关联的资源帐户。 这提供了一种让多个电话号码访问自动助理的方法。 通常，资源帐户使用免费虚拟用户电话系统许可证。 此许可证电话系统组织级别的电话号码提供高级功能，并允许您创建自动助理和呼叫队列。

> [!NOTE]
> 自动助理和呼叫队列的直接路由服务号码仅支持Microsoft Teams和呼叫代理。

   > [!TIP]
   > 若要将呼叫重定向到接线员或具有 **电话系统** 许可证的联机用户的菜单选项，你需要为其帐户启用企业语音或为其分配呼叫计划。 请参阅[分配Microsoft Teams附加许可证。](teams-add-on-licensing/assign-teams-add-on-licenses.md) 你还可以使用 Windows PowerShell。 例如运行： `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- 若要获取和使用自动助理的免费服务号码，需要设置通信信用额度。 为此，请参阅 [什么是通信信用额度？](what-are-communications-credits.md) 和 [为组织设置通信信用额度](set-up-communications-credits-for-your-organization.md)。

    > [!IMPORTANT]
    > [!重要信息] 不能将用户（订阅者）的电话号码分配给自动助理 - 只能使用收费或免费服务电话号码。

- 完整的自动助理系统通常涉及多个自动助理。
- 可以向入口点自动助理应用多个电话号码。
- 非入口点自动助理或完整系统中呼叫队列将仅需要电话号码（如果他们将进行出站 PSTN 呼叫）。
  
## <a name="feature-overview"></a>功能概述

### <a name="searching-for-users"></a>搜索用户

按名称拨叫是自动助理的一项功能，也称为目录搜索。 它使呼叫自动助理的人能够使用语音 (语音识别) 或电话键盘 (DTMF) 响应输入完整或部分名称以搜索公司的目录、查找人员，然后将呼叫转接给他们。 希望使用"按姓名拨叫"定位和联系的用户无需拥有电话号码或为其分配了呼叫计划，但如果这些用户是联机用户，则必须拥有 电话系统 许可证，或者为 Skype for Business Server 用户启用 **企业语音。** "按名称拨叫"甚至能够查找和Microsoft Teams在不同国家/地区为多个国家/地区托管的所有用户的呼叫。 根据相关先决条件，在自动助理中显式启用"按姓名拨叫"。

"按分机号拨叫"是自动助理的一项功能，也是目录搜索的一部分。 它使呼叫自动助理的用户能够使用语音 (语音识别) 或电话键盘 (DTMF) 响应输入他们尝试联系的用户的电话分机，然后将呼叫转接给他们。 希望使用"按分机拨叫"定位和联系的用户不需要拥有电话号码或为其分配了呼叫计划，但如果这些用户是在线用户，则必须拥有 电话系统 许可证，或者为 Skype for Business Server 用户启用 **企业语音。** 还需要为用户配置适当的拨号计划。 通过分机拨叫甚至能够查找和转接Microsoft Teams在多个国家/地区为多个国家/地区托管的用户。 根据相关先决条件，在自动助理中显式启用"按分机拨叫"。

#### <a name="maximum-directory-size"></a>目录最大大小

当呼叫者搜索特定人员时，Active Directory 用户"按姓名拨叫"和"按分机拨叫"可以支持的数量没有限制。 调用方可以在名字 + 姓氏 (输入部分或全名，也可以输入姓氏 + 名字) ，但需要完整的分机号码。 单个自动助理可以使用语音识别支持的最大名称列表大小是 80，000 个用户。
  
|输入类型|搜索格式|组织中的最大用户数|
|:-----|:-----|:-----|
|DTMF（键盘输入） |部分  <br/> 名字 + 姓氏  <br/> 姓氏 + 名字 |无限制  |
|语音（语音识别） |FirstName  <br/> LastName  <br/> 名字 + 姓氏  <br/> 姓氏 + 名字  | 80，000 个用户 |

> [!NOTE]
> 如果通过语音识别使用"按姓名拨叫"，但组织的 Active Directory 大于 80，000 个用户，并且尚未使用"按名字拨叫范围"功能限制范围，则按姓名拨叫仍适用于使用电话键盘的呼叫者，语音输入可用于所有其他方案。 你可以使用"拨号范围"功能，通过更改按名字拨叫的范围，减少可以呼叫的姓名，以找到特定自动助理。
  
### <a name="dial-by-name---keypad-dtmf-entry"></a>按名字拨叫 - 键盘 (DTMF) 输入

呼叫者可以通过指定尝试联系的用户的完整或部分姓名，使用"按姓名拨叫"来联系用户。 输入名称时可以使用多种格式。

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

#### <a name="dial-by-name---name-recognition-with-speech"></a>按名字拨叫 - 使用语音识别姓名

用户可以使用语音和语音识别功能在 (搜索) 。 他们还可以通过说出要查找的人的姓名来联系 Active Directory 中的任何人。 使用语音输入可以识别各种格式的名称，包括名字、姓氏、名字 + 姓氏或姓氏 + 名字。
  
你可以为自动助理启用语音识别，但是未禁用 (DTMF) 键盘输入。 电话自动助理上启用了语音识别，也随时都可以使用键盘输入。
  
与电话键盘输入一样，如果找到多个姓名，呼叫者将听到要选择的姓名列表。
  
调用方可以使用以下格式说出姓名：
  
|具有语音的名称|搜索类型|示例|搜索结果|
|:-----|:-----|:-----|:-----|
|名字 + 姓氏 |完整 |Amos Marble |Amos Marble |
|姓氏 + 名字 |完整  |Marble Amos |Amos Marble |
|FirstName |完整 |Amos |按或报 1 选择 Amos Marble  <br/> 按或报 2 选择 Amos Jones |
|LastName |完整 |Marble |按或报 1 选择 Amos Marble  <br/> 按或报 2 选择 Ben Marble |

> [!NOTE]
> 由于 Active Directory 复制延迟，新用户可能需要最多 36 小时才能在"按名称拨叫"目录中列出其姓名并识别语音识别。
  
### <a name="language-support"></a>语言支持

以下语言可用于与传出提示一起使用的文本到语音：
  
|A-E|E-J|K-Z|
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
  
|A-F|F-Z|
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
|是 | 按 1 表示"是"。 |
|不支持 | 按 2 表示"否"。 |
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

### <a name="the-operator-option"></a>运算符选项

可以选择性地设置自动助理，为呼叫者选择与人工接线员通话。
  
默认情况下，键 0 和语音命令"接线员"将呼叫引导至指定的接线员。 对于语音识别支持的所有语言，都是如此。 还可使用"设置 **菜单选项** "为运算符设置自定义值。
  
运算符可以设置为：
  
- 一Microsoft Teams已启用Skype for Business Server的用户企业语音用户。
- 为组织设置的其他自动助理。
- 组织中建立的任何现有呼叫队列。 若要详细了解呼叫队列，请参阅 [创建云呼叫队列](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)。

### <a name="business-hours-and-call-handling"></a>营业时间和呼叫处理

可以在每个自动助理上设置营业时间。 如果没有设置营业时间，所有日期以及每天的所有时间均视为营业时间，因为默认情况下设置为全天候时间表。 营业时间可以设置为一天中的休息时间，所有未设置为营业时间的营业时间均视为非营业时间。 你可以设置不同的传入呼叫处理选项和不同的问候语 (对于营业时间和) 是可选选项。
  
每个自动助理都有多个可能的呼叫处理选项：
  
- 播放问候语后，呼叫可能会断开连接。
- 您也可以：
  - 将呼叫重定向到Microsoft Teams已启用或电话系统呼叫计划企业语音的已呼叫用户。 你可以通过此设置将呼叫者直接转到语音邮件。 为此，请选择" **贵公司的人**"，此人会将其呼叫直接转到语音邮件。

  - 将呼叫重定向到呼叫队列。 若要详细了解呼叫队列，请参阅 [创建云呼叫队列](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)。

  - 将呼叫重定向到另一个自动助理。

自动助理在播放菜单提示时向呼叫者表示这些选项。 例如："按 1 表示销售，按 2 表示服务。 若要与接线员联系，请随时按 0。"

### <a name="set-menu-options"></a>设置菜单选项

云自动助理允许您创建菜单提示 ("按 1 for Sales，按 2 for Services") 并设置菜单选项以根据用户选择路由呼叫。 自动助理的菜单选项允许组织提供一系列选项，引导呼叫者更快地到达其目的地，而无需依赖人工接线员来处理传入呼叫。 菜单提示可以通过使用文本到语音 (系统生成的提示创建) 上传录制的音频文件。 语音识别接受语音命令进行免提导航，但呼叫者也可使用电话键盘导航菜单。
  
可以将密钥 0 到 9 分配给自动助理中的拨号键，Skype for Business管理中心。 可以为营业时间和非营业时间创建不同的菜单选项集，并且可以在 **菜单选项** 中启用或禁用按名字拨叫。 这些键可以映射为将呼叫转接至：
  
- 接线员，默认情况下映射到键 0。 但是，它可以重新分配到任何其他键，或者从菜单中删除。
- 呼叫队列。
- 另一种自动助理。 可以通过将一个自动助理中的"菜单选项"指向另一个自动助理及其自己的菜单选项集（称为"嵌套"自动助理）来设置多级菜单。
- Microsoft Teams 具有电话系统已启用或电话系统呼叫计划的企业语音用户。 你可以通过此设置将呼叫者直接转到语音邮件。 为此，请选择" **贵公司的人**"，此人会将其呼叫直接转到语音邮件。
  
如果已启用语音识别，则每个菜单选项的名称将成为语音识别关键字。 例如，调用方可以说"一"来选择映射到键 1 的菜单选项，也可以说"销售"来选择名为"销售"的同一菜单选项。
  
若要设置自动助理和菜单选项，请转到["设置云自动助理"。](create-a-phone-system-auto-attendant.md)
  
### <a name="assigning-phone-numbers-for-an-auto-attendant"></a>为自动助理分配电话号码

如果需要多个电话号码，可以将 Microsoft 服务号码、直接路由号码或混合号码分配给自动助理的链接资源帐户 (或多个资源帐户（如果需要多个) ）。 有关 [更多详细信息，请参阅规划](direct-routing-plan.md) 直接路由。

若要分配服务号码，需要获取或移植现有的收费或免费服务号码。 获得收费或免费服务电话号码后，这些电话号码会显示在Skype for Business  >  **中心语音** 电话  >  **号码。** **"号码** 类型"列为"**服务 - 免费"。** 若要获取服务号码，请参阅获取[](./getting-service-phone-numbers.md)Skype for Business 和 Microsoft Teams 的服务电话号码;如果要转移现有服务号码，请参阅将电话号码转移到[Teams。](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)
  
> [!NOTE]
> 如果你在美国以外，则不能使用 Microsoft Teams管理中心获取服务号码。 转到 ["改为管理组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) "，了解如何执行。
  
## <a name="related-topics"></a>相关主题

[电话系统的功能](here-s-what-you-get-with-phone-system.md)

[获取 Skype for Business 和 Microsoft Teams 的服务电话号码](./getting-service-phone-numbers.md)

[音频会议和通话套餐的国家/地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)