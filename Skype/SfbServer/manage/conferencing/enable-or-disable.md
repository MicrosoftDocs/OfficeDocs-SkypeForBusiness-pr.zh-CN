---
title: 在 Skype for Business 服务器中启用或禁用电话拨入式会议
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: '摘要: 了解如何使用 "控制面板" 或 "管理外壳" 在 Skype for Business 服务器中启用或禁用电话拨入式会议。'
ms.openlocfilehash: 6723c3501b226d11977ad176a804210540f1a2bc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294255"
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="b284a-103">在 Skype for Business 服务器中启用或禁用电话拨入式会议</span><span class="sxs-lookup"><span data-stu-id="b284a-103">Enable or disable dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="b284a-104">**摘要:** 了解如何使用 "控制面板" 或 "管理外壳" 在 Skype for Business 服务器中启用或禁用拨入式会议。</span><span class="sxs-lookup"><span data-stu-id="b284a-104">**Summary:** Learn how to use Control Panel or Management Shell to enable or disable dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="b284a-105">你可以使用 Skype for Business Server 控制面板或使用 Skype for Business Server 命令行管理器启用电话拨入式会议。</span><span class="sxs-lookup"><span data-stu-id="b284a-105">You can enable dial-in conferencing by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="b284a-106">使用 Skype for Business 服务器控制面板启用或禁用电话拨入式会议</span><span class="sxs-lookup"><span data-stu-id="b284a-106">Enable or disable dial-in conferencing by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="b284a-107">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="b284a-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="b284a-108">打开 "Skype for Business 服务器" 控制面板。</span><span class="sxs-lookup"><span data-stu-id="b284a-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="b284a-109">在左侧导航栏中，单击“**会议**”，然后单击“**会议策略**”。</span><span class="sxs-lookup"><span data-stu-id="b284a-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="b284a-110">在会议策略列表中，选择要为其启用电话拨入式会议的策略，单击“**编辑**”，然后单击“**显示详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="b284a-110">In the list of conferencing policies, select the policy for which you want to enable dial-in conferencing, click **Edit**, and then click **Show details**.</span></span> 
    
5. <span data-ttu-id="b284a-p101">若要允许用户通过电话拨入加入会议，请选中“**启用 PSTN 电话拨入式会议**”复选框。默认情况下，用户可以通过使用公用电话交换网 (PSTN) 进行电话拨入来加入会议。</span><span class="sxs-lookup"><span data-stu-id="b284a-p101">To allow users to join meeting by dialing in, check the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
6. <span data-ttu-id="b284a-113">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="b284a-113">Click **Commit**.</span></span> 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="b284a-114">使用 Skype for Business Server 命令行管理程序启用或禁用电话拨入式会议</span><span class="sxs-lookup"><span data-stu-id="b284a-114">Enable or disable dial-in conferencing by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="b284a-115">若要启用或禁用电话拨入式会议，请如下使用带 EnableDialInConferencing 参数的 **Set-CsConferencingPolicy** cmdlet：</span><span class="sxs-lookup"><span data-stu-id="b284a-115">To enable or disable dial-in conferencing, use the **Set-CsConferencingPolicy** cmdlet with the EnableDialInConferencing parameter as follows:</span></span>
  
```
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

<span data-ttu-id="b284a-116">有关详细信息, 请参阅[设置 CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="b284a-116">For more information, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

