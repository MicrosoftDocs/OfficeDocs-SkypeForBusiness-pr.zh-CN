---
title: 管理对 Microsoft Teams 的用户访问
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
description: 了解如何基于每个用户启用或禁用用户级别访问。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: a612420808af06a773d206573f02d805aac06b15
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2018
---
<a name="manage-user-access-to-microsoft-teams"></a>管理对 Microsoft Teams 的用户访问
=====================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

在用户级别中，可以启用或禁用基于每个用户分配或删除 Microsoft 小组产品许可证访问 Microsoft 小组。

目前，没有为打开团队或小组功能的子集或关闭外部授权单个用户级别策略选项。

> [!NOTE]
>Microsoft 建议启用团队为公司内所有用户，以便团队可以为项目和其他动态计划长足发展形成。 即使被确定为试点项目，它仍可能有助于使团队对所有的用户，启用，但只针对与试验组的用户的通信。

## <a name="manage-directly-through-the-office-365-admin-center"></a>直接通过 Office 365 管理中心管理

直接通过 Office 365 管理中心用户管理界面管理团队用户级别的许可证。 管理员可以在创建新用户帐户时为新用户分配许可证，也可以为已有帐户的用户分配许可证。 管理员必须拥有 Office 365 全局管理员或用户管理管理员权限才能管理 Microsoft Teams 许可证。

为用户分配 E3 或 E5 等许可证 SKU 时，会自动分配 Microsoft Teams 许可证，并为用户启用 Microsoft Teams。 管理员可以对所有 Office 365 服务和许可证进行精细的控制，可以针对特定用户或一组用户启用或禁用 Microsoft Teams 许可证。

![Office 365 管理中心中的“产品许可证”部分屏幕截图。](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

可随时禁用团队用户许可证。 一旦许可证被禁用，将阻止用户访问 Microsoft 小组的权限和用户将不再能够看到团队中的 Office 365 提供应用程序启动程序和主页。

![Office 365 管理中心中的“产品许可证”部分屏幕截图，显示选择了 Microsoft Teams。](media/Manage_user_access_to_Microsoft_Teams_image4.png)

## <a name="manage-via-powershell"></a>通过 PowerShell 管理

正如任何其他工作负荷一样，通过 PowerShell 以工作负荷许可证方式启用和禁用 Teams。 Microsoft Teams 的服务计划名称为 TEAMS1。 （有关详细信息，请参阅[通过 Office 365 PowerShell 禁用对服务的访问](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell)。）

**示例：**下面只是一个快速示例上特定的许可证类型中的每个人，您就会禁用团队。 你需要先执行此操作，然后单独为应该拥有访问权限的用户启用 Microsoft Teams，以进行试点。

要显示贵组织中具有的订阅类型，请使用以下命令：

      Get-MsolAccountSku

填写计划的名称（包括贵组织名称和学校的计划，例如 ContosoSchool:ENTERPRISEPACK_STUDENT），然后运行以下命令：

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
若要禁用团队使用命名计划活动的许可证的所有用户，请运行以下命令：

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

| | | |
|---------|---------|---------|
|![决策点图标。](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |决策点         |<ul><li>为团队服务的组织的计划整个组织是什么？  （试点或开放）</li></ul>         |
|![后续步骤图标。](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |后续步骤         |<ul><li>如果通过封闭式试点上线，请确定是通过许可还是有针对性的通信来上线。</li><li>根据决定，采取步骤以确保只试验用户有权访问团队 （如果需要）。</li><li>文档的准则为哪些用户会 （或不会） 有权访问团队。</li></ul>         |

## <a name="manage-via-office-sku-level-switch"></a>通过 Office Sku 级交换机管理
[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

1.  使用具有全局管理员权限的帐户登录 [Office 365 管理中心](https://go.microsoft.com/fwlink/?linkid=854614)。

2.  转至“**设置**” > “**服务和外接程序**”。

    ![Office 365 管理中心中的“设置”部分（选择了“服务和外接程序”）屏幕截图。 ](media/Set_up_Microsoft_Teams_in_your_Office_365_organization_image1.png)

3.  在“服务和外接程序”页面上，单击**“Microsoft Teams”**。

    ![选择了“Microsoft Teams”的“服务和外接程序”页面屏幕截图。](media/Set_up_Microsoft_Teams_in_your_Office_365_organization_image2.png)

4.  要为组织启用 Teams，请使用许可证选取器，并选择每个许可证，然后将切换设置为**“开启”**，并单击**“保存”**。

    ![Microsoft Teams 设置页面屏幕截图，显示切换设置为“开启”以启用 Microsoft Teams。](media/Services-and-addins-control-Microsoft-Teams.PNG)
