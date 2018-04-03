---
title: What are Phone System auto attendants?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.date: 01/22/2018
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
description: 'Learn what Phone System (Cloud PBX) auto attendants are and how to use them. '
ms.openlocfilehash: a1253419bdd321efd99a4ea375655d52f154b6ab
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2018
---
# <a name="what-are-phone-system-auto-attendants"></a>What are Phone System auto attendants?

Phone System in Office 365 auto attendants can be used to create a menu system for your organization that lets external and internal callers move through a menu system to locate and place or transfer calls to company users or departments in your organization.
  
当有人呼叫时，他们会收到一系列语音提示，这些提示可帮助他们呼叫用户或者在组织中找到用户并随后呼叫该用户。 An auto attendant is a series of voice prompts or an audio file that callers hear instead of a human operator when they call in to an organization. 自动助理使呼叫者能够移动浏览菜单系统，进行呼叫，或者使用电话键盘 (DTMF) 或采用语音识别功能的语音输入找到用户。 
  
To set up an auto attendant for the Phone System in Office 365, go [Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md).
  
A Phone System auto attendant has the following features:
  
- 提供企业或信息性问候语。
    
- 提供自定义企业菜单。你可以自定义这些菜单以包含更多级别。
    
- It provides directory search that enables people who call in to search the organization's directory for a name.
    
- It enables someone who calls in to reach or leave a message for a person in your organization.
    
## <a name="getting-started"></a>入门

要开始使用自动助理，记住以下几点至关重要：
  
- Your organization must have (at a minimum) an Enterprise E3 plus **Phone System** license or an Enterprise E5 license. The number of **Phone System** user licenses that are assigned impacts the number of service numbers that are available to be used for auto attendants. The number of auto attendants you can have is dependent on the number **Phone System** and **Audio Conferencing** licenses that are assigned in your organization. To learn more about licensing, go [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!TIP]
    > To redirect calls to an operator or a menu option that is an Online user with a **Phone System** license, you will need to enable them for Enterprise Voice or assign Calling Plans to them. See[Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). 你还可以使用 Windows PowerShell。 例如运行： `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- To get and use toll-free service numbers for your auto attendants, you need to set up Communications Credits. To do this, see [What are Communications Credits?](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md) and [Set up Communications Credits for your organization](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md).
    
    > [!IMPORTANT]
    > [!重要信息] 不能将用户（订阅者）的电话号码分配给自动助理 - 只能使用收费或免费服务电话号码。 
  
## <a name="feature-overview"></a>功能概述

### <a name="dial-by-name"></a>按名字拨叫

按名字拨叫是自动助理的一项功能，称为目录搜索。 It enables the people who call in to your auto attendant to use voice (speech recognition) or their phone keypad (DTMF) to enter a full or partial name to search company's directory, locate the person, and then have the call transferred to them. If you have Skype for Business Online users, **they aren't required to have a phone number or have Calling Plans assigned to them, but they must have a Phone System license** for them to be reachable when they search using Dial by Name. Dial by Name will even be able to find and transfer calls to Skype for Business Online users who are hosted in different countries or regions for multi-national organizations.
  
> [!CAUTION]
> On-premises deployments of Lync Server 2010 users won't be listed in the directory when someone searches for them. 
  
### <a name="maximum-directory-size"></a>目录最大大小

There is no limit on the Active Directory size for which Dial by Name is supported when using the phone keypad to search for entering partial or full names (FirstName + LastName, and also LastName + FirstName). However, the maximum name list size that a single auto attendant can support using name recognition with speech is 80,000 users.
  
||||
|:-----|:-----|:-----|
|**输入类型** <br/> |**搜索格式** <br/> |**组织中的最大用户数** <br/> |
|DTMF（键盘输入）  <br/> |部分  <br/> 名字 + 姓氏  <br/> 姓氏 + 名字  <br/> |没有硬性限制  <br/> |
|语音（语音识别）  <br/> |FirstName  <br/> LastName  <br/> 名字 + 姓氏  <br/> 姓氏 + 名字  <br/> |80,000 users  <br/> |
   
> [!NOTE]
> If you are using Dial by Name with speech recognition, but your organization's Active Directory is bigger than 80,000 users and you haven't limited the scope of Dial by Name using Dial Scope feature, Dial by Name will still work for your callers using a phone keypad, and voice inputs will be available for all other scenarios. 你可以使用"拨号范围"功能，通过更改按名字拨叫的范围，减少可以呼叫的姓名，以找到特定自动助理。 
  
### <a name="dial-by-name---keypad-dtmf-entry"></a>按名字拨叫 - 键盘 (DTMF) 输入

People calling in can use Dial by Name to reach users by specifying either the full or partial name of the person they are trying to reach. The good thing is that there are various formats that can be used when the name is entered.
  
搜索组织目录时，用户可以使用"0"（零）键来表示名字与姓氏之间或姓氏与名字之间的空格。输入姓名时，会要求他们用 #（井号）键表示键盘输入结束。例如，"在你输入要联系的用户姓名后，请按 # 号"。如果找到多个姓名，会向呼叫者提供姓名列表，供其从中选择。
  
用户可以在电话键盘上使用以下搜索格式搜索组织中的姓名：
  
|||||
|:-----|:-----|:-----|:-----|
|**姓名格式** <br/> |**搜索类型** <br/> |**示例** <br/> |**搜索结果** <br/> |
|名字 + 姓氏  <br/> |完整  <br/> |Amos0Marble#  <br/> |Amos Marble  <br/> |
|姓氏 + 名字  <br/> |完整  <br/> |Marble0Amos#  <br/> |Amos Marble  <br/> |
|FirstName  <br/> |完整  <br/> |Amos#  <br/> |按 1 选择 Amos Marble  <br/> 按 2 选择 Amos Marcus  <br/> |
|LastName  <br/> |完整  <br/> |Marble#  <br/> |按 1 选择 Amos Marble  <br/> 按 2 选择 Mary Marble  <br/> |
|名字或姓氏  <br/> |部分  <br/> |Mar#  <br/> |按 1 选择 Mary Marble  <br/> 按 2 选择 Mary Jones  <br/> 按 3 选择 Amos Marcus  <br/> |
|名字 + 姓氏  <br/> |部分  <br/> |Mar0Amos#  <br/> |按 1 选择 Amos Marble  <br/> 按 2 选择 Amos Marcus  <br/> |
|姓氏 + 名字  <br/> |部分  <br/> |Mar0Am#  <br/> |按 1 选择 Amos Marble  <br/> 按 2 选择 Amos Marcus  <br/> |
   
使用电话键盘搜索用户时可以使用多种特殊字符。 For example, the person will be asked to use the pound key (#), while the zero (0) key is used for a space between names. 按星号键 (*) 将重复与该用户匹配的姓名列表。
  
|||
|:-----|:-----|
|**特殊电话键盘字符** <br/> |**含义** <br/> |
|#（井号键）  <br/> |输入姓名时的结束字符。  <br/> |
|0（零）  <br/> |姓名中间的空格。  <br/> |
|*（星号键）  <br/> |重复姓名匹配列表。  <br/> |
   
### <a name="dial-by-name---name-recognition-with-speech"></a>按名字拨叫 - 使用语音识别姓名

People can search for others in their organization using their voice (speech recognition). They can also reach anyone in the company's Active Directory by saying the name of the person they are trying to locate. Using voice inputs can recognize names in various formats, including FirstName, LastName, FirstName + LastName, or LastName + FirstName.
  
When you enable speech recognition for an auto attendant, phone keypad entry (DTMF) won't be disabled, so both types of input can be used. Phone keypad entry can't be disabled and can be used at any time, even if speech recognition is enabled on the auto attendant.
  
使用电话键盘输入时，如果找到多个姓名，会向呼叫者提供姓名列表，供其从中选择。
  
呼叫者可以采用以下格式报出姓名：
  
|||||
|:-----|:-----|:-----|:-----|
|**Name with speech** <br/> |**搜索类型** <br/> |**示例** <br/> |**搜索结果** <br/> |
|名字 + 姓氏  <br/> |完整  <br/> |Amos Marble  <br/> |Amos Marble  <br/> |
|姓氏 + 名字  <br/> |完整  <br/> |Marble Amos  <br/> |Amos Marble  <br/> |
|FirstName  <br/> |完整  <br/> |Amos  <br/> |按或报 1 选择 Amos Marble  <br/> 按或报 2 选择 Amos Jones  <br/> |
|LastName  <br/> |完整  <br/> |Marble  <br/> |按或报 1 选择 Amos Marble  <br/> 按或报 2 选择 Ben Marble  <br/> |
   
> [!NOTE]
> It might take up to 36 hours for a new user to have their name listed in the directory for Dial by Name with speech recognition. 
  
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
> You can set the button that is pushed for the **Operator** to a different key by using **Menu Options**. 
  
可以将以下人员设置为接线员：
  
- A Skype for Business Online user who has a **Phone System** license that is Enterprise Voice-enabled or has Calling Plans assigned to them. 你可以通过此设置将呼叫者直接转到语音邮件。 为此，请选择" **贵公司的人**"，此人会将其呼叫直接转到语音邮件。
    
    > [!NOTE]
    > Users hosted on-premises using Lync Server 2010 can't be used as an Operator. 
  
- 为组织设置的其他自动助理。
    
- 组织中建立的任何现有呼叫队列。 To see more about call queues, see [Create a Phone System call queue](create-a-phone-system-call-queue.md).
    
### <a name="business-hours-and-call-handling"></a>营业时间和呼叫处理

营业时间在每个自动助理上设置。 如果没有设置营业时间，所有日期以及每天的所有时间均视为营业时间，因为默认情况下设置为全天候时间表。 Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours. You can set different incoming call-handling options and different greetings (which are optional), and Both can be set for business hours and after-hours.
  
Each auto attendant has call-handling options that can be set:
  
- 可以在问候之后断开呼叫。
    
- 您也可以：
    
  - Redirect the call to a Skype for Business Online user who has a **Phone System** license that is Enterprise Voice-enabled or has Calling Plans assigned to them. 你可以通过此设置将呼叫者直接转到语音邮件。 为此，请选择" **贵公司的人**"，此人会将其呼叫直接转到语音邮件。
    
    > [!NOTE]
    > 用户承载内部使用 Lync Server 2010 中不受支持。 
  
  - 重定向调用队列调用。 To see more about call queues, see [Create a Phone System call queue](create-a-phone-system-call-queue.md).
    
  - Redirect the call to another auto attendant that you have set up.
    
- 创建菜单选项并为呼叫者播放菜单提示。例如："请按 1 选择销售，按 2 选择服务。如需联系接线员，请随时按 0。"
    
### <a name="menu-options"></a>菜单选项

Phone System auto attendants allow you to create menu prompts ("Press 1 for Sales, Press 2 for Services") and set up menu options to route calls based on what the user selects. 通过为自动助理设置菜单选项，组织能够提供交互式指导，帮助用户更快达到目的地，而无需依赖人工接线员来处理传入呼叫。 Menu prompts can be created by using text-to-speech (system-generated prompts) or by uploading an audio file that has been recorded. 语音识别使用语音命令来实现无需用手操作的导航，但是呼叫者也可以使用电话键盘来导航菜单。
  
Keys 0 through 9 can be assigned to **Menu Options** in an auto attendant using the Skype for Business admin center. 可以为营业时间和非营业时间创建不同的菜单选项集，并且可以在 **菜单选项**中启用或禁用按名字拨叫。 这些键可以映射为将呼叫转接至：
  
- 接线员，默认情况下映射到键 0。 However, it can be re-assigned to any other key, or removed from the menu.
    
- A call queue.
    
- 另一种自动助理。 Multi-level menus can be set up by pointing a **Menu Option** in one auto attendant to another auto attendant with its own set of Menu Options, which is called a "nested" auto attendant.
    
- A Skype for Business Online user who has a **Phone System** license that is Enterprise Voice-enabled or has Calling Plans assigned to them. 你可以通过此设置将呼叫者直接转到语音邮件。 为此，请选择" **贵公司的人**"，此人会将其呼叫直接转到语音邮件。
    
    > [!NOTE]
    > Users hosted on-premises using Lync Server 2010 can't be used in **Menu Options**. 
  
每个菜单选项的名称将成为语音识别关键字，如果已启用语音识别。 例如，调用方可以说"One"，若要选择菜单选项映射到键 1，或者他们可以简单地说"销售额"以选择相同的菜单选项，名为"销售"。
  
若要设置自动助理和菜单选项，请[设置电话系统自动助理](set-up-a-phone-system-auto-attendant.md)。
  
### <a name="getting-service-numbers-for-an-auto-attendant"></a>获取自动助理的服务号

Before you can create and set up your auto attendants, you will need to get or transfer your existing toll or toll-free service numbers. Once you get the toll or toll-free service phone numbers, they will show up in the **Skype for Business admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md) or, if you want to transfer and existing service number, see [Transfer phone numbers to Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> If you are outside the United States, you can't use the Skype for Business admin center to get service numbers. Go [Manage phone numbers for your organization](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it.
  
## <a name="changing-the-users-caller-id-to-be-a-call-queues-phone-number"></a>Changing the user's Caller ID to be a call queue's phone number

You can protect a user's identity by changing their caller ID for the outbound calls to a call queue instead by creating a policy using the **New-CallingLineIdentity** cmdlet.
  
To do this, run:
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet. To do this, run:
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

You can get more information on how to make changes to caller ID settings in your organization [How can caller ID be used in your organization](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md).
  
## <a name="related-topics"></a>相关主题
[下面是 Office 365 中的电话系统的功能](here-s-what-you-get-with-phone-system.md)

[获取 Skype for Business 和 Microsoft Teams 的服务电话号码](getting-service-phone-numbers.md)

[音频会议和通话套餐的国家/地区可用性](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

  
 