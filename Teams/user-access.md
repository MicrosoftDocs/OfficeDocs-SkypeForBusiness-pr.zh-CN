---
title: 管理对 Microsoft Teams 的用户访问
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: ritikag
search.appverid: MET150
description: 了解如何基于每个用户启用或禁用用户级别访问。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: b1f73a709ae6235859cbdccab493d8fa6d198823
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2018
ms.locfileid: "26294958"
---
<a name="manage-user-access-to-microsoft-teams"></a>管理对 Microsoft Teams 的用户访问
=====================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

在用户级别，可以启用或禁用基于每个用户分配或删除的 Microsoft 团队产品许可证的 Microsoft 团队访问。

目前，没有为打开团队或团队功能的子集或关闭之外许可单个用户级别策略选项。

> [!NOTE]
>Microsoft 建议，您打开团队公司中的所有用户，以便团队可以该库格式正确的项目和其他动态计划。 即使您决定为试点，它可能仍会有所帮助保持团队启用所有用户，但仅具有与试点的用户组的通信。

## <a name="manage-teams-through-the-office-365-admin-center"></a>通过在 Office 365 管理中心管理团队

直接通过 Office 365 admin center 用户管理界面进行管理团队用户级许可证。 管理员可以在创建新用户帐户时为新用户分配许可证，也可以为已有帐户的用户分配许可证。 管理员必须拥有 Office 365 全局管理员或用户管理管理员权限才能管理 Microsoft Teams 许可证。

为用户分配 E3 或 E5 等许可证 SKU 时，会自动分配 Microsoft Teams 许可证，并为用户启用 Microsoft Teams。 管理员可以对所有 Office 365 服务和许可证进行精细的控制，可以针对特定用户或一组用户启用或禁用 Microsoft Teams 许可证。

![Office 365 管理中心中的“产品许可证”部分屏幕截图。](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

可以随时禁用团队用户许可证。 一旦被禁用许可证，将阻止向 Microsoft 工作组的用户访问，用户将不再能够看到团队中的 Office 365 应用程序启动器和主页。

![Office 365 管理中心中的“产品许可证”部分屏幕截图，显示选择了 Microsoft Teams。](media/Manage_user_access_to_Microsoft_Teams_image4.png)

## <a name="manage-via-powershell"></a>通过 PowerShell 自定义管理

正如任何其他工作负荷一样，通过 PowerShell 以工作负荷许可证方式启用和禁用 Teams。 Microsoft Teams 的服务计划名称为 TEAMS1。 对于政府服务计划名称是 TEAMS_GOV。 （有关详细信息，请参阅[通过 Office 365 PowerShell 禁用对服务的访问](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell)。）

**示例：** 下面是只在特定许可证类型中的所有人，您就会禁用团队的快速示例。 你需要先执行此操作，然后单独为应该拥有访问权限的用户启用 Microsoft Teams，以进行试点。

要显示贵组织中具有的订阅类型，请使用以下命令：

      Get-MsolAccountSku

填写计划的名称（包括贵组织名称和学校的计划，例如 ContosoSchool:ENTERPRISEPACK_STUDENT），然后运行以下命令：

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
若要禁用团队的所有用户与您命名计划的活动许可证，请运行以下命令：

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

| | | |
|---------|---------|---------|
|![决策点图标。](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |决策点         |<ul><li>什么是整个组织内的组织规划团队入职培训？  （试点或开放）</li></ul>         |
|![后续步骤图标。](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |后续步骤         |<ul><li>如果通过封闭式试点上线，请确定是通过许可还是有针对性的通信来上线。</li><li>决策，根据需要步骤以确保仅试验用户有权访问工作组 （如果需要）。</li><li>文档的准则为哪些用户将 （或不会） 有权访问团队。</li></ul>         |

## <a name="manage-teams-at-the-office-365-tenant-level"></a>管理 Office 365 租户级别的团队
[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

