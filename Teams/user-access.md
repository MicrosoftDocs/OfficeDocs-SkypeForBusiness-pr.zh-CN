---
title: 管理对 Microsoft Teams 的用户访问
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
f1keywords: ms.teamsadmincenter.signin.domainerror.nolicensedusers
ms.reviewer: ritikag
search.appverid: MET150
description: 了解如何基于每个用户启用或禁用用户级别访问。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 26abd2a69bc8097c4f74cbc85435cda4eec00887
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "37563111"
---
<a name="manage-user-access-to-microsoft-teams"></a>管理对 Microsoft Teams 的用户访问
=====================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

在用户级别上，可以通过分配或删除 Microsoft 团队产品许可证，在每用户基础上启用或禁用对 Microsoft 团队的访问。

使用邮件策略从团队管理中心进行管理，以控制团队中的用户可以使用哪些聊天和频道消息功能。 你可以使用默认策略或为组织中的人员创建一个或多个自定义消息策略。 若要了解详细信息，请阅读[团队中的 "管理消息策略](messaging-policies-in-teams.md)"。

> [!NOTE]
>Microsoft 建议为公司中的所有用户打开团队，以便团队可以为项目和其他动态计划 organically。 即使你决定试点，也可能仍然有助于为所有用户启用团队，但只是将目标与用户的试验组通信。

## <a name="manage-teams-through-the-microsoft-365-admin-center"></a>通过 Microsoft 365 管理中心管理团队

团队用户级许可证通过 Microsoft 365 管理中心用户管理界面直接管理。 管理员可以在创建新用户帐户时为新用户分配许可证，也可以为已有帐户的用户分配许可证。 管理员必须拥有 Office 365 全局管理员或用户管理管理员权限才能管理 Microsoft Teams 许可证。

为用户分配 E3 或 E5 等许可证 SKU 时，会自动分配 Microsoft Teams 许可证，并为用户启用 Microsoft Teams。 管理员可以对所有 Office 365 服务和许可证进行精细的控制，可以针对特定用户或一组用户启用或禁用 Microsoft Teams 许可证。

![管理中心中产品许可证部分的屏幕截图。](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

团队用户许可证可随时禁用。 禁用许可证后，将阻止用户访问 Microsoft 团队，并且用户将无法再查看 Office 365 应用启动器和主页中的团队。

![显示 "产品许可证" 部分中所选团队的屏幕截图。](media/Manage_user_access_to_Microsoft_Teams_image4.png)

## <a name="manage-via-powershell"></a>通过 PowerShell 管理

> [!IMPORTANT]
> 新 MsolLicenseOptions 将启用之前已禁用的所有服务，除非你的自定义脚本中 explictitly identitied。 例如，如果你希望在 additonally 禁用团队期间禁用这两个 Exchange & Sway，你需要在脚本中 inlcude 此操作，或者将为已标识的用户启用 Exchange & Sway。 如果你希望使用 GUI 来管理此功能，请参阅： [Office 365 许可证报告和管理工具-批量分配删除许可证](https://gallery.technet.microsoft.com/Office365-License-cfd9489c)

正如任何其他工作负荷一样，通过 PowerShell 以工作负荷许可证方式启用和禁用 Teams。 Microsoft Teams 的服务计划名称为 TEAMS1。 对于 GCC，服务计划名称为 TEAMS_GOV。 对于 GCC 高版，服务计划名称为 TEAMS_GCCHIGH。 对于 DoD，服务计划名称为 TEAMS_DOD （有关详细信息，请参阅[禁用 Office 365 PowerShell 的服务访问](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell)。）

**示例：** 以下只是有关如何针对特定许可证类型中的每个人禁用团队的快速示例。 你需要先执行此操作，然后单独为应该拥有访问权限的用户启用 Microsoft Teams，以进行试点。

要显示贵组织中具有的订阅类型，请使用以下命令：

      Get-MsolAccountSku

填写计划的名称（包括贵组织名称和学校的计划，例如 ContosoSchool:ENTERPRISEPACK_STUDENT），然后运行以下命令：

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
若要为所有用户禁用已命名计划的活动许可证的团队，请运行以下命令：

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

| | | |
|---------|---------|---------|
|![代表决策点的图标](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |决策点         |<ul><li>组织在整个组织中的团队计划的计划是什么？  （试点或开放）</li></ul>         |
|![表示后续步骤的图标](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |后续步骤         |<ul><li>如果通过已关闭的试用版进行加入，请确定你是否希望通过许可证或目标通信执行此操作。</li><li>根据决策，采取步骤确保仅允许访问团队的试用用户（如果需要）。</li><li>记录将（或不会）有权访问团队的用户的指南。</li></ul>         |

## <a name="manage-teams-at-the-office-365-tenant-level"></a>管理 Office 365 租户级别的团队
[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

