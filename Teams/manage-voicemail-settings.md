---
title: 管理云语音邮件设置
author: crowe
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
description: 管理用户的语音邮件设置。
ms.openlocfilehash: 7aa2fdf84f38cb9977b3a4156b28a96b98bbd9d7
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269597"
---
# <a name="manage-cloud-voicemail-settings-for-users"></a>为用户管理云语音邮件设置

语音邮件设置允许你为单个用户配置语音邮件设置。

在为用户配置语音邮件设置之前，应阅读[“设置云语音邮件](set-up-phone-system-voicemail.md)”。 有关为用户组设置策略的信息，请参阅 [“管理语音邮件策略](manage-voicemail-policies.md)”。

云语音邮件的默认设置为：

- 已启用语音邮件。
- 提示语言设置为用户的首选语言。
- 办公室外问候语已禁用。
- 在 Outlook 中设置自动答复时，禁用外出问候语。
- 当 Outlook 中的日历显示外出时，外出问候语会被禁用。
- 已禁用与服务共享语音邮件和听录数据以进行训练和提高准确性。
- 呼叫应答规则设置为“常规语音邮件”。
- 未设置默认问候语提示覆盖。
- 未设置默认的外出问候语提示覆盖。
- 未设置传输目标。


若要为用户管理云语音邮件功能，可以使用 Teams 管理中心或 PowerShell。 请注意，最终用户还可以通过转到 **“设置”->呼叫->配置语音邮件**，在 Teams 客户端中配置这些设置。

## <a name="use-teams-admin-center"></a>使用 Teams 管理中心

在 Teams 管理中心：

1.  在左侧导航栏中，转到 **“用户>管理用户** 并选择用户。

2.  在“用户详细信息”页上，转到 **“语音邮件”** 选项卡。

3.  更改设置。

4.  选择“**保存**”。


## <a name="use-powershell"></a>使用 PowerShell

还可以使用 PowerShell 管理语音邮件设置，如下所示：

- 若要管理单个用户的云语音邮件设置，请使用 [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings) cmdlet。 

- 若要查看设置，请使用 [Get-CsOnlineVoicemailUserSettings](/powershell/module/skype/get-csonlinevoicemailusersettings) cmdlet。

- 可以使用 [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings) cmdlet 并将 VoicemailEnabled 参数设置为$false，为用户禁用云语音邮件。 

## <a name="voicemail-settings"></a>语音邮件设置

- **已启用语音邮件** - 此设置控制是否为用户启用云语音邮件。 如果设置为 false，则云语音邮件服务将不适用于用户，也不会为用户录制语音邮件。

- **提示语言** - 此设置指定用于云语音邮件中的提示的语言。 有关详细信息 [，请参阅更改问候语和电子邮件的默认语言](change-the-default-language-for-greetings-and-emails.md)。

- **问候语设置** - 云语音邮件可以在用户在办公室和用户外出时播放特定问候语。 用户可以录制这两个问候语，也可以使用文本转语音问候语。

  - **默认问候语提示覆盖** - 指定在用户未录制问候语时将播放的文本转语音问候语。

  - **启用 Oof 问候** 语 - 指定是否在语音邮件存款方案中播放外出问候语，无论 Outlook 设置如何。

  - **启用 Oof 问候语后自动答复** - 指定当用户在 Outlook 中设置自动答复时，是否在语音邮件存款方案中播放外出问候语。

  - **启用 Oof 问候语后日历** - 指定当用户在日历中设置外出时，是否在语音邮件存款方案中播放外出问候语。

  - **默认的 Oof 问候提示覆盖** - 指定在用户外出且未录制外出问候时将播放的文本转语音问候语。

- **呼叫应答规则** - 此设置指定呼叫应答规则。 规则可以是：
  - 服务会拒绝没有消息的呼叫。
  - 只播放相关问候 (正常或外出) 。
  - 将播放相关问候 (正常或外出) ，并将呼叫者转移到指定的用户或电话号码。
  -  播放相关问候 (正常或外出) ，呼叫者可以留下语音邮件。
  - 播放相关问候 (正常或外出) ，呼叫者可以留下语音邮件，并允许按 0 转到指定的用户或电话号码。

- **共享服务改进的数据** - 指定是否与服务共享语音邮件和听录数据，以进行训练和提高准确性。 如果设置为 false，则无论用户选择如何，都不会共享语音邮件数据。

- **呼叫转移** - 指定调用方要传输到的用户或电话号码。


