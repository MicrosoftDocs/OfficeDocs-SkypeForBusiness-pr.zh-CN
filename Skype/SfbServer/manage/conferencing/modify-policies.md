---
title: 修改业务服务器中 Skype 的会议策略
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: 摘要： 了解如何修改业务服务器中 Skype 的会议策略。
ms.openlocfilehash: 36b6cb92ddb1a6628186198906da87c5dec29532
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197791"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="e05ab-103">修改业务服务器中 Skype 的会议策略</span><span class="sxs-lookup"><span data-stu-id="e05ab-103">Modify conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="e05ab-104">**摘要：** 了解如何修改业务服务器中 Skype 的会议策略。</span><span class="sxs-lookup"><span data-stu-id="e05ab-104">**Summary:** Learn how to modify conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="e05ab-105">使用适用于业务 Server Control Panel Skype 或使用 Skype 业务 Server 命令行管理程序，您可以修改会议策略。</span><span class="sxs-lookup"><span data-stu-id="e05ab-105">You can modify conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="e05ab-106">使用适用于业务 Server Control Panel Skype 修改会议策略</span><span class="sxs-lookup"><span data-stu-id="e05ab-106">Modify conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="e05ab-107">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="e05ab-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="e05ab-108">打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="e05ab-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="e05ab-109">在左侧导航栏中，单击“**会议**”，然后单击“**会议策略**”。</span><span class="sxs-lookup"><span data-stu-id="e05ab-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="e05ab-110">在会议策略列表中，单击要更改的策略，单击“**编辑**”，然后单击“**显示详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="e05ab-110">In the list of conferencing policies, click the policy that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="e05ab-111">在“**编辑会议策略**”中，修改任意策略设置（不能修改的策略名称除外）。</span><span class="sxs-lookup"><span data-stu-id="e05ab-111">In **Edit Conferencing Policy**, modify any of the policy settings, except for the policy name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="e05ab-112">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="e05ab-112">Click **Commit**.</span></span>
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="e05ab-113">使用 Skype 业务 Server 命令行管理程序修改会议策略</span><span class="sxs-lookup"><span data-stu-id="e05ab-113">Modify conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="e05ab-114">若要修改的会议策略，请使用**Set-csconferencingpolicy** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e05ab-114">To modify conferencing policies, use the **Set-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="e05ab-115">下面的示例修改会议策略 SalesConferencingPolicy 的属性值。</span><span class="sxs-lookup"><span data-stu-id="e05ab-115">The following example modifies a property value of the conferencing policy SalesConferencingPolicy.</span></span> <span data-ttu-id="e05ab-116">该命令将 AllowConferenceRecording 属性的值设置为 False：</span><span class="sxs-lookup"><span data-stu-id="e05ab-116">The command sets the value of the AllowConferenceRecording property to False:</span></span>
  
```
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

<span data-ttu-id="e05ab-117">有关详细信息，包括完成语法和参数的列表，，请参阅[Set-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="e05ab-117">For more information, including complete syntax and a list of parameters, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

