---
title: 在 Skype for Business Server 2015 中查看会议配置设置
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: 摘要： 了解如何查看会议在 Skype 业务服务器 2015年的配置设置。
ms.openlocfilehash: 382e50a0f41301953f4313c5019d1eb0d27804e5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="5852f-103">在 Skype for Business Server 2015 中查看会议配置设置</span><span class="sxs-lookup"><span data-stu-id="5852f-103">View meeting configuration settings in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5852f-104">**摘要：**了解如何查看会议在 Skype 业务服务器 2015年的配置设置。</span><span class="sxs-lookup"><span data-stu-id="5852f-104">**Summary:** Learn how to view meeting configuration settings in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="5852f-105">您可以查看会议通过 Skype 业务服务器控件面板或通过 Skype 业务服务器管理外壳程序的配置设置。</span><span class="sxs-lookup"><span data-stu-id="5852f-105">You can view meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="5852f-106">查看会议通过 Skype 业务服务器控制面板配置设置</span><span class="sxs-lookup"><span data-stu-id="5852f-106">View meeting configuration settings by using Skype for Business Server Control Panel</span></span>
<span data-ttu-id="5852f-107"><a name="BKMK_ViewJoinSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="5852f-107"></span></span>

1. <span data-ttu-id="5852f-108">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="5852f-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="5852f-109">打开 Skype 业务服务器的控制面板。</span><span class="sxs-lookup"><span data-stu-id="5852f-109">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="5852f-110">在左侧导航栏中，单击“**会议**”，然后单击“**会议配置**”。</span><span class="sxs-lookup"><span data-stu-id="5852f-110">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="5852f-111">在“**会议配置**”页上，单击要查看的会议配置。</span><span class="sxs-lookup"><span data-stu-id="5852f-111">On the **Meeting Configuration** page, click the meeting configuration that you would like to view.</span></span>
    
5. <span data-ttu-id="5852f-112">在“**编辑文件筛选器**”中，选中“**显示详细信息**”复选框。</span><span class="sxs-lookup"><span data-stu-id="5852f-112">In **Edit File Filter**, select the **Show Details** check box.</span></span>
    
    <span data-ttu-id="5852f-113">**编辑会议配置-\<策略\>**将打开并显示所选策略的设置。</span><span class="sxs-lookup"><span data-stu-id="5852f-113">**Edit Meeting Configuration - \<policy\>** opens displaying the settings for the selected policy.</span></span>
    
    <span data-ttu-id="5852f-114">有关配置设置的详细信息，请参阅[创建会议中业务服务器 2015年的 Skype 的配置设置](create-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="5852f-114">For details about configuring the settings, see [Create meeting configuration settings in Skype for Business Server 2015](create-settings.md).</span></span>
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="5852f-115">查看会议通过 Skype 业务服务器管理外壳程序的配置设置</span><span class="sxs-lookup"><span data-stu-id="5852f-115">View meeting configuration settings by using Skype for Business Server Management Shell</span></span>
<span data-ttu-id="5852f-116"><a name="BKMK_ViewJoinSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="5852f-116"></span></span>

<span data-ttu-id="5852f-117">若要查看有关所有会议配置设置的信息，可使用 **Get-CsMeetingConfiguration** cmdlet：</span><span class="sxs-lookup"><span data-stu-id="5852f-117">To view information about all your meeting configuration settings, use the **Get-CsMeetingConfiguration** cmdlet:</span></span>
  
```
Get-CsMeetingConfiguration
```

<span data-ttu-id="5852f-118">此命令会返回类似下面的信息：</span><span class="sxs-lookup"><span data-stu-id="5852f-118">This command will return information similar to the following:</span></span>
  
```
Identity                        : Global
PstnCallersBypassLobby          : True
EnableAssignedConferenceType    : True
DesignateAsPresenter            : Company
AssignedConferenceTypeByDefault : True
AdmitAnonymousUsersByDefault    : True
RequireRoomSystemsAuthorization : False
LogoURL                         :
LegalURL                        :
HelpURL                         :
CustomFooterText                :
AllowConferenceRecording        : True

```

<span data-ttu-id="5852f-119">有关详细信息，包括参数的完整列表，请参见[获取 CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="5852f-119">For more information, including a complete list of parameters, see [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).</span></span>
  

