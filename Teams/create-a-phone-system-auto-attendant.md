---
title: 为 Microsoft Teams 设置自动助理
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 了解如何为 Microsoft Teams 设置和测试自动助理。
ms.openlocfilehash: 361122f4411f6aa3621d030a7a0569b438a86c27
ms.sourcegitcommit: 7c6a9e851d2fbf055d15e681e367d9dceee0b917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/04/2021
ms.locfileid: "49751786"
---
# <a name="set-up-an-auto-attendant"></a>设置自动助理

自动助理可让你的人呼叫你的组织并导航菜单系统以与正确的部门、呼叫队列、人员或接线员通话。 可以使用 Microsoft Teams 管理中心或 PowerShell 为组织创建自动助理。

在按照本文中的过程操作之前，请确保已阅读["Teams](plan-auto-attendant-call-queue.md)自动助理计划[](plan-auto-attendant-call-queue.md#getting-started)"和"呼叫队列"，并遵循了入门步骤。

自动助理可以基于呼叫者的输入将呼叫直接路由到以下目标之一： <a name="call-routing-options" ></a>

- **组织中的人** - 组织中能够接收语音呼叫的人。 这可以是联机用户，或者是使用 Skype for Business Server 在本地托管的用户。
- **语音应用** - 另一个自动助理或呼叫队列。  (选择此目标时与自动助理或呼叫队列关联的资源帐户。) 
- **外部电话号码** - 任何电话号码。  (外部[传输技术详细信息) 。](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)
- **语音邮件** - 与指定的 Microsoft 365 组关联的语音邮箱。
- **运算符** - 为自动助理定义的接线员。 定义运算符是可选的。 可以将运算符定义为此列表中的任何其他目标。

设置自动助理时，系统会提示你选择各个阶段中的其中一个选项。

若要设置自动助理，请在 Teams 管理中心展开 **"** 语音"，单击"自动助理"，然后单击"添加 **"。**

## <a name="general-info"></a>常规信息

![姓名、接线员、时区、语言和语音输入的自动助理设置的屏幕截图](media/auto-attendant-general-info-page-new.png)

1. 在顶部的框中键入自动助理的名称。

2. 如果要指定一个运算符，请指定调用该运算符的目标。 这是可选的 (，但建议) 。 你可以设置 **"接线** 员"选项，允许呼叫者离开菜单并联系指定的人员。

3. 指定此自动助理的时区。 如果为营业时间创建单独的呼叫流，则时区用于 [计算营业时间](#call-flow-for-after-hours)。

4. 为此自动助理指定语言。 此语言将用于系统生成的语音提示。

5. 选择是否要启用语音输入。 启用后，每个菜单选项的名称将成为语音识别关键字。 例如，呼叫者可以说"一"来选择映射到键 1 的菜单选项，也可以说"销售"以选择名为"销售"的菜单选项。

6. 单击" **下一步**"。

## <a name="call-flow"></a>呼叫流

![问候消息设置的屏幕截图](media/auto-attendant-call-flow-greeting-message.png)

选择当自动助理应答呼叫时是否要播放问候语。

如果选择"**播放音频文件"，** 可以使用"上传文件"按钮上传保存为音频的录制问候消息。WAV， .MP3 或 。WMA 格式。 录制内容不能大于 5 MB。

如果选择"键入问候语"消息，系统将在自动助理应答呼叫时朗读你键入 (最多 1000) 的文本。

![呼叫路由设置的屏幕截图](media/auto-attendant-call-flow-route-call-message.png)

选择要如何路由呼叫。

如果选择" **断开连接"，** 自动助理将挂断呼叫。

如果选择" **重定向呼叫"，** 可以选择其中一个呼叫路由目标。

如果选择"**播放"菜单选项**，可选择"播放音频文件"或"键入问候语"，然后在菜单选项和目录搜索之间选择。

### <a name="menu-options"></a>菜单选项

![拨号键选项的屏幕截图](media/auto-attendant-call-flow-menu-options-complete.png)

对于拨号选项，可以将电话键盘上的 0-9 键分配给呼叫路由目标之一。  (系统 (重复)  (后退) 键由系统保留，不能重新分配 \* \# 。) 

键映射不必是连续的。 例如，可以创建将键 0、1 和 3 映射到选项的菜单，而使用 2 键。

如果已配置 0 密钥，建议将 0 密钥映射到操作员。 如果接线员未设置为任何键，则语音命令"接线员"也将被禁用。

对于每个菜单选项，请指定以下内容：

- **拨号键** - 电话键盘上的按键，用于访问此选项。 如果语音输入可用，呼叫者也可以说出此号码来访问该选项。

- **语音** 命令 - 定义呼叫者可以授予用于访问此选项的语音命令（如果启用了语音输入）。 它可以包含多个单词，例如"客户服务"或"运营与企业"。 例如，调用方可以按 2，说"两"或说"销售"以选择映射到 2 键的选项。 此文本还通过文本转语音呈现，供服务确认提示使用，该提示可能类似"将呼叫转接到销售"。

- **重定向到** - 呼叫方选择此选项时使用的呼叫路由目标。 如果要重定向到自动助理或呼叫队列，请选择与其关联的资源帐户。

### <a name="directory-search"></a>目录搜索

如果将拨号键分配给目标，建议为"目录搜索"选择"**无"。** 如果呼叫者尝试使用分配给特定目的地的键拨打名称或分机号码，他们可能会意外地路由到目标，然后他们完成输入姓名或分机号码。 建议为目录搜索创建单独的自动助理，然后通过拨号键将主要自动助理链接至该助理。

如果未分配拨号键，请选择用于 **目录搜索的选项**。

**按名称拨** 叫 - 如果启用此选项，呼叫者可以说出用户的姓名或在电话键盘上键入它。 任何联机用户或任何使用 Skype for Business Server 在本地托管的用户都是符合条件的用户，可通过按名字拨叫找到。  (你可以设置"拨号范围"页上的目录中包括和不包括[哪些人) ](#dial-scope)

**按分机拨号** - 如果启用此选项，呼叫者可以通过拨打其电话分机来与贵组织的用户联系。 任何联机用户或任何使用 Skype for Business Server 在本地托管的用户都是符合条件的用户，可通过分机 **号拨叫找到**。  (你可以设置"拨号范围"页上的目录中包括和不包括[哪些人) ](#dial-scope)

要使其可用于"按分机拨号"的用户需要具有一个指定为 Active Directory 或 Azure Active Directory 中定义的以下电话属性之一的一部分的扩展 ([](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users)请参阅"单独或批量添加用户"了解详细信息。) 

- OfficePhone
- HomePhone
- Mobile/MobilePhone
- TelephoneNumber/PhoneNumber
- OtherTelephone

在"用户电话号码"字段中输入分机号码所需的格式为：

- *+\<phone number>;ext=\<extension>*
- *+\<phone number>x\<extension>*
- *x\<extension>*

- 示例 1：Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+1555555678;ext=5678"
- 示例 2：Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+1555555678x5678"
- 示例 3：Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"

可以在 [Microsoft 365](https://admin.microsoft.com/) 管理中心或 [Azure Active Directory](https://aad.portal.azure.com)管理中心设置扩展。 最多可能需要 12 小时，更改才可供自动助理和呼叫队列使用。

> [!NOTE]
> 如果要同时使用按名字拨叫和按分机拨叫功能，可以在主自动助理上分配拨号键，以联系为按名字拨叫启用的自动 **助理**。 在此自动助理中，你可以分配 1 个键 (没有与之关联的字母，) 通过分机自动助理联系拨号。 

选择目录 **搜索选项后**，单击"下一 **步"。**

## <a name="call-flow-for-after-hours"></a>营业时间的呼叫流

!["小时之后"的"天"和"时间"设置的屏幕截图](media/auto-attendant-business-hours.png)

可以针对每个自动助理设置营业时间。 如果没有设置营业时间，所有日期以及每天的所有时间均视为营业时间，因为默认情况下设置为全天候时间表。 可以设置营业时间，同时设置一天中的休息时间，所有未设置为营业时间的营业时间均视为非工作时间。 您可以为非营业时间设置不同的传入呼叫处理选项和问候语。

根据自动助理和呼叫队列的配置方式，可能只需为具有直接电话号码的自动助理指定非营业时间呼叫路由。

如果希望为非营业时间呼叫者单独路由呼叫，请指定每天的营业时间。 例如 **，单击"** 添加新时间"以指定给定天的多个小时数集，以指定午餐休息时间。

指定营业时间后，请选择数小时的呼叫路由选项。 提供的选项与上面指定的营业时间呼叫路由相同。

完成后 **单击** "下一步"。

## <a name="call-flows-during-holidays"></a>假日期间呼叫流

![节日和节日问候语设置的屏幕截图](media/auto-attendant-holiday-greeting.png)

自动助理可以针对你设置的每个假日 [设置呼叫流](set-up-holidays-in-teams.md)。 可以为每个自动助理添加最多 20 个计划假日。

1. 在"假日呼叫设置"页上，单击"添加 **"。**

2. 键入此假日设置的名称。

3. 从 **"假日** "下拉列表中，选择想要使用的假日。

4. 选择想要使用的问候语类型。

    ![节日呼叫操作设置的屏幕截图](media/auto-attendant-holiday-actions.png)

5. 选择是否要断开连接 **或****重定向** 呼叫。

6. 如果选择重定向，请选择呼叫的呼叫路由目标。

7. 单击“**保存**”。

![假日设置的屏幕截图，其中列出了假日](media/auto-attendant-holiday-call-settings.png)

根据需要对每个额外的假日重复该过程。

添加所有假日后，单击"下一 **步"。**

## <a name="dial-scope"></a>拨号范围

![拨号范围包括和排除选项的屏幕截图](media/auto-attendant-dial-scope.png)

拨号 *范围* 定义当呼叫者使用按名字拨叫或按分机拨叫时，哪些用户在目录中可用。 默认情况下 **，"所有联机用户** "包括组织中使用 Skype for Business Server 联机用户或本地托管的所有用户。

可以通过在"包括"或"排除"下选择"自定义用户组"并选择一个或多个 Microsoft 365 组、通讯组列表或安全组来包括或排除特定用户。  例如，你可能希望从拨号目录中排除贵组织的高层。  (如果用户同时在两个列表中，则他们将被排除在 directory.) 

> [!NOTE]
> 新用户可能需要最多 36 小时才能在目录中列出其名称。

设置完拨号范围后，单击"下一 **步"。**

## <a name="resource-accounts"></a>资源帐户

所有自动助理必须具有关联的资源帐户。  第一级自动助理至少需要一个具有关联服务编号的资源帐户。 如果需要，可以将多个资源帐户分配给自动助理，每个帐户都有单独的服务编号。

![资源帐户"添加帐户"面板的屏幕截图](media/auto-attendant-add-resource-account.png)

若要添加资源帐户，请单击 **"添加帐户** "并搜索要添加的帐户。 单击 **"添加**"，然后单击"**添加"。**

![显示具有已分配服务编号的资源帐户的资源帐户列表的屏幕截图](media/auto-attendant-resource-account-assigned.png)

添加完服务帐户后，单击"提交 **"。** 这会完成自动助理配置。

## <a name="external-phone-number-transfers---technical-details"></a>外部电话号码转移 - 技术详细信息

请参阅先决条件 [，](plan-auto-attendant-call-queue.md#prerequisites) 以便自动助理在外部转接呼叫。  另外：

- 对于具有呼叫计划号码的资源[](calling-plans-for-office-365.md)帐户，必须以 E.164 格式输入外部转移电话号码 (+[国家/地区代码][区号][电话号码]) 。

- 对于具有直接路由号码的资源帐户，外部传输电话号码格式依赖于会话边界控制器 ([SBC) ](direct-routing-connect-the-sbc.md) 设置。

显示的出站电话号码按如下所示确定：

  - 对于呼叫计划号码，将显示原始呼叫者的电话号码。
  - 对于直接路由号码，发送的数字基于 SBC 上的 P-Asserted-Identity (PAI) 设置，如下所示：
    - 如果设置为"禁用"，将显示原始呼叫者的电话号码。 这是默认的推荐设置。
    - 如果设置为"已启用"，将显示资源帐户电话号码。

在 Skype for Business 混合环境中，若要将自动助理呼叫转接到 PSTN，请创建呼叫转接设置为 PSTN 号码的新本地用户。 必须为用户启用语音企业语音并分配语音策略。 若要了解有关详细信息，请参阅"[自动助理呼叫转接到 PSTN"。](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn)

### <a name="create-an-auto-attendant-with-powershell"></a>使用 PowerShell 创建自动助理

也可使用 PowerShell 创建和设置自动助理。 下面是管理自动助理所需的 cmdlet：

- [New-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant)  
- [Set-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant)
- [Get-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/get-csautoattendant)
- [Get-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays)
- [Remove-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant)
- [New-CsAutoAttendantMenu](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu)
- [New-CsOnlineAudioFile](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile)
- [New-CsAutoAttendantCallFlow](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [Export-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays)
- [New-CsOnlineTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange)
- [New-CsOnlineDateTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange)
- [New-CsOnlineSchedule](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule)
- [Get-CsAutoAttendantSupportedTimeZone](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)
- [New-CsAutoAttendantCallHandlingAssociation](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [Get-CsAutoAttendantSupportedLanguage](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [Import-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays)
- [New-CsAutoAttendantCallableEntity](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity)

## <a name="related-topics"></a>相关主题

[电话系统的功能](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[获取服务电话号码](/microsoftteams/getting-service-phone-numbers)

[音频会议和通话套餐的国家/地区可用性](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[小型企业示例 - 设置自动助理](/microsoftteams/tutorial-org-aa)

[Windows PowerShell 和 Skype for Business Online 简介](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
