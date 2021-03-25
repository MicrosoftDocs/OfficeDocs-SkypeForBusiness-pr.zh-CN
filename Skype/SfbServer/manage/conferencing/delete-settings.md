---
title: 删除 Skype for Business Server 中的会议配置设置
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: 摘要：了解如何删除 Skype for Business Server 中的会议配置设置。
ms.openlocfilehash: b0c739f0149b4e28ca23df1437caab0505e1118d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119491"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="f269d-103">删除 Skype for Business Server 中的会议配置设置</span><span class="sxs-lookup"><span data-stu-id="f269d-103">Delete meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="f269d-104">**摘要：** 了解如何删除 Skype for Business Server 中的会议配置设置。</span><span class="sxs-lookup"><span data-stu-id="f269d-104">**Summary:** Learn how to delete meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="f269d-105">可以使用 Skype for Business Server 控制面板或 Skype for Business Server 命令行管理程序删除会议配置设置。</span><span class="sxs-lookup"><span data-stu-id="f269d-105">You can delete meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="f269d-106">可以删除站点或用户配置，但不能删除全局配置。</span><span class="sxs-lookup"><span data-stu-id="f269d-106">You can delete a site or user configuration, but you cannot delete the global configuration.</span></span> <span data-ttu-id="f269d-107">如果您尝试删除全局配置，则会自动将其重置为默认值。</span><span class="sxs-lookup"><span data-stu-id="f269d-107">If you attempt to delete the global configuration, it is automatically reset to the default values.</span></span>
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="f269d-108">使用 Skype for Business Server 控制面板删除会议配置设置</span><span class="sxs-lookup"><span data-stu-id="f269d-108">Delete meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="f269d-109">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="f269d-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="f269d-110">打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="f269d-110">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="f269d-111">在左侧导航栏中，单击 **"会议"，** 然后单击"会议 **配置"。**</span><span class="sxs-lookup"><span data-stu-id="f269d-111">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="f269d-112">在会议配置列表中，单击要删除的站点或池配置，再单击"编辑"，然后单击"删除 **"。**</span><span class="sxs-lookup"><span data-stu-id="f269d-112">In the list of meeting configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="f269d-113">使用 Skype for Business Server 命令行管理程序删除会议配置设置</span><span class="sxs-lookup"><span data-stu-id="f269d-113">Delete meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="f269d-114">若要删除会议设置，请使用 **Remove-CsMeetingConfiguration** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f269d-114">To delete meeting settings, use the **Remove-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="f269d-115">以下命令删除应用于 Redmond 站点的会议配置设置：</span><span class="sxs-lookup"><span data-stu-id="f269d-115">The following command removes the meeting configuration settings applied to the Redmond site:</span></span>
  
```PowerShell
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="f269d-116">下一个命令将删除应用于站点范围的所有会议配置设置：</span><span class="sxs-lookup"><span data-stu-id="f269d-116">The next command removes all the meeting configuration settings applied to the site scope:</span></span>
  
```PowerShell
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

<span data-ttu-id="f269d-117">有关详细信息，包括参数的完整列表，请参阅[Remove-CsMeetingConfiguration。](/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="f269d-117">For more information, including a complete list of parameters, see [Remove-CsMeetingConfiguration](/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).</span></span>
