---
title: 在 Skype for Business 2015 中为用户启用呼叫寄存
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: Skype 中的呼叫寄存的用户启用业务 Server 企业语音。
ms.openlocfilehash: 88385ae1332905ae242cf0b4a5002f96b336a1af
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2018
ms.locfileid: "19500449"
---
# <a name="enable-call-park-for-users-in-skype-for-business-2015"></a><span data-ttu-id="1545d-103">在 Skype for Business 2015 中为用户启用呼叫寄存</span><span class="sxs-lookup"><span data-stu-id="1545d-103">Enable Call Park for users in Skype for Business 2015</span></span>
 
<span data-ttu-id="1545d-104">Skype 中的呼叫寄存的用户启用业务 Server 企业语音。</span><span class="sxs-lookup"><span data-stu-id="1545d-104">Enable users for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="1545d-105">默认情况下，对所有用户禁用呼叫寄存。</span><span class="sxs-lookup"><span data-stu-id="1545d-105">By default, Call Park is disabled for all users.</span></span> <span data-ttu-id="1545d-106">用户无法寄存呼叫或取回寄存的呼叫，将在语音策略中启用呼叫寄存后。</span><span class="sxs-lookup"><span data-stu-id="1545d-106">Users cannot park calls or retrieve parked calls until they are enabled for Call Park in voice policy.</span></span>
  
<span data-ttu-id="1545d-107">您可以启用呼叫寄存在全局范围，或在 site 作用域或用户作用域。</span><span class="sxs-lookup"><span data-stu-id="1545d-107">You can enable Call Park at the global scope, or at the site scope or user scope.</span></span> <span data-ttu-id="1545d-108">用户作用域优先于站点作用域，而站点作用域又优先于全局作用域。</span><span class="sxs-lookup"><span data-stu-id="1545d-108">User scope takes precedence over site scope, and site scope takes precedence over global scope.</span></span> <span data-ttu-id="1545d-109">如果您有多个语音策略，请查看所有策略，以便启用呼叫寄存，而不仅仅是全局策略。</span><span class="sxs-lookup"><span data-stu-id="1545d-109">If you have multiple voice policies, review all the policies to enable Call Park, not just the global policy.</span></span>
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a><span data-ttu-id="1545d-110">若要为用户启用呼叫寄存的业务 Server Control Panel 使用 Skype</span><span class="sxs-lookup"><span data-stu-id="1545d-110">To Use Skype for Business Server Control Panel to Enable Call Park for Users</span></span>

1. <span data-ttu-id="1545d-111">以 **RTCUniversalServerAdmins** 组成员或者 **CsVoiceAdministrator**、**CsServerAdministrator** 或 **CsAdministrator** 管理角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="1545d-111">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="1545d-112">打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="1545d-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="1545d-113">在左侧导航栏中，单击“语音路由”****。</span><span class="sxs-lookup"><span data-stu-id="1545d-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="1545d-114">单击“语音策略”**** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="1545d-114">Click the **Voice Policy** tab.</span></span>
    
5. <span data-ttu-id="1545d-115">双击现有语音策略以打开“编辑语音策略”**** 对话框。</span><span class="sxs-lookup"><span data-stu-id="1545d-115">Double-click an existing voice policy to open the **Edit Voice Policy** dialog box.</span></span>
    
6. <span data-ttu-id="1545d-116">在“呼叫功能”**** 下，选择“启用呼叫寄存”****。</span><span class="sxs-lookup"><span data-stu-id="1545d-116">Under **Calling features**, select **Enable call park**.</span></span>
    
7. <span data-ttu-id="1545d-117">单击“确定”**** 保存语音策略。</span><span class="sxs-lookup"><span data-stu-id="1545d-117">Click **OK** to save the voice policy</span></span>
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a><span data-ttu-id="1545d-118">为用户启用呼叫寄存使用 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="1545d-118">To Use Cmdlets to Enable Call Park for Users</span></span>

1. <span data-ttu-id="1545d-119">以 RTCUniversalServerAdmins 组成员或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 管理角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="1545d-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="1545d-120">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="1545d-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="1545d-121">运行：</span><span class="sxs-lookup"><span data-stu-id="1545d-121">Run:</span></span>
    
   ```
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    <span data-ttu-id="1545d-122">例如，若要为默认全局语音策略启用呼叫寄存：</span><span class="sxs-lookup"><span data-stu-id="1545d-122">For example, to enable Call Park for the default global voice policy:</span></span>
    
   ```
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a><span data-ttu-id="1545d-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1545d-123">See also</span></span>

[<span data-ttu-id="1545d-124">创建或修改语音策略和配置 PSTN 用法记录中的业务 2015 Skype</span><span class="sxs-lookup"><span data-stu-id="1545d-124">Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015</span></span>](voice-policy-and-pstn-usage-records.md)