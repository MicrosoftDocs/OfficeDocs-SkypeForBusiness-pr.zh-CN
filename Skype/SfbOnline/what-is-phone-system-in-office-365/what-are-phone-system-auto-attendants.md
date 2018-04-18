---
title: 电话系统自动助理是什么？
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.assetid: ab9f05a2-22cb-4692-a585-27f82d1b37c7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
description: '学习电话系统 (云 PBX) 自动助理是什么以及如何使用它们。 '
ms.openlocfilehash: 59c0dbc129e782749cdc873115e760f1e3d894e3
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="what-are-phone-system-auto-attendants"></a>电话系统自动助理是什么？

在 Office 365 可以使用自动助理创建为您的组织允许内部和外部的调用方的菜单系统的电话系统移动的菜单系统，以查找并放置或转移求助电话公司用户或您的组织中的部门。
  
当有人呼叫时，他们会收到一系列语音提示，这些提示可帮助他们呼叫用户或者在组织中找到用户并随后呼叫该用户。 自动助理是一系列的语音提示操作或对组织拨打电话时，呼叫者将听到而不是人工接线员的音频文件。 自动助理使呼叫者能够移动浏览菜单系统，进行呼叫，或者使用电话键盘 (DTMF) 或采用语音识别功能的语音输入找到用户。 
  
若要设置自动助理 Office 365 中的电话系统，转到[设置电话系统自动助理](set-up-a-phone-system-auto-attendant.md)。
  
电话系统自动助理具有以下功能：
  
- 提供企业或信息性问候语。
    
- 提供自定义企业菜单。你可以自定义这些菜单以包含更多级别。
    
- 它提供了使人调用中的组织名称的目录中搜索的目录搜索。
    
- 它允许在调用到达或为您的组织中的用户留言的人。
    
## <a name="getting-started"></a>入门

要开始使用自动助理，记住以下几点至关重要：
  
- 企业 E3 以及**电话系统**许可证或企业 E5 许可证，您的组织必须有 （最低要求）。 可用于自动助理被分配影响的服务号，**电话系统**用户许可证数。 自动助理可以有数是取决于您的组织中分配的数字**电话系统**和**音频会议**许可证。 若要了解有关授权的详细信息，请转[Skype 为加载项业务和 Microsoft 小组授权](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。
    
    > [!TIP]
    > 要重定向调用的运算符或使用**电话系统**许可证在线用户的菜单选项，您需要允许它们企业语音或向它们分配调用计划。 请参阅[指派的 Skype 业务和 Microsoft 小组的许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。 你还可以使用 Windows PowerShell。 例如运行： `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- 要获取并用于自动助理的免费电话服务号码，您需要设置通信贷。 若要执行此操作，请参阅[通信片尾是什么？](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md)并[设置为您的组织的通信贷](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md)。
    
    > [!IMPORTANT]
    > [!重要信息] 不能将用户（订阅者）的电话号码分配给自动助理 - 只能使用收费或免费服务电话号码。 
  
## <a name="feature-overview"></a>功能概述

### <a name="dial-by-name"></a>按名字拨叫

按名字拨叫是自动助理的一项功能，称为目录搜索。 这样的人连接到您要使用语音 （语音识别） 或其电话键盘 (DTMF) 输入全名或部分名称，以公司的目录中搜索，请人，然后有对它们的调用转移的自动助理。 如果您有 Skype 的在线业务的用户，**它们不需要有一个电话号码或调用计划分配给它们，但是它们必须具有电话系统许可证**为他们当他们搜索使用按名称拨号时可到达。 按名称拨号甚至将能够找到并转移对 Skype 的在线业务承载在不同国家或地区的多国组织中的用户。
  
> [!CAUTION]
> 内部部署的 Lync Server 2010 用户将不会列在目录中，当有人搜索。 
  
### <a name="maximum-directory-size"></a>目录最大大小

使用电话键盘输入部分或完整的名称 （名字 + 姓氏和还姓氏 + 名字字段） 进行搜索时，按名称拨号支持其 Active Directory 大小没有限制。 但是，单个的自动助理可以支持使用语音使用名称识别的最大名称列表大小是 80000 用户。
  
||||
|:-----|:-----|:-----|
|**输入类型** <br/> |**搜索格式** <br/> |**组织中的最大用户数** <br/> |
|DTMF（键盘输入）  <br/> |部分  <br/> 名字 + 姓氏  <br/> 姓氏 + 名字  <br/> |没有硬性限制  <br/> |
|语音（语音识别）  <br/> |名字字段  <br/> 姓氏  <br/> 名字 + 姓氏  <br/> 姓氏 + 名字  <br/> |80000 用户  <br/> |
   
> [!NOTE]
> 如果您使用的按名称拨号使用语音识别，但您的组织的 Active Directory 大于 80000 用户并没有限制范围内使用拨号范围功能按名称拨号，按名称拨号仍适用于您调用方使用电话键盘和语音输入可用于所有其他方案。 你可以使用"拨号范围"功能，通过更改按名字拨叫的范围，减少可以呼叫的姓名，以找到特定自动助理。 
  
### <a name="dial-by-name---keypad-dtmf-entry"></a>按名字拨叫 - 键盘 (DTMF) 输入

调用程序中的用户可以使用按名称拨号到达用户通过指定或者他们试图达到的人的全名或部分名称。 好事是时输入的名称，可以使用的各种格式。
  
搜索组织目录时，用户可以使用"0"（零）键来表示名字与姓氏之间或姓氏与名字之间的空格。输入姓名时，会要求他们用 #（井号）键表示键盘输入结束。例如，"在你输入要联系的用户姓名后，请按 # 号"。如果找到多个姓名，会向呼叫者提供姓名列表，供其从中选择。
  
用户可以在电话键盘上使用以下搜索格式搜索组织中的姓名：
  
|||||
|:-----|:-----|:-----|:-----|
|**姓名格式** <br/> |**搜索类型** <br/> |**示例** <br/> |**搜索结果** <br/> |
|名字 + 姓氏  <br/> |完整  <br/> |Amos0Marble#  <br/> |Amos Marble  <br/> |
|姓氏 + 名字  <br/> |完整  <br/> |Marble0Amos#  <br/> |Amos Marble  <br/> |
|名字字段  <br/> |完整  <br/> |Amos#  <br/> |按 1 选择 Amos Marble  <br/> 按 2 选择 Amos Marcus  <br/> |
|姓氏  <br/> |完整  <br/> |Marble#  <br/> |按 1 选择 Amos Marble  <br/> 按 2 选择 Mary Marble  <br/> |
|名字或姓氏  <br/> |部分  <br/> |Mar#  <br/> |按 1 选择 Mary Marble  <br/> 按 2 选择 Mary Jones  <br/> 按 3 选择 Amos Marcus  <br/> |
|名字 + 姓氏  <br/> |部分  <br/> |Mar0Amos#  <br/> |按 1 选择 Amos Marble  <br/> 按 2 选择 Amos Marcus  <br/> |
|姓氏 + 名字  <br/> |部分  <br/> |Mar0Am#  <br/> |按 1 选择 Amos Marble  <br/> 按 2 选择 Amos Marcus  <br/> |
   
使用电话键盘搜索用户时可以使用多种特殊字符。 例如，此人将要求使用井号键 （#），而零 (0) 键用于名称之间的空格。 按星号键 (*) 将重复与该用户匹配的姓名列表。
  
|||
|:-----|:-----|
|**特殊电话键盘字符** <br/> |**含义** <br/> |
|#（井号键）  <br/> |输入姓名时的结束字符。  <br/> |
|0（零）  <br/> |姓名中间的空格。  <br/> |
|*（星号键）  <br/> |重复姓名匹配列表。  <br/> |
   
### <a name="dial-by-name---name-recognition-with-speech"></a>按名字拨叫 - 使用语音识别姓名

人们可以搜索其他用户在其组织中使用语音 （语音识别）。 他们可以说他们正在查找的人的名字来访问公司的 Active Directory 中的任何人。 使用语音输入可以识别各种格式，包括名字、 姓氏、 名字 + 姓氏或姓氏 + 名字字段的名称。
  
自动助理的启用语音识别时，将不会禁用电话键盘输入 (DTMF)，因此可以使用这两种类型的输入。 电话键盘输入不能禁用，并可在任何时间，即使自动助理支持语音识别。
  
使用电话键盘输入时，如果找到多个姓名，会向呼叫者提供姓名列表，供其从中选择。
  
呼叫者可以采用以下格式报出姓名：
  
|||||
|:-----|:-----|:-----|:-----|
|**使用语音** <br/> |**搜索类型** <br/> |**示例** <br/> |**搜索结果** <br/> |
|名字 + 姓氏  <br/> |完整  <br/> |Amos Marble  <br/> |Amos Marble  <br/> |
|姓氏 + 名字  <br/> |完整  <br/> |Marble Amos  <br/> |Amos Marble  <br/> |
|名字字段  <br/> |完整  <br/> |Amos  <br/> |按或报 1 选择 Amos Marble  <br/> 按或报 2 选择 Amos Jones  <br/> |
|姓氏  <br/> |完整  <br/> |Marble  <br/> |按或报 1 选择 Amos Marble  <br/> 按或报 2 选择 Ben Marble  <br/> |
   
> [!NOTE]
> 可能需要 36 小时的时间让他们的姓名列入目录拨号的名称通过使用语音识别的新用户。 
  
### <a name="language-support"></a>语言支持

文本到语音转换可以使用以下语言：
  
||||
|:-----|:-----|:-----|
|阿拉伯语 (EG)  <br/> |英语 (NZ)  <br/> |韩语 (KO)  <br/> |
|中文 (HK)  <br/> |英语 (UK)  <br/> |挪威语 (NO)  <br/> |
|中文 (TW)  <br/> |英语 (US)  <br/> |波兰语 (PL)  <br/> |
|中文 (ZH)  <br/> |芬兰语 (FI)  <br/> |葡萄牙语 (BR)  <br/> |
|丹麦语 (DA)  <br/> |法语 (CA)  <br/> |葡萄牙语 (PT)  <br/> |
|荷兰语 (NL)  <br/> |法语 (FR)  <br/> |俄语 (RU)  <br/> |
|英语 (AU)  <br/> |德语 (DE)  <br/> |西班牙语 (ES)  <br/> |
|英语 (CA)  <br/> |意大利语 (IT)  <br/> |西班牙语 (MX)  <br/> |
|英语 (IN)  <br/> |日语 (JP)  <br/> |瑞典语 (SV)  <br/> |
   
用于自动助理的语音识别可以使用以下语言：
  
|||
|:-----|:-----|
|中文 (ZH)  <br/> |法语 (FR)  <br/> |
|英语 (AU)  <br/> |德语 (DE)  <br/> |
|英语 (CA)  <br/> |意大利语 (IT)  <br/> |
|英语 (IN)  <br/> |日语 (JP)  <br/> |
|英语 (UK)  <br/> |葡萄牙语 (BR)  <br/> |
|英语 (US)  <br/> |西班牙语 (ES)  <br/> |
|法语 (CA)  <br/> |西班牙语 (MX)  <br/> |
   
以下语音命令可以使用十四 (14) 种支持语音识别的语言：
  
|||
|:-----|:-----|
|**语音命令** <br/> |**含义** <br/> |
|是  <br/> |是 - 对应于按 1 表示"是"。  <br/> |
|否  <br/> |否 - 对应于按 2 表示"否"。  <br/> |
|重复  <br/> |重复选项列表 - 对应于按 * 重复选项列表。  <br/> |
|接线员  <br/> |跳转到接线员 - 对应于按 0 转到"接线员"。  <br/> |
|主菜单  <br/> |为呼叫者返回到自动助理的主菜单。  <br/> |
|零  <br/> |对应于按 0（默认情况下，与"接线员"相同）。  <br/> |
|一  <br/> |对应于按 1。  <br/> |
|二  <br/> |对应于按 2。  <br/> |
|三  <br/> |对应于按 3。  <br/> |
|四  <br/> |对应于按 4。  <br/> |
|五  <br/> |对应于按 5。  <br/> |
|六  <br/> |对应于按 6。  <br/> |
|七  <br/> |对应于按 7。  <br/> |
|八  <br/> |对应于按 8。  <br/> |
|九  <br/> |对应于按 9。  <br/> |
   
### <a name="using-the-operator-option"></a>使用接线员选项

为自动助理使用接线员是一项可选设置，此设置向呼叫者提供与真人对话的选项。
  
默认情况下将键 0 和语音命令"接线员"（可使用支持语音识别的所有语言）分配给接线员。
  
> [!NOTE]
> 您可以设置推送为**操作员**到一个不同的密钥使用**菜单选项**的按钮。 
  
可以将以下人员设置为接线员：
  
- 具有许可证的**电话系统**业务联机用户 Skype 是企业语音启用或调用计划分配给他们。 你可以通过此设置将呼叫者直接转到语音邮件。 为此，请选择" **贵公司的人**"，此人会将其呼叫直接转到语音邮件。
    
    > [!NOTE]
    > 用户承载内部使用 Lync Server 2010 不能用作运算符。 
  
- 为组织设置的其他自动助理。
    
- 组织中建立的任何现有呼叫队列。 若要查看有关调用队列的详细信息，请参阅[创建电话系统调用队列](create-a-phone-system-call-queue.md)。
    
### <a name="business-hours-and-call-handling"></a>营业时间和呼叫处理

营业时间在每个自动助理上设置。 如果没有设置营业时间，所有日期以及每天的所有时间均视为营业时间，因为默认情况下设置为全天候时间表。 工作时间可以用来设置工间休息时间期间，一天，所有未设置为正常工作时间被认为是下班后的时间。 您可以设置不同的传入呼叫处理选项和不同的问候 （这是可选的），和两个可以设置的上班和下班后。
  
每个自动助理具有可以设置的呼叫处理选项：
  
- 可以在问候之后断开呼叫。
    
- 您也可以：
    
  - 重定向到具有企业语音支持的**电话系统**许可证业务联机用户 Skype 呼叫或调用计划分配给他们。 你可以通过此设置将呼叫者直接转到语音邮件。 为此，请选择" **贵公司的人**"，此人会将其呼叫直接转到语音邮件。
    
    > [!NOTE]
    > 用户承载内部使用 Lync Server 2010 中不受支持。 
  
  - 重定向调用队列调用。 若要查看有关调用队列的详细信息，请参阅[创建电话系统调用队列](create-a-phone-system-call-queue.md)。
    
  - 重定向调用另一个您已设置的自动助理。
    
- 创建菜单选项并为呼叫者播放菜单提示。例如："请按 1 选择销售，按 2 选择服务。如需联系接线员，请随时按 0。"
    
### <a name="menu-options"></a>菜单选项

电话系统自动助理，可以创建菜单提示 （"销售的按 1，为服务请按 2"） 并设置为路由呼叫基于用户的选择的菜单选项。 通过为自动助理设置菜单选项，组织能够提供交互式指导，帮助用户更快达到目的地，而无需依赖人工接线员来处理传入呼叫。 通过使用文本到语音 （系统生成提示） 或上载已录制的音频文件，可以创建菜单提示。 语音识别使用语音命令来实现无需用手操作的导航，但是呼叫者也可以使用电话键盘来导航菜单。
  
0-9 可以分配给**菜单选项**中，在使用 Skype 业务管理中心自动助理。 可以为营业时间和非营业时间创建不同的菜单选项集，并且可以在 **菜单选项**中启用或禁用按名字拨叫。 这些键可以映射为将呼叫转接至：
  
- 接线员，默认情况下映射到键 0。 但是，它可以被重新分配给其它键，或从菜单中删除。
    
- 呼叫队列。
    
- 另一种自动助理。 多级菜单可以设置在一个自动助理的**菜单选项**指向另一个与它自己的一套菜单选项，称为"嵌套"的自动助理的自动助理。
    
- 具有许可证的**电话系统**业务联机用户 Skype 是企业语音启用或调用计划分配给他们。 你可以通过此设置将呼叫者直接转到语音邮件。 为此，请选择" **贵公司的人**"，此人会将其呼叫直接转到语音邮件。
    
    > [!NOTE]
    > 用户承载内部使用 Lync Server 2010 不能用在**菜单选项**。 
  
每个菜单选项的名称将成为语音识别关键字，如果已启用语音识别。 例如，调用方可以说"One"，若要选择菜单选项映射到键 1，或者他们可以简单地说"销售额"以选择相同的菜单选项，名为"销售"。
  
若要设置自动助理和菜单选项，请[设置电话系统自动助理](set-up-a-phone-system-auto-attendant.md)。
  
### <a name="getting-service-numbers-for-an-auto-attendant"></a>获取自动助理的服务号

Before you can create and set up your auto attendants, you will need to get or transfer your existing toll or toll-free service numbers. 一旦您获得的收费或免费服务电话号码，他们就会显示在**业务管理中心的 Skype** > **语音** > **电话号码**和**数字类型**列出将列为**服务-免费**. 若要获得服务号码，看到[Skype 业务和 Microsoft 团队的前服务电话号码](getting-service-phone-numbers.md)，或者如果要传输和现有服务号码，请参阅[传输到 Office 365 的电话号码](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md)。
  
> [!NOTE]
> 如果您不在美国境内，不能使用业务管理中心为 Skype 来获得服务号码。 改为转[管理您的组织的电话号码](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)，以了解如何执行此操作。
  
## <a name="changing-the-users-caller-id-to-be-a-call-queues-phone-number"></a>更改用户的呼叫方 ID，才能调用队列的电话号码

您可以通过更改出站呼叫的呼叫队列及其呼叫方 ID 改为创建使用**New CallingLineIdentity** cmdlet 策略保护用户的标识。
  
若要执行此操作，请运行：
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

然后将策略应用到用户使用**授予 CallingLineIdentity** cmdlet。 若要执行此操作，请运行：
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

您可以如何对组织[如何呼叫方 ID 可在您的组织](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md)中的呼叫方 ID 设置进行更改的详细信息。
  
## <a name="related-topics"></a>相关主题
[下面是 Office 365 中的电话系统的功能](here-s-what-you-get-with-phone-system.md)

[获取 Skype for Business 和 Microsoft Teams 的服务电话号码](getting-service-phone-numbers.md)

[音频会议和通话套餐的国家/地区可用性](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

  
 