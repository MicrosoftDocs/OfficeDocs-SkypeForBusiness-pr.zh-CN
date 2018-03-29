---
title: 在 Skype for Business 2015 中为用户启用呼叫寄存
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: 启用业务服务器企业语音调用公园在 Skype 的用户。
ms.openlocfilehash: 3af13e59541799a75c58f6e796bf07e7a978065e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="enable-call-park-for-users-in-skype-for-business-2015"></a><span data-ttu-id="73c5e-103">在 Skype for Business 2015 中为用户启用呼叫寄存</span><span class="sxs-lookup"><span data-stu-id="73c5e-103">Enable Call Park for users in Skype for Business 2015</span></span>
 
<span data-ttu-id="73c5e-104">启用业务服务器企业语音调用公园在 Skype 的用户。</span><span class="sxs-lookup"><span data-stu-id="73c5e-104">Enable users for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="73c5e-105">默认情况下，对所有用户禁用调用公园。</span><span class="sxs-lookup"><span data-stu-id="73c5e-105">By default, Call Park is disabled for all users.</span></span> <span data-ttu-id="73c5e-106">用户不能停放调用或检索暂停的调用直到它们对于调用公园在中启用了语音策略。</span><span class="sxs-lookup"><span data-stu-id="73c5e-106">Users cannot park calls or retrieve parked calls until they are enabled for Call Park in voice policy.</span></span>
  
<span data-ttu-id="73c5e-107">您可以启用呼叫公园在全局范围中，或者在站点范围或用户范围。</span><span class="sxs-lookup"><span data-stu-id="73c5e-107">You can enable Call Park at the global scope, or at the site scope or user scope.</span></span> <span data-ttu-id="73c5e-108">用户作用域优先于站点作用域，而站点作用域又优先于全局作用域。</span><span class="sxs-lookup"><span data-stu-id="73c5e-108">User scope takes precedence over site scope, and site scope takes precedence over global scope.</span></span> <span data-ttu-id="73c5e-109">如果您有多个语音策略，查看启用呼叫公园，不只是全球政策的所有策略。</span><span class="sxs-lookup"><span data-stu-id="73c5e-109">If you have multiple voice policies, review all the policies to enable Call Park, not just the global policy.</span></span>
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a><span data-ttu-id="73c5e-110">要对用户的业务服务器控制面板来启用调用公园使用 Skype</span><span class="sxs-lookup"><span data-stu-id="73c5e-110">To Use Skype for Business Server Control Panel to Enable Call Park for Users</span></span>

1. <span data-ttu-id="73c5e-111">以 **RTCUniversalServerAdmins** 组成员或者 **CsVoiceAdministrator**、**CsServerAdministrator** 或 **CsAdministrator** 管理角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="73c5e-111">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="73c5e-112">打开 Skype 业务服务器的控制面板。</span><span class="sxs-lookup"><span data-stu-id="73c5e-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="73c5e-113">在左侧导航栏中，单击“语音路由”****。</span><span class="sxs-lookup"><span data-stu-id="73c5e-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="73c5e-114">单击“语音策略”****选项卡。</span><span class="sxs-lookup"><span data-stu-id="73c5e-114">Click the **Voice Policy** tab.</span></span>
    
5. <span data-ttu-id="73c5e-115">双击现有语音策略以打开“编辑语音策略”****对话框。</span><span class="sxs-lookup"><span data-stu-id="73c5e-115">Double-click an existing voice policy to open the **Edit Voice Policy** dialog box.</span></span>
    
6. <span data-ttu-id="73c5e-116">在“呼叫功能”****下，选择“启用呼叫寄存”****。</span><span class="sxs-lookup"><span data-stu-id="73c5e-116">Under **Calling features**, select **Enable call park**.</span></span>
    
7. <span data-ttu-id="73c5e-117">单击“确定”****保存语音策略。</span><span class="sxs-lookup"><span data-stu-id="73c5e-117">Click **OK** to save the voice policy</span></span>
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a><span data-ttu-id="73c5e-118">若要使用 Cmdlet 以便挂断电话的用户</span><span class="sxs-lookup"><span data-stu-id="73c5e-118">To Use Cmdlets to Enable Call Park for Users</span></span>

1. <span data-ttu-id="73c5e-119">以 RTCUniversalServerAdmins 组成员或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 管理角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="73c5e-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="73c5e-120">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="73c5e-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="73c5e-121">运行：</span><span class="sxs-lookup"><span data-stu-id="73c5e-121">Run:</span></span>
    
   ```
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    <span data-ttu-id="73c5e-122">例如，若要启用默认全局语音策略调用公园：</span><span class="sxs-lookup"><span data-stu-id="73c5e-122">For example, to enable Call Park for the default global voice policy:</span></span>
    
   ```
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a><span data-ttu-id="73c5e-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="73c5e-123">See also</span></span>

#### 

[<span data-ttu-id="73c5e-124">创建或修改语音策略和业务 2015年的 Skype 在配置 PSTN 使用记录</span><span class="sxs-lookup"><span data-stu-id="73c5e-124">Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015</span></span>](voice-policy-and-pstn-usage-records.md)

