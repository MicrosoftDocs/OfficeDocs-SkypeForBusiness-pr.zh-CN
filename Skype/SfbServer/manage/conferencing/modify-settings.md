---
title: 修改会议配置设置中 Skype 业务服务器
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: 摘要： 了解如何修改会议配置设置中 Skype 业务服务器。
ms.openlocfilehash: b4b8307711fcf7b120c867debe5ab3e2978f6ef7
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20978965"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="ca46b-103">修改会议配置设置中 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="ca46b-103">Modify meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="ca46b-104">**摘要：** 了解如何修改会议配置设置中 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="ca46b-104">**Summary:** Learn how to modify meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="ca46b-105">您可以修改会议配置设置，使用的业务 Server Control Panel Skype 或使用 Skype 业务 Server Management Shell。</span><span class="sxs-lookup"><span data-stu-id="ca46b-105">You can modify meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="ca46b-106">修改使用适用于业务 Server Control Panel Skype 会议配置设置</span><span class="sxs-lookup"><span data-stu-id="ca46b-106">Modify meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="ca46b-107">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="ca46b-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="ca46b-108">打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="ca46b-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="ca46b-109">在左侧导航栏中，单击“**会议**”，然后单击“**会议配置**”。</span><span class="sxs-lookup"><span data-stu-id="ca46b-109">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="ca46b-110">在会议配置列表中，单击要更改的配置，再单击“**编辑**”，然后单击“**显示详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="ca46b-110">In the list of meeting configurations, click the configuration that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="ca46b-111">在“**编辑会议配置**”中，修改除配置名称外的任一配置设置，配置名称不能修改。</span><span class="sxs-lookup"><span data-stu-id="ca46b-111">In **Edit Meeting Configuration**, modify any of the configuration settings, except for the configuration name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="ca46b-112">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="ca46b-112">Click **Commit**.</span></span>
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="ca46b-113">修改会议使用 Skype 业务 Server 命令行管理程序配置设置</span><span class="sxs-lookup"><span data-stu-id="ca46b-113">Modify meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="ca46b-114">若要修改会议配置设置，请使用 **Set-CsMeetingConfiguration** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ca46b-114">To modify meeting configuration settings, use the **Set-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="ca46b-p101">下例所示的命令修改分配给 Redmond 站点 (-Identity site:Redmond) 的会议配置设置。在此示例中，DesignateAsPresenter 属性的值设置为 Everyone：</span><span class="sxs-lookup"><span data-stu-id="ca46b-p101">The command shown in the following example modifies the meeting configuration settings assigned to the Redmond site (-Identity site:Redmond). In this case, the value of the DesignateAsPresenter property is set to Everyone:</span></span>
  
```
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

<span data-ttu-id="ca46b-117">有关详细信息，包括完成参数的列表，请参阅[Set-csmeetingconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="ca46b-117">For more information, including a complete list of parameters, see [Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).</span></span>
  

