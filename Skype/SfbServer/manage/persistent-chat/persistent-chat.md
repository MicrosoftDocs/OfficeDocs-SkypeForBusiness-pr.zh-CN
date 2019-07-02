---
title: 管理 Skype for Business Server 2015 中的持久聊天服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c58ee4f4-563b-4d0c-be91-c62df886caa9
description: '摘要: 了解如何在 Skype for Business Server 2015 中管理持久聊天服务器。'
ms.openlocfilehash: 1702cc9891c34085f8de269d5e91723378c54ada
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418667"
---
# <a name="manage-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="16b94-103">管理 Skype for Business Server 2015 中的持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="16b94-103">Manage Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="16b94-104">**摘要:** 了解如何在 Skype for Business Server 2015 中管理持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="16b94-104">**Summary:** Learn how to manage Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="16b94-105">为您的组织设置持久聊天服务器时, 请在部署期间指定初始配置。</span><span class="sxs-lookup"><span data-stu-id="16b94-105">When you set up Persistent Chat Server for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="16b94-106">但是, 有时你可能需要更改实现持久聊天服务器支持的方式。</span><span class="sxs-lookup"><span data-stu-id="16b94-106">However, there may be times when you want to change how you implement Persistent Chat Server support.</span></span> <span data-ttu-id="16b94-107">例如, 你可能需要为组织内的特定团队或组设置持久聊天服务器支持和控件。</span><span class="sxs-lookup"><span data-stu-id="16b94-107">For example you may need to set up Persistent Chat Server support and controls differently for a specific team or group within your organization.</span></span> <span data-ttu-id="16b94-108">本部分提供了可帮助您自定义持久聊天服务器部署的信息和过程。</span><span class="sxs-lookup"><span data-stu-id="16b94-108">This section provides information and procedures to help you customize your Persistent Chat Server deployment.</span></span> <span data-ttu-id="16b94-109">有关可针对持久聊天服务器配置的功能和功能的详细信息, 请参阅[在 Skype for Business server 2015 中规划持久聊天服务器](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="16b94-109">For details about the features and functionality that you can configure for Persistent Chat Server, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span> <span data-ttu-id="16b94-110">有关部署持久聊天服务器的详细信息, 请参阅[在 Skype For Business server 2015 中部署持久聊天服务器](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="16b94-110">For details about deploying Persistent Chat Server, see [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="16b94-111">Skype for business Server 2015 中提供了持久聊天, 但 Skype for business Server 2019 不再支持此功能。</span><span class="sxs-lookup"><span data-stu-id="16b94-111">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="16b94-112">团队中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="16b94-112">The same functionality is available in Teams.</span></span> <span data-ttu-id="16b94-113">有关详细信息, 请参阅[Microsoft 团队升级](/microsoftteams/upgrade-start-here)入门。</span><span class="sxs-lookup"><span data-stu-id="16b94-113">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="16b94-114">如果需要使用持久聊天, 您可以选择将需要此功能的用户迁移到团队, 或继续使用 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="16b94-114">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
<span data-ttu-id="16b94-115">你可以通过使用控制面板或使用 Windows PowerShell cmdlet 管理持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="16b94-115">You can manage Persistent Chat Server by using the Control Panel or by using Windows PowerShell cmdlets.</span></span> 
  
<span data-ttu-id="16b94-116">要使用控制面板：</span><span class="sxs-lookup"><span data-stu-id="16b94-116">To use the Control Panel:</span></span>
  
1. <span data-ttu-id="16b94-117">使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录您的本地部署中的任一计算机。</span><span class="sxs-lookup"><span data-stu-id="16b94-117">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="16b94-118">从 "**开始**" 菜单中, 选择 "Skype For business 服务器" 控制面板或打开一个浏览器窗口, 然后输入管理员 URL。</span><span class="sxs-lookup"><span data-stu-id="16b94-118">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="16b94-119">在左侧导航栏中, 单击 "**持久聊天**"。</span><span class="sxs-lookup"><span data-stu-id="16b94-119">In the left navigation bar, click **Persistent Chat**.</span></span>
    
<span data-ttu-id="16b94-120">下表总结了可帮助你管理持久聊天服务器的 Windows PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="16b94-120">The following table summarizes the Windows PowerShell cmdlets available to help you manage Persistent Chat Server.</span></span> <span data-ttu-id="16b94-121">有关语法的详细信息，包括所有可用参数，请参阅[Skype for Business Server 2015 Management Shell](../management-shell.md)。</span><span class="sxs-lookup"><span data-stu-id="16b94-121">For details about syntax, including all available parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="16b94-122">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="16b94-122">**Cmdlet**</span></span>|<span data-ttu-id="16b94-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="16b94-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="16b94-124">New-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="16b94-124">New-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="16b94-125">创建新类别</span><span class="sxs-lookup"><span data-stu-id="16b94-125">Creates a new category</span></span>  <br/> |
|<span data-ttu-id="16b94-126">Set-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="16b94-126">Set-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="16b94-127">配置现有类别的设置</span><span class="sxs-lookup"><span data-stu-id="16b94-127">Configures settings for an existing category</span></span>  <br/> |
|<span data-ttu-id="16b94-128">Get-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="16b94-128">Get-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="16b94-129">检索有关类别的信息</span><span class="sxs-lookup"><span data-stu-id="16b94-129">Retrieves information about categories</span></span>  <br/> |
|<span data-ttu-id="16b94-130">Remove-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="16b94-130">Remove-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="16b94-131">删除类别</span><span class="sxs-lookup"><span data-stu-id="16b94-131">Removes a category</span></span>  <br/> |
|<span data-ttu-id="16b94-132">New-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="16b94-132">New-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="16b94-133">新建聊天室</span><span class="sxs-lookup"><span data-stu-id="16b94-133">Creates a new chat room</span></span>  <br/> |
|<span data-ttu-id="16b94-134">Set-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="16b94-134">Set-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="16b94-135">配置现有聊天室的设置；向聊天室分配用户和用户组</span><span class="sxs-lookup"><span data-stu-id="16b94-135">Configures settings for an existing room; assign users and user groups to the room</span></span>  <br/> |
|<span data-ttu-id="16b94-136">Get-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="16b94-136">Get-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="16b94-137">检索有关会议室的信息</span><span class="sxs-lookup"><span data-stu-id="16b94-137">Retrieves information about rooms</span></span>  <br/> |
|<span data-ttu-id="16b94-138">Clear-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="16b94-138">Clear-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="16b94-139">清除聊天室或清除聊天室中的消息</span><span class="sxs-lookup"><span data-stu-id="16b94-139">Clears a room or messages from a room</span></span>  <br/> |
|<span data-ttu-id="16b94-140">Remove-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="16b94-140">Remove-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="16b94-141">删除聊天室</span><span class="sxs-lookup"><span data-stu-id="16b94-141">Removes a room</span></span>  <br/> |
|<span data-ttu-id="16b94-142">Remove-CsPersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="16b94-142">Remove-CsPersistentChatMessage</span></span>  <br/> |<span data-ttu-id="16b94-143">从聊天室删除消息</span><span class="sxs-lookup"><span data-stu-id="16b94-143">Removes messages from a room</span></span>  <br/> |
|<span data-ttu-id="16b94-144">New-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="16b94-144">New-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="16b94-145">创建新的外接程序</span><span class="sxs-lookup"><span data-stu-id="16b94-145">Creates a new add-in</span></span>  <br/> |
|<span data-ttu-id="16b94-146">Set-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="16b94-146">Set-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="16b94-147">配置现有外接程序的设置</span><span class="sxs-lookup"><span data-stu-id="16b94-147">Configures settings for an existing add-in</span></span>  <br/> |
|<span data-ttu-id="16b94-148">Get-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="16b94-148">Get-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="16b94-149">检索有关外接程序的信息</span><span class="sxs-lookup"><span data-stu-id="16b94-149">Retrieves information about add-ins</span></span>  <br/> |
|<span data-ttu-id="16b94-150">Remove-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="16b94-150">Remove-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="16b94-151">删除外接程序</span><span class="sxs-lookup"><span data-stu-id="16b94-151">Removes an add-in</span></span>  <br/> |
|<span data-ttu-id="16b94-152">Set-CsPersistentChatComplianceConfiguration</span><span class="sxs-lookup"><span data-stu-id="16b94-152">Set-CsPersistentChatComplianceConfiguration</span></span>  <br/> |<span data-ttu-id="16b94-153">修改现有的合规性配置设置集合</span><span class="sxs-lookup"><span data-stu-id="16b94-153">Modifies an existing collection of compliance configuration settings</span></span>  <br/> |
|<span data-ttu-id="16b94-154">Export-CsPersistentChatData</span><span class="sxs-lookup"><span data-stu-id="16b94-154">Export-CsPersistentChatData</span></span>  <br/> |<span data-ttu-id="16b94-155">从持久聊天数据库中导出数据</span><span class="sxs-lookup"><span data-stu-id="16b94-155">Exports data from a Persistent Chat database</span></span>  <br/> |
|<span data-ttu-id="16b94-156">Import-CsPersistentChatData</span><span class="sxs-lookup"><span data-stu-id="16b94-156">Import-CsPersistentChatData</span></span>  <br/> |<span data-ttu-id="16b94-157">导入从先前版本 Lync Server 导出的数据</span><span class="sxs-lookup"><span data-stu-id="16b94-157">Imports data that was exported from a previous version of Lync Server</span></span>  <br/> |
   

