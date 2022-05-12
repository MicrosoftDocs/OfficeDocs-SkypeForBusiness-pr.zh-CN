---
title: 管理语音邮件策略
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 管理用户的语音邮件策略。
ms.openlocfilehash: 3f4c64194fc9e2b24c59dc7bc06ed972e801a6a8
ms.sourcegitcommit: cd9a1f7afaaf053741c81022e7052bf6f8008fcc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2022
ms.locfileid: "65370825"
---
# <a name="setting-voicemail-policies-in-your-organization"></a>设置组织的语音邮件策略

> [!WARNING]
> 对于Skype for Business客户，通过Microsoft Teams呼叫策略禁用语音邮件也可能禁用Skype for Business用户的语音邮件服务。

可以使用语音邮件策略来控制与云语音邮件相关的不同功能。

## <a name="voicemail-organization-defaults-for-all-users"></a>语音邮件组织默认为所有用户
- 已启用语音邮件听录。
- 已启用语音邮件听录翻译。
- 语音邮件听录猥亵屏蔽被禁用。
- 最大录制持续时间设置为五分钟。
- 已启用编辑呼叫应答规则。
- 主要和辅助系统提示语言设置为 null，并使用用户的语音邮件语言设置。

可以使用自动创建或创建和分配自定义策略的全局 (组织范围的默认) 策略。

## <a name="create-a-custom-voicemail-policy"></a>创建自定义语音邮件策略

按照以下步骤创建自定义语音邮件策略。

1. 在Microsoft Teams管理中心的左侧导航中，转到 **VoiceVoicemail** >  策略。
2. 选择“**添加**”。
3. 打开或关闭要在语音邮件策略中使用的功能。
4. 选择“**保存**”。

## <a name="edit-a-voicemail-policy"></a>编辑语音邮件策略

按照以下步骤编辑现有语音邮件策略。

1. 在Microsoft Teams管理中心的左侧导航中，选择 **VoiceVoicemail** >  策略。
2. 单击要修改的策略旁边，然后选择 **“编辑**”。
3. 进行所需的更改，然后单击 **“保存**”。

> [!IMPORTANT]
> 无法编辑或删除名为 TranscriptionDisabled 和 TranscriptionProfanityMaskingEnabled 的预配置策略实例。


## <a name="assign-a-custom-voicemail-policy-to-users"></a>向用户分配自定义语音邮件策略

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="voicemail-policy-settings"></a>语音邮件策略设置
  
### <a name="enable-transcription"></a>启用听录

此设置控制云语音邮件服务是否会生成录制的语音邮件的文本转录，并将其包含在语音邮件中。 听录将基于记录的语音邮件中检测到的语言进行。

### <a name="transcription-translation"></a>听录翻译

此设置控制云语音邮件服务是否会翻译录制的语音邮件的听录。 将尝试翻译为语音邮件接收器的首选语言。

### <a name="transcription-profanity-masking"></a>听录亵渎屏蔽

此设置控制云语音邮件服务是否会掩盖在语音邮件听录中发现的亵渎行为。

### <a name="maximum-recording-duration"></a>最大录制持续时间

最大录制长度控制可以录制语音邮件的最大时间。 默认值为 5 分钟。

### <a name="call-answering-rules"></a>呼叫应答规则

此设置控制是否允许用户在Microsoft Teams中配置语音邮件呼叫应答规则。

### <a name="dual-language-system-prompts"></a>双语言系统提示

默认情况下，语音邮件系统提示将以用户在设置语音邮件时选择的语言呈现给呼叫者。 如果业务要求以两种语言显示语音信箱系统提示，则可以设置主要语言和辅助语言，并且它们可能不一样。

### <a name="share-data-for-service-improvements"></a>共享用于服务改进的数据

指定是否与服务共享语音邮件和听录数据以进行训练和提高准确性。 如果设置为 false，则无论用户选择如何，都不会共享语音邮件数据。


> [!IMPORTANT]
> Microsoft 365和Office 365中的语音邮件服务会缓存语音邮件策略，并每 6 小时更新一次缓存。 因此，你所做的策略更改最多可能需要 6 小时才能应用。

## <a name="related-articles"></a>相关文章

[New-CsOnlineVoicemailPolicy](/powershell/module/skype/new-csonlinevoicemailpolicy)

[Set-CsOnlineVoicemailPolicy](/powershell/module/skype/set-csonlinevoicemailpolicy)

[Get-CsOnlineVoicemailPolicy](/powershell/module/skype/get-csonlinevoicemailpolicy)

[Grant-CsOnlineVoicemailPolicy](/powershell/module/skype/grant-csonlinevoicemailpolicy)

[Remove-CsOnlineVoicemailPolicy](/powershell/module/skype/remove-csonlinevoicemailpolicy)
