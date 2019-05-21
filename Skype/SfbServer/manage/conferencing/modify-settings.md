---
title: 在 Skype for Business 服务器中修改会议配置设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: '摘要: 了解如何在 Skype for Business Server 中修改会议配置设置。'
ms.openlocfilehash: 6e2566a5bc48e081c1912753586aef2213e1c727
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280395"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="b52b3-103">在 Skype for Business 服务器中修改会议配置设置</span><span class="sxs-lookup"><span data-stu-id="b52b3-103">Modify meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="b52b3-104">**摘要:** 了解如何在 Skype for Business Server 中修改会议配置设置。</span><span class="sxs-lookup"><span data-stu-id="b52b3-104">**Summary:** Learn how to modify meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="b52b3-105">可以使用 Skype for Business Server 控制面板或使用 Skype for business Server 命令行管理器修改会议配置设置。</span><span class="sxs-lookup"><span data-stu-id="b52b3-105">You can modify meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="b52b3-106">使用 Skype for Business Server "控制面板" 修改会议配置设置</span><span class="sxs-lookup"><span data-stu-id="b52b3-106">Modify meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="b52b3-107">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="b52b3-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="b52b3-108">打开 "Skype for Business 服务器" 控制面板。</span><span class="sxs-lookup"><span data-stu-id="b52b3-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="b52b3-109">在左侧导航栏中，单击“**会议**”，然后单击“**会议配置**”。</span><span class="sxs-lookup"><span data-stu-id="b52b3-109">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="b52b3-110">在会议配置列表中，单击要更改的配置，再单击“**编辑**”，然后单击“**显示详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="b52b3-110">In the list of meeting configurations, click the configuration that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="b52b3-111">在“**编辑会议配置**”中，修改除配置名称外的任一配置设置，配置名称不能修改。</span><span class="sxs-lookup"><span data-stu-id="b52b3-111">In **Edit Meeting Configuration**, modify any of the configuration settings, except for the configuration name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="b52b3-112">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="b52b3-112">Click **Commit**.</span></span>
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="b52b3-113">使用 Skype for Business Server 命令行管理程序修改会议配置设置</span><span class="sxs-lookup"><span data-stu-id="b52b3-113">Modify meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="b52b3-114">若要修改会议配置设置，请使用 **Set-CsMeetingConfiguration** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b52b3-114">To modify meeting configuration settings, use the **Set-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="b52b3-p101">下例所示的命令修改分配给 Redmond 站点 (-Identity site:Redmond) 的会议配置设置。在此示例中，DesignateAsPresenter 属性的值设置为 Everyone：</span><span class="sxs-lookup"><span data-stu-id="b52b3-p101">The command shown in the following example modifies the meeting configuration settings assigned to the Redmond site (-Identity site:Redmond). In this case, the value of the DesignateAsPresenter property is set to Everyone:</span></span>
  
```
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

<span data-ttu-id="b52b3-117">有关详细信息, 包括参数的完整列表, 请参阅[Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="b52b3-117">For more information, including a complete list of parameters, see [Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).</span></span>
  

