---
title: 为 Google Workspace 设置 Microsoft Teams 会议加载项
author: CarolynRowe
ms.author: crowe
ms.reviewer: aravin
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: 了解如何为 Google Workspace 设置 Microsoft Teams 会议加载项。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 020fdd048b25dc015036e49d00858c106cf9a7af
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789177"
---
# <a name="set-up-microsoft-teams-meeting-add-on-for-google-workspace"></a>为 Google Workspace 设置 Microsoft Teams 会议加载项

使用 Microsoft Teams 会议加载项可让 Google 日历用户直接从 Google Workspace 安排和加入 Microsoft Teams 会议。 用户可以访问 Teams 会议功能，包括视频和音频会议、屏幕共享、会议聊天、数字白板等。 保持联系和组织，在工作、学校和生活中共同完成更多工作。

必须由 Teams 管理员启用适用于 Google Workspace 的 Microsoft Teams 会议加载项，租户用户才能访问该应用。

## <a name="enable-or-disable-microsoft-teams-meeting-add-on-for-google-workspace-in-the-azure-portal"></a>在Azure 门户中为 Google Workspace 启用或禁用 Microsoft Teams 会议加载项

作为租户管理员，可以使用Azure 门户从组织的管理员帐户启用或禁用适用于 Google Workspace 的 Microsoft Teams 会议加载项。

默认情况下启用加载项。

1. 登录到Azure 门户。

2. 选择 **企业应用程序** > **所有应用程序**。

3. 搜索 **Google Workspace 的 Microsoft Teams 会议加载项**。

   ![Azure 门户显示所有应用程序。](media/aad-add-google-workspace.png)

4. 选择 **“是**”。

   ![Azure 门户显示 google 工作区属性。](media/google-workspace-properties.png)

5.  (可选) 若要禁用加载项，请在步骤 4 中选择 **“否** ”而不是 **“是** ”。

## <a name="disable-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a>使用 PowerShell 为 Google Workspace 禁用 Microsoft Teams 会议加载项

```powershell
Connect-AzureAD

$displayName = 'Microsoft Teams meeting add-on for Google Workspace'
$appId = '7969c887-ba98-48bb-8832-6c9239929d7c'

# Check if a service principal already exists for the app
$servicePrincipal = Get-AzureADServicePrincipal -Filter "appId eq '$appId'"
if ($servicePrincipal) {
    # Service principal exists already, disable it
    Set-AzureADServicePrincipal -ObjectId $servicePrincipal.ObjectId -AccountEnabled $false
    Write-Host "Disabled existing Service Principal \n"
} else {
    # Service principal does not yet exist, create it and disable it at the same time
    New-AzureADServicePrincipal -AppId $appId -DisplayName $displayName
    Get-AzureADServicePrincipal -Filter "appId eq '$appId'" | Set-AzureADServicePrincipal -AccountEnabled:$false
    Write-Host "Created and disabled the Service Principal \n"
}
```

有关详细信息，请参阅[使用Azure PowerShell创建 Azure 服务主体](/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0)。

## <a name="delete-the-microsoft-teams-meeting-add-on-for-google-workspace"></a>删除适用于 Google Workspace 的 Microsoft Teams 会议加载项

有关说明，请参阅 Google 文档 [“删除 Google 工作区市场”应用](https://support.google.com/a/answer/6216211?hl=en) 。

## <a name="create-the-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a>使用 PowerShell 为 Google Workspace 创建 Microsoft Teams 会议加载项

如果租户中不存在 Microsoft Teams 会议加载项，可以使用 PowerShell 创建它： 

```powershell
Connect-AzureAD

$displayName = 'Microsoft Teams meeting add-on for Google Workspace'
$appId = '7969c887-ba98-48bb-8832-6c9239929d7c'

# Check if a service principal already exists for the app
$servicePrincipal = Get-AzureADServicePrincipal -Filter "appId eq '$appId'"
if ($servicePrincipal) {
    # Service principal exists already
    Write-Host "The Service principal already exists"
} else {
    # Service principal does not yet exist, create it
    New-AzureADServicePrincipal -AppId $appId -DisplayName $displayName
    Write-Host "Created the Service Principal"
}
```
