---
title: 为业务客户端中 Skype 配置智能联系人列表
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: 摘要： 了解如何启用业务客户端 Skype 中的智能联系人列表功能。
ms.openlocfilehash: 1aba122df313384fe1680296551ff7689b237d54
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374482"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a>为业务客户端中 Skype 配置智能联系人列表

**摘要：** 了解如何启用业务客户端 Skype 中的智能联系人列表功能。

智能联系人列表功能支持自动填充最终用户的联系人列表。 时第一个 for Business，用户将自动使用 Skype 经理和其他人在上看到他们的团队。 在为 Office 365 用户，默认情况下启用此功能，但您必须明确启用此功能为您的内部部署用户通过配置客户端策略设置。

配置此功能时，请记住以下几点：

- 用户，最多为 13、 自动添加到按以下顺序智能联系人列表中：

  1. 经理

  2. 按字母顺序显示下属

  3. 按字母顺序显示同事

- 当用户第一次登录时，系统将创建一个名为“我的组”的新组。 组会自动填入管理器字段中填充的用户别名基于用户的 AD 组关系中的人员。 请注意，在“我的组”最初填充之后，对 AD 组成员资格做任何更改都不会引起“我的组”发生更新。 如果用户删除某个联系人或组，则不会重新创建联系人或组。 

- 如果自动标记功能启用，将为列表中的联系人标记状态更改。 自动标记功能默认情况下启用，但是您可以选择将其禁用。 

- 组中的所有新用户都会收到通知，知晓他们已被添加到联系人列表。 用户可以手动选择将新成员添加到其“我的组”或其选择的其他组。

- 此功能仅适用于首次登录的用户。 如果用户以前曾从任何设备（例如，任何移动设备或 Mac）登录，则该用户无法使用该功能。

## <a name="configure-smart-contacts-list"></a>配置智能联系人列表

要为您的用户启用智能联系人列表功能，需要执行以下步骤： 

- 创建一个新的 CsClientPolicy 条目并将其添加到全局客户端策略。 

- 确保将通讯簿搜索设置为仅限 Web 搜索。

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a>创建策略条目以启用智能联系人列表

若要创建一个策略项，以便启用智能联系人列表功能，用于[New-csclientpolicyentry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) cmdlet EnableClientAutoPopulateWithTeam 选项，如下所示：

```
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

接下来，使用[Set-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet 更改写入到的全局策略，如下所示：

```
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

也可以选择创建策略来关闭自动标记功能，如下所示：

```
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

还必须将对应策略的 AddressBookAvailability 参数设置为 WebSearchOnly。 有关详细信息，请参阅[Set-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps)。 

### <a name="troubleshoot"></a>疑难解答

如果智能联系人列表未按预期工作，请检查以下各项：

- 验证配置。 

- 确认已填充 AD 组织信息。

- 为业务客户端日志收集 Skype，供进一步分析新用户。

- 确认 Business 客户端 UI Skype 不显示一条消息，无法连接到通讯簿。 若要确认通讯簿连接，请执行业务客户端搜索栏 Skype 中的用户搜索。

- AD DS 复制问题可能导致无法解析当用户第一次登录到 for Business 的 Skype 联系人。


