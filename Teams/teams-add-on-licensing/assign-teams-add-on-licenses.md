---
title: 向Teams分配附加许可证
author: cichur
ms.author: v-mahoffman
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
description: 了解如何为用户Teams音频会议、会议、电话系统等功能分配附加许可证。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 47d5f5838b382459fe6820f210a29b4809525e18
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60766120"
---
# <a name="assign-teams-add-on-licenses-to-users"></a>向Teams分配附加许可证

附加许可证是音频会议、Teams和呼叫计划等特定电话系统许可证。 本文介绍如何将附加许可证批量分配给单个用户和大型用户集。

> [!NOTE]
> 请参阅[Teams附加许可证](./microsoft-teams-add-on-licensing.md)Teams附加许可证提供的功能。 你还将找到有关需要购买哪些许可证以及如何购买许可证的信息 (具体取决于你的计划) ，以便用户可以获取音频会议、免费号码和呼叫组织外部电话号码等功能。 确定要为用户提供哪些功能后，请为其分配许可证。

可以使用 Microsoft 365 管理中心 PowerShell 为组织的用户分配许可证。 你必须成为全局管理员或用户管理管理员才能管理许可证。

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a>分配许可证、呼叫计划和通信电话系统许可证之前需了解哪些信息

在开始使用之前，请查看以下要求：

- 如果使用本地公用电话交换网和 PSTN (PSTN) 连接，则只需分配一个 电话系统 许可证。 不要分配呼叫计划许可证。

- 由于用户与Microsoft 365 Microsoft Teams延迟，分配许可证后，最多可能需要 24 小时才能为用户分配呼叫计划。 如果 24 小时后未为用户分配呼叫计划，请联系业务产品 [支持人员 - 管理员帮助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。

- 如果尚未购买正确数量的许可证，则会显示一条错误消息。 如果需要购买更多通话套餐许可证，请选择购买更多许可证的选项。

- 即使为用户分配了 Enterprise E5 许可证，如果用户想要拨打或接听来自[](../what-are-communications-credits.md)PSTN 的呼叫，你仍然需要为其分配通信信用额度许可证。

- 将"呼叫计划"或"通信信用额度"许可证分配给用户后，需要获取组织的电话号码，然后将这些号码分配给用户。 有关分步说明，请参阅 [设置呼叫计划](../set-up-calling-plans.md)。

## <a name="using-the-microsoft-365-admin-center"></a>使用 Microsoft 365 管理中心

使用Microsoft 365 管理中心一次向单个用户或少量用户分配许可证。 在"许可证"页面上 (一次最多为 20 个用户分配许可证) 或"活动用户"页 (一次最多为 40 个用户分配) 。 选择的方法取决于你想要管理特定用户的产品许可证还是管理特定产品的用户许可证。

有关分步说明，请参阅[向用户分配许可证](/microsoft-365/admin/manage/assign-licenses-to-users)。

如果需要为大量用户（如数百或数千个用户）分配许可证，请使用 Powershell 或[Azure Active Directory (Azure AD) 。 ](/azure/active-directory/users-groups-roles/licensing-groups-assign)  

## <a name="using-powershell"></a>使用 PowerShell

使用 PowerShell 批量向用户分配许可证。  有关详细信息，请参阅使用 [PowerShell 向用户帐户分配许可证](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)。

### <a name="example-script"></a>示例脚本

以下示例演示了如何使用脚本向用户分配许可证。

1. 安装适用于 IT 专业人员 RTW 的 [Microsoft Online Services 64 位版本的登录助手](/collaborate/connect-redirect?DownloadID=59185)。
2. 安装Microsoft Azure Active Directory模块Windows PowerShell：
    1. 打开权限提升的 Windows PowerShell 命令提示符 (以管理员Windows PowerShell运行) 。
    2. 运行以下命令：
        ```powershell
        Install-Module MSOnline
        ```
    3. 如果系统提示你安装 NuGet提供程序，请键入 **Y，** 然后按 Enter。
    4. 如果系统提示从 PSGallery 安装模块，请键入 **Y，** 然后按 Enter。
3. 在 Windows PowerShell命令提示符下，运行以下脚本将许可证分配给用户，其中 是组织名称和要分配的许可证 \<CompanyName:License> 的标识符。 例如，litwareinc：MCOMEETADV。

    标识符不同于许可证的友好名称。 例如，音频会议标识符是 MCOMEETADV。 有关详细信息，请参阅许可 [的产品名称和 SKU 标识符](#product-names-and-sku-identifiers-for-licensing)。

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

    例如，若要分配Microsoft 365 企业版 1 和音频会议许可证，请使用脚本中的以下语法：

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    若要在不使用呼叫计划 (的情况下分配 Microsoft Business Voice) ，请使用脚本中的以下语法：

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:BUSINESS_VOICE_DIRECTROUTING" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a>用于许可的产品名称和 SKU 标识符

下面部分列出了产品名称及其相应的 SKU 部件名称，在使用 PowerShell 管理许可证时，可以使用这些部件名称作为Teams。

有关详细信息，请参阅使用[PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)查看许可证和服务、许可的产品名称和服务计划[标识符，以及](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)[教育版 SKU 参考](../sku-reference-edu.md)。

| 产品名称| SKU 部件名称 |
|--------------|---------------|
| Microsoft Enterprise E5 (电话系统)  | ENTERPRISEPREMIUM |
| Microsoft Enterprise E5 (没有音频会议)  | ENTERPRISEPREMIUM_NOPSTNCONF |
| Microsoft Enterprise E5 (音频会议)  | ENTERPRISEPREMIUM |
| Microsoft Enterprise E3 | ENTERPRISEPACK |
| Microsoft Enterprise E1 | STANDARDPACK |
| Microsoft 365 商业基础版 | O365_BUSINESS_ESSENTIALS|
| Microsoft 365 商业标准版 | O365_BUSINESS_PREMIUM|
| Microsoft 365 商业版 | SPB|
| Microsoft Business Voice (Canada) | BUSINESS_VOICE_MED  |
| Microsoft Business Voice (英国)  | BUSINESS_VOICE  |
| Microsoft Business Voice (美国)  | BUSINESS_VOICE_MED2  |
| 无需呼叫计划 (Microsoft Business Voice)  | BUSINESS_VOICE_DIRECTROUTING  |
| Microsoft Business Voice (没有美国) 套餐| BUSINESS_VOICE_DIRECTROUTING _MED |
| 音频会议 | MCOMEETADV | 
| 音频会议按分钟付费 (即用即付) </br>*要求设置和启用通信信用额度。* | MCOMEETACPEA |
| 电话系统 | MCOEV |
| 国内和国际呼叫计划 | MCOPSTN2 |
| 美国/ (/CA 的用户/月国内呼叫计划为 3000 分钟，对于欧盟/地区，每个用户/月 1200 分钟)  | MCOPSTN1 |
| 每个用户/ (国内呼叫计划为每个用户/月 120)  </br>*此计划在美国不可用。* | MCOPSTN5 |
| 针对每个国家/ (，国内呼叫计划为每个用户/月 240)  </br>*此计划在美国不可用。* | MCOPSTN6 |
| 通信点数 | MCOPSTNPP |

## <a name="related-topics"></a>相关主题

- [Teams 附加许可](./microsoft-teams-add-on-licensing.md)
- [管理用户对 Teams 的访问管理](../user-access.md)
- [使用 PowerShell 查看许可证和服务](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [用于许可的产品名称和服务计划标识符](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [教育 SKU 参考](../sku-reference-edu.md)
