---
title: 删除存档配置中 Skype 业务服务器
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fed12cb5-2c80-476a-af3b-d55b450c5fbc
description: 摘要： 了解如何删除存档配置中 Skype 业务服务器。
ms.openlocfilehash: f8cb64cf7523cfaec26006560b4f77f39d904ead
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "21018933"
---
# <a name="delete-an-archiving-configuration-in-skype-for-business-server"></a><span data-ttu-id="a1f4d-103">删除存档配置中 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="a1f4d-103">Delete an archiving configuration in Skype for Business Server</span></span>

<span data-ttu-id="a1f4d-104">**摘要：** 了解如何删除存档配置中 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="a1f4d-104">**Summary:** Learn how to delete an archiving configuration in Skype for Business Server.</span></span>
  
<span data-ttu-id="a1f4d-p101">可以删除站点配置或池配置，但无法删除全局配置。如果删除全局配置，该配置将自动重置为默认值。</span><span class="sxs-lookup"><span data-stu-id="a1f4d-p101">You can delete a site configuration or pool configuration, but you cannot delete the global configuration. If you delete the global configuration, it is automatically reset to the default values.</span></span>
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a><span data-ttu-id="a1f4d-107">使用控制面板删除存档配置</span><span class="sxs-lookup"><span data-stu-id="a1f4d-107">Delete an archiving configuration by using the Control Panel</span></span>

<span data-ttu-id="a1f4d-108">要使用控制面板删除存档配置</span><span class="sxs-lookup"><span data-stu-id="a1f4d-108">To delete an archiving configuration by using the Control Panel:</span></span>
  
1. <span data-ttu-id="a1f4d-109">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="a1f4d-109">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="a1f4d-110">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="a1f4d-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="a1f4d-111">在左侧导航栏中，单击“**监控和存档**”，然后单击“**存档配置**”。</span><span class="sxs-lookup"><span data-stu-id="a1f4d-111">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="a1f4d-112">在存档配置的列表中，单击要删除的站点或池配置，单击“**编辑**”，然后单击“**删除**”。</span><span class="sxs-lookup"><span data-stu-id="a1f4d-112">In the list of archiving configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a1f4d-113">您也可以单击全局配置，但仅在希望将全局配置重置为默认值时选择此选项。</span><span class="sxs-lookup"><span data-stu-id="a1f4d-113">You can also click the Global configuration, but choose this option only if you want to reset the Global configuration to the default values.</span></span> 
  
5. <span data-ttu-id="a1f4d-114">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="a1f4d-114">Click **Commit**.</span></span>
    
## <a name="delete-an-archiving-configuration-by-using-windows-powershell"></a><span data-ttu-id="a1f4d-115">使用 Windows PowerShell 删除存档配置</span><span class="sxs-lookup"><span data-stu-id="a1f4d-115">Delete an archiving configuration by using Windows PowerShell</span></span>

<span data-ttu-id="a1f4d-116">您还可以使用**Remove-csarchivingconfiguration** cmdlet 删除存档配置。</span><span class="sxs-lookup"><span data-stu-id="a1f4d-116">You can also delete an archiving configuration by using the **Remove-CsArchivingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="a1f4d-p102">例如，以下命令可删除应用于 Redmond 站点的存档配置设置。删除在站点范围内配置的策略后，先前受站点策略管理的用户将自动受到全局存档策略的管理：</span><span class="sxs-lookup"><span data-stu-id="a1f4d-p102">For example, the following command removes the archiving configuration settings applied to the Redmond site. When a policy configured at the site scope is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead:</span></span>
  
```
Remove-CsArchivingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="a1f4d-119">以下命令会删除应用到服务范围的所有存档配置设置：</span><span class="sxs-lookup"><span data-stu-id="a1f4d-119">The following command removes all the archiving configuration settings applied to the service scope:</span></span>
  
```
Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration
```

<span data-ttu-id="a1f4d-120">下一条命令会删除在其中已禁用 Exchange 存档的所有存档配置设置：</span><span class="sxs-lookup"><span data-stu-id="a1f4d-120">The next command removes all the archiving configuration settings where Exchange archiving has been disabled:</span></span>
  
```
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

<span data-ttu-id="a1f4d-121">您也可以使用 **Remove-CsArchivingConfiguration** cmdlet 将全局设置重置为默认值。</span><span class="sxs-lookup"><span data-stu-id="a1f4d-121">You can also use the **Remove-CsArchivingConfiguration** cmdlet to reset the global settings to default values.</span></span> <span data-ttu-id="a1f4d-122">例如，假设您已在全局级别启用 IM 会话存档；以下命令会将该值重置为默认值 None，这将在全局级别禁用存档：</span><span class="sxs-lookup"><span data-stu-id="a1f4d-122">For example, suppose you have enabled IM session archiving at the global level; the following command will reset the value to the default of None, which will disable archiving at the global level:</span></span>
  
```
Remove-CsArchivingConfiguration -Identity global
```

<span data-ttu-id="a1f4d-123">有关详细信息，请参阅[Remove-csarchivingconfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="a1f4d-123">For more information, see the help topic for the [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>