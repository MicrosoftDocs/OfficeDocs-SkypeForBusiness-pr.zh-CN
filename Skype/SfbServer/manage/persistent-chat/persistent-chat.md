---
title: 管理 Skype for Business Server 2015 中的持久聊天服务器
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c58ee4f4-563b-4d0c-be91-c62df886caa9
description: 摘要： 了解如何管理业务服务器 2015 Skype 的持久聊天服务器。
ms.openlocfilehash: 294c6bcecbbfb57bb8d2a6a785cdf20775119510
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="manage-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="485d9-103">管理 Skype for Business Server 2015 中的持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="485d9-103">Manage Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="485d9-104">**摘要：**了解如何管理业务服务器 2015 Skype 的持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="485d9-104">**Summary:** Learn how to manage Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="485d9-105">当持久聊天服务器设置为您的组织时，您指定在部署过程中的初始配置。</span><span class="sxs-lookup"><span data-stu-id="485d9-105">When you set up Persistent Chat Server for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="485d9-106">但是，可能有的次当想要更改实现持久聊天服务器支持的方式。</span><span class="sxs-lookup"><span data-stu-id="485d9-106">However, there may be times when you want to change how you implement Persistent Chat Server support.</span></span> <span data-ttu-id="485d9-107">例如您可能需要设置持久聊天服务器支持和控件以不同的方式为特定团队或组织中的组。</span><span class="sxs-lookup"><span data-stu-id="485d9-107">For example you may need to set up Persistent Chat Server support and controls differently for a specific team or group within your organization.</span></span> <span data-ttu-id="485d9-108">本节提供的信息和过程以帮助您自定义持久性聊天服务器的部署。</span><span class="sxs-lookup"><span data-stu-id="485d9-108">This section provides information and procedures to help you customize your Persistent Chat Server deployment.</span></span> <span data-ttu-id="485d9-109">有关的特性和功能可持久聊天服务器的配置的详细信息，请参阅[规划业务服务器 2015年的 Skype 的持久聊天服务器](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="485d9-109">For details about the features and functionality that you can configure for Persistent Chat Server, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span> <span data-ttu-id="485d9-110">有关部署持续聊天服务器的详细信息，请参阅[部署持续聊天中的服务器业务服务器 2015年的 Skype](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="485d9-110">For details about deploying Persistent Chat Server, see [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md).</span></span> 
  
<span data-ttu-id="485d9-111">通过使用控制面板或通过使用 Windows PowerShell 的 cmdlet，您可以管理持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="485d9-111">You can manage Persistent Chat Server by using the Control Panel or by using Windows PowerShell cmdlets.</span></span> 
  
<span data-ttu-id="485d9-112">要使用控制面板：</span><span class="sxs-lookup"><span data-stu-id="485d9-112">To use the Control Panel:</span></span>
  
1. <span data-ttu-id="485d9-113">使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录您的本地部署中的任一计算机。</span><span class="sxs-lookup"><span data-stu-id="485d9-113">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="485d9-114">从**开始**菜单中，选择 Skype 业务服务器的控制面板或打开浏览器窗口，然后输入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="485d9-114">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="485d9-115">在左侧的导航栏中，单击**持续对话**。</span><span class="sxs-lookup"><span data-stu-id="485d9-115">In the left navigation bar, click **Persistent Chat**.</span></span>
    
<span data-ttu-id="485d9-116">下表总结了可用于帮助您管理持久聊天服务器的 Windows PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="485d9-116">The following table summarizes the Windows PowerShell cmdlets available to help you manage Persistent Chat Server.</span></span> <span data-ttu-id="485d9-117">有关语法，包括所有的可用参数的详细信息请参阅[业务服务器 2015年管理外壳的 Skype](../management-shell.md)。</span><span class="sxs-lookup"><span data-stu-id="485d9-117">For details about syntax, including all available parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="485d9-118">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="485d9-118">**Cmdlet**</span></span>|<span data-ttu-id="485d9-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="485d9-119">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="485d9-120">新 CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="485d9-120">New-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="485d9-121">创建新类别</span><span class="sxs-lookup"><span data-stu-id="485d9-121">Creates a new category</span></span>  <br/> |
|<span data-ttu-id="485d9-122">一组 CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="485d9-122">Set-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="485d9-123">配置现有类别的设置</span><span class="sxs-lookup"><span data-stu-id="485d9-123">Configures settings for an existing category</span></span>  <br/> |
|<span data-ttu-id="485d9-124">获得 CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="485d9-124">Get-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="485d9-125">检索有关类别的信息</span><span class="sxs-lookup"><span data-stu-id="485d9-125">Retrieves information about categories</span></span>  <br/> |
|<span data-ttu-id="485d9-126">删除 CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="485d9-126">Remove-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="485d9-127">删除类别</span><span class="sxs-lookup"><span data-stu-id="485d9-127">Removes a category</span></span>  <br/> |
|<span data-ttu-id="485d9-128">新 CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="485d9-128">New-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="485d9-129">新建聊天室</span><span class="sxs-lookup"><span data-stu-id="485d9-129">Creates a new chat room</span></span>  <br/> |
|<span data-ttu-id="485d9-130">一组 CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="485d9-130">Set-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="485d9-131">配置现有聊天室的设置；向聊天室分配用户和用户组</span><span class="sxs-lookup"><span data-stu-id="485d9-131">Configures settings for an existing room; assign users and user groups to the room</span></span>  <br/> |
|<span data-ttu-id="485d9-132">获得 CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="485d9-132">Get-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="485d9-133">检索有关房间的信息</span><span class="sxs-lookup"><span data-stu-id="485d9-133">Retrieves information about rooms</span></span>  <br/> |
|<span data-ttu-id="485d9-134">清除-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="485d9-134">Clear-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="485d9-135">清除聊天室或清除聊天室中的消息</span><span class="sxs-lookup"><span data-stu-id="485d9-135">Clears a room or messages from a room</span></span>  <br/> |
|<span data-ttu-id="485d9-136">删除 CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="485d9-136">Remove-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="485d9-137">删除聊天室</span><span class="sxs-lookup"><span data-stu-id="485d9-137">Removes a room</span></span>  <br/> |
|<span data-ttu-id="485d9-138">删除 CsPersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="485d9-138">Remove-CsPersistentChatMessage</span></span>  <br/> |<span data-ttu-id="485d9-139">从聊天室删除消息</span><span class="sxs-lookup"><span data-stu-id="485d9-139">Removes messages from a room</span></span>  <br/> |
|<span data-ttu-id="485d9-140">新 CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="485d9-140">New-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="485d9-141">创建新的外接程序</span><span class="sxs-lookup"><span data-stu-id="485d9-141">Creates a new add-in</span></span>  <br/> |
|<span data-ttu-id="485d9-142">一组 CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="485d9-142">Set-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="485d9-143">配置现有外接程序的设置</span><span class="sxs-lookup"><span data-stu-id="485d9-143">Configures settings for an existing add-in</span></span>  <br/> |
|<span data-ttu-id="485d9-144">获得 CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="485d9-144">Get-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="485d9-145">检索有关外接程序的信息</span><span class="sxs-lookup"><span data-stu-id="485d9-145">Retrieves information about add-ins</span></span>  <br/> |
|<span data-ttu-id="485d9-146">删除 CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="485d9-146">Remove-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="485d9-147">删除外接程序</span><span class="sxs-lookup"><span data-stu-id="485d9-147">Removes an add-in</span></span>  <br/> |
|<span data-ttu-id="485d9-148">一组 CsPersistentChatComplianceConfiguration</span><span class="sxs-lookup"><span data-stu-id="485d9-148">Set-CsPersistentChatComplianceConfiguration</span></span>  <br/> |<span data-ttu-id="485d9-149">修改现有的合规性配置设置集合</span><span class="sxs-lookup"><span data-stu-id="485d9-149">Modifies an existing collection of compliance configuration settings</span></span>  <br/> |
|<span data-ttu-id="485d9-150">导出 CsPersistentChatData</span><span class="sxs-lookup"><span data-stu-id="485d9-150">Export-CsPersistentChatData</span></span>  <br/> |<span data-ttu-id="485d9-151">从持久聊天数据库中导出数据</span><span class="sxs-lookup"><span data-stu-id="485d9-151">Exports data from a Persistent Chat database</span></span>  <br/> |
|<span data-ttu-id="485d9-152">导入 CsPersistentChatData</span><span class="sxs-lookup"><span data-stu-id="485d9-152">Import-CsPersistentChatData</span></span>  <br/> |<span data-ttu-id="485d9-153">导入从先前版本 Lync Server 导出的数据</span><span class="sxs-lookup"><span data-stu-id="485d9-153">Imports data that was exported from a previous version of Lync Server</span></span>  <br/> |
   

