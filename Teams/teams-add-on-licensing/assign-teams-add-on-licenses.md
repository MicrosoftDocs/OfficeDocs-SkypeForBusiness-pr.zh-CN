---
title: 向用户分配 Teams 附加许可证
author: DaniEASmith
ms.author: danismith
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- m365initiative-meetings
search.appverid: MET150
f1.keywords:
- NOCSH
ms.reviewer: mikedav
description: 了解如何向用户分配 Teams 附加许可证，以获取音频会议、电话系统和通话套餐等功能。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 635280582796f2b373efc0c763fea0887bcd6e42
ms.sourcegitcommit: aa398950cc2f10b268c72a2b25caa0cf893e8230
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/08/2022
ms.locfileid: "69307777"
---
# <a name="assign-teams-add-on-licenses-to-users"></a>向用户分配 Teams 附加许可证

附加许可证是特定 Teams 功能（如音频会议、电话系统和通话套餐）的许可证。 本文介绍如何批量向单个用户和大型用户集分配加载项许可证。

> [!NOTE]
> 请参阅 [Teams 附加许可](./microsoft-teams-add-on-licensing.md) ，了解随附加许可证提供的 Teams 功能。 你还将找到有关需要购买哪些许可证以及如何购买它们的信息，具体取决于你的计划。 确定要为用户提供的功能后，将许可证分配给他们。

可以使用Microsoft 365 管理中心或 PowerShell 将许可证分配给组织中的用户。 你必须成为全局管理员或用户管理管理员才能管理许可证。

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a>在分配电话系统、通话套餐和通信点数许可证之前需要了解的内容

在开始之前，请查看以下要求：

- 如果使用本地公用电话交换网 (PSTN) 连接，则只需分配Teams 电话标准版许可证。 请勿分配通话套餐许可证。

- 向用户分配Microsoft通话套餐后，最长可能需要 24 小时才能在其 Teams 客户端中看到拨号盘。 如果拨号盘在 24 小时内未显示，请检查 [拨号盘配置](../dial-pad-configuration.md)。 如有必要，还可以 [联系支持人员](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。

- 如果未购买正确数量的许可证，则会收到错误消息。 如果需要购买更多通话套餐许可证，请选择购买更多套餐的选项。

- 即使为用户分配了企业 E5 许可证，你仍需要将其连接到 PSTN。 有多个 [PSTN 连接选项](../pstn-connectivity.md)，包括Microsoft Teams 通话套餐、直接路由或操作员连接。

- 向用户分配通话套餐或通信点数许可证后，需要获取组织的电话号码，然后将这些号码分配给用户。 有关分步说明，请参阅 [设置通话套餐](../set-up-calling-plans.md)。

## <a name="using-the-microsoft-365-admin-center"></a>使用 Microsoft 365 管理中心

使用Microsoft 365 管理中心一次将许可证分配给单个用户或小用户集。

在“ **许可证** ”页上分配许可证 (一次最多 20 个用户) 或 **“活动用户** ”页 () 一次最多 40 个用户。 选择的方法取决于你想要管理特定用户的产品许可证还是管理特定产品的用户许可证。

有关分步说明，请参阅[向用户分配许可证](/microsoft-365/admin/manage/assign-licenses-to-users)。

如果需要为大量用户（例如数百或数千个用户）分配许可证，请在 [Azure Active Directory (Azure AD) 中使用 PowerShell 或基于组的许可 ](/azure/active-directory/users-groups-roles/licensing-groups-assign)。

## <a name="using-powershell"></a>使用 PowerShell

使用 PowerShell 批量向用户分配许可证。 若要了解详细信息，请参阅 [使用 PowerShell 将许可证分配给用户帐户](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)。

### <a name="example-script"></a>示例脚本

下面是如何使用脚本向用户分配许可证的示例。

1. [安装用于Windows PowerShell的 Microsoft Azure Active Directory 模块](/powershell/azure/active-directory/install-msonlinev1)。
2. 在Windows PowerShell命令提示符下，运行以下脚本以向用户分配许可证，其中 `CompanyName:License` 是组织名称和要分配的许可证的标识符。 例如， `litwareinc:MCOMEETADV`。

    标识符不同于许可证的友好名称。 例如，音频会议的标识符为 `MCOMEETADV`。 若要了解详细信息，请参阅 [许可的产品名称和 SKU 标识符](#product-names-and-sku-identifiers-for-licensing)。

    ```powershell
    #Create a text file with a single column that lists the user principal names (UPNs) of users to assign licenses to. The MSOL service uses the UPN to license user accounts.
    #Example of text file:''
    #user1@domain.com
    #user2@domain.com

    #Import Module
    ipmo MSOnline

    #Authenticate to MSOLservice
    Connect-MSOLService
    #File prompt to select the userlist txt file
    [System.Reflection.Assembly]::LoadWithPartialName("System.windows.forms") | Out-Null
      $OFD = New-Object System.Windows.Forms.OpenFileDialog
      $OFD.filter = "text files (*.*)| *.txt"
      $OFD.ShowDialog() | Out-Null
      $OFD.filename

    If ($OFD.filename -eq '')
    {
    Write-Host "You did not choose a file. Try again" -ForegroundColor White -BackgroundColor Red
    }

    #Create a variable of all users
    $users = Get-Content $OFD.filename

    #License each user in the $users variable
    foreach ($user in $users)
        {
        Write-host "Assigning License: $user"
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:<CompanyName:License>" -ErrorAction SilentlyContinue
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:<CompanyName:License>" -ErrorAction SilentlyContinue
        }
    ```

    例如，若要分配Microsoft 365 企业版 E1 和音频会议许可证，请在脚本中使用以下语法：

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    若要分配具有通话套餐许可证的 Teams 电话，请在脚本中使用以下语法：

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOTEAMS_ESSENTIALS" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a>许可的产品名称和 SKU 标识符

下面是在 Teams 中使用 PowerShell 管理许可证时可以引用的产品名称及其相应 SKU 部件名称的部分列表。

若要了解详细信息，请参阅[使用 PowerShell 查看许可证和服务](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)、[许可的产品名称和服务计划标识符](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)[，以及教育版 SKU 参考](../sku-reference-edu.md)。

| 产品名称| SKU 部件名称 |
|--------------|---------------|
| Microsoft企业版 E5 (与电话系统)  | ENTERPRISEPREMIUM |
| 没有音频会议) 的 Microsoft Enterprise E5 ( | ENTERPRISEPREMIUM_NOPSTNCONF |
| Microsoft企业版 E5 (与音频会议)  | ENTERPRISEPREMIUM |
| Microsoft企业版 E3 | ENTERPRISEPACK |
| Microsoft企业版 E1 | STANDARDPACK |
| Microsoft 365 商业基础版 | O365_BUSINESS_ESSENTIALS|
| Microsoft 365 商业标准版 | O365_BUSINESS_PREMIUM|
| Microsoft 365 商业版 | SPB|
| 音频会议 | MCOMEETADV |
| 音频会议每分钟付费 (即用即付) 需要设置并启用通信点数。* | MCOMEETACPEA |
| Teams 电话标准版 | MCOEV |
| 包含通话套餐的 Teams 电话 | MCOTEAMS_ESSENTIALS |
| 国际通话套餐 | MCOPSTN2 |
| 美国/PR/CA 的国内通话套餐 (每个用户/月 3000 分钟，欧盟国家/地区/月每用户 1200 分钟)  | MCOPSTN1 |
| 国内通话套餐 (每个用户/月 120 分钟，适用于每个国家/地区)  </br>*此计划在美国中不可用。* | MCOPSTN5 |
| 国内通话套餐 (每个用户/月 240 分钟，适用于每个国家/地区)  </br>*此计划在美国中不可用。* | MCOPSTN6 |
| 通信点数 | MCOPSTNPP |
| 即用即付通话套餐 (区域 1 国家/地区)  | MCOPSTN_PAYG_1 |
| 即用即付通话套餐 (区域 2 国家/地区)  | MCOPSTN_PAYG_2 |
| Microsoft Teams 会议室基本版 | Microsoft_Teams_Rooms_Basic |
| 不使用音频会议Microsoft Teams 会议室基本版 | Microsoft_Teams_Rooms_Basic_without_Audio_Conferencing |
| Microsoft Teams 会议室专业版 | Microsoft_Teams_Rooms_Pro |
| 不使用音频会议Microsoft Teams 会议室专业版 | Microsoft_Teams_Rooms_Pro_without_Audio_Conferencing |
| Microsoft Teams Premium | Microsoft_Teams_Premium |

## <a name="related-content"></a>相关内容

- [Teams 附加许可](./microsoft-teams-add-on-licensing.md)
- [管理用户对 Teams 的访问管理](../user-access.md)
- [使用 PowerShell 查看许可证和服务](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [用于许可的产品名称和服务计划标识符](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [教育 SKU 参考](../sku-reference-edu.md)
