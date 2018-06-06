---
title: 在 Skype for Business Server 2015 中配置持久聊天室的加载项
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1037909-0750-411a-98c1-3a327eed4ae8
description: 摘要： 了解如何在 Skype for Business Server 2015 配置外接程序 Persistent Chat Server 聊天室。
ms.openlocfilehash: 64017115370c24c8c4a117f595230a6f5f741afd
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569963"
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a><span data-ttu-id="6d5d7-103">在 Skype for Business Server 2015 中配置持久聊天室的加载项</span><span class="sxs-lookup"><span data-stu-id="6d5d7-103">Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="6d5d7-104">**摘要：** 了解如何在 Skype for Business Server 2015 配置外接程序 Persistent Chat Server 聊天室。</span><span class="sxs-lookup"><span data-stu-id="6d5d7-104">**Summary:** Learn how to configure add-ins for Persistent Chat Server chat rooms in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="6d5d7-105">外接程序用于扩展聊天室内体验，方式是将 URL 与聊天室关联。</span><span class="sxs-lookup"><span data-stu-id="6d5d7-105">Add-ins are used to extend the in-room experience by associating URLs with chat rooms.</span></span> <span data-ttu-id="6d5d7-106">这些 URL 显示在客户端对话可扩展性窗格中。</span><span class="sxs-lookup"><span data-stu-id="6d5d7-106">These URLs appear in the client conversation extensibility pane.</span></span> <span data-ttu-id="6d5d7-107">典型的加载项可能包含指向截获当股票代码张贴到聊天室，并将扩展性窗格中显示库存的历史记录的 Silverlight 应用程序的 URL。</span><span class="sxs-lookup"><span data-stu-id="6d5d7-107">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="6d5d7-108">其他示例包括将 OneNote 2013 URL 作为外接程序嵌入聊天室，以包括一些共享上下文，如“指导思想”或“今日主题”。</span><span class="sxs-lookup"><span data-stu-id="6d5d7-108">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>
  
 <span data-ttu-id="6d5d7-109">您必须首先将外接程序添加到已注册外接程序列表，同时聊天室管理者或创建者需要将聊天室与外接程序关联，然后用户才能在客户端中看到外接程序。</span><span class="sxs-lookup"><span data-stu-id="6d5d7-109">Before users can see an add-in in the client, you must add the add-in to the list of registered add-ins, and chat room Managers or Creators need to associate rooms with the add-in.</span></span>
  
## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a><span data-ttu-id="6d5d7-110">使用控制面板配置聊天室的外接程序</span><span class="sxs-lookup"><span data-stu-id="6d5d7-110">Configure add-ins for chat rooms by using the Control Panel</span></span>

<span data-ttu-id="6d5d7-111">要使用控制面板配置聊天室的外接程序：</span><span class="sxs-lookup"><span data-stu-id="6d5d7-111">To configure add-ins for chat rooms by using the Control Panel:</span></span>
  
1. <span data-ttu-id="6d5d7-112">使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录您的本地部署中的任一计算机。</span><span class="sxs-lookup"><span data-stu-id="6d5d7-112">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="6d5d7-113">从**开始**菜单上，选择业务 Server Control Panel Skype 或打开一个浏览器窗口中，，然后输入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="6d5d7-113">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="6d5d7-114">在左侧导航栏中，单击“**持久聊天**”，然后单击“**外接程序**”。</span><span class="sxs-lookup"><span data-stu-id="6d5d7-114">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>
    
    <span data-ttu-id="6d5d7-115">对于多个持久聊天服务器池部署，从下拉列表中选择相应的池。</span><span class="sxs-lookup"><span data-stu-id="6d5d7-115">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>
    
4. <span data-ttu-id="6d5d7-116">在“**外接程序**”页上，单击“**新建**”。</span><span class="sxs-lookup"><span data-stu-id="6d5d7-116">On the **Add-in** page, click **New**.</span></span>
    
5. <span data-ttu-id="6d5d7-117">在**选择服务**，选择对应于需要创建外接程序的持久聊天服务器池的服务。</span><span class="sxs-lookup"><span data-stu-id="6d5d7-117">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="6d5d7-118">外接程序无法从一个池移到另一个池，或者在不同池之间共享。</span><span class="sxs-lookup"><span data-stu-id="6d5d7-118">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>
    
6. <span data-ttu-id="6d5d7-119">在“**新建外接程序**”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="6d5d7-119">In **New Add-in**, do the following:</span></span>
    
  - <span data-ttu-id="6d5d7-120">在“**名称**”中，指定新外接程序的名称。</span><span class="sxs-lookup"><span data-stu-id="6d5d7-120">In **Name**, specify a name for the new add-in.</span></span>
    
  - <span data-ttu-id="6d5d7-p103">在“**URL**”中，指定与外接程序关联的 URL。URL 将限制为 http 和 https 协议。</span><span class="sxs-lookup"><span data-stu-id="6d5d7-p103">In **URL**, specify the URL to be associated with the add-in. URLs are limited to the http and https protocols.</span></span>
    
7. <span data-ttu-id="6d5d7-123">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="6d5d7-123">Click **Commit**.</span></span>
    
## <a name="configure-add-ins-by-using-windows-powershell"></a><span data-ttu-id="6d5d7-124">使用 Windows PowerShell 配置外接程序</span><span class="sxs-lookup"><span data-stu-id="6d5d7-124">Configure add-ins by using Windows PowerShell</span></span>

<span data-ttu-id="6d5d7-125">您可以使用以下 Windows PowerShell cmdlet 配置聊天室的外接程序。</span><span class="sxs-lookup"><span data-stu-id="6d5d7-125">You can configure add-ins for chat rooms by using the following Windows PowerShell cmdlets.</span></span> <span data-ttu-id="6d5d7-126">有关语法，包括所有可用的参数的详细信息，请参阅[Skype 的业务服务器 2015年命令行管理程序](../management-shell.md)。</span><span class="sxs-lookup"><span data-stu-id="6d5d7-126">For details about syntax, including all available parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="6d5d7-127">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="6d5d7-127">**Cmdlet**</span></span>|<span data-ttu-id="6d5d7-128">**说明**</span><span class="sxs-lookup"><span data-stu-id="6d5d7-128">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6d5d7-129">New-cspersistentchataddin</span><span class="sxs-lookup"><span data-stu-id="6d5d7-129">New-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="6d5d7-130">创建新的外接程序</span><span class="sxs-lookup"><span data-stu-id="6d5d7-130">Create a new add-in</span></span>  <br/> |
|<span data-ttu-id="6d5d7-131">Set-cspersistentchataddin</span><span class="sxs-lookup"><span data-stu-id="6d5d7-131">Set-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="6d5d7-132">配置现有外接程序的设置</span><span class="sxs-lookup"><span data-stu-id="6d5d7-132">Configure settings for an existing add-in</span></span>  <br/> |
|<span data-ttu-id="6d5d7-133">Get-cspersistentchataddin</span><span class="sxs-lookup"><span data-stu-id="6d5d7-133">Get-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="6d5d7-134">检索有关外接程序的信息</span><span class="sxs-lookup"><span data-stu-id="6d5d7-134">Retrieve information about add-ins</span></span>  <br/> |
|<span data-ttu-id="6d5d7-135">删除 CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="6d5d7-135">Remove-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="6d5d7-136">删除外接程序</span><span class="sxs-lookup"><span data-stu-id="6d5d7-136">Remove an add-in</span></span>  <br/> |
   
### <a name="create-a-new-add-in"></a><span data-ttu-id="6d5d7-137">创建新的外接程序</span><span class="sxs-lookup"><span data-stu-id="6d5d7-137">Create a new add-in</span></span>

<span data-ttu-id="6d5d7-138">可以使用**新建 CsPersistentChatAddin** cmdlet 创建新的加载项。</span><span class="sxs-lookup"><span data-stu-id="6d5d7-138">You can create a new Add-in by using the **New-CsPersistentChatAddin** cmdlet.</span></span>
  
<span data-ttu-id="6d5d7-139">例如，以下命令创建的新外接程序 （具有 ITPersistentChatAddin 名称） 为池 atl cs 001.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="6d5d7-139">For example, the following command creates a new add-in (with the name ITPersistentChatAddin) for the pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="6d5d7-140">URL 参数以及参数值http://atl-cs-001.contoso.com/itchat指定外接程序的网页的位置：</span><span class="sxs-lookup"><span data-stu-id="6d5d7-140">The URL parameter and the parameter value http://atl-cs-001.contoso.com/itchat specify the location of the add-in's webpage:</span></span>
  
```
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a><span data-ttu-id="6d5d7-141">配置现有外接程序的设置</span><span class="sxs-lookup"><span data-stu-id="6d5d7-141">Configure settings for an existing add-in</span></span>

<span data-ttu-id="6d5d7-142">您可以使用 **Set-CsPersistentChatAddIn** cmdlet 配置现有外接程序的设置。</span><span class="sxs-lookup"><span data-stu-id="6d5d7-142">You can configure settings for an existing add-in by using the **Set-CsPersistentChatAddIn** cmdlet.</span></span> <span data-ttu-id="6d5d7-143">例如，以下命令可修改分配给持久聊天外接程序 ITPersistentChatAddin 的URL。</span><span class="sxs-lookup"><span data-stu-id="6d5d7-143">For example, the following command modifies the URL assigned to the Persistent Chat add-in ITPersistentChatAddin.</span></span> <span data-ttu-id="6d5d7-144">在这种情况下，将 URL 更改为http://atl-cs-001.contoso.com/itchat2:</span><span class="sxs-lookup"><span data-stu-id="6d5d7-144">In this case, the URL is changed to http://atl-cs-001.contoso.com/itchat2:</span></span>
  
```
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a><span data-ttu-id="6d5d7-145">检索有关外接程序的信息</span><span class="sxs-lookup"><span data-stu-id="6d5d7-145">Retrieve information about add-ins</span></span>

<span data-ttu-id="6d5d7-p107">您可以使用 **Get-CsPersistentChatAddin** cmdlet 获取有关外接程序的信息。例如，以下命令将为组织中配置使用的所有持久聊天外接程序返回相关信息：</span><span class="sxs-lookup"><span data-stu-id="6d5d7-p107">You can get information about add-ins by using the **Get-CsPersistentChatAddin** cmdlet. For example, the following command returns information about all the Persistent Chat add-ins configured for use in the organization:</span></span>
  
```
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a><span data-ttu-id="6d5d7-148">删除外接程序</span><span class="sxs-lookup"><span data-stu-id="6d5d7-148">Remove an add-in</span></span>

<span data-ttu-id="6d5d7-149">可以通过使用**删除 CsPersistentChatAddIn** cmdlet 删除外接程序。</span><span class="sxs-lookup"><span data-stu-id="6d5d7-149">You can remove an Add-in by using the **Remove-CsPersistentChatAddIn** cmdlet.</span></span> <span data-ttu-id="6d5d7-150">例如，以下命令可删除池 atl-cs-001.contoso.com 中的持久聊天外接程序 ITChatAddin：</span><span class="sxs-lookup"><span data-stu-id="6d5d7-150">For example, the following command removes the Persistent Chat add-in ITChatAddin found on the pool atl-cs-001.contoso.com:</span></span>
  
```
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


