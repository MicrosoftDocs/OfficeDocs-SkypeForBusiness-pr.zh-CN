---
title: 在会议中屏蔽Microsoft Teams电话号码
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
ms.reviewer: moakram
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 了解如何在会议中屏蔽Microsoft Teams电话号码
ms.openlocfilehash: afdbaa4f2f437728aad14e3731ab3e26ba90f36d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60828425"
---
# <a name="mask-phone-numbers-in-microsoft-teams-meetings"></a>在会议中屏蔽Microsoft Teams电话号码

为增加隐私，使用音频会议拨入 Teams会议的参与者的电话号码将完全向内部参与者显示。 号码会从组织外部的参与者中屏蔽。 此设置是所有组织的默认设置。 显示屏蔽数字，如下图所示：

![已屏蔽电话号码的示例。](media/hiddenPhoneNum.png)

对于特定的行业用例，管理员可以选择音频会议参与者的电话号码在租户中组织的会议中如何显示。 管理员可以从三个选项中进行选择：

- 电话外部参与者屏蔽数字。 属于会议组织者租户的参与者仍看到完整电话号码。
- 电话会议中的所有人（组织者除外）屏蔽了数字。
- 电话数字未屏蔽，因此会议中的每个人都可以看到它们。

此设置应用于会议中公开电话号码的所有图面。

## <a name="use-microsoft-powershell-to-set-phone-number-masking"></a>使用 Microsoft PowerShell 设置电话号码掩码

若要更改公用电话交换网 (PSTN) 屏蔽设置，请设置 **`MaskPstnNumbersType`** [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet 的参数，以使用其中一个可用选项。

若要仅屏蔽来自外部参与者的电话号码，请运行以下命令：

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForExternalUsers"
```

若要屏蔽会议参与者的电话号码， (组织者) ，请运行以下命令：

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForAllUsers"
```

若要禁用电话号码掩码，请运行以下命令：

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "NoMasking"
```