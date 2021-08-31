---
title: 为Microsoft Teams工作区设置会议加载项
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
description: 了解如何为 Google workspace Microsoft Teams会议加载项。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fb5f7574bd5e07598c412cd7d17f02625de2f095
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2021
ms.locfileid: "58729911"
---
# <a name="set-up-microsoft-teams-meeting-add-on-for-google-workspace"></a>为Microsoft Teams工作区设置会议加载项

使用 Microsoft Teams 会议加载项，Google 日历用户可以直接从 Google 工作区Microsoft Teams和加入会议。 用户可以访问Teams会议功能，包括视频和音频会议、屏幕共享、会议聊天、数字白板等。 保持连接并保持井井有条，在工作、学校与生活之间共同完成更多工作。

Microsoft Teams管理员必须启用 Google Workspace 的 Teams 会议加载项，租户用户才能访问该应用。

## <a name="enable-or-disable-microsoft-teams-meeting-add-on-for-google-workspace-in-the-azure-portal"></a>在 Azure Microsoft Teams中为 Google Workspace 启用或禁用会议加载项

作为租户管理员，可以使用 Azure 门户Microsoft Teams组织的管理员帐户为 Google Workspace 启用或禁用 Google Workspace 会议加载项。

默认情况下，该加载项已启用。

1. 登录到 Azure 门户。

2. 选择 **"Enterprise**  >  **应用程序""所有应用程序"。**

3. 搜索Microsoft Teams **工作区的会议加载项**。

   ![显示所有应用程序的 Azure 门户。](media/aad-add-google-workspace.png)

4. 选择"**是"。**

   ![显示 google 工作区属性的 Azure 门户。](media/google-workspace-properties.png)

5.  (可选) 若要禁用加载项，请在步骤 4 中选择"否"而不是"是"。

## <a name="disable-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a>使用 PowerShell Microsoft Teams Google Workspace 禁用会议加载项

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

有关详细信息，请参阅使用 Azure PowerShell 创建[Azure 服务主体](/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0)。

## <a name="delete-the-microsoft-teams-meeting-add-on-for-google-workspace"></a>删除Microsoft Teams工作区的会议加载项

有关说明，请参阅 Google 文档 [删除 Google Workspace Marketplace](https://support.google.com/a/answer/6216211?hl=en) 应用。