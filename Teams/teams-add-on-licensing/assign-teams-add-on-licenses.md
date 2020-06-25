---
title: 向用户分配团队附加许可证
author: LanaChin
ms.author: v-lanac
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
description: 了解如何向用户分配 "音频会议"、"电话系统" 和 "通话计划" 等功能的团队加载项许可证。
appliesto:
- Microsoft Teams
ms.openlocfilehash: c7faaf2e65330aafd809872ed19b5f2f16afc668
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868579"
---
# <a name="assign-teams-add-on-licenses-to-users"></a>向用户分配团队附加许可证

加载项许可证是特定团队功能（如音频会议、电话系统和通话计划）的许可证。 本文介绍如何将加载项许可证分配给单个用户以及批量用户的大型用户组。

> [!NOTE]
> 请参阅适用于使用加载项许可证的团队功能的[团队加载项许可](microsoft-teams-add-on-licensing.md)。 你还可以找到有关需要购买哪些许可证以及如何购买许可证的信息（取决于你的计划），以便用户可以获得音频会议、免费电话号码等功能，以及呼叫组织外部电话号码的功能。 确定所需的用户功能后，为他们分配许可证。

你可以使用 Microsoft 365 管理中心或 PowerShell 将许可证分配给你的组织中的用户。 您必须是全局管理员或用户管理管理员才能管理许可证。

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a>在分配电话系统、呼叫计划和通讯信用许可证之前需要了解的内容

开始之前，请查看以下内容：

- 如果您使用的是混合用户的本地公共交换电话网络（PSTN）连接，则只需分配电话系统许可证。 不要分配呼叫计划许可证。

- 由于 Microsoft 365 和 Microsoft 团队之间的延迟，在分配许可证后，可能需要长达24小时才能向用户分配呼叫计划。 如果在24小时后未向用户分配呼叫计划，[请联系业务产品支持-管理员帮助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。

- 如果尚未购买正确数量的许可证，您将收到一条错误消息。 如果您需要购买更多通话计划许可证，请选择购买更多电话的选项。

- 即使你的用户已分配有企业版 E5 许可证，你仍然需要将[信用点数](../what-are-communications-credits.md)许可证分配给他们，前提是他们需要从 PSTN 发出或接收呼叫。

- 向用户分配呼叫计划或通讯信用许可证后，您需要为您的组织获取电话号码，然后将这些号码分配给用户。 有关分步说明，请参阅[设置呼叫计划](../set-up-calling-plans.md)。

## <a name="using-the-microsoft-365-admin-center"></a>使用 Microsoft 365 管理中心

使用 Microsoft 365 管理中心将许可证分配给单个用户或一次一组小型用户。 你可以在 "**许可证**" 页面（一次最多20个用户）或 "**活动用户**" 页面分配许可证。 你选择的方法取决于你是要为特定用户管理产品许可证还是管理特定产品的用户许可证。

有关分步说明，请参阅[向用户分配许可证](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)。

如果需要为大量用户（如成百上千用户）分配许可证，请[在 Azure Active Directory （AZURE AD）中使用 Powershell 或基于组的许可](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)。  

## <a name="using-powershell"></a>使用 PowerShell

使用 PowerShell 批量向用户分配许可证。  若要了解详细信息，请参阅[使用 PowerShell 向用户帐户分配许可证](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)。

### <a name="example-script"></a>示例脚本

下面是如何使用脚本向用户分配许可证的示例。

1. [为 IT 专业人士 RTW 安装64位版本的 Microsoft Online Services 登录助手](https://go.microsoft.com/fwlink/p/?LinkId=286152)。
2. 安装适用于 Windows PowerShell 的 Microsoft Azure Active Directory 模块：
    1. 打开提升权限的 Windows PowerShell 命令提示符（以管理员身份运行 Windows PowerShell）。
    2. 运行以下命令：
        ```powershell
        Install-Module MSOnline
        ```
    3. 如果系统提示您安装 NuGet 提供程序，请键入 " **Y**"，然后按 Enter。
    4. 如果系统提示您从 PSGallery 安装模块，请键入**Y**，然后按 Enter。
3. 在 Windows PowerShell 命令提示符处，运行以下脚本以向你的用户分配许可证，其中 \<CompanyName:License> 是你的组织名称和要分配的许可证的标识符。 例如，litwareinc： MCOMEETADV。

    标识符与许可证的友好名称不同。 例如，音频会议的标识符是 MCOMEETADV。 若要了解详细信息，请参阅[产品名称和 SKU 标识符以获取许可](#product-names-and-sku-identifiers-for-licensing)。

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

    例如，要分配 Microsoft 365 企业版1和音频会议许可证，请在脚本中使用以下语法：

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    若要分配 Microsoft Business Voice （无需通话计划）许可证，请在脚本中使用以下语法：

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:BUSINESS_VOICE_DIRECTROUTING" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a>用于授权的产品名称和 SKU 标识符

下面是在使用 PowerShell 管理团队中的许可证时，可用作参考的产品名称及其相应 SKU 部件名称的部分列表。

若要了解详细信息，请参阅[通过 PowerShell 查看许可证和服务](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)、[产品名称和服务计划标识符以获得许可](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)和[教育 SKU 参考](../sku-reference-edu.md)。

| 产品名称| SKU 部件名称 |
|--------------|---------------|
| Microsoft 企业版 E5 （带电话系统） | ENTERPRISEPREMIUM |
| Microsoft 企业版 E5 （不带音频会议） | ENTERPRISEPREMIUM_NOPSTNCONF |
| Microsoft 企业版 E5 （带音频会议） | ENTERPRISEPREMIUM |
| Microsoft 企业版 E3 | ENTERPRISEPACK |
| Microsoft 企业版 E1 | STANDARDPACK |
| Microsoft 365 商业基础版 | O365_BUSINESS_ESSENTIALS|
| Microsoft 365 商业标准版 | O365_BUSINESS_PREMIUM|
| Microsoft 365 商业版 | SPB|
| Microsoft 商业语音（加拿大）| BUSINESS_VOICE_MED  |
| Microsoft 商业语音（英国） | BUSINESS_VOICE  |
| Microsoft 商业语音（美国） | BUSINESS_VOICE_MED2  |
| Microsoft 商业语音（无需通话计划） | BUSINESS_VOICE_DIRECTROUTING  |
| 适用于美国的 Microsoft Business Voice （无通话计划）| BUSINESS_VOICE_DIRECTROUTING _MED |
| 音频会议 | MCOMEETADV | 
| 每分钟支付的音频会议（即付即用）</br>*需要设置和启用通信信用点数。* | MCOMEETACPEA |
| 电话系统 | MCOEV |
| 国内和国际通话计划 | MCOPSTN2 |
| 国内呼叫计划（每个用户每月每月3000分钟，对于欧盟国家/地区，每个用户每月1200分钟） | MCOPSTN1 |
| 国内呼叫计划（每个国家/地区每个用户/月120分钟） </br>*此计划在美国不可用。* | MCOPSTN5 |
| 国内呼叫计划（每个国家/地区每个用户/月240分钟） </br>*此计划在美国不可用。* | MCOPSTN6 |
| 通信点数 | MCOPSTNPP |

## <a name="related-topics"></a>相关主题

- [Teams 附加许可](microsoft-teams-add-on-licensing.md)
- [管理用户对 Teams 的访问管理](../user-access.md)
- [通过 PowerShell 查看许可证和服务](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [用于许可的产品名称和服务计划标识符](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [教育 SKU 参考](../sku-reference-edu.md)