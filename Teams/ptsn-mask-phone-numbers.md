---
title: 在 Microsoft Teams 会议中屏蔽电话号码
author: heidip
ms.author: MicrosoftHeidi
manager: serdars
ms.reviewer: moakram
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 了解如何在 Microsoft Teams 会议中屏蔽电话号码
ms.openlocfilehash: e1ef25f12bdf92bc58739284af2a624257169403
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270817"
---
# <a name="mask-phone-numbers-in-microsoft-teams-meetings"></a>在 Microsoft Teams 会议中屏蔽电话号码

为了增加隐私，使用音频会议拨入 Teams 会议的参与者的电话号码将完全显示给内部参与者。 数字会从组织外部的参与者中屏蔽。 此设置是所有组织的默认设置。 掩码编号如下图所示：

![蒙面电话号码的示例。](media/hiddenPhoneNum.png)

对于特定的行业用例，管理员能够选择音频会议参与者的电话号码在租户中组织的会议中显示的方式。 管理员可以从三个选项中进行选择：

- 电话号码仅由外部参与者屏蔽。 属于会议组织者租户的参与者仍然看到完整的电话号码。
- 除组织者外，会议中每个人的电话号码都被屏蔽。
- 电话号码是未屏蔽的，这使得会议中的每个人都可以看到。

此设置应用于公开电话号码的会议中的所有表面。

## <a name="use-microsoft-powershell-to-set-phone-number-masking"></a>使用 Microsoft PowerShell 设置电话号码掩码

若要更改公共交换电话网络 (PSTN) 掩码设置，请将 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet 的参数设置 **`MaskPstnNumbersType`** 为可用选项之一。

若要仅屏蔽外部参与者的电话号码，请运行以下命令：

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForExternalUsers"
```

若要屏蔽会议 (除组织者) 以外的所有参与者的电话号码，请运行以下命令：

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForAllUsers"
```

若要禁用电话号码掩码，请运行以下命令：

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "NoMasking"
```
