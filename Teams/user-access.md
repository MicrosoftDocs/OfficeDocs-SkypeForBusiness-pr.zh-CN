---
title: "管理对 Microsoft Teams 的用户访问 | Microsoft 支持"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "了解如何基于每个用户启用或禁用用户级别访问。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 252dfa4c739fddd152c54a38dff71255706bb1ef
ms.sourcegitcommit: 9756856140ea56a94e986c134c5c04e53e5c0fa6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2017
---
<a name="manage-user-access-to-microsoft-teams"></a>管理对 Microsoft Teams 的用户访问
=====================================

在用户级别上，可以通过分配或删除 Microsoft Teams 产品许可证来基于每个用户启用或禁用对 Microsoft Teams 的访问。

当前，除了许可外，没有用于按单个用户级别开启或关闭 Microsoft Teams 或一部分 Microsoft Teams 功能的策略选项。

| | |
|---------|---------|
|![注意图标。](media/Manage_user_access_to_Microsoft_Teams_image1.png)<br></br>注意 |Microsoft 建议为公司中的所有用户启用 Microsoft Teams，以便可以根据项目和其他动态计划自然地组成团队。 即使你只是决定试点，为所有用户启用 Microsoft Teams 可能仍然很有用，但只有用户试点组可以使用它进行通信。 |

Microsoft Teams 用户级别许可证直接通过 Office 365 管理中心用户管理界面进行管理。 管理员可以在创建新用户帐户时为新用户分配许可证，也可以为已有帐户的用户分配许可证。 管理员必须拥有 Office 365 全局管理员或用户管理管理员权限才能管理 Microsoft Teams 许可证。

为用户分配 E3 或 E5 等许可证 SKU 时，会自动分配 Microsoft Teams 许可证，并为用户启用 Microsoft Teams。 管理员可以对所有 Office 365 服务和许可证进行精细的控制，可以针对特定用户或一组用户启用或禁用 Microsoft Teams 许可证。

![Office 365 管理中心中的“产品许可证”部分屏幕截图。](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

可以随时禁用 Microsoft Teams 用户许可证。 禁用许可证后，将阻止用户访问 Microsoft Teams，用户将无法再在 Office 365 应用启动程序和主页上看到 Microsoft Teams。

![Office 365 管理中心中的“产品许可证”部分屏幕截图，显示选择了 Microsoft Teams。](media/Manage_user_access_to_Microsoft_Teams_image4.png)

除了使用 Office 365 管理中心外，Office 365 管理员还可以使用 Office 365 PowerShell 分配和删除许可证。 要为用户分配许可证，请使用以下语法：

Set-MsolUserLicense -UserPrincipalName "\<Account\>" -AddLicenses "\<AccountSkuId\>"

以下示例将 litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) 许可计划中的许可证分配给未授权用户 belindan@litwareinc.com。

Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"

有关更多详细信息和示例，请参阅[*使用 Office 365 PowerShell 为用户帐户分配许可证*](https://go.microsoft.com/fwlink/?linkid=855755)。

要从现有用户帐户删除许可证，请使用以下语法：

Set-MsolUserLicense -UserPrincipalName \<Account\> -RemoveLicenses "\<AccountSkuId1\>", "\<AccountSkuId2\>"

以下示例从用户帐户 BelindaN@litwareinc.com 删除 litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) 许可证。

Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -RemoveLicenses "litwareinc:ENTERPRISEPACK"

有关更多详细信息和示例，请参阅[*使用 Office 365 PowerShell 从用户帐户删除许可证*](https://go.microsoft.com/fwlink/?linkid=855756)。

| | | |
|---------|---------|---------|
|![决策点图标。](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |决策点         |<ul><li>贵组织在组织中上线 Microsoft Teams 的计划是什么？  （试点或开放）</li></ul>         |
|![后续步骤图标。](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |后续步骤         |<ul><li>如果通过封闭式试点上线，请确定是通过许可还是有针对性的通信来上线。</li><li>根据决定，采取相应步骤来确保仅允许的试点用户可以访问 Microsoft Teams（如果需要）。</li><li>在下面记录用于规定将有权（无权）访问 Microsoft Teams 的用户的准则。</li></ul>         |
