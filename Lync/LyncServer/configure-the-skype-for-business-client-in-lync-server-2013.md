---
title: 在 Lync Server 2013 中配置 Skype for Business 客户端
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
TOCTitle: Configure the client experience
ms:assetid: 61e783f1-24f4-430b-ae52-c76a4d206dc7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn954919(v=OCS.15)
ms:contentKeyID: 65227958
ms.date: 09/18/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 632eed40992bfcff53072d618313afe3501431be
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233230"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-client-experience-with-skype-for-business"></a><span data-ttu-id="e01e8-102">Configure the client experience with Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e01e8-102">Configure the client experience with Skype for Business</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e01e8-103">_**主题上次修改时间:** 2015-09-17_</span><span class="sxs-lookup"><span data-stu-id="e01e8-103">_**Topic Last Modified:** 2015-09-17_</span></span>

<span data-ttu-id="e01e8-104">**摘要:** 本主题介绍了如何在 Lync Server 2013 环境中配置 Skype for Business 客户端用户的客户体验。</span><span class="sxs-lookup"><span data-stu-id="e01e8-104">**Summary:** This topic describes how to configure the client experience for Skype for Business client users in a Lync Server 2013 environment.</span></span> <span data-ttu-id="e01e8-105">只有在安装了12月2014累积更新 (5.0.8308.857) 或更高版本的情况运行 Lync Server 2013 时, 才能配置客户端体验。</span><span class="sxs-lookup"><span data-stu-id="e01e8-105">You can configure the client experience only if you are running Lync Server 2013 with the December 2014 Cumulative Update (5.0.8308.857) or later installed.</span></span> <span data-ttu-id="e01e8-106">有关更新 Lync Server 2013 的详细信息, 请参阅[Lync server 2013 更新](http://go.microsoft.com/fwlink/p/?linkid=532651)。</span><span class="sxs-lookup"><span data-stu-id="e01e8-106">For information about updating Lync Server 2013, see [Updates for Lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=532651).</span></span>

<span data-ttu-id="e01e8-107">Skype for business 提供基于 Skype 消费者产品体验的全新用户体验。</span><span class="sxs-lookup"><span data-stu-id="e01e8-107">Skype for Business provides a new user experience that is based on the Skype consumer product experience.</span></span> <span data-ttu-id="e01e8-108">除了 Lync 的所有功能之外, Skype for Business 还通过简化的控件和熟悉的图标提供新功能。</span><span class="sxs-lookup"><span data-stu-id="e01e8-108">In addition to all the features of Lync, Skype for Business provides new features with simplified controls and familiar icons.</span></span> <span data-ttu-id="e01e8-109">有关新的客户体验的详细信息, 请参阅[Lync 现在是 Skype for business--查看新增功能](http://go.microsoft.com/fwlink/?linkid=529022)。</span><span class="sxs-lookup"><span data-stu-id="e01e8-109">For detailed information about the new client experience, see [Lync is now Skype for Business -- see what's new](http://go.microsoft.com/fwlink/?linkid=529022).</span></span>

<span data-ttu-id="e01e8-110">Lync Server 2013 支持全新的 Skype for Business 客户端体验以及 Lync 客户端体验。</span><span class="sxs-lookup"><span data-stu-id="e01e8-110">Lync Server 2013 supports the new Skype for Business client experience as well as the Lync client experience.</span></span> <span data-ttu-id="e01e8-111">作为管理员，你可以为用户选择首选客户端体验。</span><span class="sxs-lookup"><span data-stu-id="e01e8-111">As an administrator, you can choose the preferred client experience for your users.</span></span> <span data-ttu-id="e01e8-112">例如, 你可能希望部署 Lync 客户端体验, 直到你组织中的用户在新的 Skype for Business 体验中进行了全面培训。</span><span class="sxs-lookup"><span data-stu-id="e01e8-112">For example, you might want to deploy the Lync client experience until users in your organization are fully trained in the new Skype for Business experience.</span></span> <span data-ttu-id="e01e8-113">或者, 如果尚未将所有用户升级到 Skype for business Server 2015, 你可能希望所有用户都具有相同的客户体验, 直到所有用户都升级到新服务器。</span><span class="sxs-lookup"><span data-stu-id="e01e8-113">Or, if you have not yet upgraded all users to Skype for Business Server 2015, you might want all users to have the same client experience until all are upgraded to the new server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e01e8-114">如果你的组织同时部署了 Skype for business Server 2015 和 Lync Server 2013, 则默认的客户端体验会有所不同, 具体取决于服务器版本和 UI 设置。</span><span class="sxs-lookup"><span data-stu-id="e01e8-114">If your organization has both Skype for Business Server 2015 and Lync Server 2013 deployed, the default client experience will differ depending on server versions and UI settings.</span></span> <span data-ttu-id="e01e8-115">当用户首次启动 Skype for business 时, 他们将始终看到 Skype for business 用户界面, 即使您已选择 Lync 用户界面也是如此。</span><span class="sxs-lookup"><span data-stu-id="e01e8-115">When users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync user interface.</span></span> <span data-ttu-id="e01e8-116">几分钟后, 系统会要求用户切换到 Lync 模式。</span><span class="sxs-lookup"><span data-stu-id="e01e8-116">After several minutes, users are asked to switch to Lync mode.</span></span> <span data-ttu-id="e01e8-117">有关更多信息，请参阅本主题后面部分的<STRONG>首次启动客户端行为</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="e01e8-117">For more information, see <STRONG>First launch client behavior</STRONG> later in this topic.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="e01e8-118">Lync 2013 客户端体验不是 Skype for business 2016 客户端版本的选项。</span><span class="sxs-lookup"><span data-stu-id="e01e8-118">The Lync 2013 client experience is not an option for Skype for Business 2016 client versions.</span></span> <span data-ttu-id="e01e8-119">在尝试将你的客户端环境配置为使用 Lync 2013 客户端之前，请检查客户端版本，以确保它不会以数字 16 开头；例如：16.x.x.x。</span><span class="sxs-lookup"><span data-stu-id="e01e8-119">Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span>



</div>

<div>

## <a name="configure-the-client-experience"></a><span data-ttu-id="e01e8-120">Configure the client experience</span><span class="sxs-lookup"><span data-stu-id="e01e8-120">Configure the client experience</span></span>

<span data-ttu-id="e01e8-121">你可以通过**将 set-csclientpolicy** Cmdlet 与 EnableSkypeUI 参数一起使用来指定你的组织中的用户将看到的客户体验。</span><span class="sxs-lookup"><span data-stu-id="e01e8-121">You can specify the client experience the users in your organization will see by using the **Set-CSClientPolicy** cmdlet with the EnableSkypeUI parameter.</span></span> <span data-ttu-id="e01e8-122">以下命令为组织中受全局策略影响的所有用户选择 Skype for Business 客户端体验 (请记住, 网站或特定于用户的策略替代全局策略):</span><span class="sxs-lookup"><span data-stu-id="e01e8-122">The following command selects the Skype for Business client experience for all users in your organization affected by the Global policy (remember, site or user-specific policies override the Global policy):</span></span>

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $true

<span data-ttu-id="e01e8-123">"下一步" 命令为组织中受全局策略影响的所有用户选择 Lync 客户端体验:</span><span class="sxs-lookup"><span data-stu-id="e01e8-123">The next command selects the Lync client experience for all users in your organization affected by the Global policy:</span></span>

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $false

<span data-ttu-id="e01e8-124">下一个命令为 Redmond 网站中的所有用户选择 Skype for Business 客户端体验:</span><span class="sxs-lookup"><span data-stu-id="e01e8-124">The next command selects the Skype for Business client experience for all users within the Redmond site:</span></span>

    Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true

<span data-ttu-id="e01e8-125">如果你想要为你的组织内的特定用户配置客户端体验, 你可以使用**set-csclientpolicy** cmdlet 创建新的用户策略, 然后使用**授予 set-csclientpolicy**将策略分配给特定用户。cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e01e8-125">If you want to configure the client experience for specific users within your organization, you can create a new user policy by using the **New-CsClientPolicy** cmdlet, and then assign the policy to specific users by using the **Grant-CsClientPolicy** cmdlet.</span></span>

<span data-ttu-id="e01e8-126">例如, 以下命令将创建一个新的客户端策略 SalesClientUI, 该策略将选择 Skype for Business 客户端体验:</span><span class="sxs-lookup"><span data-stu-id="e01e8-126">For example, the following command creates a new client policy, SalesClientUI, that selects the Skype for Business client experience:</span></span>

    New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true

<span data-ttu-id="e01e8-127">下一条命令向销售部门的所有成员分配 SalesClientUI 策略：</span><span class="sxs-lookup"><span data-stu-id="e01e8-127">The next command assigns the policy, SalesClientUI, to all members of the Sales department:</span></span>

    Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI

</div>

<div>

## <a name="first-launch-client-behaviors"></a><span data-ttu-id="e01e8-128">首次启动客户端行为</span><span class="sxs-lookup"><span data-stu-id="e01e8-128">First launch client behaviors</span></span>

<span data-ttu-id="e01e8-129">默认情况下, 当用户第一次启动 Skype for business 时, 他们将始终看到 Skype for business 用户界面, 即使你已选择了 EnableSkypeUI 参数的值 (如前面所述), 也可通过将参数的值设置为 $False 来查看 Lync 客户端体验。.</span><span class="sxs-lookup"><span data-stu-id="e01e8-129">By default, when users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the value of the EnableSkypeUI parameter to $False as described previously.</span></span> <span data-ttu-id="e01e8-130">几分钟时间后，系统将要求用户切换到 Lync 模式。</span><span class="sxs-lookup"><span data-stu-id="e01e8-130">After several minutes, users will then be asked to switch to Lync mode.</span></span>

<span data-ttu-id="e01e8-131">如果你希望在用户首次启动 Skype for Business 客户端时显示 Lync 用户界面，请在客户端更新后首次启动前执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="e01e8-131">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>

1.  <span data-ttu-id="e01e8-132">确认的值`EnableSkypeUI`是否设置为在你使用的策略中 $False, 如上文所述。</span><span class="sxs-lookup"><span data-stu-id="e01e8-132">Confirm that the value of `EnableSkypeUI` is set to $False in the policy you are using as described previously.</span></span>

2.  <span data-ttu-id="e01e8-p108">更新用户计算机上的系统注册表。 你应在用户首次启动 Skype for Business 客户端之前执行此操作，且你应仅执行一次此操作。 有关如何创建组策略对象以更新加入域的计算机上的注册表的信息，请参阅本主题后面部分内容。</span><span class="sxs-lookup"><span data-stu-id="e01e8-p108">Update the system registry on the user's computer. You should do this before the first time users launch the Skype for Business client, and you should do this only once. For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="e01e8-136">在 " \*\* \[HKEY\_当前\_用户\\软件\\Microsoft\\Office\\Lync\] **密钥" 中, 创建一个新的**二进制\*\*值。</span><span class="sxs-lookup"><span data-stu-id="e01e8-136">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\Lync\]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="e01e8-137">" **值名称**"必须为 **EnableSkypeUI**，" **值数据**"必须设为 **00 00 00 00**。</span><span class="sxs-lookup"><span data-stu-id="e01e8-137">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="e01e8-138">该注册表项应类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="e01e8-138">The key should look like the following:</span></span>
    
        [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
        "CanSharePptInCollab"=dword:00000001
        "CanShareOneNoteInCollab"=dword:00000001
        "CanAppShareInCollab"=dword:00000001
        "EnableSkypeUI"=hex:00,00,00,00

<span data-ttu-id="e01e8-139">当用户首次启动 Skype for Business 客户端时，现在将显示 Lync 用户界面。</span><span class="sxs-lookup"><span data-stu-id="e01e8-139">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>

<div>

## <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="e01e8-140">控制欢迎屏幕教程的显示</span><span class="sxs-lookup"><span data-stu-id="e01e8-140">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="e01e8-141">当用户打开 Skype for Business 客户端时, 默认行为是显示 "欢迎" 屏幕, 其中包含*大多数人所要求的7个快速提示*。</span><span class="sxs-lookup"><span data-stu-id="e01e8-141">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="e01e8-142">你可以关闭欢迎屏幕的显示，同时仍允许用户通过在客户端计算机上添加以下注册表值来访问教程：</span><span class="sxs-lookup"><span data-stu-id="e01e8-142">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>

<span data-ttu-id="e01e8-143">在 " \*\* \[HKEY\_当前\_用户\\软件\\Microsoft\\Office\\15.0\\Lync\] **密钥" 中, 创建一个新的**DWORD (32 位) 值\*\*。</span><span class="sxs-lookup"><span data-stu-id="e01e8-143">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="e01e8-144">" **值名称**"必须为 **IsBasicTutorialSeenByUser**，" **值数据**"必须设为 **1**。</span><span class="sxs-lookup"><span data-stu-id="e01e8-144">The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>

<span data-ttu-id="e01e8-145">该注册表项应类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="e01e8-145">The key should look like the following:</span></span>

    "IsBasicTutorialSeenByUser"=dword:00000001

</div>

<div>

## <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="e01e8-146">关闭客户端教程</span><span class="sxs-lookup"><span data-stu-id="e01e8-146">Turn off the client tutorial</span></span>

<span data-ttu-id="e01e8-147">如果你不希望你的用户能够访问教程，你可以使用以下注册表值关闭客户端教程：</span><span class="sxs-lookup"><span data-stu-id="e01e8-147">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>

<span data-ttu-id="e01e8-148">在 " \*\* \[HKEY\_当前\_用户\\软件\\Microsoft\\Office\\15.0\\Lync\] **密钥" 中, 创建一个新的**DWORD (32 位) 值\*\*。</span><span class="sxs-lookup"><span data-stu-id="e01e8-148">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="e01e8-149">" **值名称**"必须为 **TutorialFeatureEnabled**，" **值数据**"必须设为 **0**。</span><span class="sxs-lookup"><span data-stu-id="e01e8-149">The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>

    "TutorialFeatureEnabled"=dword:00000000

<span data-ttu-id="e01e8-150">你可以通过将" **值数据**"设为 **1** 来重新打开教程。</span><span class="sxs-lookup"><span data-stu-id="e01e8-150">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>

</div>

</div>

<div>

## <a name="default-client-experiences"></a><span data-ttu-id="e01e8-151">默认客户体验</span><span class="sxs-lookup"><span data-stu-id="e01e8-151">Default client experiences</span></span>

<span data-ttu-id="e01e8-152">如果你的组织同时部署了 Skype for business Server 2015 和 Lync Server, 则客户体验将有所不同, 具体取决于服务器版本和 Skype UI 设置。</span><span class="sxs-lookup"><span data-stu-id="e01e8-152">If your organization has both Skype for Business Server 2015 and Lync Server deployed, the client experience will differ depending on server versions and the Skype UI setting.</span></span> <span data-ttu-id="e01e8-153">下表显示了基于服务器版本和 UI 设置的初始客户端体验：</span><span class="sxs-lookup"><span data-stu-id="e01e8-153">The following table shows the initial client experience based on server version and the UI setting:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="e01e8-154">服务器版本</span><span class="sxs-lookup"><span data-stu-id="e01e8-154">Server version</span></span></p></th>
<th><p><span data-ttu-id="e01e8-155">EnableSkypeUI 设置</span><span class="sxs-lookup"><span data-stu-id="e01e8-155">EnableSkypeUI setting</span></span></p></th>
<th><p><span data-ttu-id="e01e8-156">客户端体验</span><span class="sxs-lookup"><span data-stu-id="e01e8-156">Client experience</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e01e8-157">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e01e8-157">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="e01e8-158">默认值</span><span class="sxs-lookup"><span data-stu-id="e01e8-158">Default</span></span></p></td>
<td><p><span data-ttu-id="e01e8-159">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e01e8-159">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e01e8-160">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e01e8-160">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="e01e8-161">True</span><span class="sxs-lookup"><span data-stu-id="e01e8-161">True</span></span></p></td>
<td><p><span data-ttu-id="e01e8-162">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e01e8-162">Skype for Business</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e01e8-163">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e01e8-163">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="e01e8-164">False</span><span class="sxs-lookup"><span data-stu-id="e01e8-164">False</span></span></p></td>
<td><p><span data-ttu-id="e01e8-165">用户要求切换到 Lync 模式 (如果将 UI 设置更改为 $true, 用户可以在以后切换到 Skype for Business)</span><span class="sxs-lookup"><span data-stu-id="e01e8-165">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e01e8-166">Lync Server 2010 或 Lync Server 2013 (有正确的修补程序)</span><span class="sxs-lookup"><span data-stu-id="e01e8-166">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="e01e8-167">默认值</span><span class="sxs-lookup"><span data-stu-id="e01e8-167">Default</span></span></p></td>
<td><p><span data-ttu-id="e01e8-168">用户要求切换到 Lync 模式 (如果将 UI 设置更改为 $true, 用户可以在以后切换到 Skype for Business)</span><span class="sxs-lookup"><span data-stu-id="e01e8-168">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e01e8-169">Lync Server 2010 或 Lync Server 2013 (有正确的修补程序)</span><span class="sxs-lookup"><span data-stu-id="e01e8-169">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="e01e8-170">True</span><span class="sxs-lookup"><span data-stu-id="e01e8-170">True</span></span></p></td>
<td><p><span data-ttu-id="e01e8-171">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e01e8-171">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e01e8-172">Lync Server 2010 或 Lync Server 2013 (有正确的修补程序)</span><span class="sxs-lookup"><span data-stu-id="e01e8-172">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="e01e8-173">False</span><span class="sxs-lookup"><span data-stu-id="e01e8-173">False</span></span></p></td>
<td><p><span data-ttu-id="e01e8-174">用户要求切换到 Lync 模式 (如果将 UI 设置更改为 $true, 用户可以在以后切换到 Skype for Business)</span><span class="sxs-lookup"><span data-stu-id="e01e8-174">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e01e8-175">Lync Server 2010 或 Lync Server 2013 (没有修补程序)</span><span class="sxs-lookup"><span data-stu-id="e01e8-175">Lync Server 2010 or Lync Server 2013 (without patches)</span></span></p></td>
<td><p><span data-ttu-id="e01e8-176">默认值</span><span class="sxs-lookup"><span data-stu-id="e01e8-176">Default</span></span></p></td>
<td><p><span data-ttu-id="e01e8-177">用户要求切换到 Lync 客户端体验 (用户稍后无法切换到 Skype for Business)</span><span class="sxs-lookup"><span data-stu-id="e01e8-177">User asked to switch to Lync client experience (user cannot switch to Skype for Business later)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e01e8-178">下表显示了管理员更改 Skype UI 体验的初始设置时的客户体验:</span><span class="sxs-lookup"><span data-stu-id="e01e8-178">The next table shows the client experience when the administrator changes the initial setting for the Skype UI experience:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="e01e8-179">服务器版本</span><span class="sxs-lookup"><span data-stu-id="e01e8-179">Server version</span></span></p></th>
<th><p><span data-ttu-id="e01e8-180">Skype UI 设置</span><span class="sxs-lookup"><span data-stu-id="e01e8-180">Skype UI setting</span></span></p></th>
<th><p><span data-ttu-id="e01e8-181">客户端 UI = Lync</span><span class="sxs-lookup"><span data-stu-id="e01e8-181">Client UI = Lync</span></span></p></th>
<th><p><span data-ttu-id="e01e8-182">客户端 UI = Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e01e8-182">Client UI = Skype for Business</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e01e8-183">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e01e8-183">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="e01e8-184">True</span><span class="sxs-lookup"><span data-stu-id="e01e8-184">True</span></span></p></td>
<td><p><span data-ttu-id="e01e8-185">用户要求切换到 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e01e8-185">User asked to switch to Skype for Business</span></span></p></td>
<td><p><span data-ttu-id="e01e8-186">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e01e8-186">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e01e8-187">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e01e8-187">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="e01e8-188">False</span><span class="sxs-lookup"><span data-stu-id="e01e8-188">False</span></span></p></td>
<td><p><span data-ttu-id="e01e8-189">Lync UI</span><span class="sxs-lookup"><span data-stu-id="e01e8-189">Lync UI</span></span></p></td>
<td><p><span data-ttu-id="e01e8-190">用户要求切换到 Lync UI</span><span class="sxs-lookup"><span data-stu-id="e01e8-190">User asked to switch to Lync UI</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e01e8-191">Lync Server 2010 或 Lync Server 2013 (有正确的修补程序)</span><span class="sxs-lookup"><span data-stu-id="e01e8-191">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="e01e8-192">True</span><span class="sxs-lookup"><span data-stu-id="e01e8-192">True</span></span></p></td>
<td><p><span data-ttu-id="e01e8-193">用户要求切换到 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e01e8-193">User asked to switch to Skype for Business</span></span></p></td>
<td><p><span data-ttu-id="e01e8-194">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e01e8-194">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e01e8-195">Lync Server 2010 或 Lync Server 2013 (有正确的修补程序)</span><span class="sxs-lookup"><span data-stu-id="e01e8-195">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="e01e8-196">False</span><span class="sxs-lookup"><span data-stu-id="e01e8-196">False</span></span></p></td>
<td><p><span data-ttu-id="e01e8-197">Lync UI</span><span class="sxs-lookup"><span data-stu-id="e01e8-197">Lync UI</span></span></p></td>
<td><p><span data-ttu-id="e01e8-198">用户要求切换到 Lync UI</span><span class="sxs-lookup"><span data-stu-id="e01e8-198">User asked to switch to Lync UI</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e01e8-199">Lync Server 2010 或 Lync Server 2013 (没有修补程序)</span><span class="sxs-lookup"><span data-stu-id="e01e8-199">Lync Server 2010 or Lync Server 2013 (without patches)</span></span></p></td>
<td><p><span data-ttu-id="e01e8-200">默认值</span><span class="sxs-lookup"><span data-stu-id="e01e8-200">Default</span></span></p></td>
<td><p><span data-ttu-id="e01e8-201">Lync 模式 (无法切换到 Skype for Business)</span><span class="sxs-lookup"><span data-stu-id="e01e8-201">Lync mode (cannot switch to Skype for Business)</span></span></p></td>
<td><p><span data-ttu-id="e01e8-202">Lync UI (无法切换到 Skype for Business)</span><span class="sxs-lookup"><span data-stu-id="e01e8-202">Lync UI (cannot switch to Skype for Business)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e01e8-203">管理 Skype for Business 客户端的配置所需的修补程序版本如下:</span><span class="sxs-lookup"><span data-stu-id="e01e8-203">The patch versions required to manage the configuration of the Skype for Business client are:</span></span>

  - <span data-ttu-id="e01e8-204">Lync Server 2010-Lync Server 2010 的2月2015累积更新 (4.0.7577.710)。</span><span class="sxs-lookup"><span data-stu-id="e01e8-204">Lync Server 2010 - February 2015 Cumulative Update (4.0.7577.710) for Lync Server 2010.</span></span> <span data-ttu-id="e01e8-205">有关信息, 请参阅[Lync Server 2010 更新](http://go.microsoft.com/fwlink/p/?linkid=532771)</span><span class="sxs-lookup"><span data-stu-id="e01e8-205">For information, see [Updates for Lync Server 2010](http://go.microsoft.com/fwlink/p/?linkid=532771)</span></span>

  - <span data-ttu-id="e01e8-206">Lync Server 2013-Lync Server 2013 的2014累积更新 (5.0.8308.857)。</span><span class="sxs-lookup"><span data-stu-id="e01e8-206">Lync Server 2013 - December 2014 Cumulative Update (5.0.8308.857) for Lync Server 2013.</span></span> <span data-ttu-id="e01e8-207">有关信息, 请参阅[Lync Server 2013 更新](http://go.microsoft.com/fwlink/p/?linkid=532772)。</span><span class="sxs-lookup"><span data-stu-id="e01e8-207">For information, see [Updates for Lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=532772).</span></span>

</div>

<div>

## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="e01e8-208">创建组策略对象以修改加入域的计算机上的注册表</span><span class="sxs-lookup"><span data-stu-id="e01e8-208">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="e01e8-p115">应仅执行一次注册表更新以在用户首次启动 Skype for Business 客户端时显示 Lync 客户端体验。 如果你使用组策略对象 (GPO) 更新注册表，你需要定义对象以创建新值，而非更新值数据。 应用 GPO 时，如果新值不存在，则 GPO 将创建新值并将值数据设为 0。</span><span class="sxs-lookup"><span data-stu-id="e01e8-p115">The registry update to display the Lync client experience the first time a user launches the Skype for Business client should be done only once. If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data. When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span>

<span data-ttu-id="e01e8-p116">以下过程介绍了如何修改注册表，使得在用户首次启动 Skype for Business 时显示 Lync 客户端体验。 你还可以如前文所述，使用此过程更新注册表以禁用欢迎屏幕教程。</span><span class="sxs-lookup"><span data-stu-id="e01e8-p116">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business. You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>

<span data-ttu-id="e01e8-214">**创建 GPO**</span><span class="sxs-lookup"><span data-stu-id="e01e8-214">**To create the GPO**</span></span>

1.  <span data-ttu-id="e01e8-215">启动" **组策略管理控制台**"。</span><span class="sxs-lookup"><span data-stu-id="e01e8-215">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="e01e8-216">有关如何使用组策略管理控制台的信息，请参阅[组策略管理控制台](http://go.microsoft.com/fwlink/?linkid=532759)。</span><span class="sxs-lookup"><span data-stu-id="e01e8-216">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](http://go.microsoft.com/fwlink/?linkid=532759).</span></span>

2.  <span data-ttu-id="e01e8-217">右键单击" **组策略对象**"节点，然后选择菜单上的" **新建**"。</span><span class="sxs-lookup"><span data-stu-id="e01e8-217">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>

3.  <span data-ttu-id="e01e8-218">在“**新建 GPO**”对话框中，输入 GPO 的名称，例如 **MakeLyncDefaultUI**，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="e01e8-218">In the **New GPO** dialog, enter a name for the GPO, for example, **MakeLyncDefaultUI**, and then click **OK**.</span></span>

4.  <span data-ttu-id="e01e8-219">右键单击您刚创建的新 GPO，然后在菜单上选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="e01e8-219">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>

5.  <span data-ttu-id="e01e8-220">在" **组策略管理编辑器**"中，依次展开" **用户配置**"、" **首选项**"、" **Windows 设置**"，然后选择" **注册表**"节点。</span><span class="sxs-lookup"><span data-stu-id="e01e8-220">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>

6.  <span data-ttu-id="e01e8-221">右键单击 "**注册表**" 节点, 然后选择 "**新建** \> **注册表项**"。</span><span class="sxs-lookup"><span data-stu-id="e01e8-221">Right-click on the **Registry** node, and then select **New** \> **Registry Item**.</span></span>

7.  <span data-ttu-id="e01e8-222">在“**新建注册表属性**”对话框上，更新以下内容：</span><span class="sxs-lookup"><span data-stu-id="e01e8-222">On the **New Registry Properties** dialog, update the following:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="e01e8-223">字段</span><span class="sxs-lookup"><span data-stu-id="e01e8-223">Field</span></span></th>
    <th><span data-ttu-id="e01e8-224">要选择或输入的值</span><span class="sxs-lookup"><span data-stu-id="e01e8-224">Value to select or enter</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="e01e8-225"><strong>操作</strong></span><span class="sxs-lookup"><span data-stu-id="e01e8-225"><strong>Action</strong></span></span></p></td>
    <td><p><span data-ttu-id="e01e8-226"><strong>创建</strong></span><span class="sxs-lookup"><span data-stu-id="e01e8-226"><strong>Create</strong></span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="e01e8-227"><strong>配置单元</strong></span><span class="sxs-lookup"><span data-stu-id="e01e8-227"><strong>Hive</strong></span></span></p></td>
    <td><p><span data-ttu-id="e01e8-228">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="e01e8-228">HKEY_CURRENT_USER</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="e01e8-229"><strong>键路径</strong></span><span class="sxs-lookup"><span data-stu-id="e01e8-229"><strong>Key Path</strong></span></span></p></td>
    <td><p><span data-ttu-id="e01e8-230">Software\Microsoft\Office\Lync</span><span class="sxs-lookup"><span data-stu-id="e01e8-230">Software\Microsoft\Office\Lync</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="e01e8-231"><strong>值名称</strong></span><span class="sxs-lookup"><span data-stu-id="e01e8-231"><strong>Value name</strong></span></span></p></td>
    <td><p><span data-ttu-id="e01e8-232">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="e01e8-232">EnableSkypeUI</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="e01e8-233"><strong>值类型</strong></span><span class="sxs-lookup"><span data-stu-id="e01e8-233"><strong>Value type</strong></span></span></p></td>
    <td><p><span data-ttu-id="e01e8-234">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="e01e8-234">REG_BINARY</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="e01e8-235"><strong>值数据</strong></span><span class="sxs-lookup"><span data-stu-id="e01e8-235"><strong>Value data</strong></span></span></p></td>
    <td><p><span data-ttu-id="e01e8-236">00000000</span><span class="sxs-lookup"><span data-stu-id="e01e8-236">00000000</span></span></p></td>
    </tr>
    </tbody>
    </table>


8.  <span data-ttu-id="e01e8-237">单击" **确定**"以保存更改，然后关闭 GPO。</span><span class="sxs-lookup"><span data-stu-id="e01e8-237">Click **OK** to save your changes, and then close the GPO.</span></span>

<span data-ttu-id="e01e8-238">接下来，你需要将你创建的 GPO 链接到你希望分配策略的用户组，比如 OU。</span><span class="sxs-lookup"><span data-stu-id="e01e8-238">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>

<span data-ttu-id="e01e8-239">**使用 GPO 分配策略**</span><span class="sxs-lookup"><span data-stu-id="e01e8-239">**To use the GPO to assign the policy**</span></span>

1.  <span data-ttu-id="e01e8-240">在组策略管理控制台中，右键单击要分配策略的 OU，然后选择" **链接到现有 GPO**"。</span><span class="sxs-lookup"><span data-stu-id="e01e8-240">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>

2.  <span data-ttu-id="e01e8-241">在" **选择 GPO**"对话框中，选择你创建的 GPO，然后选择" **确定**"。</span><span class="sxs-lookup"><span data-stu-id="e01e8-241">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>

3.  <span data-ttu-id="e01e8-242">在目标用户的计算机上，打开命令提示符并键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="e01e8-242">On the target user's computer, open a command prompt and type the following command:</span></span>
    
    <span data-ttu-id="e01e8-243">**gpupdate /target:user**</span><span class="sxs-lookup"><span data-stu-id="e01e8-243">**gpupdate /target:user**</span></span>
    
    <span data-ttu-id="e01e8-p117">应用 GPO 时，将显示消息"正在更新策略..."。 完成时，将显示消息"已成功完成用户策略更新"。</span><span class="sxs-lookup"><span data-stu-id="e01e8-p117">The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.</span></span>

4.  <span data-ttu-id="e01e8-246">在命令提示符下，键入下列命令：</span><span class="sxs-lookup"><span data-stu-id="e01e8-246">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="e01e8-247">**gpresult /r**</span><span class="sxs-lookup"><span data-stu-id="e01e8-247">**gpresult /r**</span></span>
    
    <span data-ttu-id="e01e8-248">你将在下面看到带有你创建的 GPO 名称的"已分配的组策略对象"。</span><span class="sxs-lookup"><span data-stu-id="e01e8-248">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>

<span data-ttu-id="e01e8-249">你可以检查注册表以确认 GPO 已成功更新用户计算机上的注册表。</span><span class="sxs-lookup"><span data-stu-id="e01e8-249">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry.</span></span> <span data-ttu-id="e01e8-250">打开注册表编辑器并导航到\*\* \[\_HKEY 当前\_用户\\软件\\Microsoft\\Office\\Lync\] \*\*密钥。</span><span class="sxs-lookup"><span data-stu-id="e01e8-250">Open Registry Editor and navigate to the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\Lync\]** key.</span></span> <span data-ttu-id="e01e8-251">如果 GPO 已成功更新注册表，你将看到名为 EnableSkypeUI 的值设为 0。</span><span class="sxs-lookup"><span data-stu-id="e01e8-251">If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

