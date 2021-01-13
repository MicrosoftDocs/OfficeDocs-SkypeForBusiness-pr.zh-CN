---
title: 修改 Skype for Business Server 中的会议策略
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
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: 摘要：了解如何在 Skype for Business Server 中修改会议策略。
ms.openlocfilehash: eafeb56dd9b0c36afffab07830a9efb71bde18fe
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828002"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="48386-103">修改 Skype for Business Server 中的会议策略</span><span class="sxs-lookup"><span data-stu-id="48386-103">Modify conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="48386-104">**摘要：** 了解如何在 Skype for Business Server 中修改会议策略。</span><span class="sxs-lookup"><span data-stu-id="48386-104">**Summary:** Learn how to modify conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="48386-105">可以使用 Skype for Business Server 控制面板或 Skype for Business Server 命令行管理程序修改会议策略。</span><span class="sxs-lookup"><span data-stu-id="48386-105">You can modify conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="48386-106">使用 Skype for Business Server 控制面板修改会议策略</span><span class="sxs-lookup"><span data-stu-id="48386-106">Modify conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="48386-107">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="48386-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="48386-108">打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="48386-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="48386-109">在左侧导航栏中，单击 **"会议"，** 然后单击 **"会议策略"。**</span><span class="sxs-lookup"><span data-stu-id="48386-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="48386-110">在会议策略列表中，单击要更改的策略，单击“编辑”，然后单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="48386-110">In the list of conferencing policies, click the policy that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="48386-111">在“编辑会议策略”中，修改任意策略设置（不能修改的策略名称除外）。</span><span class="sxs-lookup"><span data-stu-id="48386-111">In **Edit Conferencing Policy**, modify any of the policy settings, except for the policy name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="48386-112">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="48386-112">Click **Commit**.</span></span>
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="48386-113">使用 Skype for Business Server 命令行管理程序修改会议策略</span><span class="sxs-lookup"><span data-stu-id="48386-113">Modify conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="48386-114">若要修改会议策略，请使用 **Set-CsConferencingPolicy** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="48386-114">To modify conferencing policies, use the **Set-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="48386-115">以下示例修改会议策略 SalesConferencingPolicy 的属性值。</span><span class="sxs-lookup"><span data-stu-id="48386-115">The following example modifies a property value of the conferencing policy SalesConferencingPolicy.</span></span> <span data-ttu-id="48386-116">此命令将 AllowConferenceRecording 属性的值设置为 False：</span><span class="sxs-lookup"><span data-stu-id="48386-116">The command sets the value of the AllowConferenceRecording property to False:</span></span>
  
```PowerShell
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

<span data-ttu-id="48386-117">有关详细信息，包括完整语法和参数列表，请参阅 [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="48386-117">For more information, including complete syntax and a list of parameters, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

