---
title: 分配 Teams 许可证
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 12/14/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: mikedav
description: 了解如何将许可证分配等音频会议，电话系统的功能和呼叫计划。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 46966b7cad855ef6336b501564cde89dffd6b2b2
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32198734"
---
# <a name="assign-microsoft-teams-licenses"></a>将 Microsoft 团队许可证分配

您可以对等音频会议和电话系统，调用计划功能为用户分配许可证。 本文说明如何添加这些许可证批量和针对个别用户。 

> [!IMPORTANT]
> 请参阅[Microsoft 团队加载项授权](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)有关您需要购买的许可证和如何购买，具体取决于您的 Office 365 的计划，以便用户获取音频会议和免费电话号码，能够调用您的公司外部的电话号码。

## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>电话系统和通话套餐：分配许可证的提示和脚本

下面是您需要知道分配音频会议和电话系统，调用规划许可证之前。

- **使用的是面向混合用户的内部部署 PSTN 连接？** 如果是这样，您只需将电话系统许可证分配。 您不应将分配调用规划。

- **延迟后分配许可证**： Office 365 与 Microsoft 团队之间的延迟，因为它可能需要多达 24 小时用户要分配调用规划后分配许可证。 如果在 24 小时后用户未分配调用计划，请[与业务产品的管理员技术支持部门联系](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。

- **错误消息** ：如果你还没有购买正确数量的许可证，则会收到一条错误消息。 如果您需要购买更多调用规划许可证，请选择**购买更多**。

- **后续步骤**： 将调用规划许可证分配给您的用户后，您将需要获得您的组织，您的电话号码，然后将这些号码分配给您的组织中的人员。 有关分步说明，请参阅[Set up 调用计划](set-up-calling-plans.md)。

## <a name="assign-a-phone-system-and-calling-plan-license-to-one-user"></a>将电话系统和调用规划许可证分配给一个用户

步骤与分配 Office 365 许可证相同。 请参阅[如何分配或取消分配 Office 365 商业版适用的用户许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。

## <a name="assign-phone-system-and-calling-plan-licenses-in-bulk"></a>分配电话系统和调用规划批量许可证

1. 安装 适用于 IT 专业人员 RTW 的 Microsoft Online Services 登录助手 。 没有安装模块？ 请参阅[Microsoft Online Services 登录助手的 IT 专业人员的一项](https://go.microsoft.com/fwlink/?LinkId=625123)以下载该。

2. 安装 Windows Azure Active Directory 模块。 没有安装模块？ 下载说明和 cmdlet 语法，请参阅[Manage 使用 Windows PowerShell 的 Azure AD](https://go.microsoft.com/fwlink/p/?LinkId=320628) 。

3. 在安装模块后，请使用 Windows PowerShell 命令提示符和以下语法向用户分配许可证：

本示例指定一个 企业版 E3 许可证以及电话系统和国内通话套餐许可证。

斜体 （此示例之后，请参阅[电话系统和调用计划的产品名称或 Sku 用于脚本](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting)，） 中列出的许可证的名称或脚本中的产品名称。

```
#Create a text file with a single row containing list of UserPrincipalName (UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.

#Example of text file:
#user1@domain.com
#user2@domain.com

#Import Module
ipmo MSOnline
#Authenticate to MSOLservice.
Connect-MSOLService
#File prompt to select the userlist txt file.
[System.Reflection.Assembly]::LoadWithPartialName("System.windows.forms") | Out-Null
$OFD = New-Object System.Windows.Forms.OpenFileDialog
$OFD.filter = "text files (*.*)| *.txt"
$OFD.ShowDialog() | Out-Null
$OFD.filename
If ($OFD.filename -eq '')
{
 Write-Host "You did not choose a file. Try again" -ForegroundColor White -BackgroundColor Red
}
#Create a variable of all users.
$users = Get-Content $OFD.filename
#License each user in the $users variable.
#Use MCOPSTN1 for PSTN Domestic Calling and MCOPSTN2 for Domestic and
International Calling.
for each ($user in $users)
 {
 Write-host "Assigning License: $user"
 Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
 Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOEV " -ErrorAction SilentlyContinue
 Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOPSTN1 " -ErrorAction SilentlyContinue
 }

```
## <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a>电话系统和调用计划产品名称或 Sku 用于编写脚本

| 产品名称 | SKU 部件名称 |
|--------------|---------------|
| 企业版 E5 （带电话系统） | ENTERPRISEPREMIUM |
| 企业版 E3 | ENTERPRISEPACK | 
| 企业版 E1 | STANDARDPACK | 
| 电话系统 | MCOEV |
| 国内 & 国际呼叫计划 | MCOPSTN2 |
| 国内调用规划 （每用户每月美国/PR/CA，1200 分钟每用户每月欧盟国家/地区的 3000 分钟） | MCOPSTN1 |
| 国内调用规划 （120 分钟每用户每月的每个国家/地区） </br>*注意： 此计划在美国不可*。 | MCOPSTN5 |
| 国内调用规划 （240 分钟每用户每月的每个国家/地区） </br>*注意： 此计划在美国不可*。 | MCOPSTN6 |
| 通信点数 | MCOPSTNPP | 

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a>音频会议： 提示和分配许可证的脚本

下面是您需要知道分配音频会议许可证之前。

- **第三方音频会议提供商**： 如果某人已设置为使用第三方音频会议提供商，您将其分配的音频会议许可证时，他们将更改用于 Microsoft 为音频会议提供商。 你可以将他们更改回第三方提供商。

- **后续步骤**： 分配音频会议许可证后，您需要分配音频会议提供商。 请参阅[分配 Microsoft 作为音频会议提供商](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)。

## <a name="assign-an-audio-conferencing-license-to-one-user"></a>将音频会议许可证分配给一个用户

步骤与分配 Office 365 许可证相同。 请参阅[如何分配或取消分配 Office 365 商业版适用的用户许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。

## <a name="assign-audio-conferencing-licenses-in-bulk"></a>将批量音频会议许可证分配

1. 下载并安装[Microsoft Online Services 登录助手的 IT 专业人员的一项](https://go.microsoft.com/fwlink/?LinkId=625123)。

2. 下载并安装 Windows Azure Active Directory 模块。 下载说明和 cmdlet 语法，请参阅[Manage 使用 Windows PowerShell 的 Azure AD](https://go.microsoft.com/fwlink/p/?LinkId=320628) 。

在安装模块后，请使用 Windows PowerShell 命令提示符和以下语法向用户分配许可证：

斜体列出了在脚本中的产品名称或许可证的名称。 请参阅[音频会议产品名称或 SKU 用于编写脚本](#audio-conferencing-product-names-or-skus-used-for-scripting)的所有产品名称。

本示例指定一个要进行音频会议许可证以及一个企业版 E3 许可证。

```
#Create a text file with a single row containing list of UserPrincipalName(UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.
#Example of text file:
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
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOMEETADV " -ErrorAction SilentlyContinue
    }
```
## <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a>音频会议产品名称或 SKU 用于编写脚本

| 产品名称 | SKU 部件名称 |
|--------------|---------------|
| 音频会议 （订阅） | MCOMEETADV | 
| 音频会议支付每分钟 （付费）</br>*注意： 需要 Communications 字幕式设置和启用*。 | MCOMEETACPEA |
| 企业版 E1 | STANDARDPACK | 
| 企业版 E3 | ENTERPRISEPACK |
| 企业版 E5（无音频会议） |  ENTERPRISEPREMIUM_NOPSTNCONF |
| 企业 E5 （与音频会议） | ENTERPRISEPREMIUM |

##  <a name="communications-credits"></a>通信点数

下面是您需要知道分配 Communications 字幕式许可证之前。

- **企业 E5 客户**： 即使您的用户分配了企业 E5 许可证，但仍建议您将为其分配 Communications 字幕式许可证。

- **后续步骤** ：分配这些许可证后，你需要获得贵组织的电话号码，然后将这些号码分配给组织中的人员。 有关分步说明，请参阅[Set up 调用计划](set-up-calling-plans.md)。

## <a name="assign-a-communications-credits-license-to-one-user"></a>将通信字幕式许可证分配给一个用户

步骤与分配 Office 365 许可证相同。 请参阅[如何分配或取消分配 Office 365 商业版适用的用户许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。

## <a name="assign-communications-credits-licenses-in-bulk"></a>将批量 Communications 字幕式许可证分配

请看一下分配音频会议许可证的示例脚本。 更新其分配 Communications 字幕式许可证的信息。

## <a name="related-topics"></a>相关主题

[设置通话套餐](set-up-calling-plans.md)
</br>
[添加资金并管理通信点数](add-funds-and-manage-communications-credits.md)
