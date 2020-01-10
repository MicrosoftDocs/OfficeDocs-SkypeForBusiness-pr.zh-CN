---
title: 在 Skype for Business 客户端中配置智能联系人列表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: 摘要：了解如何在 Skype for Business 客户端中打开 "智能联系人列表" 功能。
ms.openlocfilehash: 4c867232fd07131666033dc48ff9930dcdf6dccb
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002682"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a>在 Skype for Business 客户端中配置智能联系人列表

**摘要：** 了解如何打开 Skype for Business 客户端中的 "智能联系人列表" 功能。

智能联系人列表功能支持自动填充最终用户的联系人列表。 在第一次使用 Skype for Business 时，你的用户将自动查看其团队的经理和其他人。 默认情况下，Office 365 用户已启用此功能，但你必须通过配置客户端策略设置来为你的本地用户显式启用此功能。

配置此功能时，请记住以下几点：

- 用户（最多13个）将按以下顺序自动添加到智能联系人列表中：

  1. 经理

  2. 按字母顺序显示下属

  3. 按字母顺序显示同事

- 当用户第一次登录时，系统将创建一个名为“我的组”的新组。 组将根据 "经理" 字段中填写的用户别名自动填充到用户的 AD 组关系中的人员。 请注意，在“我的组”最初填充之后，对 AD 组成员资格做任何更改都不会引起“我的组”发生更新。 如果用户删除某个联系人或组，则不会重新创建联系人或组。 

- 如果自动标记功能启用，将为列表中的联系人标记状态更改。 自动标记功能默认情况下启用，但是您可以选择将其禁用。 

- 组中的所有新用户都会收到通知，知晓他们已被添加到联系人列表。 用户可以手动选择将新成员添加到其“我的组”或其选择的其他组。

- 此功能仅适用于首次登录的用户。 如果用户以前曾从任何设备（例如，任何移动设备或 Mac）登录，则该用户无法使用该功能。

## <a name="configure-smart-contacts-list"></a>配置智能联系人列表

要为您的用户启用智能联系人列表功能，需要执行以下步骤： 

- 创建一个新的 Set-csclientpolicy 条目，并将其添加到全局客户端策略。 

- 确保将通讯簿搜索设置为仅限 Web 搜索。

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a>创建策略条目以启用智能联系人列表

若要创建策略条目以启用智能联系人列表功能，请将[CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) Cmdlet 与 EnableClientAutoPopulateWithTeam 选项结合使用，如下所示：

```powershell
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

接下来，使用[set-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet 将更改写入全局策略，如下所示：

```powershell
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

也可以选择创建策略来关闭自动标记功能，如下所示：

```powershell
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

还必须将对应策略的 AddressBookAvailability 参数设置为 WebSearchOnly。 有关详细信息，请参阅[设置 set-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps)。 

### <a name="troubleshoot"></a>疑难解答

如果智能联系人列表未按预期工作，请检查以下各项：

- 验证配置。 

- 确认已填充 AD 组织信息。

- 在新用户处收集 Skype for Business 客户端日志以供进一步分析。

- 确认 Skype for Business 客户端 UI 不显示无法连接到通讯簿的消息。 若要确认通讯簿连接，请在 Skype for Business 客户端搜索栏中执行搜索用户。

- 当用户首次登录 Skype for Business 时，AD DS 复制问题可能会导致联系人无法解析。


