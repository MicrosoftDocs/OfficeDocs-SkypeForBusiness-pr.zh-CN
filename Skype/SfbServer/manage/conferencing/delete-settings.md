---
title: 删除会议配置设置中 Skype 业务服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: 摘要： 了解如何删除会议配置设置中 Skype 业务服务器。
ms.openlocfilehash: 2fbb278745eba392016b163be8f59a3abb07b47d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919379"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="3a7b6-103">删除会议配置设置中 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="3a7b6-103">Delete meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="3a7b6-104">**摘要：** 了解如何删除会议配置设置中 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="3a7b6-104">**Summary:** Learn how to delete meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="3a7b6-105">您可以删除会议配置设置，使用的业务 Server Control Panel Skype 或使用 Skype 业务 Server Management Shell。</span><span class="sxs-lookup"><span data-stu-id="3a7b6-105">You can delete meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="3a7b6-p101">可以删除站点或用户配置，但无法删除全局配置。如果试图删除全局配置，该配置将自动重置为默认值。</span><span class="sxs-lookup"><span data-stu-id="3a7b6-p101">You can delete a site or user configuration, but you cannot delete the global configuration. If you attempt to delete the global configuration, it is automatically reset to the default values.</span></span>
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="3a7b6-108">删除会议配置设置，使用 Skype 业务 Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="3a7b6-108">Delete meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="3a7b6-109">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="3a7b6-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="3a7b6-110">打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="3a7b6-110">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="3a7b6-111">在左侧导航栏中，单击“**会议**”，然后单击“**会议配置**”。</span><span class="sxs-lookup"><span data-stu-id="3a7b6-111">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="3a7b6-112">在会议配置的列表中，单击要删除的站点或池配置，单击“**编辑**”，然后单击“**删除**”。</span><span class="sxs-lookup"><span data-stu-id="3a7b6-112">In the list of meeting configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="3a7b6-113">删除会议使用 Skype 业务 Server 命令行管理程序配置设置</span><span class="sxs-lookup"><span data-stu-id="3a7b6-113">Delete meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="3a7b6-114">若要删除会议设置，请使用 **Remove-CsMeetingConfiguration** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3a7b6-114">To delete meeting settings, use the **Remove-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="3a7b6-115">以下命令将删除应用于 Redmond 站点的会议配置设置：</span><span class="sxs-lookup"><span data-stu-id="3a7b6-115">The following command removes the meeting configuration settings applied to the Redmond site:</span></span>
  
```
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="3a7b6-116">下一个命令删除应用于站点作用域的所有会议配置设置：</span><span class="sxs-lookup"><span data-stu-id="3a7b6-116">The next command removes all the meeting configuration settings applied to the site scope:</span></span>
  
```
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

<span data-ttu-id="3a7b6-117">有关详细信息，包括完成参数的列表，请参阅[Remove-csmeetingconfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="3a7b6-117">For more information, including a complete list of parameters, see [Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).</span></span>
  

