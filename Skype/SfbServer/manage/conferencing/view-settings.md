---
title: 查看 Skype for Business 服务器中的会议配置设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: 摘要：了解如何在 Skype for Business Server 中查看会议配置设置。
ms.openlocfilehash: 858d1a3d786cb9fe3c6b33daaca8667cab2390f8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818453"
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="2ce8e-103">查看 Skype for Business 服务器中的会议配置设置</span><span class="sxs-lookup"><span data-stu-id="2ce8e-103">View meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="2ce8e-104">**摘要：** 了解如何在 Skype for Business Server 中查看会议配置设置。</span><span class="sxs-lookup"><span data-stu-id="2ce8e-104">**Summary:** Learn how to view meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="2ce8e-105">可以使用 Skype for Business Server 控制面板或使用 Skype for business Server 命令行管理器查看会议配置设置。</span><span class="sxs-lookup"><span data-stu-id="2ce8e-105">You can view meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="2ce8e-106">使用 Skype for Business 服务器控制面板查看会议配置设置</span><span class="sxs-lookup"><span data-stu-id="2ce8e-106">View meeting configuration settings by using Skype for Business Server Control Panel</span></span>
<span data-ttu-id="2ce8e-107"><a name="BKMK_ViewJoinSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="2ce8e-107"><a name="BKMK_ViewJoinSettings"> </a></span></span>

1. <span data-ttu-id="2ce8e-108">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="2ce8e-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="2ce8e-109">打开 "Skype for Business 服务器" 控制面板。</span><span class="sxs-lookup"><span data-stu-id="2ce8e-109">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="2ce8e-110">在左侧导航栏中，单击“**会议**”，然后单击“**会议配置**”。</span><span class="sxs-lookup"><span data-stu-id="2ce8e-110">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="2ce8e-111">在“**会议配置**”页上，单击要查看的会议配置。</span><span class="sxs-lookup"><span data-stu-id="2ce8e-111">On the **Meeting Configuration** page, click the meeting configuration that you would like to view.</span></span>
    
5. <span data-ttu-id="2ce8e-112">在“**编辑文件筛选器**”中，选中“**显示详细信息**”复选框。</span><span class="sxs-lookup"><span data-stu-id="2ce8e-112">In **Edit File Filter**, select the **Show Details** check box.</span></span>
    
    <span data-ttu-id="2ce8e-113">\*\*编辑会议配置- \<策略\> \*\*将打开，显示所选策略的设置。</span><span class="sxs-lookup"><span data-stu-id="2ce8e-113">**Edit Meeting Configuration - \<policy\>** opens displaying the settings for the selected policy.</span></span>
    
    <span data-ttu-id="2ce8e-114">有关配置设置的详细信息，请参阅[在 Skype For Business 服务器中创建会议配置设置](create-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="2ce8e-114">For details about configuring the settings, see [Create meeting configuration settings in Skype for Business Server](create-settings.md).</span></span>
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="2ce8e-115">使用 Skype for Business Server Management Shell 查看会议配置设置</span><span class="sxs-lookup"><span data-stu-id="2ce8e-115">View meeting configuration settings by using Skype for Business Server Management Shell</span></span>
<span data-ttu-id="2ce8e-116"><a name="BKMK_ViewJoinSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="2ce8e-116"><a name="BKMK_ViewJoinSettings"> </a></span></span>

<span data-ttu-id="2ce8e-117">若要查看有关所有会议配置设置的信息，可使用 **Get-CsMeetingConfiguration** cmdlet：</span><span class="sxs-lookup"><span data-stu-id="2ce8e-117">To view information about all your meeting configuration settings, use the **Get-CsMeetingConfiguration** cmdlet:</span></span>
  
```
Get-CsMeetingConfiguration
```

<span data-ttu-id="2ce8e-118">此命令会返回类似下面的信息：</span><span class="sxs-lookup"><span data-stu-id="2ce8e-118">This command will return information similar to the following:</span></span>
  
<pre>
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
</pre>

<span data-ttu-id="2ce8e-119">有关详细信息，包括参数的完整列表，请参阅[CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="2ce8e-119">For more information, including a complete list of parameters, see [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).</span></span>
  

