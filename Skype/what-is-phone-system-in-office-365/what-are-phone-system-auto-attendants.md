---
title: "电话系统自动助理是什么？"
ms.author: tonysmit
author: tonysmit
ms.date: 11/17/2017
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: ab9f05a2-22cb-4692-a585-27f82d1b37c7
description: "Learn what Phone System (Cloud PBX) auto attendents are and how to use them. "
---

# 电话系统自动助理是什么？

> [!IMPORTANT]
> 本文是由机器翻译的，请参阅[免责声明]。
  
在 Office 365 自动助理可用于创建菜单系统为您允许内部和外部呼叫者的组织中的电话系统移动菜单系统以查找并放置或将呼叫转接到您的组织中的部门或公司的用户。
  
当呼叫的人员时，它们将显示一系列帮助他们打电话到用户或找到您的组织中的某人，然后将呼叫转接至该用户的语音提示。为自动助理是一系列语音提示或他们呼叫进入组织时，呼叫者听到，而不是人工接线员音频文件。为自动助理允许移动菜单系统、 呼叫，或使用电话键盘上 (DTMF) 查找用户或语音输入使用语音识别的呼叫者。
  
若要设置为自动助理在 Office 365 中的电话系统转[设置电话系统自动助理](set-up-a-phone-system-auto-attendant.md)。
  
电话系统自动助理具有以下功能：
  
- 提供企业或信息性问候语。
    
- 提供自定义企业菜单。你可以自定义这些菜单以包含更多级别。
    
- 它提供了使呼叫中名称的组织的目录中搜索的人员的目录搜索。
    
- 它使某人调用中到达或离开您的组织中人员的邮件。
    
## 入门

要开始使用自动助理，记住以下几点至关重要：
  
- 企业版 E3 与 **电话系统**的许可证或企业 E5 许可证，您的组织必须 （最低）。 分配了影响服务数的数字的 **电话系统**的用户许可证数是可用于自动助理。您可以自动助理号码是取决于您的组织中分配的数字 **电话系统**和 **音频会议**许可证。若要了解有关许可，转[Skype for Business 和 Microsoft 团队许可加载项](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。
    
    > [!TIP]
    > 要重定向呼叫转接到的运算符或联机用户与 **电话系统**许可证的菜单选项，您将需要启用企业语音或为其分配呼叫计划。请参阅[分配 Skype for Business 和 Microsoft 团队合作的用户许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。您还可以使用 Windows PowerShell。例如运行：  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- 若要获取和使用自动助理服务免费电话号码，您需要设置通信贷项。若要执行此操作，请参阅[什么是通信贷项？](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md)和[为您的组织设置通信贷项](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md)。
    
    > [!IMPORTANT]
    > 不能将用户（订阅者）的电话号码分配给自动助理 - 只能使用收费或免费服务电话号码。 
  
## 功能概述

### 按名字拨叫

按名称拨号是称为目录搜索为自动助理的一项功能。它使您自动助理以使用语音 （语音识别） 或 (DTMF) 其电话键盘输入完整或部分名称搜索公司目录、 中找到的人员，和然后已为其作为呼叫转接到呼叫中的人员。如果您有 Skype for Business Online 用户， **他们不需要有电话号码或呼叫计划分配给他们，但它们必须具有一个 **电话系统**许可证** 以便使用拨号按名称搜索时可访问。按名称拨号甚至无法查找并将呼叫转接到 Skype for Business Online 用户在不同国家或地区对于跨国组织中托管。
  
> [!CAUTION]
> 本地部署的 Lync Server 2010 用户不会列出在目录中，当有人搜索。 
  
### 目录最大大小

使用电话键盘输入部分或完整名称 （名字 + 姓氏和也姓氏 + 名字） 来搜索时为其支持拨按名称的 Active Directory 大小没有限制。但是，单个自动助理可以支持使用语音识别名称的最大名称列表大小是 80000 用户。
  
||||
|:-----|:-----|:-----|
|**输入类型** <br/> |**搜索格式** <br/> |**组织中的最大用户数** <br/> |
|DTMF（键盘输入）  <br/> |部分  <br/> 名字 + 姓氏  <br/> 姓氏 + 名字  <br/> |没有硬性限制  <br/> |
|语音（语音识别）  <br/> |名字  <br/> 姓氏  <br/> 名字 + 姓氏  <br/> 姓氏 + 名字  <br/> |80000 用户  <br/> |
   
> [!NOTE]
> 如果您使用的按名称拨号使用语音识别，但您所在组织的 Active Directory 大于 80000 用户和尚未有限拨通过使用拨号范围功能名称的范围，按名称拨号仍适合您的呼叫者使用电话键盘其他所有情况下将可语音输入。拨范围功能可用于缩小是到达通过更改拨按特定的自动助理的名称范围的名称。 
  
### 按名字拨叫 - 键盘 (DTMF) 输入

拨入的人员可以使用按名称拨号到达用户通过指定或者他们尝试联系的人员的完整或部分名称。好事是输入的名称时，可以使用的各种格式。
  
搜索组织目录时，用户可以使用"0"（零）键来表示名字与姓氏之间或姓氏与名字之间的空格。输入姓名时，会要求他们用 #（井号）键表示键盘输入结束。例如，"在你输入要联系的用户姓名后，请按 # 号"。如果找到多个姓名，会向呼叫者提供姓名列表，供其从中选择。
  
用户可以在电话键盘上使用以下搜索格式搜索组织中的姓名：
  
|||||
|:-----|:-----|:-----|:-----|
|**姓名格式** <br/> |**搜索类型** <br/> |**示例** <br/> |**搜索结果** <br/> |
|名字 + 姓氏  <br/> |完整  <br/> |Amos0Marble#  <br/> |Amos Marble  <br/> |
|姓氏 + 名字  <br/> |完整  <br/> |Marble0Amos#  <br/> |Amos Marble  <br/> |
|名字  <br/> |完整  <br/> |Amos#  <br/> |按 1 选择 Amos Marble  <br/> 按 2 选择 Amos Marcus  <br/> |
|姓氏  <br/> |完整  <br/> |Marble#  <br/> |按 1 选择 Amos Marble  <br/> 按 2 选择 Mary Marble  <br/> |
|名字或姓氏  <br/> |部分  <br/> |Mar#  <br/> |按 1 选择 Mary Marble  <br/> 按 2 选择 Mary Jones  <br/> 按 3 选择 Amos Marcus  <br/> |
|名字 + 姓氏  <br/> |部分  <br/> |Mar0Amos#  <br/> |按 1 选择 Amos Marble  <br/> 按 2 选择 Amos Marcus  <br/> |
|姓氏 + 名字  <br/> |部分  <br/> |Mar0Am#  <br/> |按 1 选择 Amos Marble  <br/> 按 2 选择 Amos Marcus  <br/> |
   
有几个搜索的人员使用电话键盘时所使用的特殊字符。例如，此人将要求使用井号键 （#），而零 (0) 键用于名称之间的间距。按键星号 （*） 将重复匹配的人员的名称的列表。
  
|||
|:-----|:-----|
|**特殊电话键盘字符** <br/> |**含义** <br/> |
|#（井号键）  <br/> |输入姓名时的结束字符。  <br/> |
|0（零）  <br/> |姓名中间的空格。  <br/> |
|*（星号键）  <br/> |重复姓名匹配列表。  <br/> |
   
### 按名字拨叫 - 使用语音识别姓名

用户可以使用其语音 （语音识别） 其组织中搜索的其他人。他们可以到达公司的 Active Directory 中的任何人通过说他们正在查找的人员的名称。使用语音输入可以识别各种格式，包括名字、 姓氏、 名字 + 姓氏或姓氏 + 名字中的名称。
  
为自动助理启用语音识别时，将不会禁用电话键盘条目 (DTMF)，以便可以使用两种类型的输入。电话键盘输入不能禁用，并可在任何时候，即使语音识别启用自动助理。
  
使用电话键盘输入时，如果找到多个姓名，会向呼叫者提供姓名列表，供其从中选择。
  
呼叫者可以采用以下格式报出姓名：
  
|||||
|:-----|:-----|:-----|:-----|
|**使用语音名称** <br/> |**搜索类型** <br/> |**示例** <br/> |**搜索结果** <br/> |
|名字 + 姓氏  <br/> |完整  <br/> |Amos Marble  <br/> |Amos Marble  <br/> |
|姓氏 + 名字  <br/> |完整  <br/> |Marble Amos  <br/> |Amos Marble  <br/> |
|名字  <br/> |完整  <br/> |Amos  <br/> |按或报 1 选择 Amos Marble  <br/> 按或报 2 选择 Amos Jones  <br/> |
|姓氏  <br/> |完整  <br/> |Marble  <br/> |按或报 1 选择 Amos Marble  <br/> 按或报 2 选择 Ben Marble  <br/> |
   
> [!NOTE]
> 可能需要多达 36 小时，为新用户具有其目录中列出的拨按名称语音识别的名称。 
  
### 语言支持

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
   
以下语音命令可以使用十四 (14﻿) 种支持语音识别的语言：
  
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
   
### 使用接线员选项

为自动助理使用接线员是一项可选设置，此设置向呼叫者提供与真人对话的选项。
  
默认情况下将键 0 和语音命令"接线员"（可使用支持语音识别的所有语言）分配给接线员。
  
> [!NOTE]
> 您可以设置的推送为 **运算符**到不同的密钥使用 **菜单选项**按钮。 
  
可以将以下人员设置为接线员：
  
- Skype for Business Online 用户具有许可证的 **电话系统**的人员已启用企业语音的或呼叫计划分配给他们。您可以设置它以便呼叫的人发送到语音邮件。若要执行此操作，选择 **您所在公司的人员**，并设置此人的呼叫，直接向语音邮件自动转发。
    
    > [!NOTE]
    > 用户托管本地使用 Lync Server 2010 不能用作运算符。 
  
- 为组织设置的其他自动助理。
    
- 设置您的组织中任何现有呼叫队列。若要查看有关呼叫队列的详细信息，请参阅[创建电话系统呼叫队列](create-a-phone-system-call-queue.md)。
    
### 营业时间和呼叫处理

每个自动助理上设置工作时间。如果未设置营业时间，所有的天数和一天的所有小时被视为营业时间因为默认情况下设置 24/7 计划。阶段日和所有未设置为营业时间被视为下班后的时间，可以使用分页符设置营业时间。您可以设置不同的传入呼叫处理选项和不同的问候语 （这是可选的），然后营业时间和下班后，可以设置两项。
  
每个自动助理具有呼叫处理选项，可以对其进行设置：
  
- 可以在问候之后断开呼叫。
    
- 您也可以：
    
  - 重定向到 Skype for Business Online 用户有 **电话系统**许可证支持企业语音的呼叫，或呼叫计划分配给他们。您可以设置它以便呼叫的人发送到语音邮件。若要执行此操作，选择 **您所在公司的人员**，并设置此人的呼叫，直接向语音邮件自动转发。
    
    > [!NOTE]
    > 用户托管本地使用 Lync Server 2010 不支持。 
  
  - 重定向到呼叫队列呼叫。若要查看有关呼叫队列的详细信息，请参阅[创建电话系统呼叫队列](create-a-phone-system-call-queue.md)。
    
  - 将呼叫重定向到你设置的其他自动助理。
    
- 创建菜单选项并为呼叫者播放菜单提示。例如："请按 1 选择销售，按 2 选择服务。如需联系接线员，请随时按 0。"
    
### 菜单选项

电话系统自动助理允许您创建菜单提示 （"按 1 的销售额，按 2 服务"） 和设置路由调用基于用户的选择菜单选项。设置为自动助理菜单选项使组织可以提供了有关人员访问其目标更快，而不依赖于人工接线员处理传入呼叫的交互式指南。通过使用文本到语音转换 （系统生成的提示） 或上载已录制的音频文件，则可以创建菜单提示。语音识别为免提导航中，使用语音命令，但拨入用户还可以使用电话键盘导航菜单。
  
使用 Business 管理中心对 Skype 为自动助理，键 0 到 9 可以分配给 **菜单选项**。有关营业时间和几小时后，可以创建组不同的菜单选项和您可以启用或禁用拨按 **菜单选项**中的名称。可以映射键以将呼叫转接到：
  
- 运算符，映射键 0 默认情况下。但是，但是可以重新分配给其他键，或从菜单中删除。
    
- 呼叫队列。
    
- 其他自动助理。通过在一个自动助理 **菜单选项**指向其他自动助理菜单选项，称为"嵌套"自动助理自己设置，可以设置多级菜单。
    
- Skype for Business Online 用户具有许可证的 **电话系统**的人员已启用企业语音的或呼叫计划分配给他们。您可以设置它以便呼叫的人发送到语音邮件。若要执行此操作，选择 **您所在公司的人员**，并设置此人的呼叫，直接向语音邮件自动转发。
    
    > [!NOTE]
    > 用户托管本地使用 Lync Server 2010 不能用于中 **菜单选项**。 
  
如果已启用语音识别，每个菜单选项的名称将成为语音识别关键字。例如，呼叫者可以说"一个"以选择菜单选项映射到键 1，或者他们可以只需说"销售额"，选择相同菜单选项名为"销售额"。
  
要设置自动助理和菜单选项，请访问[设置电话系统自动助理](set-up-a-phone-system-auto-attendant.md)。
  
### 获取自动助理的服务号

您可以创建和设置自动助理之前，您需要获取或将现有收费或免费服务传输数字。一旦收费或服务的免费电话号码，它们将显示在 **Skype for Business 管理中心**> **语音**> **电话号码**，并列出的 **数字类型**将被列为 **服务-免费电话**。要获取您的服务号码，请查看[获取 Skype for Business 服务电话号码](getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md)，或如果您希望的传输和现有服务号码，请参阅[将电话号码转移到 Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md)。
  
> [!NOTE]
> 如果您是在美国以外，您无法使用 Skype for Business 管理中心获取服务号码。转[管理您的组织的电话号码](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)相反，了解如何执行此操作。 
  
## 更改为呼叫队列的电话号码的用户的呼叫者 ID

您可以通过更改其到呼叫队列出站呼叫的呼叫者 ID 改为创建使用 **New-CallingLineIdentity** cmdlet 策略保护用户的身份。
  
若要执行此操作，运行：
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

然后将该策略应用于使用 **Grant-CallingLineIdentity** cmdlet 的用户。若要执行此操作，运行：
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

您可以获得有关如何更改您的组织中的呼叫者 ID 设置的详细信息[如何在你的组织中使用来电显示](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md)。
  
## 相关主题

[下面是可以在 Office 365 中的电话系统获得](here-s-what-you-get-with-phone-system-in-office-365.md)
  
[设置呼叫计划](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  

