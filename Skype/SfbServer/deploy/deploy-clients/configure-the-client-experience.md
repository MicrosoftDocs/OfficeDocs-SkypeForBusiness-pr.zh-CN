---
title: 使用 Skype for Business 2015 配置客户端体验
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
ms.assetid: 66867a96-ff00-497d-889c-2e908cc384ce
description: 摘要：阅读本主题，了解如何为 Skype for Business 用户配置客户端体验。
ms.openlocfilehash: 1816ff9af6c8c6e28ca72420f843d224587b2c70
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096006"
---
# <a name="configure-the-client-experience-with-skype-for-business-2015"></a><span data-ttu-id="b2cba-103">使用 Skype for Business 2015 配置客户端体验</span><span class="sxs-lookup"><span data-stu-id="b2cba-103">Configure the client experience with Skype for Business 2015</span></span>
 
<span data-ttu-id="b2cba-104">**摘要：** 阅读本主题，了解如何为 Skype for Business 2015 用户配置客户端体验。</span><span class="sxs-lookup"><span data-stu-id="b2cba-104">**Summary:** Read this topic to learn how to configure the client experience for Skype for Business 2015 users.</span></span>
  
<span data-ttu-id="b2cba-105">Skype for Business 2015 提供基于 Skype 消费者产品体验的新用户体验。</span><span class="sxs-lookup"><span data-stu-id="b2cba-105">Skype for Business 2015 provides a new user experience that is based on the Skype consumer product experience.</span></span> <span data-ttu-id="b2cba-106">除了 Lync 的所有功能外，Skype for Business 还提供了新功能，并提供了简化的控件和熟悉的图标。</span><span class="sxs-lookup"><span data-stu-id="b2cba-106">In addition to all the features of Lync, Skype for Business provides new features with simplified controls and familiar icons.</span></span> <span data-ttu-id="b2cba-107">有关新客户端体验的详细信息，请参阅[探索 Skype for Business。](https://go.microsoft.com/fwlink/?LinkId=529022)</span><span class="sxs-lookup"><span data-stu-id="b2cba-107">For detailed information about the new client experience, see [Explore Skype for Business](https://go.microsoft.com/fwlink/?LinkId=529022).</span></span>
  
<span data-ttu-id="b2cba-108">Skype for Business Server 支持新的 Skype for Business 客户端体验以及 Lync 客户端体验。</span><span class="sxs-lookup"><span data-stu-id="b2cba-108">Skype for Business Server supports the new Skype for Business client experience as well as the Lync client experience.</span></span> <span data-ttu-id="b2cba-109">作为管理员，您可以选择用户的首选客户端体验。</span><span class="sxs-lookup"><span data-stu-id="b2cba-109">As an administrator, you can choose the preferred client experience for your users.</span></span> <span data-ttu-id="b2cba-110">例如，你可能想要部署 Lync 客户端体验，直到组织中用户经过全面培训了解新的 Skype for Business 体验。</span><span class="sxs-lookup"><span data-stu-id="b2cba-110">For example, you might want to deploy the Lync client experience until users in your organization are fully trained in the new Skype for Business experience.</span></span> <span data-ttu-id="b2cba-111">或者，如果你尚未将所有用户升级到 Skype for Business Server，你可能希望所有用户都具有相同的客户端体验，直到所有用户都升级到新服务器。</span><span class="sxs-lookup"><span data-stu-id="b2cba-111">Or, if you have not yet upgraded all users to Skype for Business Server, you might want all users to have the same client experience until all are upgraded to the new server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b2cba-112">如果你的组织同时部署了 Skype for Business Server 和 Lync Server，则默认客户端体验将因服务器版本和 UI 设置不同而不同。</span><span class="sxs-lookup"><span data-stu-id="b2cba-112">If your organization has both Skype for Business Server and Lync Server deployed, the default client experience will differ depending on server versions and UI settings.</span></span> <span data-ttu-id="b2cba-113">当用户首次启动 Skype for Business 时，他们将始终看到 Skype for Business 用户界面，即使你已选择 Lync 客户端体验。</span><span class="sxs-lookup"><span data-stu-id="b2cba-113">When users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience.</span></span> <span data-ttu-id="b2cba-114">几分钟后，将要求用户切换到 Lync 模式。</span><span class="sxs-lookup"><span data-stu-id="b2cba-114">After several minutes, users are asked to switch to Lync mode.</span></span> <span data-ttu-id="b2cba-115">有关详细信息，请参阅本主题稍后介绍的 **首次** 启动客户端行为。</span><span class="sxs-lookup"><span data-stu-id="b2cba-115">For more information, see **First launch client behavior** later in this topic.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b2cba-116">Lync 2013 客户端体验不是 Skype for Business 2016 客户端版本或更高版本的选项。</span><span class="sxs-lookup"><span data-stu-id="b2cba-116">The Lync 2013 client experience is not an option for Skype for Business 2016 client versions or later.</span></span> <span data-ttu-id="b2cba-117">在尝试将客户端环境配置为使用 Lync 2013 客户端之前，请检查客户端版本以确保它不会以数字 16 开始;例如：16.x.x.x。</span><span class="sxs-lookup"><span data-stu-id="b2cba-117">Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span> 
  
## <a name="configure-the-client-experience"></a><span data-ttu-id="b2cba-118">配置客户端体验</span><span class="sxs-lookup"><span data-stu-id="b2cba-118">Configure the client experience</span></span>

<span data-ttu-id="b2cba-119">可以使用 **Set-CSClientPolicy** cmdlet 和 EnableSkypeUI 参数指定组织中用户将看到的客户端体验：</span><span class="sxs-lookup"><span data-stu-id="b2cba-119">You can specify the client experience the users in your organization will see by using the **Set-CSClientPolicy** cmdlet with the EnableSkypeUI parameter:</span></span>
  
```powershell
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

<span data-ttu-id="b2cba-120">其中 XdsIdentity 引用全局策略或命名站点策略。</span><span class="sxs-lookup"><span data-stu-id="b2cba-120">where XdsIdentity refers to the Global policy or a named site policy.</span></span>
  
<span data-ttu-id="b2cba-121">以下命令为组织中受全局策略影响的所有用户选择 Skype for Business 客户端体验 (请记住，站点或用户特定的策略会覆盖全局策略) ：</span><span class="sxs-lookup"><span data-stu-id="b2cba-121">The following command selects the Skype for Business client experience for all users in your organization affected by the Global policy (remember, site or user-specific policies override the Global policy):</span></span> 
  
```powershell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

<span data-ttu-id="b2cba-122">下一个命令为组织中受全局策略影响的所有用户选择 Lync 客户端体验：</span><span class="sxs-lookup"><span data-stu-id="b2cba-122">The next command selects the Lync client experience for all users in your organization affected by the Global policy:</span></span>
  
```powershell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

<span data-ttu-id="b2cba-123">下一个命令为 Redmond 站点内的所有用户选择 Skype for Business 客户端体验：</span><span class="sxs-lookup"><span data-stu-id="b2cba-123">The next command selects the Skype for Business client experience for all users within the Redmond site:</span></span>
  
```powershell
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

<span data-ttu-id="b2cba-124">如果要为组织中特定用户配置客户端体验，可以使用 **New-CsClientPolicy** cmdlet 创建新的用户策略，然后使用 **Grant-CsClientPolicy** cmdlet 将策略分配给特定用户。</span><span class="sxs-lookup"><span data-stu-id="b2cba-124">If you want to configure the client experience for specific users within your organization, you can create a new user policy by using the **New-CsClientPolicy** cmdlet, and then assign the policy to specific users by using the **Grant-CsClientPolicy** cmdlet.</span></span>
  
<span data-ttu-id="b2cba-125">例如，以下命令创建一个新的客户端策略 SalesClientUI，用于选择 Skype for Business 客户端体验：</span><span class="sxs-lookup"><span data-stu-id="b2cba-125">For example, the following command creates a new client policy, SalesClientUI, that selects the Skype for Business client experience:</span></span>
  
```powershell
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

<span data-ttu-id="b2cba-126">下一个命令将策略 SalesClientUI 分配给销售部门的所有成员：</span><span class="sxs-lookup"><span data-stu-id="b2cba-126">The next command assigns the policy, SalesClientUI, to all members of the Sales department:</span></span>
  
```powershell
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a><span data-ttu-id="b2cba-127">首次启动客户端行为</span><span class="sxs-lookup"><span data-stu-id="b2cba-127">First launch client behaviors</span></span>

<span data-ttu-id="b2cba-128">默认情况下，当用户首次启动 Skype for Business 2015 时，他们将始终看到 Skype for Business 用户界面，即使你已按前面所述将 EnableSkypeUI 参数的值设置为 $False 选择了 Lync 客户端体验。</span><span class="sxs-lookup"><span data-stu-id="b2cba-128">By default, when users launch Skype for Business 2015 for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the value of the EnableSkypeUI parameter to $False as described previously.</span></span> <span data-ttu-id="b2cba-129">几分钟后，将要求用户切换到 Lync 模式。</span><span class="sxs-lookup"><span data-stu-id="b2cba-129">After several minutes, users will then be asked to switch to Lync mode.</span></span>
  
<span data-ttu-id="b2cba-130">如果你想要在用户首次启动 Skype for Business 客户端时显示 Lync 用户界面，请按照以下步骤在客户端更新后首次启动：</span><span class="sxs-lookup"><span data-stu-id="b2cba-130">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>
  
1. <span data-ttu-id="b2cba-131">确认 的值已  `EnableSkypeUI` 设置为 $False，如前文所述，</span><span class="sxs-lookup"><span data-stu-id="b2cba-131">Confirm that the value of  `EnableSkypeUI` is set to $False in the policy you are using as described previously.</span></span>
    
2. <span data-ttu-id="b2cba-132">更新用户计算机上系统注册表。</span><span class="sxs-lookup"><span data-stu-id="b2cba-132">Update the system registry on the user's computer.</span></span> <span data-ttu-id="b2cba-133">你应该在用户首次启动 Skype for Business 客户端之前这样做，并且你应仅执行一次此操作。</span><span class="sxs-lookup"><span data-stu-id="b2cba-133">You should do this before the first time users launch the Skype for Business client, and you should do this only once.</span></span> <span data-ttu-id="b2cba-134">若要了解如何创建组策略对象以更新加入域的计算机的注册表，请参阅本主题稍后部分的内容。</span><span class="sxs-lookup"><span data-stu-id="b2cba-134">For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="b2cba-135">在 **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** 键中，创建新的 **Binary** 值。</span><span class="sxs-lookup"><span data-stu-id="b2cba-135">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="b2cba-136">值 **名称** 必须为 **EnableSkypeUI**，值数据 **必须设置为** **00 00 00 00 00**。</span><span class="sxs-lookup"><span data-stu-id="b2cba-136">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="b2cba-137">该键应如下所示：</span><span class="sxs-lookup"><span data-stu-id="b2cba-137">The key should look like the following:</span></span>
    
   <pre>
   [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
   "CanSharePptInCollab"=dword:00000001
   "CanShareOneNoteInCollab"=dword:00000001
   "CanAppShareInCollab"=dword:00000001
   "EnableSkypeUI"=hex:00,00,00,00
   </pre>

<span data-ttu-id="b2cba-138">当用户首次启动 Skype for Business 客户端时，现在将显示 Lync 用户界面。</span><span class="sxs-lookup"><span data-stu-id="b2cba-138">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="b2cba-139">控制欢迎屏幕教程的显示</span><span class="sxs-lookup"><span data-stu-id="b2cba-139">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="b2cba-140">当用户打开 Skype for Business 客户端时，默认行为是显示欢迎屏幕，其中包括  *大多数用户请求的 7* 个快速提示。</span><span class="sxs-lookup"><span data-stu-id="b2cba-140">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes  *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="b2cba-141">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer：</span><span class="sxs-lookup"><span data-stu-id="b2cba-141">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>
  
<span data-ttu-id="b2cba-142">在 **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** 键中，创建新的 DWORD (**32 位**) 值 。</span><span class="sxs-lookup"><span data-stu-id="b2cba-142">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="b2cba-143">值 **名称** 必须为 **IsBasicTutorialSeenByUser**， **值** 数据必须设置为 **1**。</span><span class="sxs-lookup"><span data-stu-id="b2cba-143">The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>
  
<span data-ttu-id="b2cba-144">该键应如下所示：</span><span class="sxs-lookup"><span data-stu-id="b2cba-144">The key should look like the following:</span></span>
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="b2cba-145">关闭客户端教程</span><span class="sxs-lookup"><span data-stu-id="b2cba-145">Turn off the client tutorial</span></span>

<span data-ttu-id="b2cba-146">如果你不希望用户能够访问本教程，可以使用以下注册表值关闭客户端教程：</span><span class="sxs-lookup"><span data-stu-id="b2cba-146">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>
  
<span data-ttu-id="b2cba-147">在 **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** 键中，创建新的 DWORD (**32 位**) 值 。</span><span class="sxs-lookup"><span data-stu-id="b2cba-147">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="b2cba-148">值 **名称** 必须为 **TutorialFeatureEnabled**， **值** 数据必须设置为 **0**。</span><span class="sxs-lookup"><span data-stu-id="b2cba-148">The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>
  
<span data-ttu-id="b2cba-149">Lync</span><span class="sxs-lookup"><span data-stu-id="b2cba-149">Lync</span></span>
  
```console
"TutorialFeatureEnabled"=dword:00000000
```

<span data-ttu-id="b2cba-150">可以通过将值数据设置为 **1\*\*\*\*来重新** 打开教程。</span><span class="sxs-lookup"><span data-stu-id="b2cba-150">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>
  
## <a name="default-client-behaviors"></a><span data-ttu-id="b2cba-151">默认客户端行为</span><span class="sxs-lookup"><span data-stu-id="b2cba-151">Default client behaviors</span></span>

<span data-ttu-id="b2cba-152">如果你的组织同时部署了 Skype for Business Server 和 Lync Server，则客户端体验将有所不同，具体取决于服务器版本和 Skype UI 设置。</span><span class="sxs-lookup"><span data-stu-id="b2cba-152">If your organization has both Skype for Business Server and Lync Server deployed, the client experience will differ depending on server versions and the Skype UI setting.</span></span> <span data-ttu-id="b2cba-153">下表显示了基于服务器版本和 UI 设置的初始客户端体验：</span><span class="sxs-lookup"><span data-stu-id="b2cba-153">The following table shows the initial client experience based on server version and the UI setting:</span></span>
  

|<span data-ttu-id="b2cba-154">**服务器版本**</span><span class="sxs-lookup"><span data-stu-id="b2cba-154">**Server version**</span></span>|<span data-ttu-id="b2cba-155">**EnableSkypeUI 设置**</span><span class="sxs-lookup"><span data-stu-id="b2cba-155">**EnableSkypeUI setting**</span></span>|<span data-ttu-id="b2cba-156">**客户端体验**</span><span class="sxs-lookup"><span data-stu-id="b2cba-156">**Client experience**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b2cba-157">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b2cba-157">Skype for Business Server</span></span> |<span data-ttu-id="b2cba-158">默认</span><span class="sxs-lookup"><span data-stu-id="b2cba-158">Default</span></span>  <br/> |<span data-ttu-id="b2cba-159">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b2cba-159">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="b2cba-160">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b2cba-160">Skype for Business Server</span></span>  |<span data-ttu-id="b2cba-161">True</span><span class="sxs-lookup"><span data-stu-id="b2cba-161">True</span></span>  <br/> |<span data-ttu-id="b2cba-162">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b2cba-162">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="b2cba-163">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b2cba-163">Skype for Business Server</span></span>  |<span data-ttu-id="b2cba-164">False</span><span class="sxs-lookup"><span data-stu-id="b2cba-164">False</span></span>  <br/> |<span data-ttu-id="b2cba-165">用户要求切换到 Lync 模式 (如果你将 UI 设置更改为 Skype for Business，用户稍后可以$true) </span><span class="sxs-lookup"><span data-stu-id="b2cba-165">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="b2cba-166">Lync Server 2010 或 Lync Server 2013 (正确的修补程序) </span><span class="sxs-lookup"><span data-stu-id="b2cba-166">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="b2cba-167">默认</span><span class="sxs-lookup"><span data-stu-id="b2cba-167">Default</span></span>  <br/> |<span data-ttu-id="b2cba-168">用户要求切换到 Lync 模式 (如果你将 UI 设置更改为 Skype for Business，用户稍后可以$true) </span><span class="sxs-lookup"><span data-stu-id="b2cba-168">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="b2cba-169">Lync Server 2010 或 Lync Server 2013 (正确的修补程序) </span><span class="sxs-lookup"><span data-stu-id="b2cba-169">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="b2cba-170">True</span><span class="sxs-lookup"><span data-stu-id="b2cba-170">True</span></span>  <br/> |<span data-ttu-id="b2cba-171">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b2cba-171">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="b2cba-172">Lync Server 2010 或 Lync Server 2013 (正确的修补程序) </span><span class="sxs-lookup"><span data-stu-id="b2cba-172">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="b2cba-173">False</span><span class="sxs-lookup"><span data-stu-id="b2cba-173">False</span></span>  <br/> |<span data-ttu-id="b2cba-174">用户要求切换到 Lync 模式 (如果你将 UI 设置更改为 Skype for Business，用户稍后可以$true) </span><span class="sxs-lookup"><span data-stu-id="b2cba-174">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="b2cba-175">Lync Server 2010 或 Lync Server 2013 (修补程序) </span><span class="sxs-lookup"><span data-stu-id="b2cba-175">Lync Server 2010 or Lync Server 2013 (without patches)</span></span>  <br/> |<span data-ttu-id="b2cba-176">默认</span><span class="sxs-lookup"><span data-stu-id="b2cba-176">Default</span></span>  <br/> |<span data-ttu-id="b2cba-177">系统要求用户切换到 Lync 模式 (以后无法切换到 Skype for Business) </span><span class="sxs-lookup"><span data-stu-id="b2cba-177">User asked to switch to Lync mode (user cannot switch to Skype for Business later)</span></span>  <br/> |
   
<span data-ttu-id="b2cba-178">下表显示了管理员更改 Skype UI 体验的初始设置时客户端体验：</span><span class="sxs-lookup"><span data-stu-id="b2cba-178">The next table shows the client experience when the administrator changes the initial setting for the Skype UI experience:</span></span>
  

|<span data-ttu-id="b2cba-179">**服务器版本**</span><span class="sxs-lookup"><span data-stu-id="b2cba-179">**Server version**</span></span>|<span data-ttu-id="b2cba-180">**EnableSkypeUI 设置**</span><span class="sxs-lookup"><span data-stu-id="b2cba-180">**EnableSkypeUI setting**</span></span>|<span data-ttu-id="b2cba-181">**客户端 UI = Lync**</span><span class="sxs-lookup"><span data-stu-id="b2cba-181">**Client UI = Lync**</span></span>|<span data-ttu-id="b2cba-182">**客户端 UI = Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="b2cba-182">**Client UI = Skype for Business**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b2cba-183">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b2cba-183">Skype for Business Server</span></span> |<span data-ttu-id="b2cba-184">True</span><span class="sxs-lookup"><span data-stu-id="b2cba-184">True</span></span>  <br/> |<span data-ttu-id="b2cba-185">要求用户切换到 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b2cba-185">User asked to switch to Skype for Business</span></span>  <br/> |<span data-ttu-id="b2cba-186">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b2cba-186">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="b2cba-187">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b2cba-187">Skype for Business Server</span></span> |<span data-ttu-id="b2cba-188">False</span><span class="sxs-lookup"><span data-stu-id="b2cba-188">False</span></span>  <br/> |<span data-ttu-id="b2cba-189">Lync 模式</span><span class="sxs-lookup"><span data-stu-id="b2cba-189">Lync mode</span></span>  <br/> |<span data-ttu-id="b2cba-190">要求用户切换到 Lync 模式</span><span class="sxs-lookup"><span data-stu-id="b2cba-190">User asked to switch to Lync mode</span></span>  <br/> |
|<span data-ttu-id="b2cba-191">Lync Server 2010 或 Lync Server 2013 (正确的修补程序) </span><span class="sxs-lookup"><span data-stu-id="b2cba-191">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="b2cba-192">True</span><span class="sxs-lookup"><span data-stu-id="b2cba-192">True</span></span>  <br/> |<span data-ttu-id="b2cba-193">要求用户切换到 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b2cba-193">User asked to switch to Skype for Business</span></span>  <br/> |<span data-ttu-id="b2cba-194">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b2cba-194">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="b2cba-195">Lync Server 2010 或 Lync Server 2013 (正确的修补程序) </span><span class="sxs-lookup"><span data-stu-id="b2cba-195">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="b2cba-196">False</span><span class="sxs-lookup"><span data-stu-id="b2cba-196">False</span></span>  <br/> |<span data-ttu-id="b2cba-197">Lync 模式</span><span class="sxs-lookup"><span data-stu-id="b2cba-197">Lync mode</span></span>  <br/> |<span data-ttu-id="b2cba-198">要求用户切换到 Lync 模式</span><span class="sxs-lookup"><span data-stu-id="b2cba-198">User asked to switch to Lync mode</span></span>  <br/> |
|<span data-ttu-id="b2cba-199">Lync Server 2010 或 Lync Server 2013 (修补程序) </span><span class="sxs-lookup"><span data-stu-id="b2cba-199">Lync Server 2010 or Lync Server 2013 (without patches)</span></span>  <br/> |<span data-ttu-id="b2cba-200">默认</span><span class="sxs-lookup"><span data-stu-id="b2cba-200">Default</span></span>  <br/> |<span data-ttu-id="b2cba-201">Lync 模式 (无法切换到 Skype for Business) </span><span class="sxs-lookup"><span data-stu-id="b2cba-201">Lync mode (cannot switch to Skype for Business)</span></span>  <br/> |<span data-ttu-id="b2cba-202">Lync 模式 (无法切换到 Skype for Business) </span><span class="sxs-lookup"><span data-stu-id="b2cba-202">Lync mode (cannot switch to Skype for Business)</span></span>  <br/> |
   
<span data-ttu-id="b2cba-203">管理 Skype for Business 客户端配置所需的修补程序版本包括：</span><span class="sxs-lookup"><span data-stu-id="b2cba-203">The patch versions required to manage the configuration of the Skype for Business client are:</span></span>
  
- <span data-ttu-id="b2cba-204">Lync Server 2010 - 2015 年 2 月累积更新 (4.0.7577.710) Lync Server 2010。</span><span class="sxs-lookup"><span data-stu-id="b2cba-204">Lync Server 2010 - February 2015 Cumulative Update (4.0.7577.710) for Lync Server 2010.</span></span> <span data-ttu-id="b2cba-205">有关信息，请参阅 [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)</span><span class="sxs-lookup"><span data-stu-id="b2cba-205">For information, see [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)</span></span>
    
- <span data-ttu-id="b2cba-206">Lync Server 2013 - Lync Server 2013 的 2014 年 12 月累积 (5.0.8308.857) 5.0.8308.857。</span><span class="sxs-lookup"><span data-stu-id="b2cba-206">Lync Server 2013 - December 2014 Cumulative Update (5.0.8308.857) for Lync Server 2013.</span></span> <span data-ttu-id="b2cba-207">有关信息，请参阅[Updates for Lync Server 2013。](https://go.microsoft.com/fwlink/p/?LinkId=532772)</span><span class="sxs-lookup"><span data-stu-id="b2cba-207">For information, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).</span></span>
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="b2cba-208">创建组策略对象以修改加入域的计算机上注册表</span><span class="sxs-lookup"><span data-stu-id="b2cba-208">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="b2cba-209">用户首次启动 Skype for Business 2015 客户端时显示 Lync 客户端体验的注册表更新应仅执行一次。</span><span class="sxs-lookup"><span data-stu-id="b2cba-209">The registry update to display the Lync client experience the first time a user launches the Skype for Business 2015 client should be done only once.</span></span> <span data-ttu-id="b2cba-210">如果使用组策略对象 (GPO) 更新注册表，则需要定义对象以创建新值，而不是更新值数据。</span><span class="sxs-lookup"><span data-stu-id="b2cba-210">If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data.</span></span> <span data-ttu-id="b2cba-211">应用 GPO 时，如果新值不存在，GPO 将创建它，将值数据设置为 0。</span><span class="sxs-lookup"><span data-stu-id="b2cba-211">When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span> 
  
<span data-ttu-id="b2cba-212">以下过程介绍如何修改注册表，以便用户首次启动 Skype for Business 2015 客户端时显示 Lync 客户端体验。</span><span class="sxs-lookup"><span data-stu-id="b2cba-212">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business 2015 client.</span></span> <span data-ttu-id="b2cba-213">您还可以使用此过程更新注册表以禁用欢迎屏幕教程，如前面所述。</span><span class="sxs-lookup"><span data-stu-id="b2cba-213">You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>
  
### <a name="to-create-the-gpo"></a><span data-ttu-id="b2cba-214">创建 GPO</span><span class="sxs-lookup"><span data-stu-id="b2cba-214">To create the GPO</span></span>

1. <span data-ttu-id="b2cba-215">启动 **组策略管理控制台**。</span><span class="sxs-lookup"><span data-stu-id="b2cba-215">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="b2cba-216">有关如何使用组策略管理控制台的信息，请参阅组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn265969(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="b2cba-216">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn265969(v=ws.11)).</span></span>
    
2. <span data-ttu-id="b2cba-217">右键单击组 **策略对象节点** ，然后选择 **菜单** 上的新建。</span><span class="sxs-lookup"><span data-stu-id="b2cba-217">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>
    
3. <span data-ttu-id="b2cba-218">在"**新建 GPO"** 对话框中，输入 GPO 的名称，例如 MakeLyncDefaultUI，然后单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="b2cba-218">In the **New GPO** dialog, enter a name for the GPO, for example,MakeLyncDefaultUI, and then click **OK**.</span></span>
    
4. <span data-ttu-id="b2cba-219">右键单击刚创建的新 GPO， **然后从菜单中** 选择"编辑"。</span><span class="sxs-lookup"><span data-stu-id="b2cba-219">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>
    
5. <span data-ttu-id="b2cba-220">在组 **策略管理编辑器** 中，展开 **"用户配置**"，展开 **"首选项"，** 展开 **"Windows** 设置"，然后选择 **"注册表"** 节点。</span><span class="sxs-lookup"><span data-stu-id="b2cba-220">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>
    
6. <span data-ttu-id="b2cba-221">右键单击注册表 **节点**，**然后选择新建**  >  **注册表项**。</span><span class="sxs-lookup"><span data-stu-id="b2cba-221">Right-click on the **Registry** node, and then select **New** > **Registry Item**.</span></span>
    
7. <span data-ttu-id="b2cba-222">在" **新建注册表属性"** 对话框中，更新以下内容：</span><span class="sxs-lookup"><span data-stu-id="b2cba-222">On the **New Registry Properties** dialog, update the following:</span></span>
    
   |<span data-ttu-id="b2cba-223">**Field**</span><span class="sxs-lookup"><span data-stu-id="b2cba-223">**Field**</span></span>|<span data-ttu-id="b2cba-224">**要选择或输入的值**</span><span class="sxs-lookup"><span data-stu-id="b2cba-224">**Value to select or enter**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="b2cba-225">**操作**</span><span class="sxs-lookup"><span data-stu-id="b2cba-225">**Action**</span></span> <br/> |<span data-ttu-id="b2cba-226">**创建**</span><span class="sxs-lookup"><span data-stu-id="b2cba-226">**Create**</span></span> <br/> |
   |<span data-ttu-id="b2cba-227">**配置单元**</span><span class="sxs-lookup"><span data-stu-id="b2cba-227">**Hive**</span></span> <br/> | <span data-ttu-id="b2cba-228">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="b2cba-228">HKEY_CURRENT_USER</span></span> <br/> |
   |<span data-ttu-id="b2cba-229">**密钥路径**</span><span class="sxs-lookup"><span data-stu-id="b2cba-229">**Key Path**</span></span> <br/> |<span data-ttu-id="b2cba-230">Software\Microsoft\Office\Lync</span><span class="sxs-lookup"><span data-stu-id="b2cba-230">Software\Microsoft\Office\Lync</span></span>  <br/> |
   |<span data-ttu-id="b2cba-231">**值名称**</span><span class="sxs-lookup"><span data-stu-id="b2cba-231">**Value name**</span></span> <br/> |<span data-ttu-id="b2cba-232">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="b2cba-232">EnableSkypeUI</span></span>  <br/> |
   |<span data-ttu-id="b2cba-233">**值类型**</span><span class="sxs-lookup"><span data-stu-id="b2cba-233">**Value type**</span></span> <br/> |<span data-ttu-id="b2cba-234">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="b2cba-234">REG_BINARY</span></span>  <br/> |
   |<span data-ttu-id="b2cba-235">**值数据**</span><span class="sxs-lookup"><span data-stu-id="b2cba-235">**Value data**</span></span> <br/> |<span data-ttu-id="b2cba-236">00000000</span><span class="sxs-lookup"><span data-stu-id="b2cba-236">00000000</span></span>  <br/> |
   
8. <span data-ttu-id="b2cba-237">单击 **"** 确定"保存更改，然后关闭 GPO。</span><span class="sxs-lookup"><span data-stu-id="b2cba-237">Click **OK** to save your changes, and then close the GPO.</span></span>
    
<span data-ttu-id="b2cba-238">接下来，需要将创建的 GPO 链接到要为其分配策略的一组用户，例如 OU。</span><span class="sxs-lookup"><span data-stu-id="b2cba-238">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>
  
### <a name="to-use-the-gpo-to-assign-the-policy"></a><span data-ttu-id="b2cba-239">使用 GPO 分配策略</span><span class="sxs-lookup"><span data-stu-id="b2cba-239">To use the GPO to assign the policy</span></span>

1. <span data-ttu-id="b2cba-240">在组策略管理控制台中，右键单击要为其分配策略的 OU，然后选择"链接到 **现有 GPO"。**</span><span class="sxs-lookup"><span data-stu-id="b2cba-240">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>
    
2. <span data-ttu-id="b2cba-241">在"**选择 GPO"** 对话框中，选择你创建的 GPO，然后选择"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="b2cba-241">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>
    
3. <span data-ttu-id="b2cba-242">在目标用户的计算机上，打开命令提示符并键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="b2cba-242">On the target user's computer, open a command prompt and type the following command:</span></span>
       
```console
gpupdate /target:user
```

    
    The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.
    
4. <span data-ttu-id="b2cba-243">在命令提示符处，键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="b2cba-243">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="b2cba-244">**gpresult /r**</span><span class="sxs-lookup"><span data-stu-id="b2cba-244">**gpresult /r**</span></span>
    
    <span data-ttu-id="b2cba-245">你应该会看到"分配的组策略对象"，下面显示了你创建的 GPO 的名称。</span><span class="sxs-lookup"><span data-stu-id="b2cba-245">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>
    
<span data-ttu-id="b2cba-246">您还可以通过检查注册表来验证 GPO 是否成功更新了用户计算机上注册表。</span><span class="sxs-lookup"><span data-stu-id="b2cba-246">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry.</span></span> <span data-ttu-id="b2cba-247">打开注册表编辑器并导航到 **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** 项。</span><span class="sxs-lookup"><span data-stu-id="b2cba-247">Open Registry Editor and navigate to the **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** key.</span></span> <span data-ttu-id="b2cba-248">如果 GPO 成功更新注册表，你将看到一个名为 EnableSkypeUI 的值，值为 0。</span><span class="sxs-lookup"><span data-stu-id="b2cba-248">If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>
