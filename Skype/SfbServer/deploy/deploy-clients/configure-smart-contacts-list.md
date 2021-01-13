---
title: 在 Skype for Business 客户端中配置智能联系人列表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: 摘要：了解如何在 Skype for Business 客户端中启用智能联系人列表功能。
ms.openlocfilehash: d995d2addf8b774ebad9945b3f35f07ddb431855
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805772"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a>在 Skype for Business 客户端中配置智能联系人列表

**摘要：** 了解如何在 Skype for Business 客户端中启用智能联系人列表功能。

智能联系人列表功能允许自动填充最终用户的联系人列表。 首次使用 Skype for Business 时，你的用户将自动看到其经理和团队中的其他人。 默认情况下，为 Microsoft 365 和 Office 365 用户启用此功能，但您必须通过配置客户端策略设置为本地用户显式启用此功能。

配置此功能时，请牢记以下事项：

- 最多 13 个用户按以下顺序自动添加到智能联系人列表：

  1. Manager

  2. 按字母顺序指示

  3. 按字母顺序排序的对等方

- 用户首次登录时，将创建一个名为"我的组"的新组。 该组根据"经理"字段中填充的用户别名自动填充用户的 AD 组关系中的人。 请注意，对 AD 组成员身份的更改不会导致在最初填充"我的组"后进行更新。 如果用户删除联系人或组，则不重新创建联系人和组。 

- 如果启用自动标记，将为列表中的联系人标记状态更改。 默认情况下，自动标记已打开，但你可以选择将其关闭。 

- 将通知组内的所有新用户已添加到联系人列表。 用户可以手动将新成员添加到其"我的组"或他们选择的其他组。

- 此功能仅适用于首次登录的用户。 如果用户之前从任何设备（例如，任何移动设备或 Mac）登录，则不为该用户启用该功能。

## <a name="configure-smart-contacts-list"></a>配置智能联系人列表

若要为用户启用智能联系人列表功能，需要执行以下步骤： 

- 创建新的 CsClientPolicy 条目并将其添加到全局客户端策略。 

- 确保仅为 Web 搜索配置通讯簿搜索。

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a>创建策略条目以启用智能联系人列表

若要创建策略条目以启用智能联系人列表功能，请使用 [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) cmdlet 和 EnableClientAutoPopulateWithTeam 选项，如下所示：

```powershell
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

接下来，使用 [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet 将更改写入全局策略，如下所示：

```powershell
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

可以选择创建一个策略来关闭自动标记，如下所示：

```powershell
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

还必须将相应策略的 AddressBookAvailability 参数设置为 WebSearchOnly。 有关详细信息，请参阅 [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps)。 

### <a name="troubleshoot"></a>疑难解答

如果智能联系人列表未按照预期运行，请检查以下内容：

- 验证配置。 

- 确认已填充 AD 组织信息。

- 收集新用户的 Skype for Business 客户端日志，以进一步分析。

- 确认 Skype for Business 客户端 UI 未显示无法连接到通讯簿的消息。 若要确认通讯簿连接，请搜索 Skype for Business 客户端搜索栏中的用户。

- 当用户首次登录 Skype for Business 时，AD DS 复制问题可能会导致联系人无法解析。


