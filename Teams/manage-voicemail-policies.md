---
title: 管理语音邮件策略
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
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
- Phone System
description: 管理用户的语音邮件策略。
ms.openlocfilehash: 02df2f235512ce0aca658031fae000edc99b5ea9
ms.sourcegitcommit: 18e66d54a9e349d4516253addc85cc12892c69a3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2022
ms.locfileid: "68851813"
---
# <a name="manage-cloud-voicemail-policies-for-your-users"></a>管理用户的云语音邮件策略

> [!WARNING]
> 对于Skype for Business客户，通过 Microsoft Teams 呼叫策略禁用语音邮件也可能禁用Skype for Business用户的语音邮件服务。

语音邮件策略允许配置现有或新的语音邮件策略并将其分配给用户组，以实现呼叫应答规则、语音邮件听录、听录猥亵内容掩码、听录翻译和系统提示语言等功能。

在指定策略之前，应阅读[设置云语音邮件](set-up-phone-system-voicemail.md)。 有关管理单个用户的设置的信息，请参阅[管理语音邮件设置。](manage-voicemail-settings.md)

若要管理语音邮件策略，可以使用 Teams 管理中心或 New-CsOnlineVoicemailPolicy PowerShell cmdlet。 

用户的默认策略是：

- 已启用语音邮件听录。
- 已启用语音邮件听录翻译。
- 已禁用语音邮件听录猥亵内容掩码。
- 最长录制持续时间设置为 5 分钟。
- 已启用编辑呼叫应答规则。
- 主要和辅助系统提示语言设置为 null，并使用用户的语音邮件语言设置。
- 未配置预配置或后配置。

可以使用自动创建的全局 (组织范围的默认) 策略，也可以创建和分配自定义策略。

> [!IMPORTANT]
> Microsoft 365 中的语音邮件服务会缓存语音邮件策略，并每 6 小时更新一次缓存。 因此，你所做的策略更改最多可能需要 6 小时才能应用。

## <a name="use-teams-admin-center"></a>使用 Teams 管理中心

### <a name="create-a-custom-voicemail-policy"></a>创建自定义语音邮件策略

按照以下步骤创建自定义语音邮件策略。

1. 在 Microsoft Teams 管理中心的左侧导航中，转到 **“语音** > **邮件策略**”。

2. 选择“**添加**”。

3. 打开或关闭要在语音邮件策略中使用的功能。

4. 选择“**保存**”。

### <a name="edit-a-voicemail-policy"></a>编辑语音邮件策略

按照以下步骤编辑现有语音邮件策略。

1. 在 Microsoft Teams 管理中心的左侧导航栏中，选择“ **语音** > **邮件策略**”。

2. 单击要修改的策略旁边的，然后选择 **“编辑**”。

3. 进行所需的更改，然后单击“ **保存**”。

> [!IMPORTANT]
> 无法编辑或删除名为 TranscriptionDisabled 和 TranscriptionProfanityMaskingEnabled 的预配置策略实例。


### <a name="assign-a-custom-voicemail-policy-to-users"></a>向用户分配自定义语音邮件策略

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="use-powershell"></a>使用 PowerShell

还可以使用 PowerShell 配置和分配现有或新的语音邮件策略。 若要使用 PowerShell 管理策略，请使用以下 cmdlet：

- [New-CsOnlineVoicemailPolicy](/powershell/module/skype/new-csonlinevoicemailpolicy)

- [Set-CsOnlineVoicemailPolicy](/powershell/module/skype/set-csonlinevoicemailpolicy)

- [Get-CsOnlineVoicemailPolicy](/powershell/module/skype/get-csonlinevoicemailpolicy)

- [Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/grant-csonlinevoicemailpolicy)

- [Remove-CsOnlineVoicemailPolicy](/powershell/module/skype/remove-csonlinevoicemailpolicy)

## <a name="voicemail-policy-settings"></a>语音邮件策略设置
  
- **启用听录** - 此设置控制云语音邮件服务是否将生成录制的语音邮件的文本转译并将其包含在语音邮件中。 听录将根据录制的语音邮件中检测到的语言进行。

- **听录翻译** - 此设置控制云语音邮件服务是否会翻译录制的语音邮件的听录内容。 将尝试将翻译为语音邮件接收方的首选语言。

- **听录不雅内容掩码** - 此设置控制云语音邮件服务是否会屏蔽语音邮件听录中发现的亵渎内容。

- **最大录制持续时间** - 最大录制长度控制可以录制语音邮件的最长时间。 默认值为 5 分钟。

- **呼叫应答规则** - 此设置控制是否允许用户在 Microsoft Teams 中配置语音邮件呼叫应答规则。

- **双重语言系统提示** - 默认情况下，语音邮件系统提示以用户在设置语音邮件时选择的语言向呼叫者显示。 如果业务要求以两种语言显示语音邮件系统提示，则可以设置主要语言和辅助语言，并且它们可能不同。

- **PreambleAudioFile** - 目前只能通过 PowerShell 使用。 在播放用户的语音邮件问候语之前，要向呼叫者播放的音频文件。

- **PostambleAudioFile** - 目前只能通过 PowerShell 使用。 在播放用户的语音邮件问候语之后和允许呼叫者留下语音邮件之前向呼叫方播放的音频文件。

- **PreamblePostambleMandatory** - 目前只能通过 PowerShell 使用。 在调用方可以留下消息之前，必须播放 Pre-or Postamble。

### <a name="share-data-for-service-improvements"></a>共享数据以改进服务

指定是否与服务共享语音邮件和听录数据，以便训练并提高准确性。 如果设置为 false，则无论用户选择如何，都不会共享语音邮件数据。


## <a name="related-articles"></a>相关文章


