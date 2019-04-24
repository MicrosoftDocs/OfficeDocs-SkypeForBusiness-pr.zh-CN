---
title: 持久聊天外接程序主页
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatAddinMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0c0ecf64-258d-4b43-8fac-fa5ffa4e7646
description: 持久聊天页的外接程序部分可用于将 Url 与持久聊天聊天室相关联。 这些 URL 将显示在对话可扩展性窗格的聊天室中的客户端中。 管理员必须将外接程序添加到注册的外接程序列表中，且聊天室管理员/创建者必须将聊天室与其中一个注册的外接程序相关联，这样用户才能在其客户端中看到此升级。
ms.openlocfilehash: 8b0add45aaf4baf55c30d4640da09e07f96cdb0c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32200805"
---
# <a name="persistent-chat-add-in-main-page"></a><span data-ttu-id="fa08e-105">持久聊天外接程序主页</span><span class="sxs-lookup"><span data-stu-id="fa08e-105">Persistent Chat Add-in Main Page</span></span>

<span data-ttu-id="fa08e-106">**持久聊天**页的**外接程序**部分可用于将 Url 与持久聊天聊天室相关联。</span><span class="sxs-lookup"><span data-stu-id="fa08e-106">You can use the **Add-in** section of the **Persistent Chat** page to associate URLs with Persistent Chat rooms.</span></span> <span data-ttu-id="fa08e-107">这些 URL 将显示在对话可扩展性窗格的聊天室中的客户端中。</span><span class="sxs-lookup"><span data-stu-id="fa08e-107">These URLs appear in the client in the chat room in the conversation extensibility pane.</span></span> <span data-ttu-id="fa08e-108">管理员必须将外接程序添加到注册的外接程序列表中，且聊天室管理员/创建者必须将聊天室与其中一个注册的外接程序相关联，这样用户才能在其客户端中看到此升级。</span><span class="sxs-lookup"><span data-stu-id="fa08e-108">An administrator must add Add-ins to the list of registered add-ins, and chat room managers/Creators must associate rooms with one of the registered add-ins before users can see this upgrade in their client.</span></span>

<span data-ttu-id="fa08e-109">外接程序用于扩展聊天室内体验。</span><span class="sxs-lookup"><span data-stu-id="fa08e-109">Add-ins are used to extend the in-room experience.</span></span> <span data-ttu-id="fa08e-110">典型的加载项可能包含指向截获当股票代码张贴到聊天室，并将扩展性窗格中显示库存的历史记录的 Silverlight 应用程序的 URL。</span><span class="sxs-lookup"><span data-stu-id="fa08e-110">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="fa08e-111">其他示例包括将 OneNote 2013 URL 作为外接程序嵌入聊天室，以包括一些共享上下文，如“指导思想”或“今日主题”。</span><span class="sxs-lookup"><span data-stu-id="fa08e-111">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>

<span data-ttu-id="fa08e-112">若要创建的持久聊天聊天室加载项，请参阅[配置外接程序中的业务服务器 2015 Skype 的持久聊天聊天室](../../manage/persistent-chat/configure-add-ins.md)。</span><span class="sxs-lookup"><span data-stu-id="fa08e-112">To create Add-ins for Persistent Chat rooms, see [Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015](../../manage/persistent-chat/configure-add-ins.md).</span></span> <span data-ttu-id="fa08e-113">如果您是 a Persistent Chat Administrator，您可以使用控制面板或 Windows PowerShell cmdlet 创建加载项。</span><span class="sxs-lookup"><span data-stu-id="fa08e-113">If you are a Persistent Chat Administrator, you can create add-ins by using the control panel or Windows PowerShell cmdlets.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="fa08e-114">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="fa08e-114">Tasks you can perform</span></span>

<span data-ttu-id="fa08e-115">您可以在“**外接程序**”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="fa08e-115">You can perform the following tasks on the **Add-in** page:</span></span>

- [<span data-ttu-id="fa08e-116">在 Skype for Business Server 2015 中配置持久聊天室的加载项</span><span class="sxs-lookup"><span data-stu-id="fa08e-116">Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/configure-add-ins.md)

## <a name="to-configure-add-ins-for-chat-rooms"></a><span data-ttu-id="fa08e-117">配置聊天室外接程序</span><span class="sxs-lookup"><span data-stu-id="fa08e-117">To configure Add-ins for chat rooms</span></span>

<span data-ttu-id="fa08e-118">下表介绍了该页上的菜单、命令、字段和属性。</span><span class="sxs-lookup"><span data-stu-id="fa08e-118">The following lists describe the menus, command, fields, and properties on the page.</span></span>

1. <span data-ttu-id="fa08e-119">使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录您的本地部署中的任一计算机。</span><span class="sxs-lookup"><span data-stu-id="fa08e-119">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="fa08e-120">从**开始**菜单上，选择业务 Server Control Panel Skype 或打开一个浏览器窗口中，，然后输入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="fa08e-120">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="fa08e-121">有关可用于启动控制面板的不同方法的详细信息，请参阅[Open Lync Server Administrative Tools](https://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx)。</span><span class="sxs-lookup"><span data-stu-id="fa08e-121">For details about the different methods that you can use to start control panel, see [Open Lync Server Administrative Tools](https://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx).</span></span>

3. <span data-ttu-id="fa08e-122">在左侧导航栏中，单击“**持久聊天**”，然后单击“**外接程序**”。</span><span class="sxs-lookup"><span data-stu-id="fa08e-122">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>

    <span data-ttu-id="fa08e-123">对于多个持久聊天服务器池部署，从下拉列表中选择相应的池。</span><span class="sxs-lookup"><span data-stu-id="fa08e-123">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>

4. <span data-ttu-id="fa08e-124">在“**外接程序**”页上，单击“**新建**”。</span><span class="sxs-lookup"><span data-stu-id="fa08e-124">On the **Add-in** page, click **New**.</span></span>

5. <span data-ttu-id="fa08e-125">在**选择服务**，选择对应于需要创建外接程序的持久聊天服务器池的服务。</span><span class="sxs-lookup"><span data-stu-id="fa08e-125">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="fa08e-126">外接程序无法从一个池移到另一个池，或者在不同池之间共享。</span><span class="sxs-lookup"><span data-stu-id="fa08e-126">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>

6. <span data-ttu-id="fa08e-127">在“**新建外接程序**”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="fa08e-127">In **New Add-in**, do the following:</span></span>

   - <span data-ttu-id="fa08e-128">在“**名称**”中，指定新外接程序的名称。</span><span class="sxs-lookup"><span data-stu-id="fa08e-128">In **Name**, specify a name for the new add-in.</span></span>

   - <span data-ttu-id="fa08e-p107">在“**URL**”中，指定与外接程序关联的 URL。URL 将限制为 http 和 https 协议。</span><span class="sxs-lookup"><span data-stu-id="fa08e-p107">In **URL**, specify the URL to be associated with the add-in. URLs are limited to http and https protocols.</span></span>

7. <span data-ttu-id="fa08e-131">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="fa08e-131">Click **Commit**.</span></span>

## <a name="see-also"></a><span data-ttu-id="fa08e-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fa08e-132">See also</span></span>

<span data-ttu-id="fa08e-133">有关详细信息 Persistent Chat Server 特性和功能，请参阅[Plan for Persistent Chat Server in 业务服务器 2015年的 Skype](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)、[部署持久聊天服务器中的 Business Server 2015 Skype](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)和[管理持久聊天服务器在业务服务器 2015 Skype](../../manage/persistent-chat/persistent-chat.md)。</span><span class="sxs-lookup"><span data-stu-id="fa08e-133">For details about Persistent Chat Server features and capabilities, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md), and [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>


