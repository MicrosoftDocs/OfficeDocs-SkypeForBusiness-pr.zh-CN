---
title: 在 Skype for Business Server 2015 中修改会议策略
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: 摘要： 了解如何修改业务服务器 2015 Skype 会议策略。
ms.openlocfilehash: b0456db5d0c6131b3b3999a87fc824d6ee3b4b30
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="modify-conferencing-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="2ef60-103">在 Skype for Business Server 2015 中修改会议策略</span><span class="sxs-lookup"><span data-stu-id="2ef60-103">Modify conferencing policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2ef60-104">**摘要：**了解如何修改业务服务器 2015 Skype 会议策略。</span><span class="sxs-lookup"><span data-stu-id="2ef60-104">**Summary:** Learn how to modify conferencing policies in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="2ef60-105">通过 Skype 业务服务器控件面板或通过 Skype 业务服务器管理外壳，您可以修改会议策略。</span><span class="sxs-lookup"><span data-stu-id="2ef60-105">You can modify conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="2ef60-106">通过 Skype 业务服务器控件面板中修改会议策略</span><span class="sxs-lookup"><span data-stu-id="2ef60-106">Modify conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="2ef60-107">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="2ef60-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="2ef60-108">打开 Skype 业务服务器的控制面板。</span><span class="sxs-lookup"><span data-stu-id="2ef60-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="2ef60-109">在左侧导航栏中，单击“**会议**”，然后单击“**会议策略**”。</span><span class="sxs-lookup"><span data-stu-id="2ef60-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="2ef60-110">在会议策略列表中，单击要更改的策略，单击“**编辑**”，然后单击“**显示详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="2ef60-110">In the list of conferencing policies, click the policy that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="2ef60-111">在“**编辑会议策略**”中，修改任意策略设置（不能修改的策略名称除外）。</span><span class="sxs-lookup"><span data-stu-id="2ef60-111">In **Edit Conferencing Policy**, modify any of the policy settings, except for the policy name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="2ef60-112">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="2ef60-112">Click **Commit**.</span></span>
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="2ef60-113">通过 Skype 业务服务器管理外壳程序修改会议策略</span><span class="sxs-lookup"><span data-stu-id="2ef60-113">Modify conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="2ef60-114">若要修改会议策略，使用**一组 CsConferencingPolicy** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2ef60-114">To modify conferencing policies, use the **Set-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="2ef60-115">下面的示例修改会议策略 SalesConferencingPolicy 的属性值。</span><span class="sxs-lookup"><span data-stu-id="2ef60-115">The following example modifies a property value of the conferencing policy SalesConferencingPolicy.</span></span> <span data-ttu-id="2ef60-116">该命令将 AllowConferenceRecording 属性的值设置为 False：</span><span class="sxs-lookup"><span data-stu-id="2ef60-116">The command sets the value of the AllowConferenceRecording property to False:</span></span>
  
```
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

<span data-ttu-id="2ef60-117">包括完整语法和参数的列表的详细信息，请参阅[设置 CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="2ef60-117">For more information, including complete syntax and a list of parameters, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

