---
title: 什么是云自动助理？
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: makolomi
ms.date: 4/2/2019
ms.topic: article
ms.assetid: ab9f05a2-22cb-4692-a585-27f82d1b37c7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.autoattendants.overview
ms.custom:
- Phone System
description: 了解什么是云自动助理以及如何使用它们。
ms.openlocfilehash: 3dc96398cb2aa9ab3eafcc6e5d38ad2feb44b45b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299038"
---
# <a name="what-are-cloud-auto-attendants"></a>什么是云自动助理？

Office 365 中的电话系统提供自动助理, 可用于让外部呼叫者和内部呼叫者在菜单系统中移动, 以找到或将呼叫转移到组织中的公司用户或部门。
  
自动助理是呼叫者在呼叫组织时听到的一系列语音提示或音频文件, 而不是人工操作员。 当用户呼叫与自动助理关联的号码时, 他们的选择可将呼叫重定向到用户或查找组织中的某人, 然后连接到该用户。 他们可以通过电话键盘 (DTMF) 或语音识别来表示其选择, 并与菜单系统进行交互。
  
若要为 Office 365 中的电话系统设置自动助理, 请转到[设置云自动助理](create-a-phone-system-auto-attendant.md)。
  
云自动助理具有以下功能:
  
- 提供企业或信息性问候语。
- 提供自定义企业菜单。你可以自定义这些菜单以包含更多级别。
- 它提供目录搜索, 使调用的人员可以在组织的目录中搜索名称。
- 它使呼叫者能够联系到您组织中的人员或为其留下消息。
- 它支持多种语言的提示、文本到语音转换和语音识别。
- 它支持指定假日和工作时间。
- 它支持将呼叫转移到操作员、其他用户、呼叫队列和自动助理。

> [!NOTE]
> 本文适用于 Microsoft 团队和 Skype for business Online。

## <a name="getting-started"></a>入门

要开始使用自动助理，记住以下几点至关重要：

- 必须具有自动助理才能拥有关联的资源帐户。 有关资源帐户的详细信息, 请参阅[管理团队中的资源帐户](manage-resource-accounts.md)。
- 如果你计划分配直接路由号码, 你需要使用手机系统加载项获取以下许可证并将其分配给\(你的资源帐户 Office 365 企业版 E1、E3 或 E5\)。
- 如果你改为分配 Microsoft 服务号码, 你需要使用手机系统加载项和呼叫计划\(\)获取并将以下许可证分配给你的资源帐户 Office 365 企业版 E1、E3 或 E5。
- 您只需向分配了电话号码的资源帐户授予许可证。 在嵌套的自动助理或呼叫队列中, 如果自动助理或呼叫队列没有与之关联的电话号码, 则无需向其授予许可证。 

> [!NOTE]
> 只有 Microsoft 团队用户和代理才支持自动助理和呼叫队列的直接路由服务号码。

> [!NOTE]
> Microsoft 正在致力于应用程序 (如云自动助理和呼叫队列) 的无成本许可模型, 现在您需要使用用户许可模型。
    
   > [!TIP]
   > 要将呼叫重定向到使用**电话系统**许可证的联机用户的操作员或菜单选项, 您需要为企业语音启用它们或为其分配呼叫计划。 请参阅[分配 Microsoft 团队许可证](assign-teams-licenses.md)。 你还可以使用 Windows PowerShell。 例如运行： `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- 若要为自动助理获取和使用免费服务号码, 您需要设置通讯信用点数。 若要执行此操作, 请参阅[什么是通讯信用点数？](what-are-communications-credits.md)并[为您的组织设置通讯信用点数](set-up-communications-credits-for-your-organization.md)。

    > [!IMPORTANT]
    > [!重要信息] 不能将用户（订阅者）的电话号码分配给自动助理 - 只能使用收费或免费服务电话号码。

- 完整的自动助理系统通常涉及多个自动助理, 并且可能仅需要单个分配的电话号码才能用于顶级或输入自动助理。 如果你想要向系统提供多个入口点, 则完整系统中的其他自动助理或呼叫队列将仅需要一个电话号码。
- 通过将多个资源帐户与自动助理相关联, 可以将多个电话号码应用于自动助理。
  
## <a name="feature-overview"></a>功能概述

### <a name="dial-by-name"></a>按名字拨叫

按名称拨号是自动助理的一项功能, 也称为目录搜索。 它使呼叫您的自动助理的用户可以使用语音 (语音识别) 或其电话键盘 (DTMF) 响应输入完整或部分名称以搜索公司的目录, 找到该联系人, 然后将呼叫转移到他们。 您希望使用 "按名称拨入" 和 "已达到" 状态的用户**无需具有电话号码或分配给他们的通话计划, 但如果他们是联机用户或为 onpremises 用户启用了 EV, 则他们必须具有电话系统许可证**。 通过名称拨号, 您甚至可以找到并将呼叫转移到位于不同国家或地区组织的其他国家或地区的 Microsoft 团队用户。

### <a name="maximum-directory-size"></a>目录最大大小

使用电话键盘搜索 "输入部分或全名" ("名字" + "姓氏" 以及 "姓氏" + "名字") 时, 对按名称进行拨号的活动目录大小没有限制。 但是, 单个自动助理可支持使用带语音的名称识别的最大名称列表大小是80000用户。
  
|输入类型|搜索格式|组织中的最大用户数|
|:-----|:-----|:-----|
|DTMF（键盘输入） |部分  <br/> 名字 + 姓氏  <br/> 姓氏 + 名字 |无限制  |
|语音（语音识别） |名  <br/> 姓名  <br/> 名字 + 姓氏  <br/> 姓氏 + 名字  | 80000用户 |

> [!NOTE]
> 如果你使用的是使用语音识别的 "按名称拨入", 但你的组织的 Active Directory 大于80000用户, 并且你未使用 "拨号作用域" 功能限制按名称进行拨号的范围, 则使用电话键盘, "按名称拨号" 仍将适用于呼叫者, 并且语音输入将可用于所有其他方案。 你可以使用"拨号范围"功能，通过更改按名字拨叫的范围，减少可以呼叫的姓名，以找到特定自动助理。
  
### <a name="dial-by-name---keypad-dtmf-entry"></a>按名字拨叫 - 键盘 (DTMF) 输入

拨入者可以通过指定要访问的人员的全名或部分名称, 使用 "按名称拨号" 访问用户。 输入姓名时可以使用不同的格式。

搜索组织目录时，用户可以使用"0"（零）键来表示名字与姓氏之间或姓氏与名字之间的空格。 输入名称时, 系统将要求他们用 # 键终止其键盘输入。 例如，"在你输入要联系的用户姓名后，请按 # 号"。 如果找到多个姓名，会向呼叫者提供姓名列表，供其从中选择。
  
用户可以在电话键盘上使用以下搜索格式搜索组织中的姓名：
  
|姓名格式|搜索类型|示例|搜索结果|
|:-----|:-----|:-----|:-----|
|名字 + 姓氏 |完整  |Amos0Marble# |Amos Marble |
|姓氏 + 名字 |完整 |Marble0Amos#  |Amos Marble |
|名  |完整   |Amos#   |按 1 选择 Amos Marble  <br/> 按 2 选择 Amos Marcus |
|姓名 |完整 |Marble#  |按 1 选择 Amos Marble  <br/> 按 2 选择 Mary Marble |
|名字或姓氏 |部分 |Mar# |按 1 选择 Mary Marble  <br/> 按 2 选择 Mary Jones  <br/> 按 3 选择 Amos Marcus |
|名字 + 姓氏 |部分 |Mar0Amos# |按 1 选择 Amos Marble  <br/> 按 2 选择 Amos Marcus |
|姓氏 + 名字 |部分 |Mar0Am# |按 1 选择 Amos Marble  <br/> 按 2 选择 Amos Marcus |

使用电话键盘搜索用户时可以使用多种特殊字符。 例如, 将要求人员使用井号键 (#), 而零 (0) 键用于名称之间的空格。 按星号键 (*) 将重复与该用户匹配的姓名列表。
  
|特殊电话键盘字符|含义|
|:-----|:-----|
|#   |输入姓名时的结束字符。 |
|0   |姓名中间的空格。 |
|*    |重复姓名匹配列表。 |

### <a name="dial-by-name---name-recognition-with-speech"></a>按名字拨叫 - 使用语音识别姓名

用户可以使用语音 (语音识别) 在其组织中搜索其他人。 他们还可以通过说出公司的活动目录中的任何人的姓名来联系他们。 使用语音输入可以识别各种格式的名称, 包括 "名字"、"姓氏"、"名字"、"姓氏" 或 "姓氏 + 名字"。
  
为自动助理启用语音识别后, 将不会禁用电话键盘项 (DTMF), 因此可以使用这两种类型的输入。 电话键盘条目无法禁用, 并且可以随时使用, 即使自动助理上已启用语音识别也是如此。
  
使用电话键盘输入时，如果找到多个姓名，会向呼叫者提供姓名列表，供其从中选择。
  
呼叫者可以采用以下格式报出姓名：
  
|带有语音的名称|搜索类型|示例|搜索结果|
|:-----|:-----|:-----|:-----|
|名字 + 姓氏 |完整 |Amos Marble |Amos Marble |
|姓氏 + 名字 |完整  |Marble Amos |Amos Marble |
|名 |完整 |Amos |按或报 1 选择 Amos Marble  <br/> 按或报 2 选择 Amos Jones |
|姓名 |完整 |Marble |按或报 1 选择 Amos Marble  <br/> 按或报 2 选择 Ben Marble |

> [!NOTE]
> 由于 Active Directory 复制延迟, 新用户可能需要长达36小时才能将其名称列在目录中, 以便通过语音识别按名称进行拨号。
  
### <a name="language-support"></a>语言支持

文本到语音转换可以使用以下语言：
  
||||
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

用于自动助理的语音识别可以使用以下语言：
  
|||
|:-----|:-----|
|中文 (ZH)  |法语 (FR)  |
|英语 (AU)  |德语 (DE)  |
|英语 (CA)  |意大利语 (IT)  |
|英语 (IN)  |日语 (JP)  |
|英语 (UK)  |葡萄牙语 (BR)  |
|英语 (US)  |西班牙语 (ES)  |
|法语 (CA)   |西班牙语 (MX)  |

以下语音命令可以使用十四 (14) 种支持语音识别的语言：
  
|语音命令| 对应于 |
|:-----|:-----|
|是 |是 - 对应于按 1 表示"是"。 |
|否 |否 - 对应于按 2 表示"否"。 |
|重复 |重复选项列表 - 对应于按 * 重复选项列表。 |
|接线员 |跳转到接线员 - 对应于按 0 转到"接线员"。 |
|主菜单  |为呼叫者返回到自动助理的主菜单。 |
|零 |对应于按 0（默认情况下，与"接线员"相同）。|
|一 |对应于按 1。 |
|二 |对应于按 2。 |
|三|对应于按 3。|
|四 |对应于按 4。 |
|五 |对应于按 5。 |
|六  |对应于按 6。 |
|七 |对应于按 7。|
|八 |对应于按 8。|
|九  |对应于按 9。|

### <a name="using-the-operator-option"></a>使用接线员选项

将运算符用于自动助理是一种可选设置, 可向呼叫者提供对人工操作员讲话的选项。
  
Key 0 和 voice 命令 "Operator" 默认情况下, 将呼叫定向到指定的操作员。 语音识别支持的所有语言都属于这种情况。 你还可以使用**菜单选项**为该运算符设置自定义值。
  
操作员可以设置为:
  
- 已启用企业语音的 Microsoft 团队用户或 Skype for business 本地用户。
  
- 为组织设置的其他自动助理。
- 组织中建立的任何现有呼叫队列。 若要查看有关通话队列的详细信息, 请参阅[创建云呼叫队列](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)。

### <a name="business-hours-and-call-handling"></a>营业时间和呼叫处理

营业时间在每个自动助理上设置。 如果没有设置营业时间，所有日期以及每天的所有时间均视为营业时间，因为默认情况下设置为全天候时间表。 可以在一天内通过休息时间设置工作时间, 并且未设置为工作时间的所有小时都将被认为是在小时后。 您可以设置不同的传入呼叫处理选项和不同的问候语 (可选), 并且两者都可以设置为 "营业时间" 和 "工作时间后"。
  
每个自动助理都具有可设置的调用处理选项:
  
- 可以在问候之后断开呼叫。
- 您也可以：
  - 将呼叫重定向到具有 "企业语音启用" 或 "已分配呼叫计划" 的**电话系统**许可证的 Microsoft 团队用户。 你可以通过此设置将呼叫者直接转到语音邮件。 为此，请选择" **贵公司的人**"，此人会将其呼叫直接转到语音邮件。

  
  - 将呼叫重定向到呼叫队列。 若要查看有关通话队列的详细信息, 请参阅[创建云呼叫队列](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)。

  - 将呼叫重定向到已设置的其他自动助理。
- 创建菜单选项并为呼叫者播放菜单提示。例如："请按 1 选择销售，按 2 选择服务。如需联系接线员，请随时按 0。"

### <a name="menu-options"></a>菜单选项

云自动助理允许你创建菜单提示 ("按1表示销售额, 按2个服务"), 并设置菜单选项以根据用户选择的内容路由呼叫。 通过为自动助理设置菜单选项，组织能够提供交互式指导，帮助用户更快达到目的地，而无需依赖人工接线员来处理传入呼叫。 可通过使用文本到语音 (系统生成的提示) 或通过上载已录制的音频文件来创建菜单提示。 语音识别使用语音命令来实现无需用手操作的导航，但是呼叫者也可以使用电话键盘来导航菜单。
  
可以使用 Skype for Business 管理中心将键0到9分配给自动助理中的**菜单选项**。 可以为营业时间和非营业时间创建不同的菜单选项集，并且可以在 **菜单选项**中启用或禁用按名字拨叫。 这些键可以映射为将呼叫转接至：
  
- 接线员，默认情况下映射到键 0。 但是, 它可以重新分配给任何其他键, 或从菜单中删除。
- 通话队列。
- 另一种自动助理。 通过将一个自动助理中的**菜单选项**指向另一个自动助理, 并将其设置为 "嵌套" 自动助理, 可以设置多级别菜单。
- 具有**手机系统**许可证的 Microsoft 团队用户, 该许可证是企业语音启用的或分配了呼叫计划。 你可以通过此设置将呼叫者直接转到语音邮件。 为此，请选择" **贵公司的人**"，此人会将其呼叫直接转到语音邮件。
  
如果已启用语音识别, 则每个菜单选项的名称将变为语音识别关键字。 例如, 呼叫者可以说 "One" 以选择映射到键1的菜单选项, 也可以简单地说 "销售额" 以选择名为 "Sales" 的相同菜单选项。
  
若要设置自动助理和菜单选项, 请转到[设置云自动助理](create-a-phone-system-auto-attendant.md)。
  
### <a name="assigning-phone-numbers-for-an-auto-attendant"></a>为自动助理分配电话号码

您可以将 Microsoft 通话计划服务号码或直接路由混合号码分配给自动助理。 有关详细信息, 请参阅[规划直接路由](direct-routing-plan.md)。

要分配服务号码, 您需要购买或转移您现有的收费或免费服务号码。 获得收费或免费服务电话号码后, 这些电话号码将显示在 <!-- validate nav path --> **Skype for business 管理中心** > **语音** > **电话号码**, 列出的**号码类型**将列为 "**服务-** 免费"。 若要获取你的服务号码, 请参阅[获取 Skype for business 和 Microsoft 团队的服务电话号码](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers); 如果要转移和现有服务号码, 请参阅将[电话号码转移到 Office 365](transfer-phone-numbers-to-office-365.md)。
  
> [!NOTE]
> 如果您在美国以外, 则不能使用 Microsoft 团队管理中心获取服务号码。 转到 "[管理你的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)" 以了解如何操作。
  
## <a name="related-topics"></a>相关主题

[以下是 Office 365 中的电话系统功能](here-s-what-you-get-with-phone-system.md)

[获取 Skype for Business 和 Microsoft Teams 的服务电话号码](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers)

[音频会议和通话套餐的国家/地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[小型企业示例 - 设置自动助理](/microsoftteams/tutorial-org-aa)
