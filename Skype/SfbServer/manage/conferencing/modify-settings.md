---
title: 修改 Skype for Business Server 中的会议配置设置
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
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: 摘要：了解如何在 Skype for Business Server 中修改会议配置设置。
ms.openlocfilehash: 2f0d1220312ac810d26fdd4691492133e54db9b6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119411"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="d8d7e-103">修改 Skype for Business Server 中的会议配置设置</span><span class="sxs-lookup"><span data-stu-id="d8d7e-103">Modify meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="d8d7e-104">**摘要：** 了解如何在 Skype for Business Server 中修改会议配置设置。</span><span class="sxs-lookup"><span data-stu-id="d8d7e-104">**Summary:** Learn how to modify meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="d8d7e-105">可以使用 Skype for Business Server 控制面板或 Skype for Business Server 命令行管理程序修改会议配置设置。</span><span class="sxs-lookup"><span data-stu-id="d8d7e-105">You can modify meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="d8d7e-106">使用 Skype for Business Server 控制面板修改会议配置设置</span><span class="sxs-lookup"><span data-stu-id="d8d7e-106">Modify meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="d8d7e-107">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="d8d7e-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="d8d7e-108">打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="d8d7e-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="d8d7e-109">在左侧导航栏中，单击 **"会议"，** 然后单击"会议 **配置"。**</span><span class="sxs-lookup"><span data-stu-id="d8d7e-109">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="d8d7e-110">在会议配置列表中，单击要更改的配置，再单击"编辑"，然后单击"显示 **详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="d8d7e-110">In the list of meeting configurations, click the configuration that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="d8d7e-111">在 **"编辑会议配置**"中，修改任何配置设置，但配置名称除外，不能修改配置名称。</span><span class="sxs-lookup"><span data-stu-id="d8d7e-111">In **Edit Meeting Configuration**, modify any of the configuration settings, except for the configuration name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="d8d7e-112">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="d8d7e-112">Click **Commit**.</span></span>
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="d8d7e-113">使用 Skype for Business Server 命令行管理程序修改会议配置设置</span><span class="sxs-lookup"><span data-stu-id="d8d7e-113">Modify meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="d8d7e-114">若要修改会议配置设置，请使用 **Set-CsMeetingConfiguration** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d8d7e-114">To modify meeting configuration settings, use the **Set-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="d8d7e-115">以下示例中显示的命令修改分配给 Redmond 站点 (-Identity site：Redmond) 。</span><span class="sxs-lookup"><span data-stu-id="d8d7e-115">The command shown in the following example modifies the meeting configuration settings assigned to the Redmond site (-Identity site:Redmond).</span></span> <span data-ttu-id="d8d7e-116">在这种情况下，DesignateAsPresenter 属性的值设置为 Everyone：</span><span class="sxs-lookup"><span data-stu-id="d8d7e-116">In this case, the value of the DesignateAsPresenter property is set to Everyone:</span></span>
  
```PowerShell
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

<span data-ttu-id="d8d7e-117">有关详细信息，包括参数的完整列表，请参阅[Set-CsMeetingConfiguration。](/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="d8d7e-117">For more information, including a complete list of parameters, see [Set-CsMeetingConfiguration](/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).</span></span>
