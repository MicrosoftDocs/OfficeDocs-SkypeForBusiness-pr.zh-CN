---
title: 在 Skype for Business 与 Lync 客户端用户界面之间切换
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: a2394a4c-7522-484c-a047-7b3289742be0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: None
ms.custom:
- Setup
description: 'Learn how to switch between Skype for Business and Lync client user interfaces using PowerShell in Office 365 '
ms.openlocfilehash: 5458fb4838ce2e7847a49caa31f92d2151e2a382
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2018
---
# <a name="switching-between-the-skype-for-business-and-the-lync-client-user-interfaces"></a><span data-ttu-id="03bef-103">在 Skype for Business 与 Lync 客户端用户界面之间切换</span><span class="sxs-lookup"><span data-stu-id="03bef-103">Switching between the Skype for Business and the Lync client user interfaces</span></span>

<span data-ttu-id="03bef-104">对于 Skype for Business Online 组织，你可以使用 Office 365 中的 Remote PowerShell 让你的 Skype for Business 用户使用 Skype for Business 客户端或 Skype for Business (Lync) 客户端用户界面。</span><span class="sxs-lookup"><span data-stu-id="03bef-104">For Skype for Business Online organizations, you can use the Remote PowerShell in Office 365 to enable your Skype for Business users to use the Skype for Business client or the Skype for Business (Lync) client user interface.</span></span> <span data-ttu-id="03bef-105">默认设置是让用户使用 Skype for Business 客户端用户界面。</span><span class="sxs-lookup"><span data-stu-id="03bef-105">The default setting is for users to use the Skype for Business client user interface.</span></span> <span data-ttu-id="03bef-106">如果您希望使用 Lync 客户端体验，您可以管理第一个启动的客户端行为可按照本主题中后面的步骤中显示 Lync 用户界面。</span><span class="sxs-lookup"><span data-stu-id="03bef-106">If you'd prefer to use the Lync client experience, you can manage the first launch client behavior to display the Lync user interface by following the steps later in this topic.</span></span>
  
> [!NOTE]
> <span data-ttu-id="03bef-p102">[!注释] Lync 2013 客户端体验不是 Skype for Business 2016 客户端版本的一个选项。 在尝试将你的客户端环境配置为使用 Lync 2013 客户端之前，请检查客户端版本，以确保它不会以数字 16 开头；例如：16.x.x.x。</span><span class="sxs-lookup"><span data-stu-id="03bef-p102">The Lync 2013 client experience isn't an option for Skype for Business 2016 client versions. Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span> 
  
> [!TIP]
> <span data-ttu-id="03bef-109">[!提示] 如果希望轻松切换用户界面，不希望执行手动步骤，请访问 [Microsoft 下载中心](https://go.microsoft.com/fwlink/?LinkId=532431)以获取 PowerShell 脚本来简化操作。</span><span class="sxs-lookup"><span data-stu-id="03bef-109">If you want to easily switch the user interface and don't want to do the manual steps, see the [Microsoft Download Center ](https://go.microsoft.com/fwlink/?LinkId=532431) for a PowerShell script to make it easier.</span></span>
  
## <a name="switching-the-skype-for-business-user-interface-for-users"></a><span data-ttu-id="03bef-110">切换用户的 Skype for Business 用户界面</span><span class="sxs-lookup"><span data-stu-id="03bef-110">Switching the Skype for Business user interface for users</span></span>

<span data-ttu-id="03bef-p103">适用于 Skype for Business Online 的 Windows PowerShell 模块让你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。 此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。 有关其他信息，请参阅[为你的计算机配置 Skype for Business Online 管理](https://go.microsoft.com/fwlink/?LinkId=534539)。</span><span class="sxs-lookup"><span data-stu-id="03bef-p103">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). For other information, see [Configuring your computer for Skype for Business Online management](https://go.microsoft.com/fwlink/?LinkId=534539).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="03bef-p104">[!重要信息] 用于切换用户界面的  _Global_ 策略设置不会应用于已经应用了自定义设置的用户。 需要为已经应用了自定义策略的每位用户运行下面的命令，才能更改其用户界面：</span><span class="sxs-lookup"><span data-stu-id="03bef-p104">The  _Global_ policy setting for switching the user interface won't be applied to a user that already has a custom policy applied. To be able to change the user interface, you will need to run the following for each user that has a custom policy applied:</span></span>
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

> [!CAUTION]
> <span data-ttu-id="03bef-116">[!警告]  _ClientPolicyEnableSkypeUI_ 策略将替换用户的现有自定义策略设置。</span><span class="sxs-lookup"><span data-stu-id="03bef-116">The  _ClientPolicyEnableSkypeUI_ policy will replace the existing custom policy setting for the user.</span></span>
  
<span data-ttu-id="03bef-117">要让贵组织中的所有用户使用 Skype for Business 客户端，请打开 Remote PowerShell 并键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="03bef-117">To enable all of the users in your organization to use the Skype for Business client, open the Remote PowerShell and type the following:</span></span>
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

<span data-ttu-id="03bef-118">如果策略设置正确，您将看到：</span><span class="sxs-lookup"><span data-stu-id="03bef-118">If you set the policy right, you will see:</span></span>
  
![PowerShell: SkypeUIEnabled](../images/b6b9d2e1-1a37-46df-9757-f81c6054e93b.png)
  
<span data-ttu-id="03bef-120">要让贵组织中的所有用户使用 Skype for Business (Lync) 客户端，请打开 Remote PowerShell 并键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="03bef-120">To enable all of the users in your organization to use the Skype for Business (Lync) client, open the Remote PowerShell and type the following:</span></span> 
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

<span data-ttu-id="03bef-121">如果策略设置正确，您将看到：</span><span class="sxs-lookup"><span data-stu-id="03bef-121">If you set the policy right, you will see:</span></span>
  
![PowerShell: SkypeUIDisabled](../images/f14ec3ce-4eb8-4a11-826e-6029043ed054.png)
  
<span data-ttu-id="03bef-123">要让贵组织中的单个用户使用 Skype for Business 客户端，请打开 Remote PowerShell 并键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="03bef-123">To allow a single user in your organization to use the Skype for Business client, open the Remote PowerShell and type the following:</span></span>
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

<span data-ttu-id="03bef-124">如果策略设置正确，您将看到：</span><span class="sxs-lookup"><span data-stu-id="03bef-124">If you set the policy right, you will see:</span></span>
  
![Skype for Business Online - 启用 UI](../images/596aef69-41dc-4e1e-b689-2b7009ae58a1.png)
  
<span data-ttu-id="03bef-126">要让贵组织中的单个用户使用 Skype for Business (Lync) 客户端，请打开 Remote PowerShell 并键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="03bef-126">To allow a single user in your organization to use the Skype for Business (Lync) client, open the Remote PowerShell and type the following:</span></span>
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI -Identity <username>
```

<span data-ttu-id="03bef-127">如果策略设置正确，您将看到：</span><span class="sxs-lookup"><span data-stu-id="03bef-127">If you set the policy right, you will see:</span></span>
  
![Skype for Business Online - UI 已禁用](../images/61c645e0-67fc-4e03-803c-b7028a47dae3.png)
  
<span data-ttu-id="03bef-129">要让贵组织中的多个用户使用 Skype for Business 客户端，请打开 Remote PowerShell 并键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="03bef-129">To allow multiple users in your organization to use the Skype for Business client, open the Remote PowerShell and type the following:</span></span>
  

```
$users = @("sip:bob@contoso.com","sip:fred@contoso.com") 

$users | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

<span data-ttu-id="03bef-130">要让贵组织中的多个用户使用 Skype for Business (Lync) 客户端，请打开 Remote PowerShell 并键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="03bef-130">To allow multiple users in your organization to use the Skype for Business (Lync) client, open the Remote PowerShell and type the following:</span></span>
  
```
$users = @("sip:bob@contoso.com","sip:fred@contoso.com")

$users | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

<span data-ttu-id="03bef-131">要让贵组织中的一组用户使用 Skype for Business 客户端，请打开 Remote PowerShell 并键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="03bef-131">To allow a group of users in your organization to use the Skype for Business client, open the Remote PowerShell and type the following:</span></span>
  
```
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

<span data-ttu-id="03bef-132">要让贵组织中的一组用户使用 Skype for Business (Lync) 客户端，请打开 Remote PowerShell 并键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="03bef-132">To allow a group of users in your organization to use the Skype for Business (Lync) client, open the Remote PowerShell and type the following:</span></span>
  
```
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

> [!NOTE]
>  <span data-ttu-id="03bef-p105">[!注释]  用户的名称是应该为其分配该策略的用户帐户的名称。 可以以下列格式之一输入用户的帐户名称：>  用户的 SIP 地址>  用户的用户主体名称 (UPN)>  用户的域\\用户名>  用户的 Active Directory 显示名称</span><span class="sxs-lookup"><span data-stu-id="03bef-p105">The user's name is the name of the user's account that the policy should be assigned to. The user's account name can be entered in one of the following formats:>  SIP address of the user>  User Principal name (UPN) of the user>  Domain\\username of the user>  Active Directory display name of the user</span></span>
  
[<span data-ttu-id="03bef-135">使用 Windows PowerShell 管理 Lync Online</span><span class="sxs-lookup"><span data-stu-id="03bef-135">Using Windows PowerShell to manage Lync Online</span></span>](https://go.microsoft.com/fwlink/?LinkID=525453)
  
## <a name="skype-for-business-online-policy-settings"></a><span data-ttu-id="03bef-136">Skype for Business Online 策略设置</span><span class="sxs-lookup"><span data-stu-id="03bef-136">Skype for Business Online policy settings</span></span>

<span data-ttu-id="03bef-137">此表显示首次为用户应用了策略之后的用户体验：</span><span class="sxs-lookup"><span data-stu-id="03bef-137">This table shows the user experience when the policy is first applied to users:</span></span>
  
|<span data-ttu-id="03bef-138">**管理员策略设置**</span><span class="sxs-lookup"><span data-stu-id="03bef-138">**Admin policy setting**</span></span>|<span data-ttu-id="03bef-139">**显示的用户界面**</span><span class="sxs-lookup"><span data-stu-id="03bef-139">**User interface displayed**</span></span>|
|:-----|:-----|
|<span data-ttu-id="03bef-140">未设置策略。</span><span class="sxs-lookup"><span data-stu-id="03bef-140">The policy isn't set.</span></span> |<span data-ttu-id="03bef-141">用户将继续使用 Skype for Business 客户端用户界面。</span><span class="sxs-lookup"><span data-stu-id="03bef-141">The user will continue using the Skype for Business client user interface.</span></span>|
|```Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI```<br/>|<span data-ttu-id="03bef-142">用户将继续使用 Skype for Business 客户端用户界面。</span><span class="sxs-lookup"><span data-stu-id="03bef-142">The user will continue using the Skype for Business client user interface.</span></span>|
|```Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI```<br/>|<span data-ttu-id="03bef-p106">将请用户切换到 Skype for Business (Lync) 客户端用户界面。 他们可以以后切换。</span><span class="sxs-lookup"><span data-stu-id="03bef-p106">The user will be asked to switch to the Skype for Business (Lync) client user interface. They can switch later.</span></span>|
|```Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>```|<span data-ttu-id="03bef-145">用户将使用 Skype for Business 客户端用户界面。</span><span class="sxs-lookup"><span data-stu-id="03bef-145">The user will be using the Skype for Business client user interface.</span></span> |
```Grant-CsClientPolicy-PolicyName ClientPolicyDisableSkypeUI -Identity <username>```|<span data-ttu-id="03bef-146">用户可能需要切换到业务 (Lync) 客户端用户界面的 Skype。</span><span class="sxs-lookup"><span data-stu-id="03bef-146">The user will be asked to switch to the Skype for Business (Lync) client user interface.</span></span> <span data-ttu-id="03bef-147">管理员可以在以后更改用于将用户切换到 Skype for Business 客户端用户界面的设置。</span><span class="sxs-lookup"><span data-stu-id="03bef-147">An admin can change the setting in the future that will switch them to the Skype for Business client user interface.</span></span> |
   
<span data-ttu-id="03bef-148">此表显示更改了策略之后的用户体验：</span><span class="sxs-lookup"><span data-stu-id="03bef-148">This table shows the user experience when the policy is changed:</span></span>
  
|<span data-ttu-id="03bef-149">**管理员策略设置**</span><span class="sxs-lookup"><span data-stu-id="03bef-149">**Admin policy setting**</span></span>|<span data-ttu-id="03bef-150">**Skype for Business (Lync) 用户界面**</span><span class="sxs-lookup"><span data-stu-id="03bef-150">**Skype for Business (Lync) user interface**</span></span>|<span data-ttu-id="03bef-151">**Skype for Business 用户界面**</span><span class="sxs-lookup"><span data-stu-id="03bef-151">**Skype for Business user interface**</span></span>|
|:-----|:-----|:-----|
|```Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI```|<span data-ttu-id="03bef-152">将请用户切换到 Skype for Business 客户端用户界面。</span><span class="sxs-lookup"><span data-stu-id="03bef-152">The user will be asked to switch to the Skype for Business client user interface.</span></span>  <br/> |<span data-ttu-id="03bef-153">用户将继续使用 Skype for Business 客户端用户界面。</span><span class="sxs-lookup"><span data-stu-id="03bef-153">The user will continue to use the Skype for Business client user interface.</span></span>  <br/> |
|```Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI```|<span data-ttu-id="03bef-154">用户将继续使用 Skype 业务 (Lync) 接口。</span><span class="sxs-lookup"><span data-stu-id="03bef-154">The user will continue to use the Skype for Business (Lync) interface.</span></span>  <br/> |<span data-ttu-id="03bef-155">用户可能需要切换到业务 (Lync) 客户端用户界面的 Skype。</span><span class="sxs-lookup"><span data-stu-id="03bef-155">The user will be asked to switch to the Skype for Business (Lync) client user interface.</span></span>  <br/> |
|<span data-ttu-id="03bef-156">未设置策略。</span><span class="sxs-lookup"><span data-stu-id="03bef-156">The policy isn't set.</span></span>  <br/> |<span data-ttu-id="03bef-157">如果未设置此策略，用户将永远不会看到业务 (Lync) 客户端用户界面的 Skype。</span><span class="sxs-lookup"><span data-stu-id="03bef-157">Users will never see the Skype for Business (Lync) client user interface if the policy is not set.</span></span> <span data-ttu-id="03bef-158">他们将一直使用 Skype for Business 客户端用户界面。</span><span class="sxs-lookup"><span data-stu-id="03bef-158">They will always use the Skype for Business client user interface.</span></span>  <br/> |<span data-ttu-id="03bef-159">用户将继续使用 Skype for Business 客户端用户界面。</span><span class="sxs-lookup"><span data-stu-id="03bef-159">The user will continue to use the Skype for Business client user interface.</span></span>  <br/> |
   
<span data-ttu-id="03bef-p109">此表显示所有可用的联机自定义策略。 已创建新的策略来让管理员能够在 EnableSkypeUI 标志之间切换同时灵活保留旧的自定义策略。 请使用上面的 cmdlet 来向用户授予以下策略之一。</span><span class="sxs-lookup"><span data-stu-id="03bef-p109">This table shows all the Online custom policies available. There are new policies created to give admins flexibility in retaining the old custom policy while switching between the EnableSkypeUI flags. Please use the cmdlets from above to grant one of the below policies to your users.</span></span>
  
|<span data-ttu-id="03bef-163">**策略名称**</span><span class="sxs-lookup"><span data-stu-id="03bef-163">**Policy name**</span></span>|<span data-ttu-id="03bef-164">**EnableSkypeUI**</span><span class="sxs-lookup"><span data-stu-id="03bef-164">**EnableSkypeUI**</span></span>|
|:-----|:-----|
```ClientPolicyDefaultPhoto```||
```ClientPolicyDefaultPhotoDisableSkypeUI``` |<span data-ttu-id="03bef-165">假</span><span class="sxs-lookup"><span data-stu-id="03bef-165">False</span></span>|
```ClientPolicyNoIMURL```||
```ClientPolicyNoIMURLDisableSkypeUI``` |<span data-ttu-id="03bef-166">假</span><span class="sxs-lookup"><span data-stu-id="03bef-166">False</span></span>|
```ClientPolicyNoIMURLPhoto```||
```ClientPolicyNoIMURLPhotoDisableSkypeUI``` |<span data-ttu-id="03bef-167">假</span><span class="sxs-lookup"><span data-stu-id="03bef-167">False</span></span>|
```ClientPolicyNoSaveIMNoArchivingI```||
```ClientPolicyNoSaveIMNoArchivingDisableSkypeUI``` |<span data-ttu-id="03bef-168">假</span><span class="sxs-lookup"><span data-stu-id="03bef-168">False</span></span>|
```ClientPolicyNoSaveIMNoArchivingNoIMURL```||
```ClientPolicyNoSaveIMNoArchivingNoIMURLDisableSkypeUI``` |<span data-ttu-id="03bef-169">假</span><span class="sxs-lookup"><span data-stu-id="03bef-169">False</span></span>|
```ClientPolicyNoSaveIMNoArchivingNoIMURLPhoto``` ||
```ClientPolicyNoSaveIMNoArchivingNoIMURLPhotoDisableSkypeUI```|<span data-ttu-id="03bef-170">假</span><span class="sxs-lookup"><span data-stu-id="03bef-170">False</span></span>|
```ClientPolicyNoSaveIMNoArchivingPhoto```||
```ClientPolicyNoSaveIMNoArchivingPhotoDisableSkypeUI``` |<span data-ttu-id="03bef-171">假</span><span class="sxs-lookup"><span data-stu-id="03bef-171">False</span></span>|

   
<span data-ttu-id="03bef-172">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="03bef-172">To get started with Windows PowerShell, see these topics:</span></span>
  
- [<span data-ttu-id="03bef-173">为什么需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="03bef-173">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- [<span data-ttu-id="03bef-174">使用 Windows PowerShell 管理 Office 365 的最佳方法</span><span class="sxs-lookup"><span data-stu-id="03bef-174">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
## <a name="first-launch-client-behaviors"></a><span data-ttu-id="03bef-175">首次启动客户端行为</span><span class="sxs-lookup"><span data-stu-id="03bef-175">First launch client behaviors</span></span>

<span data-ttu-id="03bef-176">默认情况下，当用户启动 Skype 业务的第一次，他们将始终看到 Skype 为业务用户界面--即使您通过 Lync 客户端体验设置客户端策略选择 Lync 客户端体验 (`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`) 所述以前。</span><span class="sxs-lookup"><span data-stu-id="03bef-176">By default, when users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the client policy to the Lync client experience (`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`) as described previously.</span></span> <span data-ttu-id="03bef-177">几分钟时间后，系统将要求用户切换到 Lync 模式。</span><span class="sxs-lookup"><span data-stu-id="03bef-177">After several minutes, users will then be asked to switch to Lync mode.</span></span>
  
<span data-ttu-id="03bef-178">如果你希望在用户首次启动 Skype for Business 客户端时显示 Lync 用户界面，请在客户端更新后首次启动前执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="03bef-178">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>
  
1. <span data-ttu-id="03bef-179">按照本主题前面部分中的步骤进行操作，确认客户端策略设置为禁用 Skype for Business 用户界面。</span><span class="sxs-lookup"><span data-stu-id="03bef-179">Follow the steps earlier in this topic and confirm that the client policy is set to disable the Skype for Business user interface.</span></span>
    
2. <span data-ttu-id="03bef-p111">更新用户计算机上的系统注册表。 你应在用户首次启动 Skype for Business 客户端之前执行此操作，且你应仅执行一次此操作。 有关如何创建组策略对象以更新加入域的计算机上的注册表的信息，请参阅本主题后面部分内容。</span><span class="sxs-lookup"><span data-stu-id="03bef-p111">Update the system registry on the user's computer. You should do this before the first time users launch the Skype for Business client, and you should do this only once. For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="03bef-183">在 **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]** 注册表项中，创建新的" **二进制**"值。</span><span class="sxs-lookup"><span data-stu-id="03bef-183">In the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="03bef-184">" **值名称**"必须为 **EnableSkypeUI**，" **值数据**"必须设为 **00 00 00 00**。</span><span class="sxs-lookup"><span data-stu-id="03bef-184">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="03bef-185">该注册表项应类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="03bef-185">The key should look like the following:</span></span>
    
    <span data-ttu-id="03bef-186">[注册表\\软件\\Microsoft\\Office\\Lync]</span><span class="sxs-lookup"><span data-stu-id="03bef-186">[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]</span></span>
    
    <span data-ttu-id="03bef-187">"CanSharePptInCollab"= dword:00000001</span><span class="sxs-lookup"><span data-stu-id="03bef-187">"CanSharePptInCollab"=dword:00000001</span></span>
    
    <span data-ttu-id="03bef-188">"CanShareOneNoteInCollab"= dword:00000001</span><span class="sxs-lookup"><span data-stu-id="03bef-188">"CanShareOneNoteInCollab"=dword:00000001</span></span>
    
    <span data-ttu-id="03bef-189">"CanAppShareInCollab"= dword:00000001</span><span class="sxs-lookup"><span data-stu-id="03bef-189">"CanAppShareInCollab"=dword:00000001</span></span>
    
    <span data-ttu-id="03bef-190">"EnableSkypeUI"= 十六进制： 00 00 00、 00</span><span class="sxs-lookup"><span data-stu-id="03bef-190">"EnableSkypeUI"=hex:00,00,00,00</span></span>
    
<span data-ttu-id="03bef-191">当用户首次启动 Skype for Business 客户端时，现在将显示 Lync 用户界面。</span><span class="sxs-lookup"><span data-stu-id="03bef-191">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="03bef-192">控制欢迎屏幕教程的显示</span><span class="sxs-lookup"><span data-stu-id="03bef-192">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="03bef-193">当用户打开业务客户端的 Skype 时，默认行为是显示欢迎使用屏幕中包含*大多数人寻求 7 个快速提示*。</span><span class="sxs-lookup"><span data-stu-id="03bef-193">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="03bef-194">你可以关闭欢迎屏幕的显示，同时仍允许用户通过在客户端计算机上添加以下注册表值来访问教程：</span><span class="sxs-lookup"><span data-stu-id="03bef-194">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>
  
<span data-ttu-id="03bef-p113">在 **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]**注册表项中，创建新的 **DWORD（32 位）值**。 " **值名称**"必须为 **IsBasicTutorialSeenByUser**，" **值数据**"必须设为 **1**。</span><span class="sxs-lookup"><span data-stu-id="03bef-p113">In the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]** key, create a new **DWORD (32-bit) Value**. The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>
  
<span data-ttu-id="03bef-197">该注册表项应类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="03bef-197">The key should look like the following:</span></span>
  
```
"IsBasicTutorialSeenByUser"=dword:00000001
```

### <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="03bef-198">关闭客户端教程</span><span class="sxs-lookup"><span data-stu-id="03bef-198">Turn off the client tutorial</span></span>

<span data-ttu-id="03bef-199">如果你不希望你的用户能够访问教程，你可以使用以下注册表值关闭客户端教程：</span><span class="sxs-lookup"><span data-stu-id="03bef-199">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>
  
<span data-ttu-id="03bef-p114">在 **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]**注册表项中，创建新的 **DWORD（32 位）值**。 " **值名称**"必须为 **TutorialFeatureEnabled**，" **值数据**"必须设为 **0**。</span><span class="sxs-lookup"><span data-stu-id="03bef-p114">In the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]** key, create a new **DWORD (32-bit) Value**. The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>
  
```
"TutorialFeatureEnabled"=dword:00000000
```

<span data-ttu-id="03bef-202">你可以通过将" **值数据**"设为 **1** 来重新打开教程。</span><span class="sxs-lookup"><span data-stu-id="03bef-202">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>
  
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="03bef-203">创建组策略对象以修改加入域的计算机上的注册表</span><span class="sxs-lookup"><span data-stu-id="03bef-203">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="03bef-p115">应仅执行一次注册表更新以在用户首次启动 Skype for Business 客户端时显示 Lync 客户端体验。 如果你使用组策略对象 (GPO) 更新注册表，你需要定义对象以创建新值，而非更新值数据。 应用 GPO 时，如果新值不存在，则 GPO 将创建新值并将值数据设为 0。</span><span class="sxs-lookup"><span data-stu-id="03bef-p115">The registry update to display the Lync client experience the first time a user launches the Skype for Business client should be done only once. If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data. When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span>
  
<span data-ttu-id="03bef-p116">以下过程介绍了如何修改注册表，使得在用户首次启动 Skype for Business 时显示 Lync 客户端体验。 你还可以如前文所述，使用此过程更新注册表以禁用欢迎屏幕教程。</span><span class="sxs-lookup"><span data-stu-id="03bef-p116">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business. You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>
  
 <span data-ttu-id="03bef-209">**要创建的 GPO**</span><span class="sxs-lookup"><span data-stu-id="03bef-209">**To create the GPO**</span></span>
  
1. <span data-ttu-id="03bef-210">启动" **组策略管理控制台**"。</span><span class="sxs-lookup"><span data-stu-id="03bef-210">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="03bef-211">有关如何使用组策略管理控制台的信息，请参阅[组策略管理控制台](https://go.microsoft.com/fwlink/?LinkId=532759)。</span><span class="sxs-lookup"><span data-stu-id="03bef-211">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](https://go.microsoft.com/fwlink/?LinkId=532759).</span></span>
    
2. <span data-ttu-id="03bef-212">右键单击" **组策略对象**"节点，然后选择菜单上的" **新建**"。</span><span class="sxs-lookup"><span data-stu-id="03bef-212">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>
    
3. <span data-ttu-id="03bef-213">在" **新建 GPO**"对话框中，输入 GPO 的名称，例如 MakeLyncDefaultUI，然后单击" **确定**"。</span><span class="sxs-lookup"><span data-stu-id="03bef-213">In the **New GPO** dialog, enter a name for the GPO, for example,MakeLyncDefaultUI, and then click **OK**.</span></span>
    
4. <span data-ttu-id="03bef-214">右键单击你刚创建的新 GPO，然后在菜单上选择" **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="03bef-214">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>
    
5. <span data-ttu-id="03bef-215">在" **组策略管理编辑器**"中，依次展开" **用户配置**"、" **首选项**"、" **Windows 设置**"，然后选择" **注册表**"节点。</span><span class="sxs-lookup"><span data-stu-id="03bef-215">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>
    
6. <span data-ttu-id="03bef-216">Right-click on the **Registry** node, and then select **New** > **Registry Item**.</span><span class="sxs-lookup"><span data-stu-id="03bef-216">Right-click on the **Registry** node, and then select **New** > **Registry Item**.</span></span>
    
7. <span data-ttu-id="03bef-217">在" **新建注册表属性**"对话框上，更新以下内容：</span><span class="sxs-lookup"><span data-stu-id="03bef-217">On the **New Registry Properties** dialog, update the following:</span></span>
    
|<span data-ttu-id="03bef-218">**字段**</span><span class="sxs-lookup"><span data-stu-id="03bef-218">**Field**</span></span>|<span data-ttu-id="03bef-219">**要选择或输入的值**</span><span class="sxs-lookup"><span data-stu-id="03bef-219">**Value to select or enter**</span></span>|
|:-----|:-----|
|<span data-ttu-id="03bef-220">**操作**</span><span class="sxs-lookup"><span data-stu-id="03bef-220">**Action**</span></span> <br/> |<span data-ttu-id="03bef-221">**创建**</span><span class="sxs-lookup"><span data-stu-id="03bef-221">**Create**</span></span> <br/> |
|<span data-ttu-id="03bef-222">**配置单元**</span><span class="sxs-lookup"><span data-stu-id="03bef-222">**Hive**</span></span> <br/> | <span data-ttu-id="03bef-223">注册表</span><span class="sxs-lookup"><span data-stu-id="03bef-223">HKEY_CURRENT_USER</span></span> <br/> |
|<span data-ttu-id="03bef-224">**注册表项路径**</span><span class="sxs-lookup"><span data-stu-id="03bef-224">**Key Path**</span></span> <br/> |<span data-ttu-id="03bef-225">软件\\Microsoft\\Office\\Lync</span><span class="sxs-lookup"><span data-stu-id="03bef-225">Software\\Microsoft\\Office\\Lync</span></span>  <br/> |
|<span data-ttu-id="03bef-226">**值名称**</span><span class="sxs-lookup"><span data-stu-id="03bef-226">**Value name**</span></span> <br/> |<span data-ttu-id="03bef-227">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="03bef-227">EnableSkypeUI</span></span>  <br/> |
|<span data-ttu-id="03bef-228">**值类型**</span><span class="sxs-lookup"><span data-stu-id="03bef-228">**Value type**</span></span> <br/> |<span data-ttu-id="03bef-229">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="03bef-229">REG_BINARY</span></span>  <br/> |
|<span data-ttu-id="03bef-230">**值数据**</span><span class="sxs-lookup"><span data-stu-id="03bef-230">**Value data**</span></span> <br/> |<span data-ttu-id="03bef-231">00000000</span><span class="sxs-lookup"><span data-stu-id="03bef-231">00000000</span></span>  <br/> |
   
<span data-ttu-id="03bef-232">单击" **确定**"以保存更改，然后关闭 GPO。</span><span class="sxs-lookup"><span data-stu-id="03bef-232">Click **OK** to save your changes, and then close the GPO.</span></span>
    
<span data-ttu-id="03bef-233">接下来，你需要将你创建的 GPO 链接到你希望分配策略的用户组，比如 OU。</span><span class="sxs-lookup"><span data-stu-id="03bef-233">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>
  
 <span data-ttu-id="03bef-234">**若要使用 GPO 分配策略**</span><span class="sxs-lookup"><span data-stu-id="03bef-234">**To use the GPO to assign the policy**</span></span>
  
1. <span data-ttu-id="03bef-235">在组策略管理控制台中，右键单击要分配策略的 OU，然后选择" **链接到现有 GPO**"。</span><span class="sxs-lookup"><span data-stu-id="03bef-235">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>
    
2. <span data-ttu-id="03bef-236">在" **选择 GPO**"对话框中，选择你创建的 GPO，然后选择" **确定**"。</span><span class="sxs-lookup"><span data-stu-id="03bef-236">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>
    
3. <span data-ttu-id="03bef-237">在目标用户的计算机上，打开命令提示符并键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="03bef-237">On the target user's computer, open a command prompt and type the following command:</span></span>
    
    <span data-ttu-id="03bef-238">**gpupdate /target:user**</span><span class="sxs-lookup"><span data-stu-id="03bef-238">**gpupdate /target:user**</span></span>
    
    <span data-ttu-id="03bef-p117">应用 GPO 时，将显示消息"正在更新策略..."。 完成时，将显示消息"已成功完成用户策略更新"。</span><span class="sxs-lookup"><span data-stu-id="03bef-p117">The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.</span></span>
    
4. <span data-ttu-id="03bef-241">在命令提示符下，键入下列命令：</span><span class="sxs-lookup"><span data-stu-id="03bef-241">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="03bef-242">**gpresult /r**</span><span class="sxs-lookup"><span data-stu-id="03bef-242">**gpresult /r**</span></span>
    
    <span data-ttu-id="03bef-243">你将在下面看到带有你创建的 GPO 名称的"已分配的组策略对象"。</span><span class="sxs-lookup"><span data-stu-id="03bef-243">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>
    
<span data-ttu-id="03bef-p118">你可以检查注册表以确认 GPO 已成功更新用户计算机上的注册表。 打开注册表编辑器并导航至 **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]** 注册表项。 如果 GPO 已成功更新注册表，你将看到名为 EnableSkypeUI 的值设为 0。</span><span class="sxs-lookup"><span data-stu-id="03bef-p118">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry. Open Registry Editor and navigate to the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]** key. If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="03bef-247">相关主题</span><span class="sxs-lookup"><span data-stu-id="03bef-247">Related topics</span></span>
[<span data-ttu-id="03bef-248">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="03bef-248">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="03bef-249">允许 Skype for Business 用户添加 Skype 联系人</span><span class="sxs-lookup"><span data-stu-id="03bef-249">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 