---
title: 在Microsoft Teams 会议中屏蔽电话号码
author: heidip
ms.author: heidip
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
ms.openlocfilehash: 7072d1853a49d9e7ebc59e360c971874ed6549a3
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2022
ms.locfileid: "69242266"
---
# <a name="mask-phone-numbers-in-microsoft-teams-meetings"></a>在Microsoft Teams 会议中屏蔽电话号码

为了增加隐私，使用音频会议拨入 Teams 会议的参与者的电话号码将完全显示给内部参与者。 这些号码从组织外部的参与者中屏蔽。 此设置是所有组织的默认设置。 掩码编号如下图所示：

![掩码电话号码的示例。](media/hiddenPhoneNum.png)

对于特定的行业用例，管理员可以选择音频会议参与者的电话号码在其租户中组织的会议中的显示方式。 管理员可以从三个选项中进行选择：

- 电话号码仅对外部参与者进行屏蔽。 属于会议组织者的租户的参与者仍会看到完整的电话号码。
- 除组织者外，会议中的所有人都屏蔽了电话号码。
- 电话号码是未屏蔽的，这使得会议中的每个人都可以看到它们。

此设置应用于会议中公开电话号码的所有图面。

## <a name="use-teams-admin-center-to-set-phone-number-masking"></a>使用 Teams 管理中心设置电话号码掩码

若要在 Teams 管理中心更改公用电话交换网 (PSTN) 掩码设置，请以管理员身份登录到 Teams 管理中心，在左侧导航面板中选择“ **会议** > **网桥** ”，然后选择“ **网桥设置**”。 “桥设置”窗格底部的“**显示掩码调用方 ID**”是一个下拉列表，它允许你选择以下选项：

- 致组织外部的参与者
- 致所有会议参与者
- 已禁用

## <a name="use-microsoft-powershell-to-set-phone-number-masking"></a>使用 Microsoft PowerShell 设置电话号码掩码

若要在 PowerShell 中更改 PSTN 掩码设置，请将 **`MaskPstnNumbersType`** [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings) cmdlet 的参数设置为可用选项之一。

若要仅屏蔽来自外部参与者的电话号码，请运行以下命令：

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
