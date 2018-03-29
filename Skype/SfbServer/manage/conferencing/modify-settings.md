---
title: 在 Skype for Business Server 2015 中修改会议配置设置
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: 摘要： 了解如何修改会议在 Skype 业务服务器 2015年的配置设置。
ms.openlocfilehash: 95f28f35859553f79fc6f74f8850f224bda54deb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="12882-103">在 Skype for Business Server 2015 中修改会议配置设置</span><span class="sxs-lookup"><span data-stu-id="12882-103">Modify meeting configuration settings in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="12882-104">**摘要：**了解如何修改会议在 Skype 业务服务器 2015年的配置设置。</span><span class="sxs-lookup"><span data-stu-id="12882-104">**Summary:** Learn how to modify meeting configuration settings in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="12882-105">您可以修改会议通过 Skype 业务服务器控件面板或通过 Skype 业务服务器管理外壳程序的配置设置。</span><span class="sxs-lookup"><span data-stu-id="12882-105">You can modify meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="12882-106">修改会议通过 Skype 业务服务器控制面板配置设置</span><span class="sxs-lookup"><span data-stu-id="12882-106">Modify meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="12882-107">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="12882-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="12882-108">打开 Skype 业务服务器的控制面板。</span><span class="sxs-lookup"><span data-stu-id="12882-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="12882-109">在左侧导航栏中，单击“**会议**”，然后单击“**会议配置**”。</span><span class="sxs-lookup"><span data-stu-id="12882-109">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="12882-110">在会议配置列表中，单击要更改的配置，再单击“**编辑**”，然后单击“**显示详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="12882-110">In the list of meeting configurations, click the configuration that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="12882-111">在“**编辑会议配置**”中，修改除配置名称外的任一配置设置，配置名称不能修改。</span><span class="sxs-lookup"><span data-stu-id="12882-111">In **Edit Meeting Configuration**, modify any of the configuration settings, except for the configuration name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="12882-112">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="12882-112">Click **Commit**.</span></span>
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="12882-113">修改会议通过 Skype 业务服务器管理外壳程序的配置设置</span><span class="sxs-lookup"><span data-stu-id="12882-113">Modify meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="12882-114">若要修改会议配置设置，请使用 **Set-CsMeetingConfiguration** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="12882-114">To modify meeting configuration settings, use the **Set-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="12882-p101">下例所示的命令修改分配给 Redmond 站点 (-Identity site:Redmond) 的会议配置设置。在此示例中，DesignateAsPresenter 属性的值设置为 Everyone：</span><span class="sxs-lookup"><span data-stu-id="12882-p101">The command shown in the following example modifies the meeting configuration settings assigned to the Redmond site (-Identity site:Redmond). In this case, the value of the DesignateAsPresenter property is set to Everyone:</span></span>
  
```
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

<span data-ttu-id="12882-117">包括的参数的完整列表的详细信息，请参阅[设置 CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="12882-117">For more information, including a complete list of parameters, see [Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).</span></span>
  

