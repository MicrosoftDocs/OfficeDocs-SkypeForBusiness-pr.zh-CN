---
title: 在 Skype for Business 客户端中配置智能联系人列表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: 摘要：了解如何在 Skype for Business 客户端中打开智能联系人列表功能。
ms.openlocfilehash: d99008cde28b834f77a2935ffd7882162aa05e95
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776687"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a>在 Skype for Business 客户端中配置智能联系人列表

**摘要：** 了解如何在 Skype for Business 客户端中打开智能联系人列表功能。

智能联系人列表功能允许您的最终用户自动填充联系人列表。 在第一次使用 Skype for Business 时，您的用户将自动在其团队中查看其经理和其他人员。 默认情况下，对于 Microsoft 365 和 Office 365 用户，此功能处于启用状态，但您必须通过配置客户端策略设置为本地用户显式启用此功能。

配置此功能时，请记住以下几点：

- 用户（最长为13个）将按以下顺序自动添加到智能联系人列表中：

  1. Manager

  2. 按字母顺序定向

  3. 按字母顺序排列的对等

- 当用户第一次登录时，将创建一个名为 My Group 的新组。 根据在 "管理者" 字段中填写的用户别名，自动向用户的 AD 组关系中的人员填充该组。 请注意，AD 组成员身份的更改不会导致在最初填充时对我的组进行更新。 如果用户删除联系人或组，则不会重新创建该联系人和组。 

- 如果启用了自动标记，则列表中的联系人将标记为 "状态更改"。 自动标记默认情况下处于打开状态，但您可以选择将其关闭。 

- 组中的所有新用户都将收到通知，告知他们已被添加到联系人列表。 用户可以手动将新成员添加到其 "我的组" 或选择的其他组中。

- 此功能仅适用于首次登录的用户。 如果用户之前已从任何设备（例如，任何移动设备或 Mac）登录，则不会为该用户启用此功能。

## <a name="configure-smart-contacts-list"></a>配置智能联系人列表

若要为你的用户启用智能联系人列表功能，你将需要执行以下步骤： 

- 创建一个新的 Set-csclientpolicy 条目并将其添加到全局客户端策略。 

- 确保将通讯簿搜索配置为仅用于 Web 搜索。

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a>创建策略项以启用智能联系人列表

若要创建策略条目以启用智能联系人列表功能，请使用带 EnableClientAutoPopulateWithTeam 选项的[CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) cmdlet，如下所示：

```powershell
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

接下来，使用[set-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet 将更改写入到全局策略，如下所示：

```powershell
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

您可以根据需要创建策略来关闭自动标记，如下所示：

```powershell
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

您还必须将相应策略的 AddressBookAvailability 参数设置为 WebSearchOnly。 有关详细信息，请参阅[set-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps)。 

### <a name="troubleshoot"></a>疑难解答

如果 "智能联系人" 列表未按预期工作，请检查以下各项：

- 验证配置。 

- 确认已填充 AD 组织信息。

- 收集新用户的 Skype for Business 客户端日志，以供进一步分析。

- 确认 Skype for Business 客户端 UI 不显示无法连接到通讯簿的消息。 若要确认通讯簿连接，请在 Skype for Business 客户端搜索栏中执行用户搜索。

- 当用户首次登录 Skype for Business 时，AD DS 复制问题可能会导致联系人无法解析。


