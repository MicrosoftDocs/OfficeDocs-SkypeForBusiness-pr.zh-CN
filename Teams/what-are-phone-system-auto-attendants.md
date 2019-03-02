---
title: 什么是电话系统自动助理？
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: makolomi
ms.date: 9/1/2018
ms.topic: article
ms.assetid: ab9f05a2-22cb-4692-a585-27f82d1b37c7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
- Strat_SB_PSTN
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 了解什么是电话系统 (云 PBX) 自动助理以及如何使用它们。
ms.openlocfilehash: 8ffb43d02ed100a3767fce3338b98c05760c1c9a
ms.sourcegitcommit: 59eda0c17ff39a3e6632810391d78bbadc214419
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/01/2019
ms.locfileid: "30353503"
---
# <a name="what-are-phone-system-auto-attendants"></a>什么是电话系统自动助理？

Office 365 中的电话系统提供自动助理，可用于让外部和内部呼叫者通过菜单系统，以查找并放置或将呼叫转接到您的组织中的部门或公司用户移动。
  
自动助理是一系列语音提示或组织时，呼叫者收听，而不是 human 运算符的音频文件。 人员调用与自动助理的号码，他们的选项可以呼叫重定向到用户或您的组织中找到某人，然后连接到该用户。 他们可以 express 他们的选项，并通过使用电话小键盘 (DTMF) 或语音识别与菜单系统进行交互。
  
若要设置自动助理的 Office 365 中的电话系统，转到[设置电话系统自动助理](create-a-phone-system-auto-attendant.md)。
  
电话系统自动助理拥有下列功能：
  
- 提供企业或信息性问候语。
- 提供自定义企业菜单。你可以自定义这些菜单以包含更多级别。
- 它提供目录搜索，使呼叫在名称组织的目录中搜索的人员。
- 使某人调用中访问或留言您的组织中的人员。

> [!NOTE]
> 本文同时适用于 Microsoft 团队和 Skype 业务 online。

## <a name="getting-started"></a>入门

要开始使用自动助理，记住以下几点至关重要：
  
- 企业版 E3 以及**电话系统**的许可证或企业 E5 许可证，您的组织必须 （最低要求）。 可供用于自动助理的**电话系统**的用户许可证分配影响的服务数数字的号码。 您可以自动助理数是取决于您的组织中分配的号码**电话系统**和**音频会议**许可证。 若要了解有关授权的详细信息，请参阅[Microsoft 团队加载项授权](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。
    
    > [!TIP]
    > 要重定向呼叫的运算符或联机用户与**电话系统**许可证的菜单选项，您将需要启用企业语音或分配给它们的调用计划。 请参阅[分配的 Microsoft 团队许可证](assign-teams-licenses.md)。 你还可以使用 Windows PowerShell。 例如运行： `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- 若要获取并使用自动助理服务免费电话号码，您需要设置 Communications 字幕式。 若要执行此操作，请参阅[Communications 字幕式是什么？](what-are-communications-credits.md)并[设置为您的组织的通信字幕式](set-up-communications-credits-for-your-organization.md)。

    > [!IMPORTANT]
    > [!重要信息] 不能将用户（订阅者）的电话号码分配给自动助理 - 只能使用收费或免费服务电话号码。
- 自动助理需要具有关联的资源帐户。 有关资源帐户的详细信息，请参阅[团队中的管理资源帐户](manage-resource-accounts.md)。
- 完成自动助理系统通常将涉及多个自动助理和可能只需一个分配的电话号码的顶级或项自动助理。 其他自动助理或完整系统中的呼叫队列只需要一个电话号码如果您想要提供多个到系统的入口点。
- 很可能要应用于自动助理的多个电话号码，通过将多个电话号码的自动助理资源帐户相关联。
  
## <a name="feature-overview"></a>功能概述

### <a name="dial-by-name"></a>按名字拨叫

按名称拨号是自动助理，也称为目录搜索功能。 使呼叫您的自动助理要使用语音 （语音识别） 或其电话 (DTMF) 小键盘响应输入搜索公司目录，找到该人，全称或部分名称，然后向其转接呼叫的人员。 您想要找出并达到使用按名称的拨号用户**不需要具有电话号码或调用计划分配给它们，但是它们必须具有电话系统许可证**。 按名称的电话拨甚至可以查找和将呼叫转接到的 Microsoft 团队承载在不同的国家或地区的多个国家/地区的组织的用户。

### <a name="maximum-directory-size"></a>目录最大大小

使用电话小键盘输入部分或完整名称 （FirstName + LastName 和还 LastName + FirstName） 搜索时为其支持按名称拨号 Active Directory 大小没有限制。 但是，单一的自动助理可以支持使用语音识别功能识别的名称的最大名称列表大小是 80,000 用户。
  
|输入类型|搜索格式|组织中的最大用户数|
|:-----|:-----|:-----|
|DTMF（键盘输入） |部分  <br/> 名字 + 姓氏  <br/> 姓氏 + 名字 |没有硬性限制  |
|语音（语音识别） |FirstName  <br/> 姓氏  <br/> 名字 + 姓氏  <br/> 姓氏 + 名字  |80,000 用户 |

> [!NOTE]
> 如果您使用的按名称的拨号使用语音识别功能识别的但您的组织的 Active Directory 大于 80,000 用户和没有限制拨号按使用拨号作用域功能的名称的范围，拨号按名称仍然有效的呼叫者使用电话小键盘和语音输入将适用于所有其他方案。 你可以使用"拨号范围"功能，通过更改按名字拨叫的范围，减少可以呼叫的姓名，以找到特定自动助理。
  
### <a name="dial-by-name---keypad-dtmf-entry"></a>按名字拨叫 - 键盘 (DTMF) 输入

调用中的人员可以使用按名称拨号推向用户通过指定可以尝试与取得联系的联系人的全称或部分名称。 好处是时输入的名称，可以使用的各种格式。

搜索组织目录时，用户可以使用"0"（零）键来表示名字与姓氏之间或姓氏与名字之间的空格。输入姓名时，会要求他们用 #（井号）键表示键盘输入结束。例如，"在你输入要联系的用户姓名后，请按 # 号"。如果找到多个姓名，会向呼叫者提供姓名列表，供其从中选择。
  
用户可以在电话键盘上使用以下搜索格式搜索组织中的姓名：
  
|姓名格式|搜索类型|示例|搜索结果|
|:-----|:-----|:-----|:-----|
|名字 + 姓氏 |完整  |Amos0Marble# |Amos Marble |
|姓氏 + 名字 |完整 |Marble0Amos#  |Amos Marble |
|FirstName  |完整   |Amos#   |按 1 选择 Amos Marble  <br/> 按 2 选择 Amos Marcus |
|姓氏 |完整 |Marble#  |按 1 选择 Amos Marble  <br/> 按 2 选择 Mary Marble |
|名字或姓氏 |部分 |Mar# |按 1 选择 Mary Marble  <br/> 按 2 选择 Mary Jones  <br/> 按 3 选择 Amos Marcus |
|名字 + 姓氏 |部分 |Mar0Amos# |按 1 选择 Amos Marble  <br/> 按 2 选择 Amos Marcus |
|姓氏 + 名字 |部分 |Mar0Am# |按 1 选择 Amos Marble  <br/> 按 2 选择 Amos Marcus |

使用电话键盘搜索用户时可以使用多种特殊字符。 例如，此人将要求使用井号键 （#），而零 (0) 键用于名称之间的空格。 按星号键 (*) 将重复与该用户匹配的姓名列表。
  
|特殊电话键盘字符|含义|
|:-----|:-----|
|#（井号键） |输入姓名时的结束字符。 |
|0（零） |姓名中间的空格。 |
|*（星号键）  |重复姓名匹配列表。 |

### <a name="dial-by-name---name-recognition-with-speech"></a>按名字拨叫 - 使用语音识别姓名

人员可以搜索其组织使用其语音 （语音识别） 中的其他人。 它们可告知他们正在查找的人员的姓名来达到公司的 Active Directory 中的任何人。 使用语音输入可以识别的各种格式，包括 FirstName、 LastName、 FirstName + 姓氏或姓氏 + 名字的名称。
  
启用语音识别功能识别的自动助理时，不会禁用电话小键盘条目 (DTMF)，因此可以使用两种类型的输入。 电话小键盘条目不能禁用，并且可在任何时候，即使自动助理上启用了语音识别。
  
使用电话键盘输入时，如果找到多个姓名，会向呼叫者提供姓名列表，供其从中选择。
  
呼叫者可以采用以下格式报出姓名：
  
|使用语音名称|搜索类型|示例|搜索结果|
|:-----|:-----|:-----|:-----|
|名字 + 姓氏 |完整 |Amos Marble |Amos Marble |
|姓氏 + 名字 |完整  |Marble Amos |Amos Marble |
|FirstName |完整 |Amos |按或报 1 选择 Amos Marble  <br/> 按或报 2 选择 Amos Jones |
|姓氏 |完整 |Marble |按或报 1 选择 Amos Marble  <br/> 按或报 2 选择 Ben Marble |

> [!NOTE]
> 可能需要 36 小时的时间的新用户具有其列在目录中的拨号按名称语音识别的名称。
  
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
  
|语音命令|含义|
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

为自动助理使用接线员是一项可选设置，此设置向呼叫者提供与真人对话的选项。
  
默认情况下将键 0 和语音命令"接线员"（可使用支持语音识别的所有语言）分配给接线员。
  
> [!NOTE]
> 您可以设置的推送为**运算符**到不同的密钥使用**菜单选项**按钮。
  
可以将以下人员设置为接线员：
  
- 具有许可证的**电话系统**的 Microsoft 团队用户启用企业语音或调用计划分配给它们。 你可以通过此设置将呼叫者直接转到语音邮件。 为此，请选择" **贵公司的人**"，此人会将其呼叫直接转到语音邮件。

    > [!NOTE]
    > 用户托管在本地使用 Lync Server 2010 不能用作运算符。
  
- 为组织设置的其他自动助理。
- 组织中建立的任何现有呼叫队列。 若要查看有关呼叫队列的详细信息，请参阅[创建电话系统呼叫队列](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)。

### <a name="business-hours-and-call-handling"></a>营业时间和呼叫处理

营业时间在每个自动助理上设置。 如果没有设置营业时间，所有日期以及每天的所有时间均视为营业时间，因为默认情况下设置为全天候时间表。 营业时间可以使用页符期间日和所有未设置为视为下班后营业时间的时间设置。 您可以设置不同的传入呼叫处理选项和不同问候语 （这是可选的），并同时可以设置的工作时间和下班后。
  
每个自动助理具有可设置的呼叫处理选项：
  
- 可以在问候之后断开呼叫。
- 您也可以：
  - 已启用企业语音的**电话系统**许可证的 Microsoft 团队用户将呼叫重定向或调用计划分配给它们。 你可以通过此设置将呼叫者直接转到语音邮件。 为此，请选择" **贵公司的人**"，此人会将其呼叫直接转到语音邮件。

    > [!NOTE]
    > 用户托管在本地不支持使用 Lync Server 2010。
  
  - 向呼叫队列将呼叫重定向。 若要查看有关呼叫队列的详细信息，请参阅[创建电话系统呼叫队列](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)。

  - 呼叫重定向到另一个已设置的自动助理。
- 创建菜单选项并为呼叫者播放菜单提示。例如："请按 1 选择销售，按 2 选择服务。如需联系接线员，请随时按 0。"

### <a name="menu-options"></a>菜单选项

电话系统自动助理，可以创建菜单提示 （"按 1 为销售，按 2 的服务"） 和设置以基于用户的选择将呼叫路由的菜单选项。 通过为自动助理设置菜单选项，组织能够提供交互式指导，帮助用户更快达到目的地，而无需依赖人工接线员来处理传入呼叫。 通过使用文本到语音转换 （系统生成的提示） 或上载音频文件已记录，可以创建菜单提示。 语音识别使用语音命令来实现无需用手操作的导航，但是呼叫者也可以使用电话键盘来导航菜单。
  
0-9 可分配给**菜单选项**中的业务管理中心使用 Skype 的自动助理。 可以为营业时间和非营业时间创建不同的菜单选项集，并且可以在 **菜单选项**中启用或禁用按名字拨叫。 这些键可以映射为将呼叫转接至：
  
- 接线员，默认情况下映射到键 0。 但是，它可以重新分配到任何其他项，或从菜单中删除。
- 呼叫队列。
- 另一种自动助理。 可以通过在一个自动助理**菜单选项**指向另一个自动助理菜单选项，该数据库称为"嵌套"的自动助理自己集设置多级菜单。
- 具有许可证的**电话系统**的 Microsoft 团队用户启用企业语音或调用计划分配给它们。 你可以通过此设置将呼叫者直接转到语音邮件。 为此，请选择" **贵公司的人**"，此人会将其呼叫直接转到语音邮件。

    > [!NOTE]
    > 用户托管在本地使用 Lync Server 2010 不能在**菜单选项**。
  
如果已启用语音识别，每个菜单选项的名称将成为语音识别关键字。 例如，呼叫者可以说"之一"，选择映射到键 1，菜单选项或它们只可以说"Sales"选择相同的菜单选项名为"Sales"。
  
若要设置自动助理和菜单选项，请转[设置电话系统自动助理](create-a-phone-system-auto-attendant.md)。
  
### <a name="getting-service-numbers-for-an-auto-attendant"></a>获取自动助理的服务号

Before you can create and set up your auto attendants, you will need to get or transfer your existing toll or toll-free service numbers. 一旦您获取的收费电话或免费电话服务电话号码，它们会显示在**业务管理中心的 Skype** > **语音** > **电话号码**，并列出**Service-作为免费电话**号码类型**列出将**. 若要获取服务号码，请参阅[Getting 服务电话号码的业务和 Microsoft 团队的 Skype](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers) ，或如果您希望进行传输和现有服务号码，请参阅[传输到 Office 365 的电话号码](transfer-phone-numbers-to-office-365.md)。
  
> [!NOTE]
> 如果您在美国以外，您无法使用业务管理中心的 Skype 获取服务号码。 而是转[管理组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)以了解如何执行此操作。
  
## <a name="changing-the-users-caller-id-to-be-a-call-queues-phone-number"></a>更改用户的来电显示为呼叫队列的电话号码

通过使用**新建 CallingLineIdentity** cmdlet 创建策略，可将出站呼叫的来电显示更改为呼叫队列，从而保护用户的身份。
  
若要执行此操作，请运行：
  
``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

然后使用 **Grant-CallingLineIdentity** cmdlet 将策略应用于用户。 若要执行此操作，请运行：
  
``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

您可以获取有关如何对您[如何可以呼叫者 ID 是您组织中使用](/SkypeForBusiness/what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization)的组织中的呼叫者 ID 设置进行更改的详细信息。
  
## <a name="related-topics"></a>相关主题

[以下是 Office 365 中的电话系统功能](here-s-what-you-get-with-phone-system.md)

[获取 Skype for Business 和 Microsoft Teams 的服务电话号码](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers)

[音频会议和通话套餐的国家/地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[小型企业示例-设置的自动助理](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)
