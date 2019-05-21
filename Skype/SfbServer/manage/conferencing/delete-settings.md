---
title: 删除 Skype for Business 服务器中的会议配置设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: '摘要: 了解如何在 Skype for Business Server 中删除会议配置设置。'
ms.openlocfilehash: a728f1c1de3470cf505163c5cb25996c190e9026
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306473"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="82cff-103">删除 Skype for Business 服务器中的会议配置设置</span><span class="sxs-lookup"><span data-stu-id="82cff-103">Delete meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="82cff-104">**摘要:** 了解如何在 Skype for Business Server 中删除会议配置设置。</span><span class="sxs-lookup"><span data-stu-id="82cff-104">**Summary:** Learn how to delete meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="82cff-105">可以使用 Skype for Business Server 控制面板或使用 Skype for business Server 命令行管理器删除会议配置设置。</span><span class="sxs-lookup"><span data-stu-id="82cff-105">You can delete meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="82cff-p101">可以删除站点或用户配置，但无法删除全局配置。如果试图删除全局配置，该配置将自动重置为默认值。</span><span class="sxs-lookup"><span data-stu-id="82cff-p101">You can delete a site or user configuration, but you cannot delete the global configuration. If you attempt to delete the global configuration, it is automatically reset to the default values.</span></span>
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="82cff-108">使用 Skype for Business 服务器控制面板删除会议配置设置</span><span class="sxs-lookup"><span data-stu-id="82cff-108">Delete meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="82cff-109">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="82cff-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="82cff-110">打开 "Skype for Business 服务器" 控制面板。</span><span class="sxs-lookup"><span data-stu-id="82cff-110">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="82cff-111">在左侧导航栏中，单击“**会议**”，然后单击“**会议配置**”。</span><span class="sxs-lookup"><span data-stu-id="82cff-111">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="82cff-112">在会议配置的列表中，单击要删除的站点或池配置，单击“**编辑**”，然后单击“**删除**”。</span><span class="sxs-lookup"><span data-stu-id="82cff-112">In the list of meeting configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="82cff-113">使用 Skype for Business Server 命令行管理程序删除会议配置设置</span><span class="sxs-lookup"><span data-stu-id="82cff-113">Delete meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="82cff-114">若要删除会议设置，请使用 **Remove-CsMeetingConfiguration** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="82cff-114">To delete meeting settings, use the **Remove-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="82cff-115">以下命令将删除应用于 Redmond 站点的会议配置设置：</span><span class="sxs-lookup"><span data-stu-id="82cff-115">The following command removes the meeting configuration settings applied to the Redmond site:</span></span>
  
```
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="82cff-116">下一个命令删除应用于站点作用域的所有会议配置设置：</span><span class="sxs-lookup"><span data-stu-id="82cff-116">The next command removes all the meeting configuration settings applied to the site scope:</span></span>
  
```
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

<span data-ttu-id="82cff-117">有关详细信息, 包括参数的完整列表, 请参阅[Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="82cff-117">For more information, including a complete list of parameters, see [Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).</span></span>
  

