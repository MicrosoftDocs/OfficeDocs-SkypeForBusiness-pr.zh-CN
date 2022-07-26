---
title: 电话号码和许可更改
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: conceptual
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
ms.custom: ''
description: 了解许可更改如何影响电话号码管理。
ms.openlocfilehash: 58821f950baf68474a637a8d76acaab9a088f31e
ms.sourcegitcommit: f5d784df59a8010b390691bbb20c4ea66c46280b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/26/2022
ms.locfileid: "67005456"
---
# <a name="how-licensing-affects-phone-number-management"></a>许可如何影响电话号码管理

如何删除和分配用户许可证可能会影响用户在 Microsoft Teams 中拨打和接收公共交换电话网络 (PSTN) 呼叫的能力。 本文介绍如何管理许可更改，以确保用户发出和接收 PSTN 呼叫的能力不受影响。

有关管理电话号码的一般信息，请参阅 [管理组织的电话号码](manage-phone-numbers-landing-page.md)。 有关 Teams 加载项许可的一般信息，请参阅 [Microsoft Teams 加载项许可证](/teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。



## <a name="remove-a-license"></a>删除许可证

如果你有一个用户分配了电话号码，并且删除了一个或多个先决条件许可证，则删除许可证也会从用户中取消分配电话号码。 如果没有分配的电话号码，用户在 Microsoft Teams 中拨打和接收 PSTN 呼叫的能力会受到影响。

根据用户的 [PSTN 连接选项](pstn-connectivity.md)，删除许可证会对电话参数产生以下影响：

- **从具有通话套餐电话号码的用户中删除 Microsoft 365 呼叫计划许可证** 将：
  - 将 OnPremLineUri 中的任何值复制到 LineUri
  - 将 EnterpriseVoiceEnabled 设置为 False
  - 在电话号码数据库中将电话号码分配状态设置为“未分配”


- **从具有 Operator Connect 电话号码的用户中删除 Microsoft 365 电话系统许可证** 将：
  - Clear LineUri
  - 将 EnterpriseVoiceEnabled 设置为 False
  - 在电话号码数据库中将电话号码的分配状态设置为“未分配”


- **从具有直接路由电话号码的用户中删除 Microsoft 365 电话系统许可证** 将：
  - Clear LineUri
  - 将 EnterpriseVoiceEnabled 设置为 False
  - 从电话号码数据库中删除电话号码


## <a name="change-a-license"></a>更改许可证

如果需要更改涉及某个先决条件许可证的用户的许可证，应确保同时进行和保存许可更改。 此方法将确保用户保留其分配的电话号码，并可在 Microsoft Teams 中继续拨打和接收 PSTN 呼叫。 

例如，假设要将Microsoft 365 E5许可证分配给当前拥有Microsoft 365 E3许可证的用户。 

- 如果使用的是 Teams 管理中心，请在用户详细信息 **的“许可证和应用** ”选项卡中，确保删除旧许可证，并在单击“ **保存更改**”之前添加新许可证。 

- 如果使用的是 PowerShell cmdlet、 [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense) 或 [Set-MgUserLicense](/powershell/module/microsoft.graph.users.actions/set-mguserlicense)，请执行一次 cmdlet，并同时使用 -AddLicenses 和 -RemoveLicenses 参数。

 (如果删除旧许可证并保存更改，然后添加新许可证并保存更改，则电话号码将取消分配，并且用户可能无法在 Microsoft Teams 中拨打和接收 PSTN 呼叫。 分配新许可证后，需要将电话号码重新分配给用户。) 










