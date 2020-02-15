---
title: Lync Server 2013：配置聊天室的外接程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure add-ins for rooms
ms:assetid: 4eeaf19e-8369-4f6f-af65-a283cf7daa1c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204878(v=OCS.15)
ms:contentKeyID: 48184090
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40a9e7a2c947d18e8359e2199ec8c3e40e00ed98
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028773"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-add-ins-for-rooms-in-lync-server-2013"></a><span data-ttu-id="22def-102">在 Lync Server 2013 中配置聊天室的外接程序</span><span class="sxs-lookup"><span data-stu-id="22def-102">Configure add-ins for rooms in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22def-103">_**上次修改的主题：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="22def-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="22def-104">在 Lync Server 2013 控制面板中，可以使用 "**持久聊天**" 页的 "**加载项**" 部分将 url 与持久聊天室相关联。</span><span class="sxs-lookup"><span data-stu-id="22def-104">In Lync Server 2013 Control Panel, you can use the **Add-in** section of the **Persistent Chat** page to associate URLs with Persistent Chat rooms.</span></span> <span data-ttu-id="22def-105">这些 Url 显示在对话可扩展性窗格中聊天室的 Lync 2013 客户端中。</span><span class="sxs-lookup"><span data-stu-id="22def-105">These URLs appear in the Lync 2013 client in the chat room in the conversation extensibility pane.</span></span> <span data-ttu-id="22def-106">管理员必须将外接程序添加到已注册的外接程序列表中，聊天室管理员/创建者必须将聊天室与注册的外接程序关联，然后用户才能在其 Lync 2013 客户端中看到此升级。</span><span class="sxs-lookup"><span data-stu-id="22def-106">An administrator must add Add-ins to the list of registered add-ins, and chat room managers/Creators have to associate rooms with one of the registered add-ins before users can see this upgrade in their Lync 2013 client.</span></span>

<span data-ttu-id="22def-107">外接程序用于扩展聊天室内体验。</span><span class="sxs-lookup"><span data-stu-id="22def-107">Add-ins are used to extend the in-room experience.</span></span> <span data-ttu-id="22def-108">典型加载项可能包含指向 Silverlight 应用程序的 URL，在将股票代号发布到聊天室时，会对该 URL 进行拦截，并在 "可扩展性" 窗格中显示股票历史记录。</span><span class="sxs-lookup"><span data-stu-id="22def-108">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="22def-109">其他示例包括将 OneNote 2013 URL 作为外接程序嵌入聊天室，以包括一些共享上下文，如“指导思想”或“今日主题”。</span><span class="sxs-lookup"><span data-stu-id="22def-109">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>

<div>

## <a name="to-configure-add-ins-for-chat-rooms"></a><span data-ttu-id="22def-110">配置聊天室外接程序</span><span class="sxs-lookup"><span data-stu-id="22def-110">To configure Add-ins for chat rooms</span></span>

1.  <span data-ttu-id="22def-111">使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录到您的本地部署中的任一计算机。</span><span class="sxs-lookup"><span data-stu-id="22def-111">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="22def-112">从 "**开始**" 菜单中，选择 "Lync Server 控制面板" 或打开一个浏览器窗口，然后输入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="22def-112">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="22def-113">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="22def-113">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="22def-114">您还可以使用 Windows PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="22def-114">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="22def-115">有关详细信息，请参阅部署文档中的<A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">使用 Windows PowerShell Cmdlet 配置持久聊天服务器</A>。</span><span class="sxs-lookup"><span data-stu-id="22def-115">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="22def-116">在左侧导航栏中，单击“持久聊天”\*\*\*\*，然后单击“外接程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="22def-116">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>
    
    <span data-ttu-id="22def-117">对于多个持久聊天服务器池部署，请从下拉列表中选择相应的池。</span><span class="sxs-lookup"><span data-stu-id="22def-117">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>

4.  <span data-ttu-id="22def-118">在“外接程序”\*\*\*\* 页上，单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="22def-118">On the **Add-in** page, click **New**.</span></span>

5.  <span data-ttu-id="22def-119">在 "**选择服务**" 中，选择与需要在其中创建外接程序的持久聊天服务器池对应的服务。</span><span class="sxs-lookup"><span data-stu-id="22def-119">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="22def-120">外接程序无法从一个池移到另一个池，或者在不同池之间共享。</span><span class="sxs-lookup"><span data-stu-id="22def-120">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>

6.  <span data-ttu-id="22def-121">在“新建外接程序”\*\*\*\* 中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="22def-121">In **New Add-in**, do the following:</span></span>
    
      - <span data-ttu-id="22def-122">在“名称”\*\*\*\* 中，指定新外接程序的名称。</span><span class="sxs-lookup"><span data-stu-id="22def-122">In **Name**, specify a name for the new add-in.</span></span>
    
      - <span data-ttu-id="22def-p106">在“URL”\*\*\*\* 中，指定与外接程序关联的 URL。URL 限制为 http 和 https 协议。</span><span class="sxs-lookup"><span data-stu-id="22def-p106">In **URL**, specify the URL to be associated with the add-in. URLs are limited to http and https protocols.</span></span>

7.  <span data-ttu-id="22def-125">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="22def-125">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="22def-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="22def-126">See Also</span></span>


[<span data-ttu-id="22def-127">打开 Lync Server 2013 管理工具</span><span class="sxs-lookup"><span data-stu-id="22def-127">Open Lync Server 2013 administrative tools</span></span>](lync-server-2013-open-lync-server-administrative-tools.md)  


[<span data-ttu-id="22def-128">使用 Windows PowerShell cmdlet 配置持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="22def-128">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</span></span>](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

