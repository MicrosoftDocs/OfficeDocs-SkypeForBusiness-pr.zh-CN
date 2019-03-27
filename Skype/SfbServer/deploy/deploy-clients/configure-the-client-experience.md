---
title: 配置与业务 2015年的 Skype 的客户端体验
ms.reviewer: ''
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66867a96-ff00-497d-889c-2e908cc384ce
description: 摘要： 阅读本主题可了解如何配置 Skype 业务用户的客户端体验。
ms.openlocfilehash: b8d258236a5254aa1dab5e86edb9586ea514c689
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875790"
---
# <a name="configure-the-client-experience-with-skype-for-business-2015"></a><span data-ttu-id="e2875-103">配置与业务 2015年的 Skype 的客户端体验</span><span class="sxs-lookup"><span data-stu-id="e2875-103">Configure the client experience with Skype for Business 2015</span></span>
 
<span data-ttu-id="e2875-104">**摘要：** 阅读本主题可了解如何配置 Business 2015 用户 Skype 的客户端体验。</span><span class="sxs-lookup"><span data-stu-id="e2875-104">**Summary:** Read this topic to learn how to configure the client experience for Skype for Business 2015 users.</span></span>
  
<span data-ttu-id="e2875-105">Skype 的业务 2015年提供基于 Skype 使用者产品体验的新用户体验。</span><span class="sxs-lookup"><span data-stu-id="e2875-105">Skype for Business 2015 provides a new user experience that is based on the Skype consumer product experience.</span></span> <span data-ttu-id="e2875-106">Lync 的所有功能，除了 for Business 的 Skype 提供了简化的控件与熟悉的图标的新功能。</span><span class="sxs-lookup"><span data-stu-id="e2875-106">In addition to all the features of Lync, Skype for Business provides new features with simplified controls and familiar icons.</span></span> <span data-ttu-id="e2875-107">有关新的客户端体验的详细信息，请参阅[浏览 for Business 的 Skype](https://go.microsoft.com/fwlink/?LinkId=529022)。</span><span class="sxs-lookup"><span data-stu-id="e2875-107">For detailed information about the new client experience, see [Explore Skype for Business](https://go.microsoft.com/fwlink/?LinkId=529022).</span></span>
  
<span data-ttu-id="e2875-108">Skype 业务服务器支持的商业客户端体验，以及 Lync 客户端体验的新 Skype。</span><span class="sxs-lookup"><span data-stu-id="e2875-108">Skype for Business Server supports the new Skype for Business client experience as well as the Lync client experience.</span></span> <span data-ttu-id="e2875-109">作为管理员，你可以为用户选择首选客户端体验。</span><span class="sxs-lookup"><span data-stu-id="e2875-109">As an administrator, you can choose the preferred client experience for your users.</span></span> <span data-ttu-id="e2875-110">例如，您可能想要部署 Lync 客户端体验，直到您的组织中的用户进行完全培训中商业体验的新的 Skype。</span><span class="sxs-lookup"><span data-stu-id="e2875-110">For example, you might want to deploy the Lync client experience until users in your organization are fully trained in the new Skype for Business experience.</span></span> <span data-ttu-id="e2875-111">或者，如果您具有尚未升级所有用户到 Skype 业务服务器，您可能希望所有用户都相同的客户端体验，直到所有都升级到新服务器。</span><span class="sxs-lookup"><span data-stu-id="e2875-111">Or, if you have not yet upgraded all users to Skype for Business Server, you might want all users to have the same client experience until all are upgraded to the new server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e2875-112">如果您的组织有两个 Skype 业务 server 和 Lync Server 部署，将根据服务器版本和 UI 设置不同默认客户端体验。</span><span class="sxs-lookup"><span data-stu-id="e2875-112">If your organization has both Skype for Business Server and Lync Server deployed, the default client experience will differ depending on server versions and UI settings.</span></span> <span data-ttu-id="e2875-113">当用户首次启动 for Business 的 Skype 时，它们始终会看到业务用户界面-Skype，即使您所选择的 Lync 客户端体验。</span><span class="sxs-lookup"><span data-stu-id="e2875-113">When users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience.</span></span> <span data-ttu-id="e2875-114">几分钟后，询问用户要切换到 Lync 模式。</span><span class="sxs-lookup"><span data-stu-id="e2875-114">After several minutes, users are asked to switch to Lync mode.</span></span> <span data-ttu-id="e2875-115">有关更多信息，请参阅本主题后面部分的**首次启动客户端行为**。</span><span class="sxs-lookup"><span data-stu-id="e2875-115">For more information, see **First launch client behavior** later in this topic.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e2875-116">Lync 2013 客户端体验不业务 2016年客户端版本或更高版本的 Skype 选项。</span><span class="sxs-lookup"><span data-stu-id="e2875-116">The Lync 2013 client experience is not an option for Skype for Business 2016 client versions or later.</span></span> <span data-ttu-id="e2875-117">在尝试将你的客户端环境配置为使用 Lync 2013 客户端之前，请检查客户端版本，以确保它不会以数字 16 开头；例如：16.x.x.x。</span><span class="sxs-lookup"><span data-stu-id="e2875-117">Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span> 
  
## <a name="configure-the-client-experience"></a><span data-ttu-id="e2875-118">配置客户端体验</span><span class="sxs-lookup"><span data-stu-id="e2875-118">Configure the client experience</span></span>

<span data-ttu-id="e2875-119">您可以使用 **Set-CSClientPolicy** cmdlet 及 EnableSkypeUI 参数，指定组织内的用户将获得怎样的客户端体验：</span><span class="sxs-lookup"><span data-stu-id="e2875-119">You can specify the client experience the users in your organization will see by using the **Set-CSClientPolicy** cmdlet with the EnableSkypeUI parameter:</span></span>
  
```
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

<span data-ttu-id="e2875-120">其中 XdsIdentity 表示全局策略或指定站点策略。</span><span class="sxs-lookup"><span data-stu-id="e2875-120">where XdsIdentity refers to the Global policy or a named site policy.</span></span>
  
<span data-ttu-id="e2875-121">下面的命令组织受全局策略中选定的所有用户的商业客户端体验的 Skype （请记住，站点或特定于用户策略将覆盖全局策略）：</span><span class="sxs-lookup"><span data-stu-id="e2875-121">The following command selects the Skype for Business client experience for all users in your organization affected by the Global policy (remember, site or user-specific policies override the Global policy):</span></span> 
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

<span data-ttu-id="e2875-122">下一个命令选择受全局策略在组织中的所有用户的 Lync 客户端体验：</span><span class="sxs-lookup"><span data-stu-id="e2875-122">The next command selects the Lync client experience for all users in your organization affected by the Global policy:</span></span>
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

<span data-ttu-id="e2875-123">下一个命令选择为 Redmond 站点内的所有用户的商业客户端体验的 Skype:</span><span class="sxs-lookup"><span data-stu-id="e2875-123">The next command selects the Skype for Business client experience for all users within the Redmond site:</span></span>
  
```
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

<span data-ttu-id="e2875-124">如果您想要配置组织内的特定用户的客户端体验，您可以使用**New-csclientpolicy** cmdlet 创建一个新用户策略，然后使用**Grant-csclientpolicy**将策略分配给特定用户cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e2875-124">If you want to configure the client experience for specific users within your organization, you can create a new user policy by using the **New-CsClientPolicy** cmdlet, and then assign the policy to specific users by using the **Grant-CsClientPolicy** cmdlet.</span></span>
  
<span data-ttu-id="e2875-125">例如，以下命令创建新的客户端策略，SalesClientUI，选择业务客户端体验的 Skype 的：</span><span class="sxs-lookup"><span data-stu-id="e2875-125">For example, the following command creates a new client policy, SalesClientUI, that selects the Skype for Business client experience:</span></span>
  
```
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

<span data-ttu-id="e2875-126">下一条命令向销售部门的所有成员分配 SalesClientUI 策略：</span><span class="sxs-lookup"><span data-stu-id="e2875-126">The next command assigns the policy, SalesClientUI, to all members of the Sales department:</span></span>
  
```
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a><span data-ttu-id="e2875-127">首次启动客户端行为</span><span class="sxs-lookup"><span data-stu-id="e2875-127">First launch client behaviors</span></span>

<span data-ttu-id="e2875-128">默认情况下，当用户启动的业务 2015 Skype 第一次，他们将始终看到业务用户界面-Skype 即使选择通过将 EnableSkypeUI 参数的值设置为 $False，如下所述的 Lync 客户端体验以前。</span><span class="sxs-lookup"><span data-stu-id="e2875-128">By default, when users launch Skype for Business 2015 for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the value of the EnableSkypeUI parameter to $False as described previously.</span></span> <span data-ttu-id="e2875-129">几分钟时间后，系统将要求用户切换到 Lync 模式。</span><span class="sxs-lookup"><span data-stu-id="e2875-129">After several minutes, users will then be asked to switch to Lync mode.</span></span>
  
<span data-ttu-id="e2875-130">如果你希望在用户首次启动 Skype for Business 客户端时显示 Lync 用户界面，请在客户端更新后首次启动前执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="e2875-130">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>
  
1. <span data-ttu-id="e2875-131">确认的值`EnableSkypeUI`设置为 $False 中使用如前面所述的策略。</span><span class="sxs-lookup"><span data-stu-id="e2875-131">Confirm that the value of  `EnableSkypeUI` is set to $False in the policy you are using as described previously.</span></span>
    
2. <span data-ttu-id="e2875-p106">更新用户计算机上的系统注册表。 你应在用户首次启动 Skype for Business 客户端之前执行此操作，且你应仅执行一次此操作。 有关如何创建组策略对象以更新加入域的计算机上的注册表的信息，请参阅本主题后面部分内容。</span><span class="sxs-lookup"><span data-stu-id="e2875-p106">Update the system registry on the user's computer. You should do this before the first time users launch the Skype for Business client, and you should do this only once. For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="e2875-135">在 **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** 键中，创建新的“**二进制**”值。</span><span class="sxs-lookup"><span data-stu-id="e2875-135">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="e2875-136">" **值名称**"必须为 **EnableSkypeUI**，" **值数据**"必须设为 **00 00 00 00**。</span><span class="sxs-lookup"><span data-stu-id="e2875-136">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="e2875-137">该注册表项应类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="e2875-137">The key should look like the following:</span></span>
    
   <pre>
   [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
   "CanSharePptInCollab"=dword:00000001
   "CanShareOneNoteInCollab"=dword:00000001
   "CanAppShareInCollab"=dword:00000001
   "EnableSkypeUI"=hex:00,00,00,00
   </pre>

<span data-ttu-id="e2875-138">当用户首次启动 Skype for Business 客户端时，现在将显示 Lync 用户界面。</span><span class="sxs-lookup"><span data-stu-id="e2875-138">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="e2875-139">控制欢迎屏幕教程的显示</span><span class="sxs-lookup"><span data-stu-id="e2875-139">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="e2875-140">当用户打开 Skype 业务客户端时的默认行为是显示欢迎屏幕包含*多数人寻求 7 导航的快速提示*。</span><span class="sxs-lookup"><span data-stu-id="e2875-140">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes  *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="e2875-141">你可以关闭欢迎屏幕的显示，同时仍允许用户通过在客户端计算机上添加以下注册表值来访问教程：</span><span class="sxs-lookup"><span data-stu-id="e2875-141">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>
  
<span data-ttu-id="e2875-p108">在 **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** 键中，创建新的 **DWORD（32 位）值**。**值名称**必须为 **IsBasicTutorialSeenByUser**，**值数据**必须设为 **1**。</span><span class="sxs-lookup"><span data-stu-id="e2875-p108">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** key, create a new **DWORD (32-bit) Value**. The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>
  
<span data-ttu-id="e2875-144">该键应类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="e2875-144">The key should look like the following:</span></span>
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="e2875-145">关闭客户端教程</span><span class="sxs-lookup"><span data-stu-id="e2875-145">Turn off the client tutorial</span></span>

<span data-ttu-id="e2875-146">如果您不希望您的用户能够访问教程，您可以使用以下注册表值关闭客户端教程：</span><span class="sxs-lookup"><span data-stu-id="e2875-146">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>
  
<span data-ttu-id="e2875-p109">在 **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** 键中，创建新的 **DWORD（32 位）值**。**值名称**必须为 **TutorialFeatureEnabled**，**值数据**必须设为 **0**。</span><span class="sxs-lookup"><span data-stu-id="e2875-p109">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** key, create a new **DWORD (32-bit) Value**. The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>
  
<span data-ttu-id="e2875-149">Lync</span><span class="sxs-lookup"><span data-stu-id="e2875-149">Lync</span></span>
  
```
"TutorialFeatureEnabled"=dword:00000000
```

<span data-ttu-id="e2875-150">您可以通过将**值数据**设为 **1** 来重新打开教程。</span><span class="sxs-lookup"><span data-stu-id="e2875-150">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>
  
## <a name="default-client-behaviors"></a><span data-ttu-id="e2875-151">默认客户端行为</span><span class="sxs-lookup"><span data-stu-id="e2875-151">Default client behaviors</span></span>

<span data-ttu-id="e2875-152">如果您的组织有两个 Skype 业务 server 和 Lync Server 部署，客户端体验将将有所不同具体取决于服务器版本和 Skype UI 设置。</span><span class="sxs-lookup"><span data-stu-id="e2875-152">If your organization has both Skype for Business Server and Lync Server deployed, the client experience will differ depending on server versions and the Skype UI setting.</span></span> <span data-ttu-id="e2875-153">下表显示了基于服务器版本和 UI 设置的初始客户端体验：</span><span class="sxs-lookup"><span data-stu-id="e2875-153">The following table shows the initial client experience based on server version and the UI setting:</span></span>
  

|<span data-ttu-id="e2875-154">**服务器版本**</span><span class="sxs-lookup"><span data-stu-id="e2875-154">**Server version**</span></span>|<span data-ttu-id="e2875-155">**EnableSkypeUI 设置**</span><span class="sxs-lookup"><span data-stu-id="e2875-155">**EnableSkypeUI setting**</span></span>|<span data-ttu-id="e2875-156">**客户端体验**</span><span class="sxs-lookup"><span data-stu-id="e2875-156">**Client experience**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e2875-157">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e2875-157">Skype for Business Server</span></span> |<span data-ttu-id="e2875-158">默认值</span><span class="sxs-lookup"><span data-stu-id="e2875-158">Default</span></span>  <br/> |<span data-ttu-id="e2875-159">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e2875-159">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="e2875-160">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e2875-160">Skype for Business Server</span></span>  |<span data-ttu-id="e2875-161">True</span><span class="sxs-lookup"><span data-stu-id="e2875-161">True</span></span>  <br/> |<span data-ttu-id="e2875-162">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e2875-162">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="e2875-163">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e2875-163">Skype for Business Server</span></span>  |<span data-ttu-id="e2875-164">False</span><span class="sxs-lookup"><span data-stu-id="e2875-164">False</span></span>  <br/> |<span data-ttu-id="e2875-165">要求用户切换到 Lync 模式 （用户可以切换到 for Business 更高版本的 Skype 如果将 UI 设置更改为 $true）</span><span class="sxs-lookup"><span data-stu-id="e2875-165">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="e2875-166">Lync Server 2010 或 Lync Server 2013 （具有正确的修补程序）</span><span class="sxs-lookup"><span data-stu-id="e2875-166">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="e2875-167">默认值</span><span class="sxs-lookup"><span data-stu-id="e2875-167">Default</span></span>  <br/> |<span data-ttu-id="e2875-168">要求用户切换到 Lync 模式 （用户可以切换到 for Business 更高版本的 Skype 如果将 UI 设置更改为 $true）</span><span class="sxs-lookup"><span data-stu-id="e2875-168">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="e2875-169">Lync Server 2010 或 Lync Server 2013 （具有正确的修补程序）</span><span class="sxs-lookup"><span data-stu-id="e2875-169">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="e2875-170">True</span><span class="sxs-lookup"><span data-stu-id="e2875-170">True</span></span>  <br/> |<span data-ttu-id="e2875-171">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e2875-171">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="e2875-172">Lync Server 2010 或 Lync Server 2013 （具有正确的修补程序）</span><span class="sxs-lookup"><span data-stu-id="e2875-172">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="e2875-173">False</span><span class="sxs-lookup"><span data-stu-id="e2875-173">False</span></span>  <br/> |<span data-ttu-id="e2875-174">要求用户切换到 Lync 模式 （用户可以切换到 for Business 更高版本的 Skype 如果将 UI 设置更改为 $true）</span><span class="sxs-lookup"><span data-stu-id="e2875-174">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="e2875-175">Lync Server 2010 或 Lync Server 2013 （不带修补程序）</span><span class="sxs-lookup"><span data-stu-id="e2875-175">Lync Server 2010 or Lync Server 2013 (without patches)</span></span>  <br/> |<span data-ttu-id="e2875-176">默认值</span><span class="sxs-lookup"><span data-stu-id="e2875-176">Default</span></span>  <br/> |<span data-ttu-id="e2875-177">要求用户切换到 Lync 模式 （用户无法切换到 Skype for Business 更高版本）</span><span class="sxs-lookup"><span data-stu-id="e2875-177">User asked to switch to Lync mode (user cannot switch to Skype for Business later)</span></span>  <br/> |
   
<span data-ttu-id="e2875-178">下表显示了客户端体验时管理员变化的 Skype UI 体验的初始设置：</span><span class="sxs-lookup"><span data-stu-id="e2875-178">The next table shows the client experience when the administrator changes the initial setting for the Skype UI experience:</span></span>
  

|<span data-ttu-id="e2875-179">**服务器版本**</span><span class="sxs-lookup"><span data-stu-id="e2875-179">**Server version**</span></span>|<span data-ttu-id="e2875-180">**EnableSkypeUI 设置**</span><span class="sxs-lookup"><span data-stu-id="e2875-180">**EnableSkypeUI setting**</span></span>|<span data-ttu-id="e2875-181">**客户端 UI = Lync**</span><span class="sxs-lookup"><span data-stu-id="e2875-181">**Client UI = Lync**</span></span>|<span data-ttu-id="e2875-182">**客户端 UI = Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="e2875-182">**Client UI = Skype for Business**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e2875-183">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e2875-183">Skype for Business Server</span></span> |<span data-ttu-id="e2875-184">True</span><span class="sxs-lookup"><span data-stu-id="e2875-184">True</span></span>  <br/> |<span data-ttu-id="e2875-185">要求用户要切换到 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e2875-185">User asked to switch to Skype for Business</span></span>  <br/> |<span data-ttu-id="e2875-186">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e2875-186">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="e2875-187">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e2875-187">Skype for Business Server</span></span> |<span data-ttu-id="e2875-188">False</span><span class="sxs-lookup"><span data-stu-id="e2875-188">False</span></span>  <br/> |<span data-ttu-id="e2875-189">Lync 模式</span><span class="sxs-lookup"><span data-stu-id="e2875-189">Lync mode</span></span>  <br/> |<span data-ttu-id="e2875-190">要求用户切换到 Lync 模式</span><span class="sxs-lookup"><span data-stu-id="e2875-190">User asked to switch to Lync mode</span></span>  <br/> |
|<span data-ttu-id="e2875-191">Lync Server 2010 或 Lync Server 2013 （具有正确的修补程序）</span><span class="sxs-lookup"><span data-stu-id="e2875-191">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="e2875-192">True</span><span class="sxs-lookup"><span data-stu-id="e2875-192">True</span></span>  <br/> |<span data-ttu-id="e2875-193">要求用户要切换到 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e2875-193">User asked to switch to Skype for Business</span></span>  <br/> |<span data-ttu-id="e2875-194">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e2875-194">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="e2875-195">Lync Server 2010 或 Lync Server 2013 （具有正确的修补程序）</span><span class="sxs-lookup"><span data-stu-id="e2875-195">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="e2875-196">False</span><span class="sxs-lookup"><span data-stu-id="e2875-196">False</span></span>  <br/> |<span data-ttu-id="e2875-197">Lync 模式</span><span class="sxs-lookup"><span data-stu-id="e2875-197">Lync mode</span></span>  <br/> |<span data-ttu-id="e2875-198">要求用户切换到 Lync 模式</span><span class="sxs-lookup"><span data-stu-id="e2875-198">User asked to switch to Lync mode</span></span>  <br/> |
|<span data-ttu-id="e2875-199">Lync Server 2010 或 Lync Server 2013 （不带修补程序）</span><span class="sxs-lookup"><span data-stu-id="e2875-199">Lync Server 2010 or Lync Server 2013 (without patches)</span></span>  <br/> |<span data-ttu-id="e2875-200">默认值</span><span class="sxs-lookup"><span data-stu-id="e2875-200">Default</span></span>  <br/> |<span data-ttu-id="e2875-201">Lync 模式 （不能切换到 for Business 的 Skype）</span><span class="sxs-lookup"><span data-stu-id="e2875-201">Lync mode (cannot switch to Skype for Business)</span></span>  <br/> |<span data-ttu-id="e2875-202">Lync 模式 （不能切换到 for Business 的 Skype）</span><span class="sxs-lookup"><span data-stu-id="e2875-202">Lync mode (cannot switch to Skype for Business)</span></span>  <br/> |
   
<span data-ttu-id="e2875-203">管理业务客户端 Skype 的配置所需的修补程序版本是：</span><span class="sxs-lookup"><span data-stu-id="e2875-203">The patch versions required to manage the configuration of the Skype for Business client are:</span></span>
  
- <span data-ttu-id="e2875-204">Lync Server 2010-Lync Server 2010 的 2015 年 2 月版累积更新 (4.0.7577.710)。</span><span class="sxs-lookup"><span data-stu-id="e2875-204">Lync Server 2010 - February 2015 Cumulative Update (4.0.7577.710) for Lync Server 2010.</span></span> <span data-ttu-id="e2875-205">有关信息，请参阅[Lync Server 2010 更新](https://go.microsoft.com/fwlink/p/?LinkId=532771)</span><span class="sxs-lookup"><span data-stu-id="e2875-205">For information, see [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)</span></span>
    
- <span data-ttu-id="e2875-206">Lync Server 2013-Lync Server 2013 的 2014 年 12 月累积更新 (5.0.8308.857)。</span><span class="sxs-lookup"><span data-stu-id="e2875-206">Lync Server 2013 - December 2014 Cumulative Update (5.0.8308.857) for Lync Server 2013.</span></span> <span data-ttu-id="e2875-207">有关信息，请参阅[Lync Server 2013 的更新](https://go.microsoft.com/fwlink/p/?LinkId=532772)。</span><span class="sxs-lookup"><span data-stu-id="e2875-207">For information, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).</span></span>
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="e2875-208">创建组策略对象以修改加入域的计算机上的注册表</span><span class="sxs-lookup"><span data-stu-id="e2875-208">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="e2875-209">要显示的 Lync 客户端体验第一次用户启动业务 2015年客户端 Skype 的注册表更新应仅执行一次。</span><span class="sxs-lookup"><span data-stu-id="e2875-209">The registry update to display the Lync client experience the first time a user launches the Skype for Business 2015 client should be done only once.</span></span> <span data-ttu-id="e2875-210">如果你使用组策略对象 (GPO) 更新注册表，你需要定义对象以创建新值，而非更新值数据。</span><span class="sxs-lookup"><span data-stu-id="e2875-210">If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data.</span></span> <span data-ttu-id="e2875-211">应用 GPO 时，如果新值不存在，则 GPO 将创建新值并将值数据设为 0。</span><span class="sxs-lookup"><span data-stu-id="e2875-211">When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span> 
  
<span data-ttu-id="e2875-212">以下过程介绍如何修改注册表，以使 Lync 客户端体验显示第一次用户启动业务 2015年客户端 Skype。</span><span class="sxs-lookup"><span data-stu-id="e2875-212">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business 2015 client.</span></span> <span data-ttu-id="e2875-213">你还可以如前文所述，使用此流程更新注册表以禁用欢迎屏幕教程。</span><span class="sxs-lookup"><span data-stu-id="e2875-213">You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>
  
### <a name="to-create-the-gpo"></a><span data-ttu-id="e2875-214">创建 GPO</span><span class="sxs-lookup"><span data-stu-id="e2875-214">To create the GPO</span></span>

1. <span data-ttu-id="e2875-215">启动" **组策略管理控制台**"。</span><span class="sxs-lookup"><span data-stu-id="e2875-215">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="e2875-216">有关如何使用组策略管理控制台的信息，请参阅[组策略管理控制台](https://go.microsoft.com/fwlink/?LinkId=532759)。</span><span class="sxs-lookup"><span data-stu-id="e2875-216">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](https://go.microsoft.com/fwlink/?LinkId=532759).</span></span>
    
2. <span data-ttu-id="e2875-217">右键单击" **组策略对象**"节点，然后选择菜单上的" **新建**"。</span><span class="sxs-lookup"><span data-stu-id="e2875-217">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>
    
3. <span data-ttu-id="e2875-218">在" **新建 GPO**"对话框中，输入 GPO 的名称，例如 MakeLyncDefaultUI，然后单击" **确定**"。</span><span class="sxs-lookup"><span data-stu-id="e2875-218">In the **New GPO** dialog, enter a name for the GPO, for example,MakeLyncDefaultUI, and then click **OK**.</span></span>
    
4. <span data-ttu-id="e2875-219">右键单击你刚创建的新 GPO，然后在菜单上选择" **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="e2875-219">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>
    
5. <span data-ttu-id="e2875-220">在" **组策略管理编辑器**"中，依次展开" **用户配置**"、" **首选项**"、" **Windows 设置**"，然后选择" **注册表**"节点。</span><span class="sxs-lookup"><span data-stu-id="e2875-220">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>
    
6. <span data-ttu-id="e2875-221">Right-click on the **Registry** node, and then select **New** > **Registry Item**.</span><span class="sxs-lookup"><span data-stu-id="e2875-221">Right-click on the **Registry** node, and then select **New** > **Registry Item**.</span></span>
    
7. <span data-ttu-id="e2875-222">在" **新建注册表属性**"对话框上，更新以下内容：</span><span class="sxs-lookup"><span data-stu-id="e2875-222">On the **New Registry Properties** dialog, update the following:</span></span>
    
   |<span data-ttu-id="e2875-223">**字段**</span><span class="sxs-lookup"><span data-stu-id="e2875-223">**Field**</span></span>|<span data-ttu-id="e2875-224">**要选择或输入的值**</span><span class="sxs-lookup"><span data-stu-id="e2875-224">**Value to select or enter**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="e2875-225">**操作**</span><span class="sxs-lookup"><span data-stu-id="e2875-225">**Action**</span></span> <br/> |<span data-ttu-id="e2875-226">**创建**</span><span class="sxs-lookup"><span data-stu-id="e2875-226">**Create**</span></span> <br/> |
   |<span data-ttu-id="e2875-227">**配置单元**</span><span class="sxs-lookup"><span data-stu-id="e2875-227">**Hive**</span></span> <br/> | <span data-ttu-id="e2875-228">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="e2875-228">HKEY_CURRENT_USER</span></span> <br/> |
   |<span data-ttu-id="e2875-229">**键路径**</span><span class="sxs-lookup"><span data-stu-id="e2875-229">**Key Path**</span></span> <br/> |<span data-ttu-id="e2875-230">Software\Microsoft\Office\Lync</span><span class="sxs-lookup"><span data-stu-id="e2875-230">Software\Microsoft\Office\Lync</span></span>  <br/> |
   |<span data-ttu-id="e2875-231">**值名称**</span><span class="sxs-lookup"><span data-stu-id="e2875-231">**Value name**</span></span> <br/> |<span data-ttu-id="e2875-232">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="e2875-232">EnableSkypeUI</span></span>  <br/> |
   |<span data-ttu-id="e2875-233">**值类型**</span><span class="sxs-lookup"><span data-stu-id="e2875-233">**Value type**</span></span> <br/> |<span data-ttu-id="e2875-234">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="e2875-234">REG_BINARY</span></span>  <br/> |
   |<span data-ttu-id="e2875-235">**值数据**</span><span class="sxs-lookup"><span data-stu-id="e2875-235">**Value data**</span></span> <br/> |<span data-ttu-id="e2875-236">00000000</span><span class="sxs-lookup"><span data-stu-id="e2875-236">00000000</span></span>  <br/> |
   
8. <span data-ttu-id="e2875-237">单击" **确定**"以保存更改，然后关闭 GPO。</span><span class="sxs-lookup"><span data-stu-id="e2875-237">Click **OK** to save your changes, and then close the GPO.</span></span>
    
<span data-ttu-id="e2875-238">接下来，您需要将您创建的 GPO 链接到您希望分配策略的用户组，比如 OU。</span><span class="sxs-lookup"><span data-stu-id="e2875-238">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>
  
### <a name="to-use-the-gpo-to-assign-the-policy"></a><span data-ttu-id="e2875-239">使用 GPO 分配策略</span><span class="sxs-lookup"><span data-stu-id="e2875-239">To use the GPO to assign the policy</span></span>

1. <span data-ttu-id="e2875-240">在组策略管理控制台中，右键单击要分配策略的 OU，然后选择“**链接到现有 GPO**”。</span><span class="sxs-lookup"><span data-stu-id="e2875-240">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>
    
2. <span data-ttu-id="e2875-241">在" **选择 GPO**"对话框中，选择你创建的 GPO，然后选择" **确定**"。</span><span class="sxs-lookup"><span data-stu-id="e2875-241">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>
    
3. <span data-ttu-id="e2875-242">在目标用户的计算机上，打开命令提示符并键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="e2875-242">On the target user's computer, open a command prompt and type the following command:</span></span>
       
```
gpupdate /target:user
```

    
    The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.
    
4. <span data-ttu-id="e2875-243">在命令提示符下，键入下列命令：</span><span class="sxs-lookup"><span data-stu-id="e2875-243">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="e2875-244">**gpresult /r**</span><span class="sxs-lookup"><span data-stu-id="e2875-244">**gpresult /r**</span></span>
    
    <span data-ttu-id="e2875-245">您将在下面看到带有您创建的 GPO 名称的“已分配的组策略对象”。</span><span class="sxs-lookup"><span data-stu-id="e2875-245">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>
    
<span data-ttu-id="e2875-p115">您可以检查注册表以确认 GPO 已成功更新用户计算机上的注册表。打开注册表编辑器并导航至 **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** 键。如果 GPO 已成功更新注册表，您将看到名为 EnableSkypeUI 的值设为 0。</span><span class="sxs-lookup"><span data-stu-id="e2875-p115">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry. Open Registry Editor and navigate to the **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** key. If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>
  

