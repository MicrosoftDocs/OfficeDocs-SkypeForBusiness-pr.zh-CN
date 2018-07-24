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
description: 摘要： 了解如何管理 Persistent Chat Server in Skype for Business Server 2015。
ms.openlocfilehash: 2511de09c321c70d73d824f5fc94bf21fa674131
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20967896"
---
# <a name="manage-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="8ed6a-103">管理 Skype for Business Server 2015 中的持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="8ed6a-103">Manage Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8ed6a-104">**摘要：** 了解如何管理 Persistent Chat Server in Skype 的业务服务器 2015年。</span><span class="sxs-lookup"><span data-stu-id="8ed6a-104">**Summary:** Learn how to manage Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="8ed6a-105">当您为组织设置了持久聊天服务器时，则指定部署过程中的初始配置。</span><span class="sxs-lookup"><span data-stu-id="8ed6a-105">When you set up Persistent Chat Server for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="8ed6a-106">但是，有时可能时您想要更改如何实现持久聊天服务器支持。</span><span class="sxs-lookup"><span data-stu-id="8ed6a-106">However, there may be times when you want to change how you implement Persistent Chat Server support.</span></span> <span data-ttu-id="8ed6a-107">例如，您可能需要设置持久聊天服务器支持和不同的特定团队或组织内的组的控件。</span><span class="sxs-lookup"><span data-stu-id="8ed6a-107">For example you may need to set up Persistent Chat Server support and controls differently for a specific team or group within your organization.</span></span> <span data-ttu-id="8ed6a-108">本节提供的信息和过程可帮助您自定义持久聊天服务器部署。</span><span class="sxs-lookup"><span data-stu-id="8ed6a-108">This section provides information and procedures to help you customize your Persistent Chat Server deployment.</span></span> <span data-ttu-id="8ed6a-109">有关的特性和功能，您可以配置持久聊天服务器的详细信息，请参阅[Plan for Persistent Chat Server in Skype 的业务服务器 2015年](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="8ed6a-109">For details about the features and functionality that you can configure for Persistent Chat Server, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span> <span data-ttu-id="8ed6a-110">有关部署持久聊天服务器的详细信息，请参阅[部署持久聊天服务器中的业务服务器 2015 Skype](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="8ed6a-110">For details about deploying Persistent Chat Server, see [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="8ed6a-111">持久聊天中的业务服务器 2015 Skype 可用但业务服务器 2019年不再支持在 Skype。</span><span class="sxs-lookup"><span data-stu-id="8ed6a-111">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="8ed6a-112">中团队提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="8ed6a-112">The same functionality is available in Teams.</span></span> <span data-ttu-id="8ed6a-113">有关详细信息，请参阅[从企业对 Microsoft 团队的 Skype 旅程](/microsoftteams/journey-skypeforbusiness-teams)。</span><span class="sxs-lookup"><span data-stu-id="8ed6a-113">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="8ed6a-114">如果您需要使用持久聊天，您的选择是也迁移要求给团队，此功能的用户或继续对业务服务器 2015年使用 Skype。</span><span class="sxs-lookup"><span data-stu-id="8ed6a-114">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
<span data-ttu-id="8ed6a-115">使用控制面板，或使用 Windows PowerShell cmdlet，您可以管理持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="8ed6a-115">You can manage Persistent Chat Server by using the Control Panel or by using Windows PowerShell cmdlets.</span></span> 
  
<span data-ttu-id="8ed6a-116">要使用控制面板：</span><span class="sxs-lookup"><span data-stu-id="8ed6a-116">To use the Control Panel:</span></span>
  
1. <span data-ttu-id="8ed6a-117">使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录您的本地部署中的任一计算机。</span><span class="sxs-lookup"><span data-stu-id="8ed6a-117">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="8ed6a-118">从**开始**菜单上，选择业务 Server Control Panel Skype 或打开一个浏览器窗口中，，然后输入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="8ed6a-118">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="8ed6a-119">在左侧的导航栏中，单击**持久聊天**。</span><span class="sxs-lookup"><span data-stu-id="8ed6a-119">In the left navigation bar, click **Persistent Chat**.</span></span>
    
<span data-ttu-id="8ed6a-120">下表汇总了可用于帮助您管理持久聊天服务器的 Windows PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8ed6a-120">The following table summarizes the Windows PowerShell cmdlets available to help you manage Persistent Chat Server.</span></span> <span data-ttu-id="8ed6a-121">有关语法，包括所有可用的参数的详细信息，请参阅[Skype 的业务服务器 2015年命令行管理程序](../management-shell.md)。</span><span class="sxs-lookup"><span data-stu-id="8ed6a-121">For details about syntax, including all available parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="8ed6a-122">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="8ed6a-122">**Cmdlet**</span></span>|<span data-ttu-id="8ed6a-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="8ed6a-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8ed6a-124">New-cspersistentchatcategory</span><span class="sxs-lookup"><span data-stu-id="8ed6a-124">New-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="8ed6a-125">创建新类别</span><span class="sxs-lookup"><span data-stu-id="8ed6a-125">Creates a new category</span></span>  <br/> |
|<span data-ttu-id="8ed6a-126">Set-cspersistentchatcategory</span><span class="sxs-lookup"><span data-stu-id="8ed6a-126">Set-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="8ed6a-127">配置现有类别的设置</span><span class="sxs-lookup"><span data-stu-id="8ed6a-127">Configures settings for an existing category</span></span>  <br/> |
|<span data-ttu-id="8ed6a-128">Get-cspersistentchatcategory</span><span class="sxs-lookup"><span data-stu-id="8ed6a-128">Get-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="8ed6a-129">检索有关类别的信息</span><span class="sxs-lookup"><span data-stu-id="8ed6a-129">Retrieves information about categories</span></span>  <br/> |
|<span data-ttu-id="8ed6a-130">删除 CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="8ed6a-130">Remove-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="8ed6a-131">删除类别</span><span class="sxs-lookup"><span data-stu-id="8ed6a-131">Removes a category</span></span>  <br/> |
|<span data-ttu-id="8ed6a-132">New-cspersistentchatroom</span><span class="sxs-lookup"><span data-stu-id="8ed6a-132">New-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="8ed6a-133">新建聊天室</span><span class="sxs-lookup"><span data-stu-id="8ed6a-133">Creates a new chat room</span></span>  <br/> |
|<span data-ttu-id="8ed6a-134">Set-cspersistentchatroom</span><span class="sxs-lookup"><span data-stu-id="8ed6a-134">Set-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="8ed6a-135">配置现有聊天室的设置；向聊天室分配用户和用户组</span><span class="sxs-lookup"><span data-stu-id="8ed6a-135">Configures settings for an existing room; assign users and user groups to the room</span></span>  <br/> |
|<span data-ttu-id="8ed6a-136">Get-cspersistentchatroom</span><span class="sxs-lookup"><span data-stu-id="8ed6a-136">Get-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="8ed6a-137">检索有关聊天室的信息</span><span class="sxs-lookup"><span data-stu-id="8ed6a-137">Retrieves information about rooms</span></span>  <br/> |
|<span data-ttu-id="8ed6a-138">Clear-cspersistentchatroom</span><span class="sxs-lookup"><span data-stu-id="8ed6a-138">Clear-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="8ed6a-139">清除聊天室或清除聊天室中的消息</span><span class="sxs-lookup"><span data-stu-id="8ed6a-139">Clears a room or messages from a room</span></span>  <br/> |
|<span data-ttu-id="8ed6a-140">即 Remove-cspersistentchatroom</span><span class="sxs-lookup"><span data-stu-id="8ed6a-140">Remove-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="8ed6a-141">删除聊天室</span><span class="sxs-lookup"><span data-stu-id="8ed6a-141">Removes a room</span></span>  <br/> |
|<span data-ttu-id="8ed6a-142">删除 CsPersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="8ed6a-142">Remove-CsPersistentChatMessage</span></span>  <br/> |<span data-ttu-id="8ed6a-143">从聊天室删除消息</span><span class="sxs-lookup"><span data-stu-id="8ed6a-143">Removes messages from a room</span></span>  <br/> |
|<span data-ttu-id="8ed6a-144">New-cspersistentchataddin</span><span class="sxs-lookup"><span data-stu-id="8ed6a-144">New-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="8ed6a-145">创建新的外接程序</span><span class="sxs-lookup"><span data-stu-id="8ed6a-145">Creates a new add-in</span></span>  <br/> |
|<span data-ttu-id="8ed6a-146">Set-cspersistentchataddin</span><span class="sxs-lookup"><span data-stu-id="8ed6a-146">Set-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="8ed6a-147">配置现有外接程序的设置</span><span class="sxs-lookup"><span data-stu-id="8ed6a-147">Configures settings for an existing add-in</span></span>  <br/> |
|<span data-ttu-id="8ed6a-148">Get-cspersistentchataddin</span><span class="sxs-lookup"><span data-stu-id="8ed6a-148">Get-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="8ed6a-149">检索有关外接程序的信息</span><span class="sxs-lookup"><span data-stu-id="8ed6a-149">Retrieves information about add-ins</span></span>  <br/> |
|<span data-ttu-id="8ed6a-150">删除 CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="8ed6a-150">Remove-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="8ed6a-151">删除外接程序</span><span class="sxs-lookup"><span data-stu-id="8ed6a-151">Removes an add-in</span></span>  <br/> |
|<span data-ttu-id="8ed6a-152">Set-cspersistentchatcomplianceconfiguration</span><span class="sxs-lookup"><span data-stu-id="8ed6a-152">Set-CsPersistentChatComplianceConfiguration</span></span>  <br/> |<span data-ttu-id="8ed6a-153">修改现有的合规性配置设置集合</span><span class="sxs-lookup"><span data-stu-id="8ed6a-153">Modifies an existing collection of compliance configuration settings</span></span>  <br/> |
|<span data-ttu-id="8ed6a-154">Export-cspersistentchatdata</span><span class="sxs-lookup"><span data-stu-id="8ed6a-154">Export-CsPersistentChatData</span></span>  <br/> |<span data-ttu-id="8ed6a-155">从持久聊天数据库中导出数据</span><span class="sxs-lookup"><span data-stu-id="8ed6a-155">Exports data from a Persistent Chat database</span></span>  <br/> |
|<span data-ttu-id="8ed6a-156">Import-cspersistentchatdata</span><span class="sxs-lookup"><span data-stu-id="8ed6a-156">Import-CsPersistentChatData</span></span>  <br/> |<span data-ttu-id="8ed6a-157">导入从先前版本 Lync Server 导出的数据</span><span class="sxs-lookup"><span data-stu-id="8ed6a-157">Imports data that was exported from a previous version of Lync Server</span></span>  <br/> |
   

