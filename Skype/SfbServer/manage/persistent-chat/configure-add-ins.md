---
title: 在 Skype for Business Server 2015 中配置持久聊天室的加载项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1037909-0750-411a-98c1-3a327eed4ae8
description: 摘要： 了解如何在 Skype for Business Server 2015 配置外接程序 Persistent Chat Server 聊天室。
ms.openlocfilehash: 146f05b181998f995b6e15b0717034a55f518d7f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910254"
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a><span data-ttu-id="e8ef5-103">在 Skype for Business Server 2015 中配置持久聊天室的加载项</span><span class="sxs-lookup"><span data-stu-id="e8ef5-103">Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e8ef5-104">**摘要：** 了解如何在 Skype for Business Server 2015 配置外接程序 Persistent Chat Server 聊天室。</span><span class="sxs-lookup"><span data-stu-id="e8ef5-104">**Summary:** Learn how to configure add-ins for Persistent Chat Server chat rooms in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="e8ef5-105">外接程序用于扩展聊天室内体验，方式是将 URL 与聊天室关联。</span><span class="sxs-lookup"><span data-stu-id="e8ef5-105">Add-ins are used to extend the in-room experience by associating URLs with chat rooms.</span></span> <span data-ttu-id="e8ef5-106">这些 URL 显示在客户端对话可扩展性窗格中。</span><span class="sxs-lookup"><span data-stu-id="e8ef5-106">These URLs appear in the client conversation extensibility pane.</span></span> <span data-ttu-id="e8ef5-107">典型的加载项可能包含指向截获当股票代码张贴到聊天室，并将扩展性窗格中显示库存的历史记录的 Silverlight 应用程序的 URL。</span><span class="sxs-lookup"><span data-stu-id="e8ef5-107">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="e8ef5-108">其他示例包括将 OneNote 2013 URL 作为外接程序嵌入聊天室，以包括一些共享上下文，如“指导思想”或“今日主题”。</span><span class="sxs-lookup"><span data-stu-id="e8ef5-108">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>
  
 <span data-ttu-id="e8ef5-109">您必须首先将外接程序添加到已注册外接程序列表，同时聊天室管理者或创建者需要将聊天室与外接程序关联，然后用户才能在客户端中看到外接程序。</span><span class="sxs-lookup"><span data-stu-id="e8ef5-109">Before users can see an add-in in the client, you must add the add-in to the list of registered add-ins, and chat room Managers or Creators need to associate rooms with the add-in.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e8ef5-110">持久聊天中的业务服务器 2015 Skype 可用但业务服务器 2019年不再支持在 Skype。</span><span class="sxs-lookup"><span data-stu-id="e8ef5-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="e8ef5-111">中团队提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="e8ef5-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="e8ef5-112">有关详细信息，请参阅[从企业对 Microsoft 团队的 Skype 旅程](/microsoftteams/journey-skypeforbusiness-teams)。</span><span class="sxs-lookup"><span data-stu-id="e8ef5-112">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="e8ef5-113">如果您需要使用持久聊天，您的选择是也迁移要求给团队，此功能的用户或继续对业务服务器 2015年使用 Skype。</span><span class="sxs-lookup"><span data-stu-id="e8ef5-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a><span data-ttu-id="e8ef5-114">使用控制面板配置聊天室的外接程序</span><span class="sxs-lookup"><span data-stu-id="e8ef5-114">Configure add-ins for chat rooms by using the Control Panel</span></span>

<span data-ttu-id="e8ef5-115">要使用控制面板配置聊天室的外接程序：</span><span class="sxs-lookup"><span data-stu-id="e8ef5-115">To configure add-ins for chat rooms by using the Control Panel:</span></span>
  
1. <span data-ttu-id="e8ef5-116">使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录您的本地部署中的任一计算机。</span><span class="sxs-lookup"><span data-stu-id="e8ef5-116">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="e8ef5-117">从**开始**菜单上，选择业务 Server Control Panel Skype 或打开一个浏览器窗口中，，然后输入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="e8ef5-117">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="e8ef5-118">在左侧导航栏中，单击“**持久聊天**”，然后单击“**外接程序**”。</span><span class="sxs-lookup"><span data-stu-id="e8ef5-118">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>
    
    <span data-ttu-id="e8ef5-119">对于多个持久聊天服务器池部署，从下拉列表中选择相应的池。</span><span class="sxs-lookup"><span data-stu-id="e8ef5-119">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>
    
4. <span data-ttu-id="e8ef5-120">在“**外接程序**”页上，单击“**新建**”。</span><span class="sxs-lookup"><span data-stu-id="e8ef5-120">On the **Add-in** page, click **New**.</span></span>
    
5. <span data-ttu-id="e8ef5-121">在**选择服务**，选择对应于需要创建外接程序的持久聊天服务器池的服务。</span><span class="sxs-lookup"><span data-stu-id="e8ef5-121">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="e8ef5-122">外接程序无法从一个池移到另一个池，或者在不同池之间共享。</span><span class="sxs-lookup"><span data-stu-id="e8ef5-122">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>
    
6. <span data-ttu-id="e8ef5-123">在“**新建外接程序**”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="e8ef5-123">In **New Add-in**, do the following:</span></span>
    
   - <span data-ttu-id="e8ef5-124">在“**名称**”中，指定新外接程序的名称。</span><span class="sxs-lookup"><span data-stu-id="e8ef5-124">In **Name**, specify a name for the new add-in.</span></span>
    
   - <span data-ttu-id="e8ef5-p104">在“**URL**”中，指定与外接程序关联的 URL。URL 将限制为 http 和 https 协议。</span><span class="sxs-lookup"><span data-stu-id="e8ef5-p104">In **URL**, specify the URL to be associated with the add-in. URLs are limited to the http and https protocols.</span></span>
    
7. <span data-ttu-id="e8ef5-127">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="e8ef5-127">Click **Commit**.</span></span>
    
## <a name="configure-add-ins-by-using-windows-powershell"></a><span data-ttu-id="e8ef5-128">使用 Windows PowerShell 配置外接程序</span><span class="sxs-lookup"><span data-stu-id="e8ef5-128">Configure add-ins by using Windows PowerShell</span></span>

<span data-ttu-id="e8ef5-p105">您可以使用以下 Windows PowerShell cmdlet 配置聊天室的外接程序。有关语法的详细信息，包括所有可用参数，请参阅[Skype for Business Server 2015 Management Shell](../management-shell.md)。</span><span class="sxs-lookup"><span data-stu-id="e8ef5-p105">You can configure add-ins for chat rooms by using the following Windows PowerShell cmdlets. For details about syntax, including all available parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="e8ef5-131">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="e8ef5-131">**Cmdlet**</span></span>|<span data-ttu-id="e8ef5-132">**说明**</span><span class="sxs-lookup"><span data-stu-id="e8ef5-132">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e8ef5-133">New-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="e8ef5-133">New-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="e8ef5-134">创建新的外接程序</span><span class="sxs-lookup"><span data-stu-id="e8ef5-134">Create a new add-in</span></span>  <br/> |
|<span data-ttu-id="e8ef5-135">Set-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="e8ef5-135">Set-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="e8ef5-136">配置现有外接程序的设置</span><span class="sxs-lookup"><span data-stu-id="e8ef5-136">Configure settings for an existing add-in</span></span>  <br/> |
|<span data-ttu-id="e8ef5-137">Get-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="e8ef5-137">Get-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="e8ef5-138">检索有关外接程序的信息</span><span class="sxs-lookup"><span data-stu-id="e8ef5-138">Retrieve information about add-ins</span></span>  <br/> |
|<span data-ttu-id="e8ef5-139">Remove-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="e8ef5-139">Remove-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="e8ef5-140">删除外接程序</span><span class="sxs-lookup"><span data-stu-id="e8ef5-140">Remove an add-in</span></span>  <br/> |
   
### <a name="create-a-new-add-in"></a><span data-ttu-id="e8ef5-141">创建新的外接程序</span><span class="sxs-lookup"><span data-stu-id="e8ef5-141">Create a new add-in</span></span>

<span data-ttu-id="e8ef5-142">可以使用**新建 CsPersistentChatAddin** cmdlet 创建新的加载项。</span><span class="sxs-lookup"><span data-stu-id="e8ef5-142">You can create a new Add-in by using the **New-CsPersistentChatAddin** cmdlet.</span></span>
  
<span data-ttu-id="e8ef5-143">例如，以下命令创建的新外接程序 （具有 ITPersistentChatAddin 名称） 为池 atl cs 001.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="e8ef5-143">For example, the following command creates a new add-in (with the name ITPersistentChatAddin) for the pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="e8ef5-144">URL 参数以及参数值http://atl-cs-001.contoso.com/itchat指定外接程序的网页的位置：</span><span class="sxs-lookup"><span data-stu-id="e8ef5-144">The URL parameter and the parameter value http://atl-cs-001.contoso.com/itchat specify the location of the add-in's webpage:</span></span>
  
```
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a><span data-ttu-id="e8ef5-145">配置现有外接程序的设置</span><span class="sxs-lookup"><span data-stu-id="e8ef5-145">Configure settings for an existing add-in</span></span>

<span data-ttu-id="e8ef5-146">您可以使用 **Set-CsPersistentChatAddIn** cmdlet 配置现有外接程序的设置。</span><span class="sxs-lookup"><span data-stu-id="e8ef5-146">You can configure settings for an existing add-in by using the **Set-CsPersistentChatAddIn** cmdlet.</span></span> <span data-ttu-id="e8ef5-147">例如，以下命令可修改分配给持久聊天外接程序 ITPersistentChatAddin 的URL。</span><span class="sxs-lookup"><span data-stu-id="e8ef5-147">For example, the following command modifies the URL assigned to the Persistent Chat add-in ITPersistentChatAddin.</span></span> <span data-ttu-id="e8ef5-148">在这种情况下，将 URL 更改为http://atl-cs-001.contoso.com/itchat2:</span><span class="sxs-lookup"><span data-stu-id="e8ef5-148">In this case, the URL is changed to http://atl-cs-001.contoso.com/itchat2:</span></span>
  
```
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a><span data-ttu-id="e8ef5-149">检索有关外接程序的信息</span><span class="sxs-lookup"><span data-stu-id="e8ef5-149">Retrieve information about add-ins</span></span>

<span data-ttu-id="e8ef5-p108">您可以使用 **Get-CsPersistentChatAddin** cmdlet 获取有关外接程序的信息。例如，以下命令将为组织中配置使用的所有持久聊天外接程序返回相关信息：</span><span class="sxs-lookup"><span data-stu-id="e8ef5-p108">You can get information about add-ins by using the **Get-CsPersistentChatAddin** cmdlet. For example, the following command returns information about all the Persistent Chat add-ins configured for use in the organization:</span></span>
  
```
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a><span data-ttu-id="e8ef5-152">删除外接程序</span><span class="sxs-lookup"><span data-stu-id="e8ef5-152">Remove an add-in</span></span>

<span data-ttu-id="e8ef5-153">可以通过使用**删除 CsPersistentChatAddIn** cmdlet 删除外接程序。</span><span class="sxs-lookup"><span data-stu-id="e8ef5-153">You can remove an Add-in by using the **Remove-CsPersistentChatAddIn** cmdlet.</span></span> <span data-ttu-id="e8ef5-154">例如，以下命令可删除池 atl-cs-001.contoso.com 中的持久聊天外接程序 ITChatAddin：</span><span class="sxs-lookup"><span data-stu-id="e8ef5-154">For example, the following command removes the Persistent Chat add-in ITChatAddin found on the pool atl-cs-001.contoso.com:</span></span>
  
```
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


