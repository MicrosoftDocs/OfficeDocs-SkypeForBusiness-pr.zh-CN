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
- highpri
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: ''
description: 了解许可更改如何影响电话号码管理。
ms.openlocfilehash: f75c5aeea577163e9f3ee6d1d4302836de0d1e7e
ms.sourcegitcommit: 321de0e5d8846caaaab944826f6ca06394e707ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/16/2022
ms.locfileid: "69414669"
---
# <a name="how-licensing-affects-phone-number-management"></a>许可如何影响电话号码管理

删除许可证并将其分配给用户的方式可能会影响用户在 Microsoft Teams 中拨打和接收公用电话交换网 (PSTN) 呼叫的能力。 本文介绍如何管理许可更改，以确保用户拨打和接听 PSTN 呼叫的能力不受影响。

有关管理电话号码的一般信息，请参阅 [管理组织的电话号码](manage-phone-numbers-landing-page.md)。 有关 Teams 加载项许可的一般信息，请参阅[Microsoft Teams 附加许可证](/teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。



## <a name="remove-a-license"></a>删除许可证

如果你的用户具有分配的电话号码，并且你删除了一个或多个先决条件许可证，则删除许可证也会取消分配该用户的电话号码。 如果没有分配的电话号码，用户在Microsoft Teams 中拨打和接听 PSTN 呼叫的能力将受到影响。

根据用户的 [PSTN 连接选项](pstn-connectivity.md)，删除许可证会对电话参数产生以下影响：

- **从具有通话套餐电话号码的用户中删除 Microsoft 365 通话套餐许可证** 将：
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

如果需要更改涉及先决条件许可证之一的用户的许可证，应确保同时进行和保存许可更改。 此方法可确保用户保留其分配的电话号码，并且可以继续在 Microsoft Teams 中拨打和接听 PSTN 呼叫。 

例如，假设你想要将Microsoft 365 E5许可证分配给当前拥有Microsoft 365 E3许可证的用户。 

- 如果使用 Teams 管理中心，请在用户详细信息上的“ **许可证和应用** ”选项卡中，确保删除旧许可证并添加新许可证，然后单击“ **保存更改**”。 

- 如果使用 PowerShell cmdlet、 [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense) 或 [Set-MgUserLicense](/powershell/module/microsoft.graph.users.actions/set-mguserlicense)，请执行一次 cmdlet，并使用 -AddLicenses 和 -RemoveLicenses 参数。

 (如果删除旧许可证并保存更改，然后添加新许可证并保存更改，则电话号码将取消分配，并且用户可能无法在 Microsoft Teams 中拨打和接听 PSTN 呼叫。 分配新许可证后，需要将电话号码重新分配给 user.) 

有关如何使用基于组的许可同时更改许可证的信息，请参阅 [更改 Azure Active Directory 中用户或组的许可证分配](/azure/active-directory/enterprise-users/licensing-groups-change-licenses)。
