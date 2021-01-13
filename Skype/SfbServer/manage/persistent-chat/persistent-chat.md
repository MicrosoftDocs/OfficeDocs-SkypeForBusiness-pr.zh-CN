---
title: 在 Skype for Business Server 2015 中管理持久聊天服务器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c58ee4f4-563b-4d0c-be91-c62df886caa9
description: 摘要：了解如何在 Skype for Business Server 2015 中管理持久聊天服务器。
ms.openlocfilehash: 9a97511f9b4c2adae7ead816e86876f05dd39790
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832882"
---
# <a name="manage-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="cbeaf-103">在 Skype for Business Server 2015 中管理持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="cbeaf-103">Manage Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="cbeaf-104">**摘要：** 了解如何在 Skype for Business Server 2015 中管理持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="cbeaf-104">**Summary:** Learn how to manage Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="cbeaf-105">为组织设置持久聊天服务器时，在部署过程中指定初始配置。</span><span class="sxs-lookup"><span data-stu-id="cbeaf-105">When you set up Persistent Chat Server for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="cbeaf-106">但是，有时可能需要更改实现持久聊天服务器支持。</span><span class="sxs-lookup"><span data-stu-id="cbeaf-106">However, there may be times when you want to change how you implement Persistent Chat Server support.</span></span> <span data-ttu-id="cbeaf-107">例如，您可能需要为组织的特定团队或组设置不同的持久聊天服务器支持和控件。</span><span class="sxs-lookup"><span data-stu-id="cbeaf-107">For example you may need to set up Persistent Chat Server support and controls differently for a specific team or group within your organization.</span></span> <span data-ttu-id="cbeaf-108">本节提供可帮助您自定义持久聊天服务器部署的信息和过程。</span><span class="sxs-lookup"><span data-stu-id="cbeaf-108">This section provides information and procedures to help you customize your Persistent Chat Server deployment.</span></span> <span data-ttu-id="cbeaf-109">有关您可以为持久聊天服务器配置的特性和功能的详细信息，请参阅 Plan [for Persistent Chat Server in Skype for Business Server 2015。](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)</span><span class="sxs-lookup"><span data-stu-id="cbeaf-109">For details about the features and functionality that you can configure for Persistent Chat Server, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span> <span data-ttu-id="cbeaf-110">有关部署持久聊天服务器的详细信息，请参阅在 [Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)中部署持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="cbeaf-110">For details about deploying Persistent Chat Server, see [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="cbeaf-111">持久聊天在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。</span><span class="sxs-lookup"><span data-stu-id="cbeaf-111">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="cbeaf-112">Teams 中也提供相同的功能。</span><span class="sxs-lookup"><span data-stu-id="cbeaf-112">The same functionality is available in Teams.</span></span> <span data-ttu-id="cbeaf-113">有关详细信息，请参阅 [Microsoft Teams](/microsoftteams/upgrade-start-here)升级入门。</span><span class="sxs-lookup"><span data-stu-id="cbeaf-113">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="cbeaf-114">如果你需要使用持久聊天，你的选择是：将需要此功能的用户迁移到 Teams，或者继续使用 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="cbeaf-114">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
<span data-ttu-id="cbeaf-115">您可以使用控制面板或 cmdlet 管理持久聊天Windows PowerShell服务器。</span><span class="sxs-lookup"><span data-stu-id="cbeaf-115">You can manage Persistent Chat Server by using the Control Panel or by using Windows PowerShell cmdlets.</span></span> 
  
<span data-ttu-id="cbeaf-116">若要使用控制面板：</span><span class="sxs-lookup"><span data-stu-id="cbeaf-116">To use the Control Panel:</span></span>
  
1. <span data-ttu-id="cbeaf-117">使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录到您的本地部署中的任一计算机。</span><span class="sxs-lookup"><span data-stu-id="cbeaf-117">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="cbeaf-118">从 **"开始** "菜单中，选择 Skype for Business Server 控制面板或打开浏览器窗口，然后输入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="cbeaf-118">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="cbeaf-119">在左侧导航栏中，单击 **"持久聊天"。**</span><span class="sxs-lookup"><span data-stu-id="cbeaf-119">In the left navigation bar, click **Persistent Chat**.</span></span>
    
<span data-ttu-id="cbeaf-120">下表总结了可用于Windows PowerShell持久聊天服务器的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cbeaf-120">The following table summarizes the Windows PowerShell cmdlets available to help you manage Persistent Chat Server.</span></span> <span data-ttu-id="cbeaf-121">有关语法的详细信息，包括所有可用参数，请参阅 Skype [for Business Server 2015 Management Shell。](../management-shell.md)</span><span class="sxs-lookup"><span data-stu-id="cbeaf-121">For details about syntax, including all available parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="cbeaf-122">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="cbeaf-122">**Cmdlet**</span></span>|<span data-ttu-id="cbeaf-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="cbeaf-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cbeaf-124">New-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="cbeaf-124">New-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="cbeaf-125">创建新类别</span><span class="sxs-lookup"><span data-stu-id="cbeaf-125">Creates a new category</span></span>  <br/> |
|<span data-ttu-id="cbeaf-126">Set-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="cbeaf-126">Set-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="cbeaf-127">配置现有类别的设置</span><span class="sxs-lookup"><span data-stu-id="cbeaf-127">Configures settings for an existing category</span></span>  <br/> |
|<span data-ttu-id="cbeaf-128">Get-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="cbeaf-128">Get-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="cbeaf-129">检索有关类别的信息</span><span class="sxs-lookup"><span data-stu-id="cbeaf-129">Retrieves information about categories</span></span>  <br/> |
|<span data-ttu-id="cbeaf-130">Remove-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="cbeaf-130">Remove-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="cbeaf-131">删除类别</span><span class="sxs-lookup"><span data-stu-id="cbeaf-131">Removes a category</span></span>  <br/> |
|<span data-ttu-id="cbeaf-132">New-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="cbeaf-132">New-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="cbeaf-133">创建新的聊天室</span><span class="sxs-lookup"><span data-stu-id="cbeaf-133">Creates a new chat room</span></span>  <br/> |
|<span data-ttu-id="cbeaf-134">Set-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="cbeaf-134">Set-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="cbeaf-135">配置现有聊天室的设置;将用户和用户组分配给聊天室</span><span class="sxs-lookup"><span data-stu-id="cbeaf-135">Configures settings for an existing room; assign users and user groups to the room</span></span>  <br/> |
|<span data-ttu-id="cbeaf-136">Get-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="cbeaf-136">Get-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="cbeaf-137">检索有关聊天室的信息</span><span class="sxs-lookup"><span data-stu-id="cbeaf-137">Retrieves information about rooms</span></span>  <br/> |
|<span data-ttu-id="cbeaf-138">Clear-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="cbeaf-138">Clear-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="cbeaf-139">清除聊天室或聊天室的消息</span><span class="sxs-lookup"><span data-stu-id="cbeaf-139">Clears a room or messages from a room</span></span>  <br/> |
|<span data-ttu-id="cbeaf-140">Remove-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="cbeaf-140">Remove-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="cbeaf-141">删除聊天室</span><span class="sxs-lookup"><span data-stu-id="cbeaf-141">Removes a room</span></span>  <br/> |
|<span data-ttu-id="cbeaf-142">Remove-CsPersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="cbeaf-142">Remove-CsPersistentChatMessage</span></span>  <br/> |<span data-ttu-id="cbeaf-143">从聊天室中删除邮件</span><span class="sxs-lookup"><span data-stu-id="cbeaf-143">Removes messages from a room</span></span>  <br/> |
|<span data-ttu-id="cbeaf-144">New-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="cbeaf-144">New-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="cbeaf-145">创建新的外接程序</span><span class="sxs-lookup"><span data-stu-id="cbeaf-145">Creates a new add-in</span></span>  <br/> |
|<span data-ttu-id="cbeaf-146">Set-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="cbeaf-146">Set-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="cbeaf-147">配置现有外接程序的设置</span><span class="sxs-lookup"><span data-stu-id="cbeaf-147">Configures settings for an existing add-in</span></span>  <br/> |
|<span data-ttu-id="cbeaf-148">Get-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="cbeaf-148">Get-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="cbeaf-149">检索有关加载项的信息</span><span class="sxs-lookup"><span data-stu-id="cbeaf-149">Retrieves information about add-ins</span></span>  <br/> |
|<span data-ttu-id="cbeaf-150">Remove-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="cbeaf-150">Remove-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="cbeaf-151">删除加载项</span><span class="sxs-lookup"><span data-stu-id="cbeaf-151">Removes an add-in</span></span>  <br/> |
|<span data-ttu-id="cbeaf-152">Set-CsPersistentChatComplianceConfiguration</span><span class="sxs-lookup"><span data-stu-id="cbeaf-152">Set-CsPersistentChatComplianceConfiguration</span></span>  <br/> |<span data-ttu-id="cbeaf-153">修改现有的合规性配置设置集合</span><span class="sxs-lookup"><span data-stu-id="cbeaf-153">Modifies an existing collection of compliance configuration settings</span></span>  <br/> |
|<span data-ttu-id="cbeaf-154">Export-CsPersistentChatData</span><span class="sxs-lookup"><span data-stu-id="cbeaf-154">Export-CsPersistentChatData</span></span>  <br/> |<span data-ttu-id="cbeaf-155">从持久聊天数据库导出数据</span><span class="sxs-lookup"><span data-stu-id="cbeaf-155">Exports data from a Persistent Chat database</span></span>  <br/> |
|<span data-ttu-id="cbeaf-156">Import-CsPersistentChatData</span><span class="sxs-lookup"><span data-stu-id="cbeaf-156">Import-CsPersistentChatData</span></span>  <br/> |<span data-ttu-id="cbeaf-157">导入从以前版本的 Lync Server 导出的数据</span><span class="sxs-lookup"><span data-stu-id="cbeaf-157">Imports data that was exported from a previous version of Lync Server</span></span>  <br/> |
   

