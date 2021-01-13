---
title: 在 Skype for Business Server 2015 中为持久聊天室配置外接程序
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
ms.assetid: c1037909-0750-411a-98c1-3a327eed4ae8
description: 摘要：了解如何在 Skype for Business Server 2015 中为持久聊天服务器聊天室配置外接程序。
ms.openlocfilehash: 1aca54f3db1229527256d1e2801cb057f4f79387
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815073"
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a><span data-ttu-id="cff66-103">在 Skype for Business Server 2015 中为持久聊天室配置外接程序</span><span class="sxs-lookup"><span data-stu-id="cff66-103">Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="cff66-104">**摘要：** 了解如何在 Skype for Business Server 2015 中为持久聊天服务器聊天室配置外接程序。</span><span class="sxs-lookup"><span data-stu-id="cff66-104">**Summary:** Learn how to configure add-ins for Persistent Chat Server chat rooms in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="cff66-105">外接程序用于通过将 URL 与聊天室关联来扩展聊天室内体验。</span><span class="sxs-lookup"><span data-stu-id="cff66-105">Add-ins are used to extend the in-room experience by associating URLs with chat rooms.</span></span> <span data-ttu-id="cff66-106">这些 URL 显示在客户端对话扩展性窗格中。</span><span class="sxs-lookup"><span data-stu-id="cff66-106">These URLs appear in the client conversation extensibility pane.</span></span> <span data-ttu-id="cff66-107">典型的外接程序可能包括指向 Silverlight 应用程序的 URL，该应用程序在将股票代码张贴到聊天室时截获，在可扩展性窗格中显示股票历史记录。</span><span class="sxs-lookup"><span data-stu-id="cff66-107">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="cff66-108">其他示例包括将 OneNote 2013 URL 作为外接程序嵌入聊天室，以包括一些共享上下文，例如“第一个想到的品牌”(Top of mind) 或“今日主题”(Topic of the day)。</span><span class="sxs-lookup"><span data-stu-id="cff66-108">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>
  
 <span data-ttu-id="cff66-109">用户必须先将外接程序添加到已注册的外接程序列表中，聊天室管理员或创建者需要将聊天室与外接程序关联，用户才能在客户端中查看外接程序。</span><span class="sxs-lookup"><span data-stu-id="cff66-109">Before users can see an add-in in the client, you must add the add-in to the list of registered add-ins, and chat room Managers or Creators need to associate rooms with the add-in.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cff66-110">持久聊天在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。</span><span class="sxs-lookup"><span data-stu-id="cff66-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="cff66-111">Teams 中也提供相同的功能。</span><span class="sxs-lookup"><span data-stu-id="cff66-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="cff66-112">有关详细信息，请参阅 [Microsoft Teams](/microsoftteams/upgrade-start-here)升级入门。</span><span class="sxs-lookup"><span data-stu-id="cff66-112">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="cff66-113">如果你需要使用持久聊天，你的选择是：将需要此功能的用户迁移到 Teams，或者继续使用 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="cff66-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a><span data-ttu-id="cff66-114">使用控制面板配置聊天室的外接程序</span><span class="sxs-lookup"><span data-stu-id="cff66-114">Configure add-ins for chat rooms by using the Control Panel</span></span>

<span data-ttu-id="cff66-115">若要使用控制面板为聊天室配置外接程序，</span><span class="sxs-lookup"><span data-stu-id="cff66-115">To configure add-ins for chat rooms by using the Control Panel:</span></span>
  
1. <span data-ttu-id="cff66-116">使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录到您的本地部署中的任一计算机。</span><span class="sxs-lookup"><span data-stu-id="cff66-116">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="cff66-117">从 **"开始** "菜单中，选择 Skype for Business Server 控制面板或打开浏览器窗口，然后输入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="cff66-117">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="cff66-118">在左侧导航栏中，单击“持久聊天”，然后单击“外接程序”。</span><span class="sxs-lookup"><span data-stu-id="cff66-118">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>
    
    <span data-ttu-id="cff66-119">对于多个持久聊天服务器池部署，请从下拉列表中选择相应的池。</span><span class="sxs-lookup"><span data-stu-id="cff66-119">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>
    
4. <span data-ttu-id="cff66-120">在“外接程序”页上，单击“新建”。</span><span class="sxs-lookup"><span data-stu-id="cff66-120">On the **Add-in** page, click **New**.</span></span>
    
5. <span data-ttu-id="cff66-121">在 **"选择服务**"中，选择与需要创建外接程序的持久聊天服务器池对应的服务。</span><span class="sxs-lookup"><span data-stu-id="cff66-121">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="cff66-122">外接程序无法从一个池移到另一个池，或者在不同池之间共享。</span><span class="sxs-lookup"><span data-stu-id="cff66-122">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>
    
6. <span data-ttu-id="cff66-123">在“新建外接程序”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="cff66-123">In **New Add-in**, do the following:</span></span>
    
   - <span data-ttu-id="cff66-124">在“名称”中，指定新外接程序的名称。</span><span class="sxs-lookup"><span data-stu-id="cff66-124">In **Name**, specify a name for the new add-in.</span></span>
    
   - <span data-ttu-id="cff66-125">在“URL”中，指定与外接程序关联的 URL。</span><span class="sxs-lookup"><span data-stu-id="cff66-125">In **URL**, specify the URL to be associated with the add-in.</span></span> <span data-ttu-id="cff66-126">URL 仅限于 http 和 https 协议。</span><span class="sxs-lookup"><span data-stu-id="cff66-126">URLs are limited to the http and https protocols.</span></span>
    
7. <span data-ttu-id="cff66-127">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="cff66-127">Click **Commit**.</span></span>
    
## <a name="configure-add-ins-by-using-windows-powershell"></a><span data-ttu-id="cff66-128">使用加载项配置Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cff66-128">Configure add-ins by using Windows PowerShell</span></span>

<span data-ttu-id="cff66-129">您可以使用以下 cmdlet 配置聊天室的Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="cff66-129">You can configure add-ins for chat rooms by using the following Windows PowerShell cmdlets.</span></span> <span data-ttu-id="cff66-130">有关语法的详细信息，包括所有可用参数，请参阅 Skype [for Business Server 2015 Management Shell。](../management-shell.md)</span><span class="sxs-lookup"><span data-stu-id="cff66-130">For details about syntax, including all available parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="cff66-131">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="cff66-131">**Cmdlet**</span></span>|<span data-ttu-id="cff66-132">**说明**</span><span class="sxs-lookup"><span data-stu-id="cff66-132">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cff66-133">New-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="cff66-133">New-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="cff66-134">创建新的外接程序</span><span class="sxs-lookup"><span data-stu-id="cff66-134">Create a new add-in</span></span>  <br/> |
|<span data-ttu-id="cff66-135">Set-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="cff66-135">Set-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="cff66-136">配置现有外接程序的设置</span><span class="sxs-lookup"><span data-stu-id="cff66-136">Configure settings for an existing add-in</span></span>  <br/> |
|<span data-ttu-id="cff66-137">Get-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="cff66-137">Get-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="cff66-138">检索有关加载项的信息</span><span class="sxs-lookup"><span data-stu-id="cff66-138">Retrieve information about add-ins</span></span>  <br/> |
|<span data-ttu-id="cff66-139">Remove-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="cff66-139">Remove-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="cff66-140">删除加载项</span><span class="sxs-lookup"><span data-stu-id="cff66-140">Remove an add-in</span></span>  <br/> |
   
### <a name="create-a-new-add-in"></a><span data-ttu-id="cff66-141">创建新的外接程序</span><span class="sxs-lookup"><span data-stu-id="cff66-141">Create a new add-in</span></span>

<span data-ttu-id="cff66-142">您可以使用 **New-CsPersistentChatAddin** cmdlet 创建新的外接程序。</span><span class="sxs-lookup"><span data-stu-id="cff66-142">You can create a new Add-in by using the **New-CsPersistentChatAddin** cmdlet.</span></span>
  
<span data-ttu-id="cff66-143">例如，以下命令为池池 (ITPersistentChatAddin) 一个新的atl-cs-001.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="cff66-143">For example, the following command creates a new add-in (with the name ITPersistentChatAddin) for the pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="cff66-144">URL 参数和参数值指定 http://atl-cs-001.contoso.com/itchat 外接程序网页的位置：</span><span class="sxs-lookup"><span data-stu-id="cff66-144">The URL parameter and the parameter value http://atl-cs-001.contoso.com/itchat specify the location of the add-in's webpage:</span></span>
  
```PowerShell
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a><span data-ttu-id="cff66-145">配置现有外接程序的设置</span><span class="sxs-lookup"><span data-stu-id="cff66-145">Configure settings for an existing add-in</span></span>

<span data-ttu-id="cff66-146">您可以使用 **Set-CsPersistentChatAddIn cmdlet** 配置现有外接程序的设置。</span><span class="sxs-lookup"><span data-stu-id="cff66-146">You can configure settings for an existing add-in by using the **Set-CsPersistentChatAddIn** cmdlet.</span></span> <span data-ttu-id="cff66-147">例如，以下命令修改分配给持久聊天外接程序 ITPersistentChatAddin 的 URL。</span><span class="sxs-lookup"><span data-stu-id="cff66-147">For example, the following command modifies the URL assigned to the Persistent Chat add-in ITPersistentChatAddin.</span></span> <span data-ttu-id="cff66-148">在这种情况下，URL 更改为 http://atl-cs-001.contoso.com/itchat2:</span><span class="sxs-lookup"><span data-stu-id="cff66-148">In this case, the URL is changed to http://atl-cs-001.contoso.com/itchat2:</span></span>
  
```PowerShell
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a><span data-ttu-id="cff66-149">检索有关加载项的信息</span><span class="sxs-lookup"><span data-stu-id="cff66-149">Retrieve information about add-ins</span></span>

<span data-ttu-id="cff66-150">您可以使用 **Get-CsPersistentChatAddin** cmdlet 获取有关外接程序的信息。</span><span class="sxs-lookup"><span data-stu-id="cff66-150">You can get information about add-ins by using the **Get-CsPersistentChatAddin** cmdlet.</span></span> <span data-ttu-id="cff66-151">例如，以下命令返回有关配置为在组织内使用的所有持久聊天加载项的信息：</span><span class="sxs-lookup"><span data-stu-id="cff66-151">For example, the following command returns information about all the Persistent Chat add-ins configured for use in the organization:</span></span>
  
```PowerShell
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a><span data-ttu-id="cff66-152">删除加载项</span><span class="sxs-lookup"><span data-stu-id="cff66-152">Remove an add-in</span></span>

<span data-ttu-id="cff66-153">您可以使用 **Remove-CsPersistentChatAddIn cmdlet 删除** 外接程序。</span><span class="sxs-lookup"><span data-stu-id="cff66-153">You can remove an Add-in by using the **Remove-CsPersistentChatAddIn** cmdlet.</span></span> <span data-ttu-id="cff66-154">例如，以下命令删除池池上的持久聊天外接程序 ITChatAddin atl-cs-001.contoso.com：</span><span class="sxs-lookup"><span data-stu-id="cff66-154">For example, the following command removes the Persistent Chat add-in ITChatAddin found on the pool atl-cs-001.contoso.com:</span></span>
  
```PowerShell
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


