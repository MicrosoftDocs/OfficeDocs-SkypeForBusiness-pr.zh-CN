---
title: 在 Skype for Business 中为用户启用呼叫等待
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: 在 Skype for Business Server 服务中为用户启用呼叫企业语音。
ms.openlocfilehash: e9bbc42f5940af0cfc94ab83eae981dd023c9fcd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830952"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a><span data-ttu-id="fa8bf-103">在 Skype for Business 中为用户启用呼叫等待</span><span class="sxs-lookup"><span data-stu-id="fa8bf-103">Enable Call Park for users in Skype for Business</span></span>
 
<span data-ttu-id="fa8bf-104">在 Skype for Business Server 服务中为用户启用呼叫企业语音。</span><span class="sxs-lookup"><span data-stu-id="fa8bf-104">Enable users for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="fa8bf-105">默认情况下，为所有用户禁用呼叫等待。</span><span class="sxs-lookup"><span data-stu-id="fa8bf-105">By default, Call Park is disabled for all users.</span></span> <span data-ttu-id="fa8bf-106">在语音策略中为呼叫等待启用之前，用户无法呼叫或取回已呼叫。</span><span class="sxs-lookup"><span data-stu-id="fa8bf-106">Users cannot park calls or retrieve parked calls until they are enabled for Call Park in voice policy.</span></span>
  
<span data-ttu-id="fa8bf-107">可以在全局范围、站点范围或用户范围启用呼叫。</span><span class="sxs-lookup"><span data-stu-id="fa8bf-107">You can enable Call Park at the global scope, or at the site scope or user scope.</span></span> <span data-ttu-id="fa8bf-108">用户作用域优先于站点范围，站点作用域优先于全局范围。</span><span class="sxs-lookup"><span data-stu-id="fa8bf-108">User scope takes precedence over site scope, and site scope takes precedence over global scope.</span></span> <span data-ttu-id="fa8bf-109">如果你有多个语音策略，请查看所有策略以启用呼叫管理，而不只是全局策略。</span><span class="sxs-lookup"><span data-stu-id="fa8bf-109">If you have multiple voice policies, review all the policies to enable Call Park, not just the global policy.</span></span>
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a><span data-ttu-id="fa8bf-110">使用 Skype for Business Server 控制面板为用户启用呼叫等待</span><span class="sxs-lookup"><span data-stu-id="fa8bf-110">To Use Skype for Business Server Control Panel to Enable Call Park for Users</span></span>

1. <span data-ttu-id="fa8bf-111">以 **RTCUniversalServerAdmins** 组的成员或 **CsVoiceAdministrator、CsServerAdministrator** 或 **CsAdministrator** 管理角色 的成员登录到计算机。 </span><span class="sxs-lookup"><span data-stu-id="fa8bf-111">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="fa8bf-112">打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="fa8bf-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="fa8bf-113">在左侧导航栏中，单击 **“语音路由”**。</span><span class="sxs-lookup"><span data-stu-id="fa8bf-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="fa8bf-114">单击 **"语音策略"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="fa8bf-114">Click the **Voice Policy** tab.</span></span>
    
5. <span data-ttu-id="fa8bf-115">双击现有语音策略以打开 **"编辑语音策略"** 对话框。</span><span class="sxs-lookup"><span data-stu-id="fa8bf-115">Double-click an existing voice policy to open the **Edit Voice Policy** dialog box.</span></span>
    
6. <span data-ttu-id="fa8bf-116">在 **"呼叫功能**"下，**选择"启用呼叫允许"。**</span><span class="sxs-lookup"><span data-stu-id="fa8bf-116">Under **Calling features**, select **Enable call park**.</span></span>
    
7. <span data-ttu-id="fa8bf-117">单击 **"** 确定"保存语音策略</span><span class="sxs-lookup"><span data-stu-id="fa8bf-117">Click **OK** to save the voice policy</span></span>
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a><span data-ttu-id="fa8bf-118">使用 Cmdlet 为用户启用呼叫等待</span><span class="sxs-lookup"><span data-stu-id="fa8bf-118">To Use Cmdlets to Enable Call Park for Users</span></span>

1. <span data-ttu-id="fa8bf-119">以 RTCUniversalServerAdmins 组成员或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 管理角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="fa8bf-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="fa8bf-120">启动 Skype for Business Server命令行管理程序：单击"开始"，**单击"所有** 程序"，再单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="fa8bf-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="fa8bf-121">运行：</span><span class="sxs-lookup"><span data-stu-id="fa8bf-121">Run:</span></span>
    
   ```powershell
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    <span data-ttu-id="fa8bf-122">例如，若要为默认全局语音策略启用呼叫等待：</span><span class="sxs-lookup"><span data-stu-id="fa8bf-122">For example, to enable Call Park for the default global voice policy:</span></span>
    
   ```powershell
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a><span data-ttu-id="fa8bf-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fa8bf-123">See also</span></span>



[<span data-ttu-id="fa8bf-124">在 Skype for Business 中创建或修改语音策略和配置 PSTN 用法记录</span><span class="sxs-lookup"><span data-stu-id="fa8bf-124">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)

