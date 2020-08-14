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
description: 了解云自动助理以及如何使用它们让呼叫者在菜单系统中移动，以找到并将呼叫放入或转移到用户或部门。
ms.openlocfilehash: 88b1a67c1438efb5ef1113999feeffd9735f293f
ms.sourcegitcommit: eb8b573a426b6a68c763968c4cd2d45bc0d6a4b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/14/2020
ms.locfileid: "46672833"
---
# <a name="what-are-cloud-auto-attendants"></a>什么是云自动助理？

"电话系统" 提供自动助理，可用于让外部呼叫者和内部呼叫者在菜单系统中移动，以找到或将呼叫转移到组织中的用户或部门。
  
自动助理通常是系统中的节点，向呼叫者提供一系列语音提示或音频文件，而不是人工操作员。 当用户呼叫与自动助理关联的号码时，他们的选择可将呼叫重定向到用户或查找组织中的某人，然后连接到该用户。 他们可以通过使用电话键盘 (DTMF) 或语音识别来表示其选择，并与菜单系统进行交互。 他们所做的选择也可以将呼叫重定向到另一个自动助理或呼叫队列。
  
若要为手机系统设置自动助理，请转到 [设置云自动助理](create-a-phone-system-auto-attendant.md)。
  
云自动助理具有以下功能：
  
- 提供企业或信息性问候语。
- 提供自定义企业菜单。你可以自定义这些菜单以包含更多级别。
- 它提供目录搜索，使调用的人员可以在组织的目录中搜索名称。
- 它使呼叫者能够联系到您组织中的人员或为其留下消息。
- 它支持多种语言的提示、文本到语音转换和语音识别。
- 它支持指定假日和工作时间。
- 它支持将呼叫转移到操作员、其他用户、呼叫队列和自动助理。
- 它支持呼叫者共享语音邮件，以便为组织留下消息。

> [!NOTE]
> 本文适用于 Microsoft 团队和 Skype for business Online。

## <a name="getting-started"></a>入门

要开始使用自动助理，记住以下几点至关重要：

- 必须具有自动助理才能拥有关联的资源帐户。 有关资源帐户的详细信息，请参阅 [管理团队中的资源帐户](manage-resource-accounts.md) 。 <!-- You can either use an existing resource account or create a new resource account as you set up your auto attendant. -->
- 将电话号码分配给自动助理时，严格地说，您正在将其分配给与该自动助理关联的资源帐户。 这提供了一种让多个电话号码访问自动助理的方法。 通常，资源帐户将使用免费的电话系统虚拟用户许可证。 此许可证为组织级别的电话号码提供电话系统功能，并允许你创建自动助理和呼叫队列。

> [!NOTE]
> 只有 Microsoft 团队用户和呼叫代理才支持自动助理和呼叫队列的直接路由服务号码。

   > [!TIP]
   > 若要将呼叫重定向到使用 **电话系统** 许可证的联机用户的操作员或菜单选项，您需要为企业语音启用其帐户或为其分配呼叫计划。 请参阅 [分配 Microsoft 团队附加设备许可证](teams-add-on-licensing/assign-teams-add-on-licenses.md)。 你还可以使用 Windows PowerShell。 例如运行： `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- 若要为自动助理获取和使用免费服务号码，您需要设置通讯信用点数。 若要执行此操作，请参阅 [什么是通讯信用点数？](what-are-communications-credits.md) 并 [为您的组织设置通讯信用点数](set-up-communications-credits-for-your-organization.md)。

    > [!IMPORTANT]
    > [!重要信息] 不能将用户（订阅者）的电话号码分配给自动助理 - 只能使用收费或免费服务电话号码。

- 完整的自动助理系统通常会涉及多个自动助理。
- 可以对入门级自动助理应用多个电话号码。
- 如果整个系统中的非入门级自动助理或呼叫队列将在其上发出出站 PSTN 呼叫，则仅需要一个电话号码。
  
## <a name="feature-overview"></a>功能概述

### <a name="searching-for-users"></a>搜索用户

按名称拨号是自动助理的一项功能，也称为目录搜索。 它使呼叫您的自动助理的人可以使用语音 (语音识别) 或其电话键盘 (DTMF) 响应输入完整或部分名称以搜索公司的目录，找到该联系人，然后将呼叫转移到他们。 您希望使用 "按名称拨入" 和 "已达到" 状态的用户 **无需具有电话号码或有分配给他们的通话计划，但他们必须具有电话系统许可证（如果他们是联机用户）或为 Skype for Business 服务器用户启用的企业语音**。 通过名称拨号，您甚至可以找到并将呼叫转移到位于不同国家或地区组织的其他国家或地区的 Microsoft 团队用户。 根据所涉及的先决条件，在自动助理中明确启用 "按名称拨号"。

"通过分机号码拨号" 是自动助理的一项功能，它也是目录搜索的一部分。 它使呼叫您的自动助理的人可以使用语音 (语音识别) 或其电话键盘 (DTMF) 响应输入他们尝试访问的用户的电话分机，然后将呼叫转移到他们。 您希望使用 "通过分机拨入" 和 "已达到" 的用户  **无需具有电话号码或分配给他们的通话计划，但他们必须具有电话系统许可证（如果他们是联机用户）或为 Skype for Business 服务器用户启用的企业语音**。 您还需要为用户配置适当配置的拨号计划。 通过分机号码进行拨号，甚至可以查找与多国组织的不同国家或地区托管的 Microsoft 团队用户的呼叫和转移呼叫。 根据所涉及的先决条件，你可以显式启用自动助理中的 "通过扩展拨号"。

#### <a name="maximum-directory-size"></a>目录最大大小

对按名称拨入的 Active Directory 用户的数量没有限制，并且通过分机支持呼叫者搜索特定人员时可以支持。 呼叫者可以输入姓名 + LastName (部分或全名，也可以输入姓氏 + 名字) ，但需要完整的分机号码。 单个自动助理可以使用语音识别支持的最大名称列表大小是80000用户。
  
|输入类型|搜索格式|组织中的最大用户数|
|:-----|:-----|:-----|
|DTMF（键盘输入） |部分  <br/> 名字 + 姓氏  <br/> 姓氏 + 名字 |无限制  |
|语音（语音识别） |名  <br/> 姓名  <br/> 名字 + 姓氏  <br/> 姓氏 + 名字  | 80000用户 |

> [!NOTE]
> 如果你使用的是使用语音识别的 "按名称拨号"，但你的组织的 Active Directory 大于80000用户，并且你没有通过 "拨号作用域" 功能限制按名称进行拨号的范围，则按名称使用电话键盘仍可使用呼叫者，并且语音输入将可用于所有其他方案。 你可以使用"拨号范围"功能，通过更改按名字拨叫的范围，减少可以呼叫的姓名，以找到特定自动助理。
  
### <a name="dial-by-name---keypad-dtmf-entry"></a>按名字拨叫 - 键盘 (DTMF) 输入
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

#### <a name="dial-by-name---name-recognition-with-speech"></a>按名字拨叫 - 使用语音识别姓名

用户可以通过语音 (语音识别) 搜索其组织中的其他人。 他们还可以通过说出用户正在尝试查找的人员的姓名，与 Active Directory 中的任何人联系。 使用语音输入可以识别各种格式的名称，包括 "名字"、"姓氏"、"名字"、"姓氏" 或 "姓氏 + 名字"。
  
你可以启用自动助理的语音识别，但电话键盘条目 (DTMF) 不会禁用。 即使自动助理上已启用语音识别，也可以随时使用电话键盘条目。
  
与电话键盘条目一样，如果找到多个姓名，呼叫者将听到要选择的姓名列表。
  
调用方可以通过以下格式表达名称：
  
|带有语音的名称|搜索类型|示例|搜索结果|
|:-----|:-----|:-----|:-----|
|名字 + 姓氏 |完整 |Amos Marble |Amos Marble |
|姓氏 + 名字 |完整  |Marble Amos |Amos Marble |
|名 |完整 |Amos |按或报 1 选择 Amos Marble  <br/> 按或报 2 选择 Amos Jones |
|姓名 |完整 |Marble |按或报 1 选择 Amos Marble  <br/> 按或报 2 选择 Ben Marble |

> [!NOTE]
> 由于 Active Directory 复制延迟，新用户可能需要长达36小时才能将其名称列在目录中，以便通过语音识别按名称进行拨号。
  
### <a name="language-support"></a>语言支持

以下语言适用于与传出提示一起使用的文本到语音转换：
  
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

自动助理的语音识别输入适用于以下语言：
  
|||
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

### <a name="the-operator-option"></a>运算符选项

可选择将自动助理设置为向呼叫者提供一个选择以与人工接线员讲话。
  
Key 0 和 voice 命令 "Operator" 默认情况下，将呼叫定向到指定的操作员。 语音识别支持的所有语言都属于这种情况。 你还可以使用 " **设置菜单选项** " 设置运算符的自定义值。
  
操作员可以设置为：
  
- 企业语音启用的 Microsoft 团队用户或 Skype for business 服务器用户。
- 为组织设置的其他自动助理。
- 组织中建立的任何现有呼叫队列。 若要查看有关通话队列的详细信息，请参阅 [创建云呼叫队列](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)。

### <a name="business-hours-and-call-handling"></a>营业时间和呼叫处理

可以在每个自动助理上设置工作时间。 如果没有设置营业时间，所有日期以及每天的所有时间均视为营业时间，因为默认情况下设置为全天候时间表。 可以在一天内通过休息时间设置工作时间，并且未设置为工作时间的所有小时都将被认为是在小时后。 你可以设置不同的传入呼叫处理选项和不同的问候语 (这些选项是工作时间和工作时间后的可选) 。
  
每个自动助理有几个可能的调用处理选项：
  
- 播放问候语后，呼叫可能断开连接。
- 您也可以：
  - 将呼叫重定向到具有 "企业语音启用" 或 "已分配呼叫计划" 的 **电话系统** 许可证的 Microsoft 团队用户。 你可以通过此设置将呼叫者直接转到语音邮件。 为此，请选择" **贵公司的人**"，此人会将其呼叫直接转到语音邮件。

  - 将呼叫重定向到呼叫队列。 若要查看有关通话队列的详细信息，请参阅 [创建云呼叫队列](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)。

  - 将呼叫重定向到另一个自动助理。

在播放菜单提示时，这些选项由自动助理表示给呼叫者。 例如： "按1查看销售额，按2表示服务。 若要向操作员讲话，请在任何时候按0。 "

### <a name="set-menu-options"></a>设置菜单选项

云自动助理允许你创建菜单提示 ( "按1键进行销售，按2项服务" ) 并设置菜单选项以根据用户选择路由呼叫。 自动助理的菜单选项让组织提供一系列选项，可指导呼叫者更快地向其目标，而无需依靠人工接线员处理传入呼叫。 可通过使用文本到语音 (系统生成的提示) 或上载录制的音频文件来创建菜单提示。 语音识别接受用于无人参与导航的语音命令，但呼叫的人员也可以使用电话键盘导航菜单。
  
可以使用 Skype for Business 管理中心将键0到9分配给自动助理中的电话。 可以为营业时间和非营业时间创建不同的菜单选项集，并且可以在 **菜单选项**中启用或禁用按名字拨叫。 这些键可以映射为将呼叫转接至：
  
- 接线员，默认情况下映射到键 0。 但是，可以将其重新分配给任何其他键，或将其从菜单中删除。
- 通话队列。
- 另一种自动助理。 通过将一个自动助理中的 **菜单选项** 指向另一个自动助理，并将其设置为 "嵌套" 自动助理，可以设置多级别菜单。
- 具有 **手机系统** 许可证的 Microsoft 团队用户，该许可证是企业语音启用的或分配了呼叫计划。 你可以通过此设置将呼叫者直接转到语音邮件。 为此，请选择" **贵公司的人**"，此人会将其呼叫直接转到语音邮件。
  
如果已启用语音识别，则每个菜单选项的名称将变为语音识别关键字。 例如，呼叫者可以说 "One" 以选择映射到键1的菜单选项，或者说 "销售额" 以选择名为 "Sales" 的相同菜单选项。
  
若要设置自动助理和菜单选项，请转到 [设置云自动助理](create-a-phone-system-auto-attendant.md)。
  
### <a name="assigning-phone-numbers-for-an-auto-attendant"></a>为自动助理分配电话号码

如果需要多个电话号码，您可以为您的自动助理的链接资源帐户 (或多个资源帐户分配 Microsoft 服务号码、直接路由号码或混合号码) 。 有关其他详细信息，请参阅 [规划直接路由](direct-routing-plan.md) 。

要分配服务号码，您需要购买或移植您现有的收费或免费服务号码。 获得收费或免费服务电话号码后，它们将显示在**Skype for business 管理中心的**  >  **语音**  >  **电话号码**中。 **号码类型** 列为 " **服务-** 免费"。 若要获取你的服务号码，请参阅 [获取 Skype for business 和 Microsoft 团队的服务电话号码](/microsoftteams/getting-service-phone-numbers) ; 如果要转移和现有服务号码，请参阅 [将电话号码转移到团队](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)。
  
> [!NOTE]
> 如果您在美国以外，则不能使用 Microsoft 团队管理中心获取服务号码。 转到 " [管理你的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) " 以了解如何操作。
  
## <a name="related-topics"></a>相关主题

[电话系统的功能](here-s-what-you-get-with-phone-system.md)

[获取 Skype for Business 和 Microsoft Teams 的服务电话号码](/microsoftteams/getting-service-phone-numbers)

[音频会议和通话套餐的国家/地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[小型企业示例 - 设置自动助理](/microsoftteams/tutorial-org-aa)
