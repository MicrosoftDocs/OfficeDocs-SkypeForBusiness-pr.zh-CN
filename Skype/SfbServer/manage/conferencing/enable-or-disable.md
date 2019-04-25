---
title: 启用或禁用业务服务器中 Skype 电话拨入式会议
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: 摘要： 了解如何使用控制面板或命令行管理程序启用或禁用业务服务器中 Skype 电话拨入式会议。
ms.openlocfilehash: 216973e8d3a887dcae308fc5efa6d67b2415493b
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222826"
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="3f6f1-103">启用或禁用业务服务器中 Skype 电话拨入式会议</span><span class="sxs-lookup"><span data-stu-id="3f6f1-103">Enable or disable dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="3f6f1-104">**摘要：** 了解如何使用控制面板或命令行管理程序启用或禁用业务服务器中 Skype 电话拨入式会议。</span><span class="sxs-lookup"><span data-stu-id="3f6f1-104">**Summary:** Learn how to use Control Panel or Management Shell to enable or disable dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="3f6f1-105">使用适用于业务 Server Control Panel Skype 或使用 Skype 业务 Server 命令行管理程序，您可以启用电话拨入式会议。</span><span class="sxs-lookup"><span data-stu-id="3f6f1-105">You can enable dial-in conferencing by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="3f6f1-106">启用或禁用使用适用于业务 Server Control Panel Skype 的电话拨入式会议</span><span class="sxs-lookup"><span data-stu-id="3f6f1-106">Enable or disable dial-in conferencing by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="3f6f1-107">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="3f6f1-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="3f6f1-108">打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="3f6f1-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="3f6f1-109">在左侧导航栏中，单击“**会议**”，然后单击“**会议策略**”。</span><span class="sxs-lookup"><span data-stu-id="3f6f1-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="3f6f1-110">在会议策略列表中，选择要为其启用电话拨入式会议的策略，单击“**编辑**”，然后单击“**显示详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="3f6f1-110">In the list of conferencing policies, select the policy for which you want to enable dial-in conferencing, click **Edit**, and then click **Show details**.</span></span> 
    
5. <span data-ttu-id="3f6f1-p101">若要允许用户通过电话拨入加入会议，请选中“**启用 PSTN 电话拨入式会议**”复选框。默认情况下，用户可以通过使用公用电话交换网 (PSTN) 进行电话拨入来加入会议。</span><span class="sxs-lookup"><span data-stu-id="3f6f1-p101">To allow users to join meeting by dialing in, check the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
6. <span data-ttu-id="3f6f1-113">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="3f6f1-113">Click **Commit**.</span></span> 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="3f6f1-114">启用或禁用使用 Skype 业务 Server Management Shell 的电话拨入式会议</span><span class="sxs-lookup"><span data-stu-id="3f6f1-114">Enable or disable dial-in conferencing by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="3f6f1-115">若要启用或禁用电话拨入式会议，请如下使用带 EnableDialInConferencing 参数的 **Set-CsConferencingPolicy** cmdlet：</span><span class="sxs-lookup"><span data-stu-id="3f6f1-115">To enable or disable dial-in conferencing, use the **Set-CsConferencingPolicy** cmdlet with the EnableDialInConferencing parameter as follows:</span></span>
  
```
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

<span data-ttu-id="3f6f1-116">有关详细信息，请参阅[Set-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="3f6f1-116">For more information, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

