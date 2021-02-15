---
title: 向用户分配 Teams 附加许可证
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
search.appverid: MET150
f1.keywords:
- NOCSH
ms.reviewer: mikedav
description: 了解如何为音频会议、电话系统和呼叫计划等功能的用户分配 Teams 附加许可证。
appliesto:
- Microsoft Teams
ms.openlocfilehash: f0b7a997525759741e35fa5450c9b8777519c6c7
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196926"
---
# <a name="assign-teams-add-on-licenses-to-users"></a>向用户分配 Teams 附加许可证

附加许可证是特定 Teams 功能（如音频会议、电话系统和通话计划）的许可证。 本文介绍如何将附加许可证批量分配给单个用户和大型用户集。

> [!NOTE]
> 有关 [随附加许可证一](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing) 起提供的 Teams 功能，请参阅 Teams 附加许可。 你还将找到有关需要购买哪些许可证以及如何购买许可证的信息 (具体取决于你的计划) ，以便用户可以获取音频会议、免费电话号码等功能，以及拨打组织外部的电话号码的功能。 确定要为用户提供哪些功能后，为其分配许可证。

可以使用 Microsoft 365 管理中心或 PowerShell 向组织的用户分配许可证。 只有全局管理员或用户管理管理员才能管理许可证。

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a>分配电话系统、呼叫计划和通信信用额度许可证之前需了解哪些信息

在开始使用之前，请查看以下要求：

- 如果为混合用户使用本地公用电话交换网 (PSTN) 连接，则只需分配电话系统许可证。 不要分配呼叫计划许可证。

- 由于 Microsoft 365 和 Microsoft Teams 之间的延迟，分配许可证后，最多可能需要 24 小时才能为用户分配呼叫计划。 如果 24 小时后未为用户分配呼叫计划，请联系业务产品 [支持人员 - 管理员帮助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。

- 如果尚未购买正确数量的许可证，则会显示一条错误消息。 如果需要购买更多通话套餐许可证，请选择购买更多许可证的选项。

- 即使为用户分配了企业版 E5 许可证，如果用户希望拨打或[](../what-are-communications-credits.md)接听来自 PSTN 的呼叫，你仍然需要为其分配通信信用额度许可证。

- 向用户分配"呼叫计划"或"通信积分"许可证后，需要获取组织的电话号码，然后将这些号码分配给用户。 有关分步说明，请参阅"[设置呼叫计划"。](../set-up-calling-plans.md)

## <a name="using-the-microsoft-365-admin-center"></a>使用 Microsoft 365 管理中心

使用 Microsoft 365 管理中心一次向单个用户或少量用户分配许可证。 在"许可证"页面上 **(许可证** ，一次最多为 20) 或 **"活动用户"** 页面。 选择的方法取决于是管理特定用户的产品许可证，还是管理特定产品的用户许可证。

有关分步说明，请参阅"[向用户分配许可证"。](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)

如果需要为大量用户（如数百或数千个用户）分配许可证，请使用 Azure Active Directory (Azure AD) 中的 [Powershell 或基于组的许可 ](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)。  

## <a name="using-powershell"></a>使用 PowerShell

使用 PowerShell 将许可证批量分配给用户。  若要了解有关详细信息，请参阅使用 [PowerShell 将许可证分配给用户帐户](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)。

### <a name="example-script"></a>示例脚本

以下示例演示了如何使用脚本向用户分配许可证。

1. 安装适用于 IT 专业人员 RTW Microsoft Online Services [64 位版本的登录助手](https://docs.microsoft.com/collaborate/connect-redirect?DownloadID=59185)。
2. 安装 Microsoft Azure Active Directory 模块Windows PowerShell：
    1. 打开提升的 Windows PowerShell 命令提示符 (以管理员Windows PowerShell运行) 。
    2. 运行以下命令：
        ```powershell
        Install-Module MSOnline
        ```
    3. 如果系统提示安装 NuGet 提供程序，请键入 **Y，** 然后按 Enter。
    4. 如果系统提示从 PSGallery 安装模块，请键入 **Y，** 然后按 Enter。
3. 在Windows PowerShell命令提示符下，运行以下脚本将许可证分配给用户，组织名称和要分配的许可证 \<CompanyName:License> 的标识符在哪里。 例如，litwareinc：MCOMEETADV。

    标识符不同于许可证的友好名称。 例如，音频会议标识符是 MCOMEETADV。 若要了解有关详细信息，请参阅 [许可的产品名称和 SKU 标识符](#product-names-and-sku-identifiers-for-licensing)。

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

    例如，若要分配 Microsoft 365 企业版 1 和音频会议许可证，请使用脚本中的以下语法：

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    若要在不使用呼叫 (许可证的情况下分配 Microsoft Business Voice) ，请使用脚本中的以下语法：

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:BUSINESS_VOICE_DIRECTROUTING" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a>用于许可的产品名称和 SKU 标识符

下面是部分产品名称及其对应的 SKU 部件名称列表，使用 PowerShell 在 Teams 中管理许可证时，可以使用这些部件名称作为参考。

有关详细信息，请参阅使用[PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)查看许可证和服务、许可[](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)的产品名称和服务计划标识符，以及教育[版 SKU 参考](../sku-reference-edu.md)。

| 产品名称| SKU 部件名称 |
|--------------|---------------|
| 将 Microsoft 企业版 E5 (手机系统)  | ENTERPRISEPREMIUM |
| 无需音频会议 (Microsoft 企业版 E5)  | ENTERPRISEPREMIUM_NOPSTNCONF |
| 将 Microsoft 企业版 E5 (音频会议)  | ENTERPRISEPREMIUM |
| Microsoft Enterprise E3 | ENTERPRISEPACK |
| Microsoft Enterprise E1 | STANDARDPACK |
| Microsoft 365 商业基础版 | O365_BUSINESS_ESSENTIALS|
| Microsoft 365 商业标准版 | O365_BUSINESS_PREMIUM|
| Microsoft 365 商业版 | SPB|
| Microsoft Business Voice (Canada) | BUSINESS_VOICE_MED  |
| Microsoft Business Voice (英国)  | BUSINESS_VOICE  |
| Microsoft Business Voice (美国)  | BUSINESS_VOICE_MED2  |
| 无需呼叫 (Microsoft Business Voice)  | BUSINESS_VOICE_DIRECTROUTING  |
| Microsoft Business Voice (美国) 套餐| BUSINESS_VOICE_DIRECTROUTING _MED |
| 音频会议 | MCOMEETADV | 
| 音频会议按分钟付费 (即用即付) </br>*要求设置和启用通信信用额度。* | MCOMEETACPEA |
| 电话系统 | MCOEV |
| 国内和国际呼叫计划 | MCOPSTN2 |
| 美国/ (/CA 的国内呼叫计划为每个用户/月 3000 分钟，欧盟/地区/地区为每个用户/月 1200)  | MCOPSTN1 |
| 每个用户/ (的国内呼叫计划为 120 分钟)  </br>*此计划在美国不可用。* | MCOPSTN5 |
| 每个用户/ (的国内呼叫计划为 240 分钟)  </br>*此计划在美国不可用。* | MCOPSTN6 |
| 通信点数 | MCOPSTNPP |

## <a name="related-topics"></a>相关主题

- [Teams 附加许可](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)
- [管理用户对 Teams 的访问管理](../user-access.md)
- [使用 PowerShell 查看许可证和服务](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [用于许可的产品名称和服务计划标识符](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [教育 SKU 参考](../sku-reference-edu.md)