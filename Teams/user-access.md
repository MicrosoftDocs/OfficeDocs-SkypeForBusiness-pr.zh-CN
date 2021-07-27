---
title: 管理对 Microsoft Teams 的用户访问
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
description: 了解如何通过向组织中的用户分配或删除 Teams 许可证来管理对 Teams 的用户访问。
f1.keywords:
- CSH
- ms.teamsadmincenter.signin.domainerror.nolicensedusers
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: c996df5c0253f3eee02a2b76297952ccf9cf56d3
ms.sourcegitcommit: b387296c043fcf10fba7b9ef416328383e54a565
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/26/2021
ms.locfileid: "53587481"
---
# <a name="manage-user-access-to-teams"></a>管理对 Teams 的用户访问

你可通过分配或删除 Microsoft Teams 产品许可证，在用户级别管理对 Teams 的访问权限。 除了匿名加入 Teams 会议外，组织中的每个用户都必须拥有 Teams 许可证才能使用 Teams。 你可以在创建新用户帐户时为新用户分配 Teams 许可证，也可以为已有帐户的用户分配 Teams 许可证。

默认情况下，向用户分配许可计划（例如 Microsoft 365 企业版 E3 或 Microsoft 365 商业高级版）时，将自动分配 Teams 许可证，并且将为该用户启用 Teams。 你可随时通过删除或分配许可证来为用户禁用或启用 Teams。

使用从 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Teams 管理中心</a>管理的消息传递策略来控制 Teams 中的用户可以使用哪些聊天和频道消息传递功能。 可以使用默认策略，或者为组织中的人员创建一个或多个自定义消息策略。 若要了解更多详细信息，请参阅[在 Teams 中管理消息传递策略](messaging-policies-in-teams.md)。
你可在 Microsoft 365 管理中心或使用 PowerShell 来管理 Teams 许可证。 你必须成为全局管理员或用户管理管理员才能管理许可证。

> [!NOTE]
> 建议为所有用户启用 Teams，以便可以有组织地为项目和其他动态计划建立团队。 即使你只是在进行试点，为所有用户启用 Teams 也仍然可能很有用，但这只针对试点用户组的通信。

## <a name="using-the-microsoft-365-admin-center"></a>使用 Microsoft 365 管理中心

Teams 用户级别许可证是直接通过 Microsoft 365 管理中心用户管理界面管理的。 管理员可以在创建新用户帐户时为新用户分配许可证，也可以为已有帐户的用户分配许可证。 

> [!IMPORTANT]
> 管理员必须拥有全局管理员或用户管理管理员权限，才能管理 Microsoft Teams 许可证。
使用 Microsoft 365 管理中心一次管理单个用户或小部分用户的 Teams 许可证。 你可以在 **“许可证”** 页面（同时最多支持 20 个用户）或 **“活动用户”** 页面上管理 Teams 许可证。 选择的方法取决于你想要管理特定用户的产品许可证还是管理特定产品的用户许可证。

如果你需要为大量用户（如成百上千个用户）管理 Teams 许可证，请[使用 PowerShell ](#using-powershell) 或使用[在 Azure Active Directory (Azure AD) 中基于组的许可计划](/azure/active-directory/users-groups-roles/licensing-groups-assign)。 

### <a name="assign-a-teams-license"></a>分配 Teams 许可证

两者步骤有所不同，具体取决于你是使用 **“许可证”** 页面还是 **“活动用户”** 页面。  有关分步说明，请参阅[向用户分配许可证](/microsoft-365/admin/manage/assign-licenses-to-users)。

|&nbsp;|&nbsp;|
|---------|---------|
|![为用户启用Teams许可证的屏幕截图 1](media/assign-teams-licenses-1.png)    | ![为用户Teams许可证的屏幕截图 2](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a>删除 Teams 许可证

> [!IMPORTANT]
> 禁用 SKU 需要大约 24 小时Teams SKU 才能生效。

从用户删除 Teams 许可证时，将针对该用户禁用 Teams，然后他们将不会再在应用启动器或主页中看到 Teams。 有关详细步骤，请参阅[取消分配用户许可证](/microsoft-365/admin/manage/remove-licenses-from-users)。

|&nbsp;|&nbsp;|
|---------|---------|
|![用户禁用Teams许可证的屏幕截图 1](media/remove-teams-licenses-1.png)    | ![用户禁用Teams许可证的屏幕截图 2](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a>使用 PowerShell

使用 PowerShell 批量管理用户的 Teams 许可证。 你可以通过 PowerShell 来启用和禁用 Teams，方法与启用和禁用任何其他服务计划许可证相同。 你需要 Teams 服务计划的标识符，如下所示：

- Microsoft Teams：TEAMS1
- 适用于 GCC 的 Microsoft Teams：TEAMS_GOV
- 适用于 DOD 的 Microsoft Teams：TEAMS_DOD

### <a name="assign-teams-licenses-in-bulk"></a>批量分配 Teams 许可证

有关详细步骤，请参阅[使用 PowerShell 向用户帐户分配许可证](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)。

### <a name="remove-teams-licenses-in-bulk"></a>批量删除 Teams 许可证

有关详细步骤，请参阅[使用 PowerShell 禁止访问服务](/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) 和 [在分配用户许可证时禁止访问服务](/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)。

#### <a name="example"></a>示例 

以下示例演示了如何使用 [New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) 和 [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense) cmdlet 来为具有特定许可计划的用户禁用 Teams。 例如，请按照以下步骤操作，先为具有特定许可计划的所有用户禁用 Teams。 然后为应有权访问 Teams 的每位单独用户启用 Teams。

> [!IMPORTANT]
> [New-MsolLicenseOption](/powershell/module/msonline/new-msollicenseoptions) cmdlet 将启用先前禁用的所有服务，除非在自定义脚本中显式标识。 例如，如果希望在禁用 Teams 的同时禁用 Exchange 和 Sway，则需要在脚本中包括这个，否则将同时为已标识的用户启用 Exchange 和 Sway。

运行以下命令，显示组织中所有可用的许可计划。 有关详细信息，请参阅[使用 PowerShell 查看许可证和服务](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)。


```powershell
Get-MsolAccountSku
```

运行以下命令，其中 \<CompanyName:License> 是组织名称和在前一步中为许可计划所检索的标识符。 例如，ContosoSchool:ENTERPRISEPACK_STUDENT。

```powershell
$acctSKU="<CompanyName:License>
$x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
```

运行以下命令，对拥有许可计划有效许可证的所有用户禁用 Teams。

```powershell
Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x
```

## <a name="related-topics"></a>相关主题

- [Teams 附加许可许可证](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [分配 Teams 附加许可证](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [使用 PowerShell 查看许可证和服务](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [用于许可的产品名称和服务计划标识符](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [教育 SKU 参考](sku-reference-edu.md)
