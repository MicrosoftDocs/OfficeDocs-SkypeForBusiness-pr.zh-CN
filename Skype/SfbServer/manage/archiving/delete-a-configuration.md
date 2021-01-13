---
title: 删除 Skype for Business Server 中的存档配置
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
ms.assetid: fed12cb5-2c80-476a-af3b-d55b450c5fbc
description: 摘要：了解如何删除 Skype for Business Server 中的存档配置。
ms.openlocfilehash: a9d24a17ec769f5686502beb325e021c8b0f39c3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817622"
---
# <a name="delete-an-archiving-configuration-in-skype-for-business-server"></a><span data-ttu-id="06269-103">删除 Skype for Business Server 中的存档配置</span><span class="sxs-lookup"><span data-stu-id="06269-103">Delete an archiving configuration in Skype for Business Server</span></span>

<span data-ttu-id="06269-104">**摘要：** 了解如何删除 Skype for Business Server 中的存档配置。</span><span class="sxs-lookup"><span data-stu-id="06269-104">**Summary:** Learn how to delete an archiving configuration in Skype for Business Server.</span></span>
  
<span data-ttu-id="06269-105">您可以删除站点配置或池配置，但无法删除全局配置。</span><span class="sxs-lookup"><span data-stu-id="06269-105">You can delete a site configuration or pool configuration, but you cannot delete the global configuration.</span></span> <span data-ttu-id="06269-106">如果删除全局配置，该配置将自动重置为默认值。</span><span class="sxs-lookup"><span data-stu-id="06269-106">If you delete the global configuration, it is automatically reset to the default values.</span></span>
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a><span data-ttu-id="06269-107">使用控制面板删除存档配置</span><span class="sxs-lookup"><span data-stu-id="06269-107">Delete an archiving configuration by using the Control Panel</span></span>

<span data-ttu-id="06269-108">使用控制面板删除存档配置：</span><span class="sxs-lookup"><span data-stu-id="06269-108">To delete an archiving configuration by using the Control Panel:</span></span>
  
1. <span data-ttu-id="06269-109">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="06269-109">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="06269-110">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="06269-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="06269-111">在左侧导航栏中，单击 **“监控和存档”**，然后单击 **“存档配置”**。</span><span class="sxs-lookup"><span data-stu-id="06269-111">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="06269-112">在存档配置列表中，单击要删除的站点或池配置，再单击"编辑"，然后单击"**删除"。**</span><span class="sxs-lookup"><span data-stu-id="06269-112">In the list of archiving configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="06269-113">还可以单击"全局"配置，但仅在希望将全局配置重置为默认值时选择此选项。</span><span class="sxs-lookup"><span data-stu-id="06269-113">You can also click the Global configuration, but choose this option only if you want to reset the Global configuration to the default values.</span></span> 
  
5. <span data-ttu-id="06269-114">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="06269-114">Click **Commit**.</span></span>
    
## <a name="delete-an-archiving-configuration-by-using-windows-powershell"></a><span data-ttu-id="06269-115">使用配置删除存档Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="06269-115">Delete an archiving configuration by using Windows PowerShell</span></span>

<span data-ttu-id="06269-116">您还可以使用 **Remove-CsArchivingConfiguration** cmdlet 删除存档配置。</span><span class="sxs-lookup"><span data-stu-id="06269-116">You can also delete an archiving configuration by using the **Remove-CsArchivingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="06269-117">例如，以下命令将删除应用于 Redmond 站点的存档配置设置。</span><span class="sxs-lookup"><span data-stu-id="06269-117">For example, the following command removes the archiving configuration settings applied to the Redmond site.</span></span> <span data-ttu-id="06269-118">删除在站点范围配置的策略后，之前由站点策略管理的用户将自动受到全局存档策略的管理：</span><span class="sxs-lookup"><span data-stu-id="06269-118">When a policy configured at the site scope is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead:</span></span>
  
```PowerShell
Remove-CsArchivingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="06269-119">以下命令删除应用于服务范围的所有存档配置设置：</span><span class="sxs-lookup"><span data-stu-id="06269-119">The following command removes all the archiving configuration settings applied to the service scope:</span></span>
  
```PowerShell
Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration
```

<span data-ttu-id="06269-120">下一个命令将删除已禁用 Exchange 存档的所有存档配置设置：</span><span class="sxs-lookup"><span data-stu-id="06269-120">The next command removes all the archiving configuration settings where Exchange archiving has been disabled:</span></span>
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

<span data-ttu-id="06269-121">您还可以使用 **Remove-CsArchivingConfiguration** cmdlet 将全局设置重置为默认值。</span><span class="sxs-lookup"><span data-stu-id="06269-121">You can also use the **Remove-CsArchivingConfiguration** cmdlet to reset the global settings to default values.</span></span> <span data-ttu-id="06269-122">例如，假设您在全局级别启用了 IM 会话存档;以下命令将该值重置为默认值 None，这将在全局级别禁用存档：</span><span class="sxs-lookup"><span data-stu-id="06269-122">For example, suppose you have enabled IM session archiving at the global level; the following command will reset the value to the default of None, which will disable archiving at the global level:</span></span>
  
```PowerShell
Remove-CsArchivingConfiguration -Identity global
```

<span data-ttu-id="06269-123">有关详细信息，请参阅 [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="06269-123">For more information, see the help topic for the [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
