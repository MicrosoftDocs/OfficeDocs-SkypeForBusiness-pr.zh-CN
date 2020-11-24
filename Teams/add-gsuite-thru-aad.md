---
title: 设置 Google Workspace 的 Microsoft 团队会议加载项
author: cichur
ms.author: v-cichur
ms.reviewer: aravin
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: 了解如何为 Google Workspace 设置 Microsoft 团队会议加载项。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9c86d707a4298d88d3ae0cff389bda73490390e4
ms.sourcegitcommit: 882ed439f8bba27b1cf0c14056c146267cacd359
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "49387282"
---
# <a name="set-up-microsoft-teams-meeting-add-on-for-google-workspace"></a>设置 Google Workspace 的 Microsoft 团队会议加载项

使用 Microsoft 团队会议加载项，可让 Google 日历用户直接从 Google Workspace 安排和加入 Microsoft 团队会议。 用户将能够访问团队会议功能，包括视频和音频会议、屏幕共享、会议聊天、数字白板等。 保持连接和组织，以便在工作、学校和生活中共同完成更多工作。

对于 Google Workspace，Microsoft 团队会议加载项必须由团队管理员启用，租户用户才能访问该应用。

## <a name="enable-or-disable-microsoft-teams-meeting-add-on-for-google-workspace-in-the-azure-portal"></a>在 Azure 门户中启用或禁用 Google Workspace 的 Microsoft 团队会议加载项

作为租户管理员，你可以使用 Azure 门户从你的组织的管理员帐户启用或禁用 Google Workspace 的 Microsoft 团队会议加载项。

默认情况下启用加载项。

1. 登录到 Azure 门户。

2. 选择 "**企业应用程序**  >  **所有应用程序**"。

3. 搜索适用于 **Google Workspace 的 Microsoft 团队会议加载项**。

   ![显示所有应用程序的 Azure 门户](media/aad-add-google-workspace.png)

4. 选择 **"是"**。

   ![显示 google workspace 属性的 Azure 门户](media/google-workspace-properties.png)

5.  (可选) 禁用加载项，请在步骤4中选择 " **否** "，而不是 **"是"** 。

## <a name="disable-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a>使用 PowerShell 禁用 Google Workspace 的 Microsoft 团队会议加载项

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
    $servicePrincipal = New-AzureADServicePrincipal -AppId $appId -DisplayName $displayName -AccountEnabled $false
    Write-Host "Created and disabled the Service Principal \n"
}
```

有关详细信息，请参阅 [使用 Azure PowerShell 创建 azure 服务主体](https://docs.microsoft.com/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0)。

## <a name="delete-the-microsoft-teams-meeting-add-on-for-google-workspace"></a>删除 Google Workspace 的 Microsoft 团队会议加载项

有关说明，请参阅 Google 文档 " [删除 Google Workspace Marketplace 应用](https://support.google.com/a/answer/6216211?hl=en) "。
