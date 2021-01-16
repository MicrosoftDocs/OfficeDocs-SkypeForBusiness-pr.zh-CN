---
title: 为 Google Workspace 设置 Microsoft Teams 会议加载项
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
description: 了解如何为 Google Workspace 设置 Microsoft Teams 会议加载项。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9c86d707a4298d88d3ae0cff389bda73490390e4
ms.sourcegitcommit: 380cd74c08cd34e1c3f73f5c0f51da4ae2674f6f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2021
ms.locfileid: "49880864"
---
# <a name="set-up-microsoft-teams-meeting-add-on-for-google-workspace"></a><span data-ttu-id="c7ddb-103">为 Google Workspace 设置 Microsoft Teams 会议加载项</span><span class="sxs-lookup"><span data-stu-id="c7ddb-103">Set up Microsoft Teams meeting add-on for Google Workspace</span></span>

<span data-ttu-id="c7ddb-104">使用 Microsoft Teams 会议加载项，Google 日历用户可以直接从 Google Workspace 安排和加入 Microsoft Teams 会议。</span><span class="sxs-lookup"><span data-stu-id="c7ddb-104">Using the Microsoft Teams meeting add-on lets Google calendar users schedule and join a Microsoft Teams meeting directly from Google Workspace.</span></span> <span data-ttu-id="c7ddb-105">用户可以访问 Teams 会议功能，包括视频和音频会议、屏幕共享、会议聊天、数字白板等。</span><span class="sxs-lookup"><span data-stu-id="c7ddb-105">Users will get access to Teams meetings features including video and audio conferencing, screen sharing, meeting chat, digital whiteboards, and more.</span></span> <span data-ttu-id="c7ddb-106">保持连接和井井有条，在工作、学校与生活之间共同完成更多工作。</span><span class="sxs-lookup"><span data-stu-id="c7ddb-106">Stay connected and organized to get more done together across work, school, and life.</span></span>

<span data-ttu-id="c7ddb-107">必须先由 Teams 管理员启用适用于 Google Workspace 的 Microsoft Teams 会议加载项，租户用户才能访问该应用。</span><span class="sxs-lookup"><span data-stu-id="c7ddb-107">The Microsoft Teams meeting add-on for Google Workspace must be enabled by a Teams admin before tenant users can access the app.</span></span>

## <a name="enable-or-disable-microsoft-teams-meeting-add-on-for-google-workspace-in-the-azure-portal"></a><span data-ttu-id="c7ddb-108">在 Azure 门户中启用或禁用 Google Workspace 的 Microsoft Teams 会议加载项</span><span class="sxs-lookup"><span data-stu-id="c7ddb-108">Enable or disable Microsoft Teams meeting add-on for Google Workspace in the Azure portal</span></span>

<span data-ttu-id="c7ddb-109">作为租户管理员，可以使用 Azure 门户从组织的管理员帐户为 Google Workspace 启用或禁用 Microsoft Teams 会议加载项。</span><span class="sxs-lookup"><span data-stu-id="c7ddb-109">As a tenant administrator, you can enable or disable a Microsoft Teams meeting add-on for Google Workspace from your organization's admin account using the Azure portal.</span></span>

<span data-ttu-id="c7ddb-110">默认情况下启用加载项。</span><span class="sxs-lookup"><span data-stu-id="c7ddb-110">The add-on is enabled by default.</span></span>

1. <span data-ttu-id="c7ddb-111">登录到 Azure 门户。</span><span class="sxs-lookup"><span data-stu-id="c7ddb-111">Sign in to the Azure portal.</span></span>

2. <span data-ttu-id="c7ddb-112">选择 **"企业应用程序**  >  **所有应用程序"。**</span><span class="sxs-lookup"><span data-stu-id="c7ddb-112">Select **Enterprise applications** > **All applications**.</span></span>

3. <span data-ttu-id="c7ddb-113">搜索 **Google Workspace 的 Microsoft Teams 会议加载项**。</span><span class="sxs-lookup"><span data-stu-id="c7ddb-113">Search for **Microsoft Teams meeting add-on for Google Workspace**.</span></span>

   ![显示所有应用程序的 Azure 门户](media/aad-add-google-workspace.png)

4. <span data-ttu-id="c7ddb-115">选择 **"是"。**</span><span class="sxs-lookup"><span data-stu-id="c7ddb-115">Select **Yes**.</span></span>

   ![显示 Google 工作区属性的 Azure 门户](media/google-workspace-properties.png)

5. <span data-ttu-id="c7ddb-117"> (可选) 禁用加载项，请在步骤 4 中选择 **"** 否"而不是"是"。</span><span class="sxs-lookup"><span data-stu-id="c7ddb-117">(Optional) To disable the add-on, select **No** instead of **Yes** in Step 4.</span></span>

## <a name="disable-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a><span data-ttu-id="c7ddb-118">使用 PowerShell 禁用 Google Workspace 的 Microsoft Teams 会议加载项</span><span class="sxs-lookup"><span data-stu-id="c7ddb-118">Disable Microsoft Teams meeting add-on for Google Workspace using PowerShell</span></span>

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

<span data-ttu-id="c7ddb-119">有关详细信息，请参阅"使用 Azure PowerShell 创建[Azure 服务主体"。](https://docs.microsoft.com/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0)</span><span class="sxs-lookup"><span data-stu-id="c7ddb-119">For more information, see [Create an Azure service principal with Azure PowerShell](https://docs.microsoft.com/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0).</span></span>

## <a name="delete-the-microsoft-teams-meeting-add-on-for-google-workspace"></a><span data-ttu-id="c7ddb-120">删除 Google Workspace 的 Microsoft Teams 会议加载项</span><span class="sxs-lookup"><span data-stu-id="c7ddb-120">Delete the Microsoft Teams meeting add-on for Google Workspace</span></span>

<span data-ttu-id="c7ddb-121">有关说明，请参阅 Google 文档 ["删除 Google Workspace Marketplace](https://support.google.com/a/answer/6216211?hl=en) 应用"。</span><span class="sxs-lookup"><span data-stu-id="c7ddb-121">See the Google documentation [Delete a Google Workspace Marketplace app](https://support.google.com/a/answer/6216211?hl=en) for instructions.</span></span>
