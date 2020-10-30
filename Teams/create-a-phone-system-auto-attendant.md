---
title: 为 Microsoft 团队设置自动助理
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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 了解如何为 Microsoft 团队设置和测试自动助理。
ms.openlocfilehash: 513950c51035496ec1691fd9ac584467fe734827
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803800"
---
# <a name="set-up-an-auto-attendant"></a>设置自动助理

自动助理允许用户呼叫你的组织，并导航菜单系统以与右部门通话、呼叫队列、人员或操作员。 你可以通过 Microsoft 团队管理中心或通过 PowerShell 为你的组织创建自动助理。 

请确保你拥有 [团队自动助理和呼叫队列](plan-auto-attendant-call-queue.md) 的阅读计划，然后按照本文中的步骤操作，然后按照 [入门步骤](plan-auto-attendant-call-queue.md#getting-started) 操作。

自动助理可根据呼叫者的输入将呼叫定向到以下目的地之一： <a name="call-routing-options" ></a>

- **组织中的人员** -您的组织中能够接收语音呼叫的人员。 这可以是联机用户，也可以是使用 Skype for Business 服务器内部托管的用户。
- **语音应用** -另一个自动助理或呼叫队列。  (选择 "选择此目标时与自动助理或呼叫队列相关联的资源帐户"。 ) 
- **外部电话号码** -任何电话号码。  (参阅 [外部转接技术详细信息](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)) 。
- **语音邮件** -与你指定的 Microsoft 365 组相关联的语音邮箱。
- **Operator** -为自动助理定义的操作员。 定义运算符是可选的。 操作员可以定义为此列表中的任何其他目标。

设置自动助理时，系统会提示你在各个阶段选择其中一个选项。

若要设置自动助理，请在 "团队管理中心" 中，展开 " **语音** "，单击 " **自动助理** "，然后单击 " **添加** "。

## <a name="general-info"></a>常规信息

![](media/auto-attendant-general-info-page-new.png)

1. 在顶部的框中键入自动助理的名称。

2. 如果要指定一个运算符，请指定调用该操作员的目标。 这是可选的 (但建议) 。 你可以将 " **操作员** " 选项设置为允许呼叫者跳出菜单，并向指定的人讲话。

3. 指定此自动助理的时区。 如果您在 [下班后创建单独的通话流](#call-flow-for-after-hours)，则会使用时区计算营业时间。

4. 指定此自动助理的语言。 此语言将用于系统生成的语音提示。

5. 选择是否要启用语音输入。 启用后，每个菜单选项的名称将变为语音识别关键字。 例如，呼叫者可以说 "One" 以选择映射到键1的菜单选项，或者说 "销售额" 以选择名为 "Sales" 的菜单选项。

6. 单击" **下一步** "。

## <a name="call-flow"></a>通话流

![](media/auto-attendant-call-flow-greeting-message.png)

选择在自动助理接听呼叫时是否要播放问候语。

如果选择 " **播放音频文件** "，你可以使用 " **上传文件** " 按钮上载另存为音频的录制问候语消息。WAV，。MP3 或。WMA 格式。 录制内容不能大于 5 MB。

如果选择 " **键入问候语** "，系统将在自动助理接听呼叫时，读取您键入的文本 (最多为1000个字符的文本) 。

![](media/auto-attendant-call-flow-route-call-message.png)

选择您希望路由呼叫的方式。

如果您选择 " **断开连接** "，自动助理将挂起呼叫。

如果选择 " **重定向呼叫** "，则可以选择其中一个呼叫传送目的地。

如果选择 " **播放菜单" 选项** ，则可以选择 **播放音频文件** 或 **键入问候语** ，然后在菜单选项和目录搜索之间进行选择。

### <a name="menu-options"></a>菜单选项

![](media/auto-attendant-call-flow-menu-options-complete.png)

对于拨号选项，您可以将电话键盘上的0-9 键分配给其中一个呼叫传送目的地。  (键 \* (重复) ， \# (后) 由系统保留，并且不能重新分配。 ) 

键映射不必是连续的。 例如，可以创建一个映射到选项的键为0、1和3的菜单，而不使用2键。

如果已配置，我们建议将0键映射到操作员。 如果运算符未设置为任何键，则语音命令 "Operator" 也会被禁用。 

对于每个菜单选项，请指定以下内容：

- " **拨号键** "-电话键盘上的键以访问此选项。 如果语音输入可用，呼叫方还可以使用此号码访问该选项。

- **语音命令** -定义当语音输入已启用时，呼叫者可以提供的语音命令来访问此选项。 它可以包含多个词语，如 "客户服务" 或 "操作和用户"。 例如，呼叫者可以按2、说出 "二" 或说 "销售额" 以选择映射到2键的选项。 此文本还会由用于服务确认提示的文本（如 "将您的呼叫转移到销售人员"）呈现为语音。

- **重定向至** -呼叫路由目标，当呼叫方选择此选项时使用。 如果要重定向到自动助理或呼叫队列，请选择与其关联的资源帐户。

### <a name="directory-search"></a>目录搜索

如果为目的地分配了拨号键，我们建议您选择 " **无** " 进行 **目录搜索** 。 如果呼叫者尝试使用分配给特定目的地的密钥来拨打名称或分机，则它们可能会在完成输入名称或扩展名之前意外地路由到目标。 我们建议你为目录搜索创建单独的自动助理，并让你的主自动助理通过拨号键链接到它。

如果您没有分配拨号键，请选择 **目录搜索** 选项。

**按名称拨号** -如果启用此选项，呼叫者可以说出用户的姓名或在电话键盘上键入它。 任何带电话系统许可证的在线用户或使用 Skype for Business Server 本地托管的任何用户都是符合条件的用户，可通过 "按名称拨号" 找到。  (你可以设置 " [拨号作用域](#dial-scope) " 页面上的目录中和未包含的人员。 ) 

**按分机号码拨号** -如果启用此选项，则呼叫者可以通过拨打电话分机与您的组织中的用户联系。 任何具有电话系统许可证的在线用户或使用 Skype for Business Server 本地托管的任何用户都是符合条件的用户，并且可以 **通过 "通过分机拨入** " 找到。  (你可以设置 " [拨号作用域](#dial-scope) " 页面上的目录中和未包含的人员。 ) 

希望可供拨号使用的用户需要将扩展指定为在 Active Directory 或 Azure Active Directory 中定义的以下某个电话属性的一部分 (请参阅 [单独或批量添加用户](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) 以了解详细信息。 ) 

- OfficePhone
- HomePhone
- 手机/MobilePhone
- TelephoneNumber/电话号码
- OtherTelephone

在 "用户电话号码" 字段中输入扩展名所需的格式为 *+ <phone number> ext = <extension>* 或 *+ <phone number> x <extension>* 。

你可以在 [Microsoft 365 管理中心](https://admin.microsoft.com/) 或 [Azure Active Directory 管理中心](https://aad.portal.azure.com)中设置扩展。 在自动助理和呼叫队列中进行更改前，最多可能需要12小时。

> [!NOTE]
> 如果想要同时使用 " **按姓名** 拨号" 和 " **按分机号码拨号** " 功能，您可以在您的主自动助理上分配一个拨号键，以到达启用 " **按名称拨号** " 的自动助理。 在该自动助理中，你可以分配一个没有与之关联的字母 (的键) **通过分机** 自动助理到达拨号。

选择 **目录搜索** 选项后，单击 " **下一步** "。

## <a name="call-flow-for-after-hours"></a>下班后的通话流程

![](media/auto-attendant-business-hours.png)

可以为每个自动助理设置工作时间。 如果没有设置营业时间，所有日期以及每天的所有时间均视为营业时间，因为默认情况下设置为全天候时间表。 可以在一天内通过休息时间设置工作时间，并且未设置为工作时间的所有小时都将被认为是在小时后。 你可以设置不同的传入呼叫处理选项和问候语。

根据您配置的自动助理和呼叫队列的方式，您可能只需为带有直接电话号码的自动助理指定 "时间后的呼叫路由"。

如果需要在下班后呼叫者单独呼叫路由，请指定每天的工作时间。 单击 " **添加新时间** " 以指定给定日期的多个小时集，例如，指定午餐休息时间。

一旦您指定了您的工作时间，请选择下班后的呼叫路线选项。 相同的选项可用于您在上面指定的工作时间呼叫路由。

完成后，单击 " **下一步** "。

## <a name="call-flows-during-holidays"></a>假期期间的通话流

![](media/auto-attendant-holiday-greeting.png)

您的自动助理可以为 [您设置](set-up-holidays-in-teams.md)的每个假日提供一个呼叫流。 可以为每个自动助理添加最多 20 个计划假日。

1. 在 "假日呼叫设置" 页面上，单击 " **添加** "。

2. 键入此假日设置的名称。

3. 从 " **假日** " 下拉列表中，选择要使用的假日。

4. 选择要使用的问候语类型。

    ![](media/auto-attendant-holiday-actions.png)

5. 选择是否要 **断开连接** 或 **重定向** 呼叫。

6. 如果您选择重定向，请选择呼叫的呼叫传送目的地。

7. 单击“ **保存** ”。

![](media/auto-attendant-holiday-call-settings.png)

根据需要为每个额外的假日重复该过程。

添加完所有假日后，单击 " **下一步** "。

## <a name="dial-scope"></a>拨号作用域

![](media/auto-attendant-dial-scope.png)

当呼叫者使用按名称拨号或按扩展方式拨号时， *拨号作用域* 定义哪些用户在目录中可用。 **所有联机用户** 的默认值包括您的组织中的所有用户，这些用户是使用电话系统许可证的联机用户或使用 Skype For business 服务器内部托管的用户。

通过选择 " **包含** " 或 " **排除** " 下的 " **自定义用户组** "，然后选择一个或多个 Microsoft 365 组、通讯组列表或安全组，可以包含或排除特定用户。 例如，您可能希望从 "拨号目录" 中将组织中的主管排除在您的组织中。  (如果用户在两个列表中，则会将其从目录中排除。 ) 

> [!NOTE]
> 新用户可能需要长达36小时才能在目录中列出其名称。

设置完拨号作用域后，单击 " **下一步** "。

## <a name="resource-accounts"></a>资源帐户

所有自动助理都必须具有关联的资源帐户。  第一级自动助理至少需要一个具有关联服务号码的资源帐户。 如果需要，您可以将多个资源帐户分配给自动助理，每个帐户都有一个单独的服务编号。

![](media/auto-attendant-add-resource-account.png)

若要添加资源帐户，请单击 " **添加帐户** "，然后搜索要添加的帐户。 单击 " **添加** "，然后单击 " **添加** "。

![](media/auto-attendant-resource-account-assigned.png)

添加完服务帐户后，单击 " **提交** "。 这将完成自动助理配置。

## <a name="external-phone-number-transfers---technical-details"></a>外部电话号码传输-技术详细信息

将呼叫转移到外部电话号码时，与自动助理或呼叫队列关联的资源帐户必须具有电话号码和 Microsoft 365 Phone System-虚拟用户许可证。 进一步

- 对于带有呼叫计划编号的资源帐户，请分配 [呼叫计划](calling-plans-for-office-365.md) 许可证。
- 对于具有直接路由号码的资源帐户，请分配 [联机语音路由策略](manage-voice-routing-policies.md)。

显示的出站电话号码按如下方式确定：

  - 对于呼叫计划号码，将显示原始呼叫者的电话号码。
  - 对于直接路由号码，发送的号码基于 P 宣称的身份 (PAI 在 SBC 上) 设置，如下所示：
    - 如果设置为 "已禁用"，将显示原始呼叫者的电话号码。 这是默认和推荐的设置。
    - 如果设置为 "启用"，则显示资源帐户电话号码。

不支持在通话计划中继和直接路由中继之间转移。

在混合环境中，若要通过 Skype for Business PSTN 集成将自动助理呼叫转移到 PSTN，请使用设置为 PSTN 号码的呼叫转接来创建新的本地用户。 必须为用户启用企业语音并分配语音策略。 若要了解详细信息，请参阅 [自动助理呼叫转接到 PSTN](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn)。

### <a name="create-an-auto-attendant-with-powershell"></a>使用 PowerShell 创建自动助理

您也可以使用 PowerShell 创建和设置自动助理。 下面是管理自动助理所需的 cmdlet：

- [新-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)  
- [Set-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant?view=skype-ps)
- [CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/get-csautoattendant?view=skype-ps)
- [CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays?view=skype-ps)
- [Remove-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant?view=skype-ps)
- [新-CsAutoAttendantMenu](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu?view=skype-ps)
- [新-CsOnlineAudioFile](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile?view=skype-ps)
- [新-CsAutoAttendantCallFlow](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow?view=skype-ps)
- [Export-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps)
- [New-CsOnlineTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange?view=skype-ps)
- [New-CsOnlineDateTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps)
- [New-CsOnlineSchedule](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule?view=skype-ps)
- [CsAutoAttendantSupportedTimeZone](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone?view=skype-ps)
- [新-CsAutoAttendantCallHandlingAssociation](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation?view=skype-ps)
- [CsAutoAttendantSupportedLanguage](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage?view=skype-ps)
- [Import-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays?view=skype-ps)
- [新-CsAutoAttendantCallableEntity](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity?view=skype-ps)


## <a name="related-topics"></a>相关主题

[电话系统的功能](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[获取服务电话号码](/microsoftteams/getting-service-phone-numbers)

[音频会议和通话套餐的国家/地区可用性](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[小型企业版示例-设置自动助理](/microsoftteams/tutorial-org-aa) 

[Windows PowerShell 和 Skype for Business Online 简介](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
