---
title: 在 Lync Server 2013 中配置 Skype for Business 客户端
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure the client experience
ms:assetid: 61e783f1-24f4-430b-ae52-c76a4d206dc7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn954919(v=OCS.15)
ms:contentKeyID: 65227958
ms.date: 09/18/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b89457c35bc9c9c0150b84ab34f4103776206ad
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180775"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-client-experience-with-skype-for-business"></a><span data-ttu-id="2308e-102">配置 Skype for Business 的客户端体验</span><span class="sxs-lookup"><span data-stu-id="2308e-102">Configure the client experience with Skype for Business</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2308e-103">_**上次修改的主题：** 2015-09-17_</span><span class="sxs-lookup"><span data-stu-id="2308e-103">_**Topic Last Modified:** 2015-09-17_</span></span>

<span data-ttu-id="2308e-104">**摘要：** 本主题介绍如何在 Lync Server 2013 环境中为 Skype for business 客户端用户配置客户端体验。</span><span class="sxs-lookup"><span data-stu-id="2308e-104">**Summary:** This topic describes how to configure the client experience for Skype for Business client users in a Lync Server 2013 environment.</span></span> <span data-ttu-id="2308e-105">仅当您使用12月2014累积更新（5.0.8308.857）或更高版本安装了运行 Lync Server 2013 时，才能配置客户端体验。</span><span class="sxs-lookup"><span data-stu-id="2308e-105">You can configure the client experience only if you are running Lync Server 2013 with the December 2014 Cumulative Update (5.0.8308.857) or later installed.</span></span> <span data-ttu-id="2308e-106">有关更新 Lync Server 2013 的信息，请参阅[Lync server 2013 更新](https://go.microsoft.com/fwlink/p/?linkid=532651)。</span><span class="sxs-lookup"><span data-stu-id="2308e-106">For information about updating Lync Server 2013, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=532651).</span></span>

<span data-ttu-id="2308e-107">Skype for Business 提供了基于 Skype 消费者产品体验的全新用户体验。</span><span class="sxs-lookup"><span data-stu-id="2308e-107">Skype for Business provides a new user experience that is based on the Skype consumer product experience.</span></span> <span data-ttu-id="2308e-108">除 Lync 的所有功能外，Skype for Business 还提供了具有简化的控件和熟悉的图标的新功能。</span><span class="sxs-lookup"><span data-stu-id="2308e-108">In addition to all the features of Lync, Skype for Business provides new features with simplified controls and familiar icons.</span></span> <span data-ttu-id="2308e-109">有关新的客户端体验的详细信息，请参阅[Lync 现在为 Skype For business--了解新增功能](https://go.microsoft.com/fwlink/?linkid=529022)。</span><span class="sxs-lookup"><span data-stu-id="2308e-109">For detailed information about the new client experience, see [Lync is now Skype for Business -- see what's new](https://go.microsoft.com/fwlink/?linkid=529022).</span></span>

<span data-ttu-id="2308e-110">Lync Server 2013 支持新的 Skype for Business 客户端体验和 Lync 客户端体验。</span><span class="sxs-lookup"><span data-stu-id="2308e-110">Lync Server 2013 supports the new Skype for Business client experience as well as the Lync client experience.</span></span> <span data-ttu-id="2308e-111">作为管理员，你可以为你的用户选择首选的客户端体验。</span><span class="sxs-lookup"><span data-stu-id="2308e-111">As an administrator, you can choose the preferred client experience for your users.</span></span> <span data-ttu-id="2308e-112">例如，您可能希望部署 Lync 客户端体验，直到贵组织中的用户在新的 Skype for Business 体验中进行了全面培训。</span><span class="sxs-lookup"><span data-stu-id="2308e-112">For example, you might want to deploy the Lync client experience until users in your organization are fully trained in the new Skype for Business experience.</span></span> <span data-ttu-id="2308e-113">或者，如果尚未将所有用户升级到 Skype for Business Server 2015，您可能希望所有用户都具有相同的客户端体验，直至所有用户都已升级到新服务器。</span><span class="sxs-lookup"><span data-stu-id="2308e-113">Or, if you have not yet upgraded all users to Skype for Business Server 2015, you might want all users to have the same client experience until all are upgraded to the new server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2308e-114">如果你的组织同时部署了 Skype for Business Server 2015 和 Lync Server 2013，则默认的客户端体验会有所不同，具体取决于服务器版本和 UI 设置。</span><span class="sxs-lookup"><span data-stu-id="2308e-114">If your organization has both Skype for Business Server 2015 and Lync Server 2013 deployed, the default client experience will differ depending on server versions and UI settings.</span></span> <span data-ttu-id="2308e-115">当用户首次启动 Skype for business 时，他们将始终看到 Skype for Business 用户界面，即使您已选择 Lync 用户界面也是如此。</span><span class="sxs-lookup"><span data-stu-id="2308e-115">When users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync user interface.</span></span> <span data-ttu-id="2308e-116">几分钟后，系统会要求用户切换到 Lync 模式。</span><span class="sxs-lookup"><span data-stu-id="2308e-116">After several minutes, users are asked to switch to Lync mode.</span></span> <span data-ttu-id="2308e-117">有关详细信息，请参阅本主题后面的<STRONG>首次启动客户端行为</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="2308e-117">For more information, see <STRONG>First launch client behavior</STRONG> later in this topic.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="2308e-118">Lync 2013 客户端体验不是 Skype for business 2016 客户端版本的选项。</span><span class="sxs-lookup"><span data-stu-id="2308e-118">The Lync 2013 client experience is not an option for Skype for Business 2016 client versions.</span></span> <span data-ttu-id="2308e-119">在尝试将客户端环境配置为使用 Lync 2013 客户端之前，请检查客户端版本以确保其不以数字16开头;例如： x.x.x。</span><span class="sxs-lookup"><span data-stu-id="2308e-119">Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span>



</div>

<div>

## <a name="configure-the-client-experience"></a><span data-ttu-id="2308e-120">配置客户端体验</span><span class="sxs-lookup"><span data-stu-id="2308e-120">Configure the client experience</span></span>

<span data-ttu-id="2308e-121">您可以通过将**set-csclientpolicy** Cmdlet 与 EnableSkypeUI 参数一起使用，指定组织中的用户将看到的客户端体验。</span><span class="sxs-lookup"><span data-stu-id="2308e-121">You can specify the client experience the users in your organization will see by using the **Set-CSClientPolicy** cmdlet with the EnableSkypeUI parameter.</span></span> <span data-ttu-id="2308e-122">以下命令为组织中受全局策略影响的所有用户选择 Skype for Business 客户端体验（请记住，站点或用户特定的策略会覆盖全局策略）：</span><span class="sxs-lookup"><span data-stu-id="2308e-122">The following command selects the Skype for Business client experience for all users in your organization affected by the Global policy (remember, site or user-specific policies override the Global policy):</span></span>

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $true

<span data-ttu-id="2308e-123">下一条命令为组织中受全局策略影响的所有用户选择 Lync 客户端体验：</span><span class="sxs-lookup"><span data-stu-id="2308e-123">The next command selects the Lync client experience for all users in your organization affected by the Global policy:</span></span>

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $false

<span data-ttu-id="2308e-124">下一个命令为 Redmond 站点内的所有用户选择 Skype for Business 客户端体验：</span><span class="sxs-lookup"><span data-stu-id="2308e-124">The next command selects the Skype for Business client experience for all users within the Redmond site:</span></span>

    Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true

<span data-ttu-id="2308e-125">如果要为组织中的特定用户配置客户端体验，可以使用**set-csclientpolicy** cmdlet 创建新的用户策略，然后使用**set-csclientpolicy** cmdlet 将策略分配给特定用户。</span><span class="sxs-lookup"><span data-stu-id="2308e-125">If you want to configure the client experience for specific users within your organization, you can create a new user policy by using the **New-CsClientPolicy** cmdlet, and then assign the policy to specific users by using the **Grant-CsClientPolicy** cmdlet.</span></span>

<span data-ttu-id="2308e-126">例如，以下命令将创建一个新的客户端策略 SalesClientUI，该策略选择 Skype for Business 客户端体验：</span><span class="sxs-lookup"><span data-stu-id="2308e-126">For example, the following command creates a new client policy, SalesClientUI, that selects the Skype for Business client experience:</span></span>

    New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true

<span data-ttu-id="2308e-127">下一个命令将策略 SalesClientUI 分配给销售部门的所有成员：</span><span class="sxs-lookup"><span data-stu-id="2308e-127">The next command assigns the policy, SalesClientUI, to all members of the Sales department:</span></span>

    Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI

</div>

<div>

## <a name="first-launch-client-behaviors"></a><span data-ttu-id="2308e-128">首次启动客户端行为</span><span class="sxs-lookup"><span data-stu-id="2308e-128">First launch client behaviors</span></span>

<span data-ttu-id="2308e-129">默认情况下，当用户首次启动 Skype for business 时，他们将始终看到 Skype for Business 用户界面，即使您已通过将 EnableSkypeUI 参数的值设置为 $False （如上文所述）选择了 Lync 客户端体验，也是如此.</span><span class="sxs-lookup"><span data-stu-id="2308e-129">By default, when users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the value of the EnableSkypeUI parameter to $False as described previously.</span></span> <span data-ttu-id="2308e-130">几分钟后，系统会要求用户切换到 Lync 模式。</span><span class="sxs-lookup"><span data-stu-id="2308e-130">After several minutes, users will then be asked to switch to Lync mode.</span></span>

<span data-ttu-id="2308e-131">如果您想要在用户首次启动 Skype for Business 客户端时显示 Lync 用户界面，请在更新客户端后第一次启动时，按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="2308e-131">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>

1.  <span data-ttu-id="2308e-132">确认 "" 的`EnableSkypeUI`值设置为 "在您正在使用的策略中 $False"，如上文所述。</span><span class="sxs-lookup"><span data-stu-id="2308e-132">Confirm that the value of `EnableSkypeUI` is set to $False in the policy you are using as described previously.</span></span>

2.  <span data-ttu-id="2308e-133">更新用户计算机上的系统注册表。</span><span class="sxs-lookup"><span data-stu-id="2308e-133">Update the system registry on the user's computer.</span></span> <span data-ttu-id="2308e-134">你应在用户首次启动 Skype for Business 客户端之前执行此操作，并且应仅执行一次此操作。</span><span class="sxs-lookup"><span data-stu-id="2308e-134">You should do this before the first time users launch the Skype for Business client, and you should do this only once.</span></span> <span data-ttu-id="2308e-135">有关如何创建组策略对象以更新加入域的计算机上的注册表的信息，请参阅本主题后面的部分。</span><span class="sxs-lookup"><span data-stu-id="2308e-135">For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="2308e-136">在 " \*\* \[HKEY\_当前\_用户\\软件\\Microsoft\\Office\\Lync\] **密钥" 中，创建新的**二进制\*\*值。</span><span class="sxs-lookup"><span data-stu-id="2308e-136">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\Lync\]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="2308e-137">**值名称**必须为**EnableSkypeUI**，并且**值数据**必须设置为**00 00 00 00**。</span><span class="sxs-lookup"><span data-stu-id="2308e-137">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="2308e-138">该注册表项应类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="2308e-138">The key should look like the following:</span></span>
    
        [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
        "CanSharePptInCollab"=dword:00000001
        "CanShareOneNoteInCollab"=dword:00000001
        "CanAppShareInCollab"=dword:00000001
        "EnableSkypeUI"=hex:00,00,00,00

<span data-ttu-id="2308e-139">在用户首次启动 Skype for Business 客户端时，将显示 Lync 用户界面。</span><span class="sxs-lookup"><span data-stu-id="2308e-139">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>

<div>

## <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="2308e-140">控制欢迎屏幕教程的显示</span><span class="sxs-lookup"><span data-stu-id="2308e-140">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="2308e-141">当用户打开 Skype for Business 客户端时，默认行为是显示欢迎屏幕，其中包括*大多数用户要求的7条快速提示*。</span><span class="sxs-lookup"><span data-stu-id="2308e-141">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="2308e-142">您可以关闭欢迎屏幕的显示，但仍允许用户通过在客户端计算机上添加以下注册表值来访问教程：</span><span class="sxs-lookup"><span data-stu-id="2308e-142">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>

<span data-ttu-id="2308e-143">在 " \*\* \[HKEY\_当前\_用户\\软件\\Microsoft\\Office\\15.0\\Lync\] **密钥" 中，创建新的**DWORD （32位）值\*\*。</span><span class="sxs-lookup"><span data-stu-id="2308e-143">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="2308e-144">**值名称**必须为**IsBasicTutorialSeenByUser**，并且**值 data**必须设置为**1**。</span><span class="sxs-lookup"><span data-stu-id="2308e-144">The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>

<span data-ttu-id="2308e-145">该注册表项应类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="2308e-145">The key should look like the following:</span></span>

    "IsBasicTutorialSeenByUser"=dword:00000001

</div>

<div>

## <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="2308e-146">关闭客户端教程</span><span class="sxs-lookup"><span data-stu-id="2308e-146">Turn off the client tutorial</span></span>

<span data-ttu-id="2308e-147">如果您不希望您的用户能够访问教程，则可以使用以下注册表值关闭客户端教程：</span><span class="sxs-lookup"><span data-stu-id="2308e-147">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>

<span data-ttu-id="2308e-148">在 " \*\* \[HKEY\_当前\_用户\\软件\\Microsoft\\Office\\15.0\\Lync\] **密钥" 中，创建新的**DWORD （32位）值\*\*。</span><span class="sxs-lookup"><span data-stu-id="2308e-148">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="2308e-149">**值名称**必须为**TutorialFeatureEnabled**，并且**值 data**必须设置为**0**。</span><span class="sxs-lookup"><span data-stu-id="2308e-149">The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>

    "TutorialFeatureEnabled"=dword:00000000

<span data-ttu-id="2308e-150">您可以通过将**值数据**设置为**1**来重新打开教程。</span><span class="sxs-lookup"><span data-stu-id="2308e-150">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>

</div>

</div>

<div>

## <a name="default-client-experiences"></a><span data-ttu-id="2308e-151">默认客户端体验</span><span class="sxs-lookup"><span data-stu-id="2308e-151">Default client experiences</span></span>

<span data-ttu-id="2308e-152">如果你的组织同时部署了 Skype for Business Server 2015 和 Lync Server，则客户端体验会有所不同，具体取决于服务器版本和 Skype UI 设置。</span><span class="sxs-lookup"><span data-stu-id="2308e-152">If your organization has both Skype for Business Server 2015 and Lync Server deployed, the client experience will differ depending on server versions and the Skype UI setting.</span></span> <span data-ttu-id="2308e-153">下表显示了基于服务器版本和 UI 设置的初始客户端体验：</span><span class="sxs-lookup"><span data-stu-id="2308e-153">The following table shows the initial client experience based on server version and the UI setting:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="2308e-154">服务器版本</span><span class="sxs-lookup"><span data-stu-id="2308e-154">Server version</span></span></p></th>
<th><p><span data-ttu-id="2308e-155">EnableSkypeUI 设置</span><span class="sxs-lookup"><span data-stu-id="2308e-155">EnableSkypeUI setting</span></span></p></th>
<th><p><span data-ttu-id="2308e-156">客户端体验</span><span class="sxs-lookup"><span data-stu-id="2308e-156">Client experience</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2308e-157">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2308e-157">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="2308e-158">默认值</span><span class="sxs-lookup"><span data-stu-id="2308e-158">Default</span></span></p></td>
<td><p><span data-ttu-id="2308e-159">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2308e-159">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2308e-160">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2308e-160">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="2308e-161">True</span><span class="sxs-lookup"><span data-stu-id="2308e-161">True</span></span></p></td>
<td><p><span data-ttu-id="2308e-162">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2308e-162">Skype for Business</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2308e-163">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2308e-163">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="2308e-164">False</span><span class="sxs-lookup"><span data-stu-id="2308e-164">False</span></span></p></td>
<td><p><span data-ttu-id="2308e-165">用户需要切换到 Lync 模式（如果将 UI 设置更改为 $true，用户可以在稍后切换到 Skype for Business）</span><span class="sxs-lookup"><span data-stu-id="2308e-165">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2308e-166">Lync Server 2010 或 Lync Server 2013 （带有正确的修补程序）</span><span class="sxs-lookup"><span data-stu-id="2308e-166">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="2308e-167">默认值</span><span class="sxs-lookup"><span data-stu-id="2308e-167">Default</span></span></p></td>
<td><p><span data-ttu-id="2308e-168">用户需要切换到 Lync 模式（如果将 UI 设置更改为 $true，用户可以在稍后切换到 Skype for Business）</span><span class="sxs-lookup"><span data-stu-id="2308e-168">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2308e-169">Lync Server 2010 或 Lync Server 2013 （带有正确的修补程序）</span><span class="sxs-lookup"><span data-stu-id="2308e-169">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="2308e-170">True</span><span class="sxs-lookup"><span data-stu-id="2308e-170">True</span></span></p></td>
<td><p><span data-ttu-id="2308e-171">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2308e-171">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2308e-172">Lync Server 2010 或 Lync Server 2013 （带有正确的修补程序）</span><span class="sxs-lookup"><span data-stu-id="2308e-172">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="2308e-173">False</span><span class="sxs-lookup"><span data-stu-id="2308e-173">False</span></span></p></td>
<td><p><span data-ttu-id="2308e-174">用户需要切换到 Lync 模式（如果将 UI 设置更改为 $true，用户可以在稍后切换到 Skype for Business）</span><span class="sxs-lookup"><span data-stu-id="2308e-174">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2308e-175">Lync Server 2010 或 Lync Server 2013 （无修补程序）</span><span class="sxs-lookup"><span data-stu-id="2308e-175">Lync Server 2010 or Lync Server 2013 (without patches)</span></span></p></td>
<td><p><span data-ttu-id="2308e-176">默认值</span><span class="sxs-lookup"><span data-stu-id="2308e-176">Default</span></span></p></td>
<td><p><span data-ttu-id="2308e-177">用户要求切换到 Lync 客户端体验（用户稍后无法切换到 Skype for Business）</span><span class="sxs-lookup"><span data-stu-id="2308e-177">User asked to switch to Lync client experience (user cannot switch to Skype for Business later)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2308e-178">下表显示管理员更改 Skype UI 体验的初始设置时的客户端体验：</span><span class="sxs-lookup"><span data-stu-id="2308e-178">The next table shows the client experience when the administrator changes the initial setting for the Skype UI experience:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="2308e-179">服务器版本</span><span class="sxs-lookup"><span data-stu-id="2308e-179">Server version</span></span></p></th>
<th><p><span data-ttu-id="2308e-180">Skype UI 设置</span><span class="sxs-lookup"><span data-stu-id="2308e-180">Skype UI setting</span></span></p></th>
<th><p><span data-ttu-id="2308e-181">客户端 UI = Lync</span><span class="sxs-lookup"><span data-stu-id="2308e-181">Client UI = Lync</span></span></p></th>
<th><p><span data-ttu-id="2308e-182">客户端 UI = Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2308e-182">Client UI = Skype for Business</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2308e-183">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2308e-183">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="2308e-184">True</span><span class="sxs-lookup"><span data-stu-id="2308e-184">True</span></span></p></td>
<td><p><span data-ttu-id="2308e-185">用户需要切换到 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2308e-185">User asked to switch to Skype for Business</span></span></p></td>
<td><p><span data-ttu-id="2308e-186">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2308e-186">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2308e-187">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2308e-187">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="2308e-188">False</span><span class="sxs-lookup"><span data-stu-id="2308e-188">False</span></span></p></td>
<td><p><span data-ttu-id="2308e-189">Lync UI</span><span class="sxs-lookup"><span data-stu-id="2308e-189">Lync UI</span></span></p></td>
<td><p><span data-ttu-id="2308e-190">用户要求切换到 Lync UI</span><span class="sxs-lookup"><span data-stu-id="2308e-190">User asked to switch to Lync UI</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2308e-191">Lync Server 2010 或 Lync Server 2013 （带有正确的修补程序）</span><span class="sxs-lookup"><span data-stu-id="2308e-191">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="2308e-192">True</span><span class="sxs-lookup"><span data-stu-id="2308e-192">True</span></span></p></td>
<td><p><span data-ttu-id="2308e-193">用户需要切换到 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2308e-193">User asked to switch to Skype for Business</span></span></p></td>
<td><p><span data-ttu-id="2308e-194">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2308e-194">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2308e-195">Lync Server 2010 或 Lync Server 2013 （带有正确的修补程序）</span><span class="sxs-lookup"><span data-stu-id="2308e-195">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="2308e-196">False</span><span class="sxs-lookup"><span data-stu-id="2308e-196">False</span></span></p></td>
<td><p><span data-ttu-id="2308e-197">Lync UI</span><span class="sxs-lookup"><span data-stu-id="2308e-197">Lync UI</span></span></p></td>
<td><p><span data-ttu-id="2308e-198">用户要求切换到 Lync UI</span><span class="sxs-lookup"><span data-stu-id="2308e-198">User asked to switch to Lync UI</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2308e-199">Lync Server 2010 或 Lync Server 2013 （无修补程序）</span><span class="sxs-lookup"><span data-stu-id="2308e-199">Lync Server 2010 or Lync Server 2013 (without patches)</span></span></p></td>
<td><p><span data-ttu-id="2308e-200">默认值</span><span class="sxs-lookup"><span data-stu-id="2308e-200">Default</span></span></p></td>
<td><p><span data-ttu-id="2308e-201">Lync 模式（无法切换到 Skype for Business）</span><span class="sxs-lookup"><span data-stu-id="2308e-201">Lync mode (cannot switch to Skype for Business)</span></span></p></td>
<td><p><span data-ttu-id="2308e-202">Lync UI （无法切换到 Skype for Business）</span><span class="sxs-lookup"><span data-stu-id="2308e-202">Lync UI (cannot switch to Skype for Business)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2308e-203">管理 Skype for Business 客户端的配置所需的修补程序版本包括：</span><span class="sxs-lookup"><span data-stu-id="2308e-203">The patch versions required to manage the configuration of the Skype for Business client are:</span></span>

  - <span data-ttu-id="2308e-204">Lync Server 2010-Lync Server 2010 的二月份2015累积更新（4.0.7577.710）。</span><span class="sxs-lookup"><span data-stu-id="2308e-204">Lync Server 2010 - February 2015 Cumulative Update (4.0.7577.710) for Lync Server 2010.</span></span> <span data-ttu-id="2308e-205">有关信息，请参阅[Lync Server 2010 更新](https://go.microsoft.com/fwlink/p/?linkid=532771)</span><span class="sxs-lookup"><span data-stu-id="2308e-205">For information, see [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkid=532771)</span></span>

  - <span data-ttu-id="2308e-206">Lync Server 2013-Lync Server 2013 的12月2014累积更新（5.0.8308.857）。</span><span class="sxs-lookup"><span data-stu-id="2308e-206">Lync Server 2013 - December 2014 Cumulative Update (5.0.8308.857) for Lync Server 2013.</span></span> <span data-ttu-id="2308e-207">有关信息，请参阅[Lync Server 2013 更新](https://go.microsoft.com/fwlink/p/?linkid=532772)。</span><span class="sxs-lookup"><span data-stu-id="2308e-207">For information, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=532772).</span></span>

</div>

<div>

## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="2308e-208">创建组策略对象以修改加入域的计算机上的注册表</span><span class="sxs-lookup"><span data-stu-id="2308e-208">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="2308e-209">在用户首次启动 Skype for Business 客户端时，要显示 Lync 客户端体验的注册表更新应仅执行一次。</span><span class="sxs-lookup"><span data-stu-id="2308e-209">The registry update to display the Lync client experience the first time a user launches the Skype for Business client should be done only once.</span></span> <span data-ttu-id="2308e-210">如果使用组策略对象（GPO）更新注册表，则需要定义对象以创建新值，而不是更新值数据。</span><span class="sxs-lookup"><span data-stu-id="2308e-210">If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data.</span></span> <span data-ttu-id="2308e-211">应用 GPO 时，如果新值不存在，GPO 将创建它并将值数据设置为0。</span><span class="sxs-lookup"><span data-stu-id="2308e-211">When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span>

<span data-ttu-id="2308e-212">以下过程介绍如何修改注册表，以便在用户首次启动 Skype for Business 时显示 Lync 客户端体验。</span><span class="sxs-lookup"><span data-stu-id="2308e-212">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business.</span></span> <span data-ttu-id="2308e-213">您还可以使用此过程更新注册表以禁用欢迎屏幕教程（如上文所述）。</span><span class="sxs-lookup"><span data-stu-id="2308e-213">You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>

<span data-ttu-id="2308e-214">**创建 GPO**</span><span class="sxs-lookup"><span data-stu-id="2308e-214">**To create the GPO**</span></span>

1.  <span data-ttu-id="2308e-215">启动 "**组策略管理控制台**"。</span><span class="sxs-lookup"><span data-stu-id="2308e-215">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="2308e-216">有关如何使用组策略管理控制台的信息，请参阅[组策略管理控制台](https://go.microsoft.com/fwlink/?linkid=532759)。</span><span class="sxs-lookup"><span data-stu-id="2308e-216">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](https://go.microsoft.com/fwlink/?linkid=532759).</span></span>

2.  <span data-ttu-id="2308e-217">右键单击 "**组策略对象**" 节点，然后在菜单上选择 "**新建**"。</span><span class="sxs-lookup"><span data-stu-id="2308e-217">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>

3.  <span data-ttu-id="2308e-218">在 "**新建 GPO** " 对话框中，输入 GPO 的名称，例如 "**例如 makelyncdefaultui**"，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="2308e-218">In the **New GPO** dialog, enter a name for the GPO, for example, **MakeLyncDefaultUI**, and then click **OK**.</span></span>

4.  <span data-ttu-id="2308e-219">右键单击刚创建的新 GPO，然后从菜单中选择 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="2308e-219">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>

5.  <span data-ttu-id="2308e-220">在**组策略管理编辑器**中，展开 **"用户配置**"，展开 "**首选项**"，展开 " **Windows 设置**"，然后选择 "**注册表**" 节点。</span><span class="sxs-lookup"><span data-stu-id="2308e-220">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>

6.  <span data-ttu-id="2308e-221">右键单击 "**注册表**" 节点，然后选择 "**新建** \> **注册表项**"。</span><span class="sxs-lookup"><span data-stu-id="2308e-221">Right-click on the **Registry** node, and then select **New** \> **Registry Item**.</span></span>

7.  <span data-ttu-id="2308e-222">在 "**新建注册表属性**" 对话框中，更新以下内容：</span><span class="sxs-lookup"><span data-stu-id="2308e-222">On the **New Registry Properties** dialog, update the following:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="2308e-223">字段</span><span class="sxs-lookup"><span data-stu-id="2308e-223">Field</span></span></th>
    <th><span data-ttu-id="2308e-224">要选择或输入的值</span><span class="sxs-lookup"><span data-stu-id="2308e-224">Value to select or enter</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="2308e-225"><strong>操作</strong></span><span class="sxs-lookup"><span data-stu-id="2308e-225"><strong>Action</strong></span></span></p></td>
    <td><p><span data-ttu-id="2308e-226"><strong>创建</strong></span><span class="sxs-lookup"><span data-stu-id="2308e-226"><strong>Create</strong></span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="2308e-227"><strong>配置单元</strong></span><span class="sxs-lookup"><span data-stu-id="2308e-227"><strong>Hive</strong></span></span></p></td>
    <td><p><span data-ttu-id="2308e-228">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="2308e-228">HKEY_CURRENT_USER</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="2308e-229"><strong>键路径</strong></span><span class="sxs-lookup"><span data-stu-id="2308e-229"><strong>Key Path</strong></span></span></p></td>
    <td><p><span data-ttu-id="2308e-230">Software\Microsoft\Office\Lync</span><span class="sxs-lookup"><span data-stu-id="2308e-230">Software\Microsoft\Office\Lync</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="2308e-231"><strong>值名称</strong></span><span class="sxs-lookup"><span data-stu-id="2308e-231"><strong>Value name</strong></span></span></p></td>
    <td><p><span data-ttu-id="2308e-232">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="2308e-232">EnableSkypeUI</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="2308e-233"><strong>值类型</strong></span><span class="sxs-lookup"><span data-stu-id="2308e-233"><strong>Value type</strong></span></span></p></td>
    <td><p><span data-ttu-id="2308e-234">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="2308e-234">REG_BINARY</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="2308e-235"><strong>值数据</strong></span><span class="sxs-lookup"><span data-stu-id="2308e-235"><strong>Value data</strong></span></span></p></td>
    <td><p><span data-ttu-id="2308e-236">00000000</span><span class="sxs-lookup"><span data-stu-id="2308e-236">00000000</span></span></p></td>
    </tr>
    </tbody>
    </table>


8.  <span data-ttu-id="2308e-237">单击 **"确定"** 以保存所做的更改，然后关闭该 GPO。</span><span class="sxs-lookup"><span data-stu-id="2308e-237">Click **OK** to save your changes, and then close the GPO.</span></span>

<span data-ttu-id="2308e-238">接下来，您需要将您创建的 GPO 链接到您要为其分配策略的用户组，例如 OU。</span><span class="sxs-lookup"><span data-stu-id="2308e-238">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>

<span data-ttu-id="2308e-239">**使用 GPO 分配策略**</span><span class="sxs-lookup"><span data-stu-id="2308e-239">**To use the GPO to assign the policy**</span></span>

1.  <span data-ttu-id="2308e-240">在组策略管理控制台中，右键单击要为其分配策略的 OU，然后选择 "**链接到现有 GPO**"。</span><span class="sxs-lookup"><span data-stu-id="2308e-240">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>

2.  <span data-ttu-id="2308e-241">在 "**选择 gpo** " 对话框中，选择您创建的 GPO，然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="2308e-241">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>

3.  <span data-ttu-id="2308e-242">在目标用户的计算机上，打开命令提示符并键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="2308e-242">On the target user's computer, open a command prompt and type the following command:</span></span>
    
    <span data-ttu-id="2308e-243">**gpupdate/target： user**</span><span class="sxs-lookup"><span data-stu-id="2308e-243">**gpupdate /target:user**</span></span>
    
    <span data-ttu-id="2308e-244">邮件 "正在更新策略 ..."在应用 GPO 时显示。</span><span class="sxs-lookup"><span data-stu-id="2308e-244">The message "Updating policy..." is displayed while the GPO is applied.</span></span> <span data-ttu-id="2308e-245">完成后，将显示消息 "已成功完成用户策略更新"。</span><span class="sxs-lookup"><span data-stu-id="2308e-245">When it is completed, the message "User Policy update has completed successfully" is displayed.</span></span>

4.  <span data-ttu-id="2308e-246">在命令提示符处，键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="2308e-246">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="2308e-247">**gpresult/r**</span><span class="sxs-lookup"><span data-stu-id="2308e-247">**gpresult /r**</span></span>
    
    <span data-ttu-id="2308e-248">您应该会看到 "分配的组策略对象"，其名称如下所示：您创建的 GPO 的名称。</span><span class="sxs-lookup"><span data-stu-id="2308e-248">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>

<span data-ttu-id="2308e-249">您还可以通过检查注册表来验证 GPO 是否已成功更新用户计算机上的注册表。</span><span class="sxs-lookup"><span data-stu-id="2308e-249">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry.</span></span> <span data-ttu-id="2308e-250">打开注册表编辑器并导航到\*\* \[\_HKEY CURRENT\_USER\\Software\\Microsoft\\Office\\Lync\] \*\* key。</span><span class="sxs-lookup"><span data-stu-id="2308e-250">Open Registry Editor and navigate to the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\Lync\]** key.</span></span> <span data-ttu-id="2308e-251">如果 GPO 已成功更新注册表，您将看到一个名为 EnableSkypeUI 的值，值为0。</span><span class="sxs-lookup"><span data-stu-id="2308e-251">If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

