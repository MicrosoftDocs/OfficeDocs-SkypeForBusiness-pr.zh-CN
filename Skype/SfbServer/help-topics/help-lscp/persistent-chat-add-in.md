---
title: 持久聊天外接程序
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatAddin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66124a70-67e8-4bda-9da5-8ab13afccf49
description: 您可以使用"持久聊天"页的"外接程序"部分将 URL 与持久聊天室关联。 这些 URL 显示在对话可扩展性窗格的聊天室的客户端中。 管理员必须将外接程序添加到已注册的外接程序列表中，并且聊天室管理员/创建者必须将聊天室与其中一个注册的外接程序关联，用户才能在客户端中查看此升级。
ms.openlocfilehash: c90383a26c658e8da73df09368a5d8fe04cfe69b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099498"
---
# <a name="persistent-chat-add-in"></a><span data-ttu-id="5241b-105">持久聊天外接程序</span><span class="sxs-lookup"><span data-stu-id="5241b-105">Persistent Chat Add-in</span></span>

<span data-ttu-id="5241b-106">您可以使用" **持久聊天"** 页的"外接程序" **部分将** URL 与持久聊天室关联。</span><span class="sxs-lookup"><span data-stu-id="5241b-106">You can use the **Add-in** section of the **Persistent Chat** page to associate URLs with Persistent Chat rooms.</span></span> <span data-ttu-id="5241b-107">这些 URL 显示在对话可扩展性窗格的聊天室的客户端中。</span><span class="sxs-lookup"><span data-stu-id="5241b-107">These URLs appear in the client in the chat room in the conversation extensibility pane.</span></span> <span data-ttu-id="5241b-108">管理员必须将外接程序添加到已注册的外接程序列表中，并且聊天室管理员/创建者必须将聊天室与其中一个注册的外接程序关联，用户才能在客户端中查看此升级。</span><span class="sxs-lookup"><span data-stu-id="5241b-108">An administrator must add Add-ins to the list of registered add-ins, and chat room managers/Creators must associate rooms with one of the registered add-ins before users can see this upgrade in their client.</span></span>

<span data-ttu-id="5241b-109">外接程序用于扩展聊天室内体验。</span><span class="sxs-lookup"><span data-stu-id="5241b-109">Add-ins are used to extend the in-room experience.</span></span> <span data-ttu-id="5241b-110">典型的外接程序可能包括一个指向 Silverlight 应用程序的 URL，该应用程序在将股票代码张贴到聊天室时截获，在可扩展性窗格中显示股票历史记录。</span><span class="sxs-lookup"><span data-stu-id="5241b-110">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="5241b-111">其他示例包括将 OneNote 2013 URL 作为外接程序嵌入聊天室，以包括一些共享上下文，例如“第一个想到的品牌”(Top of mind) 或“今日主题”(Topic of the day)。</span><span class="sxs-lookup"><span data-stu-id="5241b-111">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>

<span data-ttu-id="5241b-112">若要为持久聊天室创建外接程序，请参阅 Configure [add-ins for Persistent Chat rooms in Skype for Business Server 2015。](../../manage/persistent-chat/configure-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="5241b-112">To create Add-ins for Persistent Chat rooms, see [Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015](../../manage/persistent-chat/configure-add-ins.md).</span></span> <span data-ttu-id="5241b-113">如果您是持久聊天管理员，可以使用控制面板或 cmdlet 创建Windows PowerShell外接程序。</span><span class="sxs-lookup"><span data-stu-id="5241b-113">If you are a Persistent Chat Administrator, you can create add-ins by using the control panel or Windows PowerShell cmdlets.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="5241b-114">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="5241b-114">Tasks that you can perform</span></span>

<span data-ttu-id="5241b-115">您可以在“外接程序”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="5241b-115">You can perform the following tasks on the **Add-in** page:</span></span>

- [<span data-ttu-id="5241b-116">Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5241b-116">Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/configure-add-ins.md)

## <a name="to-configure-add-ins-for-chat-rooms"></a><span data-ttu-id="5241b-117">配置聊天室外接程序</span><span class="sxs-lookup"><span data-stu-id="5241b-117">To configure Add-ins for chat rooms</span></span>

<span data-ttu-id="5241b-118">下表介绍了该页上的菜单、命令、字段和属性。</span><span class="sxs-lookup"><span data-stu-id="5241b-118">The following lists describe the menus, command, fields, and properties on the page.</span></span>

1. <span data-ttu-id="5241b-119">使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录到您的本地部署中的任一计算机。</span><span class="sxs-lookup"><span data-stu-id="5241b-119">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="5241b-120">从" **开始** "菜单中，选择 Skype for Business Server 控制面板或打开浏览器窗口，然后输入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="5241b-120">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="5241b-121">有关可用于启动控制面板的不同方法的详细信息，请参阅 [Open Lync Server Administrative Tools](/previous-versions/office/lync-server-2013/lync-server-2013-open-lync-server-administrative-tools)。</span><span class="sxs-lookup"><span data-stu-id="5241b-121">For details about the different methods that you can use to start the control panel, see [Open Lync Server Administrative Tools](/previous-versions/office/lync-server-2013/lync-server-2013-open-lync-server-administrative-tools).</span></span>

3. <span data-ttu-id="5241b-122">在左侧导航栏中，单击“持久聊天”，然后单击“外接程序”。</span><span class="sxs-lookup"><span data-stu-id="5241b-122">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>

    <span data-ttu-id="5241b-123">对于多个持久聊天服务器池部署，请从下拉列表中选择相应的池。</span><span class="sxs-lookup"><span data-stu-id="5241b-123">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>

4. <span data-ttu-id="5241b-124">在“外接程序”页上，单击“新建”。</span><span class="sxs-lookup"><span data-stu-id="5241b-124">On the **Add-in** page, click **New**.</span></span>

5. <span data-ttu-id="5241b-125">在 **"选择服务**"中，选择与需要创建外接程序的持久聊天服务器池对应的服务。</span><span class="sxs-lookup"><span data-stu-id="5241b-125">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="5241b-126">外接程序无法从一个池移到另一个池，或者在不同池之间共享。</span><span class="sxs-lookup"><span data-stu-id="5241b-126">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>

6. <span data-ttu-id="5241b-127">在“新建外接程序”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="5241b-127">In **New Add-in**, do the following:</span></span>

   - <span data-ttu-id="5241b-128">在“名称”中，指定新外接程序的名称。</span><span class="sxs-lookup"><span data-stu-id="5241b-128">In **Name**, specify a name for the new add-in.</span></span>

   - <span data-ttu-id="5241b-p107">在“URL”中，指定与外接程序关联的 URL。URL 限制为 http 和 https 协议。</span><span class="sxs-lookup"><span data-stu-id="5241b-p107">In **URL**, specify the URL to be associated with the add-in. URLs are limited to http and https protocols.</span></span>

7. <span data-ttu-id="5241b-131">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="5241b-131">Click **Commit**.</span></span>

## <a name="see-also"></a><span data-ttu-id="5241b-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5241b-132">See also</span></span>

<span data-ttu-id="5241b-133">有关持久聊天服务器特性和功能的详细信息，请参阅 Plan [for Persistent Chat Server in Skype for Business Server 2015、Deploy](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md) [Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)和 Manage Persistent Chat Server in Skype for Business Server [2015。](../../manage/persistent-chat/persistent-chat.md)</span><span class="sxs-lookup"><span data-stu-id="5241b-133">For details about Persistent Chat Server features and capabilities, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md), and [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>