---
title: 向用户分配 Teams 加载项许可证
author: DaniEASmith
ms.author: danismith
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
description: 了解如何为音频会议、电话系统和通话套餐等功能的用户分配 Teams 加载项许可证。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 380abec55466d831722c76c9e552055378ecf1df
ms.sourcegitcommit: 791d0a341ff873145fa893ece05055729b0b8d50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/18/2022
ms.locfileid: "66838817"
---
# <a name="assign-teams-add-on-licenses-to-users"></a>向用户分配 Teams 加载项许可证

加载项许可证是特定 Teams 功能（如音频会议、电话系统和通话套餐）的许可证。 本文介绍如何批量向单个用户和大型用户集分配加载项许可证。

> [!NOTE]
> 请参阅 [Teams 加载项许可证](./microsoft-teams-add-on-licensing.md) 提供的 Teams 功能的加载项许可。 你还将根据你的计划找到有关需要购买哪些许可证以及如何购买这些许可证的信息。 确定用户所需的功能后，请将许可证分配给他们。

可以使用Microsoft 365 管理中心或 PowerShell 向组织中的用户分配许可证。 你必须成为全局管理员或用户管理管理员才能管理许可证。

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a>分配电话系统、呼叫计划和通信信用额度许可证之前需要了解的内容

在开始之前，请查看以下要求：

- 如果使用本地公用交换电话网络 (PSTN) 用户连接，则只需分配Teams 电话标准版许可证。 请勿分配通话套餐许可证。

- 将 Microsoft 呼叫计划分配给用户后，可能需要长达 24 小时才能在其 Teams 客户端中看到拨号盘。 如果拨号盘在 24 小时内未显示，请检查 [拨号盘配置](../dial-pad-configuration.md)。 如有必要，还可以 [联系支持人员](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。

- 如果尚未购买正确的许可证数，则会收到错误消息。 如果需要购买更多通话套餐许可证，请选择“购买更多”选项。

- 即使为用户分配了企业 E5 许可证，仍需要将其连接到 PSTN。 有几个 [PSTN 连接选项](../pstn-connectivity.md)，包括Microsoft Teams 通话套餐、直接路由或运算符连接。

- 将通话套餐或通信信用额度许可证分配给用户后，需要获取组织的电话号码，然后将这些号码分配给用户。 有关分步说明，请参阅 [“设置呼叫计划](../set-up-calling-plans.md)”。

## <a name="using-the-microsoft-365-admin-center"></a>使用 Microsoft 365 管理中心

使用Microsoft 365 管理中心一次向单个用户或少量用户分配许可证。

在“ **许可证** ”页 (一次最多为 20 名用户分配许可证) 或 **“活动用户** ”页面 (一次最多 40 个用户) 。 选择的方法取决于你想要管理特定用户的产品许可证还是管理特定产品的用户许可证。

有关分步说明，请参阅[向用户分配许可证](/microsoft-365/admin/manage/assign-licenses-to-users)。

如果需要为大量用户（例如成百上千的用户）分配许可证，请 [在 Azure Active Directory 中使用 Powershell 或基于组的许可 (Azure AD) ](/azure/active-directory/users-groups-roles/licensing-groups-assign)。

## <a name="using-powershell"></a>使用 PowerShell

使用 PowerShell 批量向用户分配许可证。 若要了解详细信息，请参阅使用 [PowerShell 将许可证分配给用户帐户](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)。

### <a name="example-script"></a>示例脚本

下面是一个示例，说明如何使用脚本向用户分配许可证。

1. 安装适用于 [IT 专业人员 RTW 的 Microsoft Online Services 登录助手](/collaborate/connect-redirect?DownloadID=59185)的 64 位版本。
2. 安装用于Windows PowerShell的Microsoft Azure Active Directory模块：
    1. 打开提升的Windows PowerShell命令提示符 (以管理员) 身份运行Windows PowerShell。
    2. 运行以下命令：
        ```powershell
        Install-Module MSOnline
        ```
    3. 如果系统提示安装 NuGet 提供程序，请键入 **Y**，然后按 Enter。
    4. 如果系统提示从 PSGallery 安装模块，请键入 **Y**，然后按 Enter。
3. 在Windows PowerShell命令提示符处，运行以下脚本，将许可证分配给用户，组织名称和要分配的许可证的标识符在哪里\<CompanyName:License>。 例如，litwareinc：MCOMEETADV。

    标识符不同于许可证的友好名称。 例如，音频会议的标识符是 MCOMEETADV。 若要了解详细信息，请参阅 [产品名称和 SKU 标识符以获取许可](#product-names-and-sku-identifiers-for-licensing)。

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

## <a name="product-names-and-sku-identifiers-for-licensing"></a>用于许可的产品名称和 SKU 标识符

下面是使用 PowerShell 管理 Teams 中的许可证时可以引用的产品名称及其相应 SKU 部件名称的部分列表。

若要了解详细信息，请参阅 [使用 PowerShell 查看许可证和服务](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)、 [产品名称和服务计划标识符以获取许可](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)以及 [教育 SKU 参考](../sku-reference-edu.md)。

| 产品名称| SKU 部件名称 |
|--------------|---------------|
| Microsoft Enterprise E5 (电话系统)  | ENTERPRISEPREMIUM |
| 没有音频会议) 的 Microsoft Enterprise E5 ( | ENTERPRISEPREMIUM_NOPSTNCONF |
| Microsoft Enterprise E5 (音频会议)  | ENTERPRISEPREMIUM |
| Microsoft Enterprise E3 | ENTERPRISEPACK |
| Microsoft Enterprise E1 | STANDARDPACK |
| Microsoft 365 商业基础版 | O365_BUSINESS_ESSENTIALS|
| Microsoft 365 商业标准版 | O365_BUSINESS_PREMIUM|
| Microsoft 365 商业版 | SPB|
| 音频会议 | MCOMEETADV |
| 音频会议按分钟付费 () 需要设置和启用通信额度。* | MCOMEETACPEA |
| Teams 电话标准版 | MCOEV |
| 包含通话套餐的 Teams 电话 | MCOTEAMS_ESSENTIALS |
| 国际通话套餐 | MCOPSTN2 |
| 美国/PR/CA 的国内通话计划 (每个用户/月 3000 分钟，欧盟国家为每个用户/月 1200 分钟)  | MCOPSTN1 |
| 每个国家/地区的国内通话计划 (每个用户/月 120 分钟)  </br>*此计划在美国中不可用。* | MCOPSTN5 |
| 每个国家/地区的国内通话计划 (每个用户/月 240 分钟)  </br>*此计划在美国中不可用。* | MCOPSTN6 |
| 通信点数 | MCOPSTNPP |

## <a name="related-content"></a>相关内容

- [Teams 附加许可](./microsoft-teams-add-on-licensing.md)
- [管理用户对 Teams 的访问管理](../user-access.md)
- [使用 PowerShell 查看许可证和服务](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [用于许可的产品名称和服务计划标识符](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [教育 SKU 参考](../sku-reference-edu.md)
