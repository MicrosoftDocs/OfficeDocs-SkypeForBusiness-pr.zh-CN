---
title: Lync Server 2013：创建或修改代理组
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an agent group
ms:assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205370(v=OCS.15)
ms:contentKeyID: 48185784
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99fed5bf80979ef807f45ce7e5ecdc8e8a16329b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739552"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-agent-group-in-lync-server-2013"></a><span data-ttu-id="c0a4a-102">在 Lync Server 2013 中创建或修改代理组</span><span class="sxs-lookup"><span data-stu-id="c0a4a-102">Create or modify an agent group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0a4a-103">_**主题上次修改时间：** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="c0a4a-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="c0a4a-104">使用下列过程之一可创建或修改代理组。</span><span class="sxs-lookup"><span data-stu-id="c0a4a-104">Use one of the following procedures to create or modify an agent group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c0a4a-105">管理员（例如 CsVoiceAdministrator）必须先为企业语音和 Lync 服务器启用用户，然后才能将用户分配给代理组。</span><span class="sxs-lookup"><span data-stu-id="c0a4a-105">An Administrator—for example, CsVoiceAdministrator—must enable users for Enterprise Voice and Lync Server before the users can be assigned to agent groups.</span></span> <span data-ttu-id="c0a4a-106">如果你是托管工作流的委派的响应组管理器之一，则可以创建代理组并使用你管理的工作流中的代理组。</span><span class="sxs-lookup"><span data-stu-id="c0a4a-106">If you are one of the delegated Response Group Managers for a managed workflow, you can create agent groups and use the agent groups in the workflows that you manage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c0a4a-p102">如果将用户分配为响应组代理，需告知用户，如果用户已启用隐私模式，则需搜索“RGS Presence Watcher”联系人并将其添加到联系人列表。已启用隐私模式但未将“RGS Presence Watcher”添加到联系人列表中的代理将无法接收拨打到响应组的呼叫。未启用隐私模式的代理不受影响。</span><span class="sxs-lookup"><span data-stu-id="c0a4a-p102">When you assign users as response group agents, inform them that, if they have Privacy mode enabled, they need to search for "RGS Presence Watcher" contacts and add them to their Contacts list. Agents who have Privacy mode enabled, but who do not have "RGS Presence Watcher" in their Contacts list, cannot receive calls to the response group. Agents who do not have Privacy mode enabled are not affected.</span></span>



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-an-agent-group"></a><span data-ttu-id="c0a4a-110">使用 Lync Server "控制面板" 创建或修改代理组</span><span class="sxs-lookup"><span data-stu-id="c0a4a-110">To use Lync Server Control Panel to create or modify an agent group</span></span>

1.  <span data-ttu-id="c0a4a-111">以 RTCUniversalServerAdmins 组成员的身份，或支持响应组的某个预定义管理角色的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="c0a4a-111">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c0a4a-112">如果您是托管工作流的委派响应组管理员之一，则可创建组并在管理的工作流中使用这些组。</span><span class="sxs-lookup"><span data-stu-id="c0a4a-112">If you are one of the delegated Response Group Managers for a managed workflow, you can create groups and use them in the workflows that you manage.</span></span>

    
    </div>

2.  <span data-ttu-id="c0a4a-113">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="c0a4a-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c0a4a-114">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="c0a4a-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c0a4a-115">在左侧导航栏中，单击“响应组”\*\*\*\*，然后单击“组”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c0a4a-115">In the left navigation bar, click **Response Groups**, and then click **Group**.</span></span>

4.  <span data-ttu-id="c0a4a-116">在“组”\*\*\*\* 页上执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="c0a4a-116">On the **Group** page, do one of the following:</span></span>
    
      - <span data-ttu-id="c0a4a-p104">要创建新的代理组，请单击“新建”\*\*\*\*。在“选择服务”\*\*\*\* 搜索字段中，键入要添加组的“ApplicationServer”\*\*\*\* 服务的全部或部分名称，在服务的结果列表中单击所需的服务，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c0a4a-p104">To create a new agent group, click **New**. In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service where you want to add the group. In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="c0a4a-p105">要修改现有的代理组，在搜索字段中键入代理组的全部或部分名称。在结果列表中，单击您需要的组，单击“编辑”\*\*\*\*，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c0a4a-p105">To modify an existing agent group, type all or part of the name of the agent group in the search field. In the resulting list, click the group that you want, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="c0a4a-122">在“名称”\*\*\*\* 中，键入代理组的标识名称。</span><span class="sxs-lookup"><span data-stu-id="c0a4a-122">In **Name**, type an identifying name for the agent group.</span></span>

6.  <span data-ttu-id="c0a4a-123">在“说明”\*\*\*\* 中，键入对该组的说明。</span><span class="sxs-lookup"><span data-stu-id="c0a4a-123">In **Description**, type a description for the group.</span></span>

7.  <span data-ttu-id="c0a4a-124">在“参与策略”\*\*\*\* 中，选择下列操作之一，从而设置组的登录行为：</span><span class="sxs-lookup"><span data-stu-id="c0a4a-124">In the **Participation policy**, select one of the following to set up the sign-in behavior for the group:</span></span>
    
      - <span data-ttu-id="c0a4a-125">选择“非正式”\*\*\*\* 指定组中的代理无需登录组和从组中注销。</span><span class="sxs-lookup"><span data-stu-id="c0a4a-125">Select **Informal** to specify that agents in the group do not need to sign in and out of the group.</span></span> <span data-ttu-id="c0a4a-126">当代理登录到 Lync Server 2013 时，它会自动登录到该组。</span><span class="sxs-lookup"><span data-stu-id="c0a4a-126">Agents are automatically signed in to the group when they sign in to Lync Server 2013.</span></span>
    
      - <span data-ttu-id="c0a4a-127">选择“正式”\*\*\*\* 指定组中的代理必须登录到组和从组中注销。</span><span class="sxs-lookup"><span data-stu-id="c0a4a-127">Select **Formal** to specify that agents in the group must sign in and out of the group.</span></span> <span data-ttu-id="c0a4a-128">选择此选项时，代理将单击 Lync 中的菜单项以打开 Internet Explorer，并显示用于登录和注销组的网页控制台。</span><span class="sxs-lookup"><span data-stu-id="c0a4a-128">When you select this option, agents click a menu item in Lync to open Internet Explorer and display a webpage console for signing in and out of the group.</span></span>

8.  <span data-ttu-id="c0a4a-129">在“警报时间(秒)”\*\*\*\* 中，指定将呼叫转至下一个空闲的代理之前，向某位代理响铃的秒数（默认为 20 秒）。</span><span class="sxs-lookup"><span data-stu-id="c0a4a-129">In **Alert time (seconds)**, specify the number of seconds to ring an agent before offering the call to the next available agent (the default is 20 seconds).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c0a4a-p108">代理警报时间设置不能超出 180 秒，如果代理警报时间超过 180 秒，客户端应用程序会拒绝呼叫，因为 SIP 事务计时器达到其最长等待时间。</span><span class="sxs-lookup"><span data-stu-id="c0a4a-p108">The agent alert time setting cannot exceed 180 seconds. If the agent alert time exceeds 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span>

    
    </div>

9.  <span data-ttu-id="c0a4a-132">在“路由方法”\*\*\*\* 中，选择将呼叫路由至组中代理的方法，具体如下：</span><span class="sxs-lookup"><span data-stu-id="c0a4a-132">In **Routing method**, select the method for routing calls to agents in the group as follows:</span></span>
    
      - <span data-ttu-id="c0a4a-133">若要首先向已闲置时间最长的代理（已有最长时间的 Lync 服务器中存在**可用**或**非活动**）提供新呼叫，请单击 "**最长空闲**"。</span><span class="sxs-lookup"><span data-stu-id="c0a4a-133">To offer a new call first to the agent who has been idle the longest (has had a presence of **Available** or **Inactive** in Lync Server the longest), click **Longest idle**.</span></span>
    
      - <span data-ttu-id="c0a4a-p109">若要将新呼叫同时路由至所有空闲的代理，请单击“并行”\*\*\*\*。呼叫将发往第一个接受该呼叫的代理。</span><span class="sxs-lookup"><span data-stu-id="c0a4a-p109">To offer a new call to all available agents at the same time, click **Parallel**. The call is sent to the first agent who accepts it.</span></span>
    
      - <span data-ttu-id="c0a4a-136">若要将新呼叫轮流路由至每个代理，请单击“循环”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c0a4a-136">To offer a new call to each agent in turn, click **Round robin**.</span></span>
    
      - <span data-ttu-id="c0a4a-137">若要将新呼叫始终按照“代理”\*\*\*\* 列表中代理的排列顺序路由至代理，请单击“串行”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c0a4a-137">To always offer a new call to the agents in the order in which they are listed in the **Agent** list, click **Serial**.</span></span>
    
      - <span data-ttu-id="c0a4a-138">若要同时向所有登录到 Lync Server 2013 和响应组应用程序的代理提供新呼叫，请单击 "**助理**"。</span><span class="sxs-lookup"><span data-stu-id="c0a4a-138">To offer a new call to all agents who are signed into Lync Server 2013 and the Response Group application at the same time, regardless of their current presence, click **Attendant**.</span></span> <span data-ttu-id="c0a4a-139">配置为代理的 Lync 2010 助理用户可以查看正在等待的所有呼叫，并以任何顺序应答等待通话。</span><span class="sxs-lookup"><span data-stu-id="c0a4a-139">Lync 2010 Attendant users who are configured as agents can see all the calls that are waiting and answer waiting calls in any order.</span></span> <span data-ttu-id="c0a4a-140">呼叫将发送给接受它的第一位工程师，之后，其他 Lync 2010 助理用户将不再看到该呼叫。</span><span class="sxs-lookup"><span data-stu-id="c0a4a-140">The call is sent to the first agent who accepts it, after which the other Lync 2010 Attendant users no longer see the call.</span></span>

10. <span data-ttu-id="c0a4a-141">在“代理”\*\*\*\* 中，指定创建代理列表要采用的方式：</span><span class="sxs-lookup"><span data-stu-id="c0a4a-141">In **Agents**, specify how you want to create your agents list:</span></span>
    
      - <span data-ttu-id="c0a4a-142">要使用自定义的代理列表，请单击“定义自定义代理组”\*\*\*\*，并执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="c0a4a-142">To use a custom list of agents, click **Define a custom group of agents**, and do one of the following:</span></span>
        
          - <span data-ttu-id="c0a4a-p111">要向代理组添加用户，请单击“选择”\*\*\*\*，然后在“选择代理”\*\*\*\* 搜索字段中，键入要添加到该组的用户的全部或部分名称，再单击“查找”\*\*\*\*。在结果代理列表中，单击该用户，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c0a4a-p111">To add a user to the agent group, click **Select**, and then in the **Select Agents** search field, type all or part of the name of the user that you want to add to this group, and then click **Find**. In the resulting list of agents, click the user, and then click **OK**.</span></span>
        
          - <span data-ttu-id="c0a4a-145">要从代理组中删除用户，请在代理列表中，单击要删除的用户，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c0a4a-145">To remove a user from the agent group, in the list of agents, click the user you want to remove, and then click **Remove**.</span></span>
        
          - <span data-ttu-id="c0a4a-146">对于使用循环路由或串行路由的组，要更改呼叫路由至该组中代理的顺序，请在代理列表中，单击用户，然后单击向上箭头或向下箭头。</span><span class="sxs-lookup"><span data-stu-id="c0a4a-146">To change the order in which agents are offered calls in groups that use either round robin routing or serial routing, in the list of agents, click a user, and then click the up arrow or down arrow.</span></span>
    
      - <span data-ttu-id="c0a4a-147">要将 Microsoft Exchange Server 通讯组列表用作代理组，请单击“使用现有的电子邮件通讯组列表”\*\*\*\*，然后在“通讯组列表地址”\*\*\*\* 中键入该通讯组列表的电子邮件地址（例如 NetworkSupport@contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="c0a4a-147">To use a Microsoft Exchange Server distribution list as your agent group, click **Use an existing email distribution list**, and then in **Distribution list address**, type the email address of the distribution list (for example, NetworkSupport@contoso.com).</span></span>
        
        <span data-ttu-id="c0a4a-148">如果使用电子邮件通讯组列表，则将受到以下约束：</span><span class="sxs-lookup"><span data-stu-id="c0a4a-148">If you use an email distribution list, you are subject to the following constraints:</span></span>
        
          - <span data-ttu-id="c0a4a-p112">不能为代理组选择多个通讯组列表。每个组仅支持一个通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="c0a4a-p112">You cannot select multiple distribution lists for the agent group. Each group supports only a single distribution list.</span></span>
        
          - <span data-ttu-id="c0a4a-151">如果通讯组列表包含一个或多个通讯组列表，则不会将嵌套的通讯组列表的成员添加到代理列表。</span><span class="sxs-lookup"><span data-stu-id="c0a4a-151">If the distribution list contains one or more distribution lists, members of the nested distribution lists are not added to the agent list.</span></span>
        
          - <span data-ttu-id="c0a4a-152">如果选择串行路由或循环路由，则服务器会根据路由方法和通讯组列表中代理的排列顺序，将传入呼叫路由至相应的代理。</span><span class="sxs-lookup"><span data-stu-id="c0a4a-152">If serial or round robin routing is selected, the server offers an incoming call to the appropriate agent according to the routing method and according to the order in which agents are listed in the distribution list.</span></span>
        
          - <span data-ttu-id="c0a4a-p113">如果通讯组列表包含已启用 Lync Server 2010 但未启用企业语音的用户，它们将作为不正常的代理添加到代理组。确保通信组列表的所有成员已为其用户帐户启用企业语音。</span><span class="sxs-lookup"><span data-stu-id="c0a4a-p113">If the distribution list contains users for which Lync Server 2010 is enabled but Enterprise Voice is not enabled, they will be added to the agent group as dysfunctional agents. Make sure that all members of the distribution list have Enterprise Voice enabled for their user accounts.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="c0a4a-155">如果您使用电子邮件通讯组列表，响应组管理员或用户可能会看到隐藏的成员身份或隐藏的列表。</span><span class="sxs-lookup"><span data-stu-id="c0a4a-155">If you use an email distribution list, hidden memberships or hidden lists might become visible to the Response Group administrator or users.</span></span>

        
        </div>
        
        <span data-ttu-id="c0a4a-156">在下列情况中，可以看见隐藏成员身份或隐藏列表：</span><span class="sxs-lookup"><span data-stu-id="c0a4a-156">Hidden memberships or hidden lists can become visible as follows:</span></span>
        
          - <span data-ttu-id="c0a4a-157">如果配置了通讯组列表以使成员身份处于隐藏状态，并且响应组管理员将通讯组列表分配给代理列表，则用户可以调用该组以查明成员的成员。</span><span class="sxs-lookup"><span data-stu-id="c0a4a-157">If a distribution list was configured so that the membership is hidden and the Response Group administrator assigns the distribution list to the agent list, users can call the group to find out who the members are.</span></span>
        
          - <span data-ttu-id="c0a4a-158">如果已将通讯组列表配置为在 Exchange 全局地址列表中隐藏，则响应组管理员可能能够查看通讯组列表并将其分配给代理列表（如果响应组进程具有相应的用户权限），并且权限，即使管理员没有相应的用户权利和权限也是如此。</span><span class="sxs-lookup"><span data-stu-id="c0a4a-158">If a distribution list was configured so that it is hidden in the Exchange Global Address List, the Response Group administrator might be able to see the distribution list and assign it to the agent list if the Response Group process has the appropriate user rights and permissions, even if the administrator does not have the appropriate user rights and permissions.</span></span>

11. <span data-ttu-id="c0a4a-159">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="c0a4a-159">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-agent-group"></a><span data-ttu-id="c0a4a-160">使用 Windows PowerShell 创建或修改代理组</span><span class="sxs-lookup"><span data-stu-id="c0a4a-160">To use Windows PowerShell to create or modify an agent group</span></span>

1.  <span data-ttu-id="c0a4a-161">以 RTCUniversalServerAdmins 组成员的身份，或支持响应组的某个预定义管理角色的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="c0a4a-161">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="c0a4a-162">启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="c0a4a-162">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="c0a4a-163">使用  **New-CsRgsAgentGroup** 可创建新代理组。</span><span class="sxs-lookup"><span data-stu-id="c0a4a-163">Use **New-CsRgsAgentGroup** to create a new agent group.</span></span> <span data-ttu-id="c0a4a-164">使用  **Set-CsRgsAgentGroup** 可修改现有代理组。</span><span class="sxs-lookup"><span data-stu-id="c0a4a-164">Use **Set-CsRgsAgentGroup** to modify an existing agent group.</span></span> <span data-ttu-id="c0a4a-165">在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="c0a4a-165">At the command line, run:</span></span>
    
        New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
    
    <span data-ttu-id="c0a4a-166">例如：</span><span class="sxs-lookup"><span data-stu-id="c0a4a-166">For example:</span></span>
    
        New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c0a4a-p115">代理警报时间设置不能超出 180 秒，如果代理警报时间超过 180 秒，客户端应用程序会拒绝呼叫，因为 SIP 事务计时器达到其最长等待时间。</span><span class="sxs-lookup"><span data-stu-id="c0a4a-p115">The agent alert time setting cannot exceed 180 seconds. If the agent alert time is greater than 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span>

    
    </div>

4.  <span data-ttu-id="c0a4a-p116">确认是否已创建代理组。运行：</span><span class="sxs-lookup"><span data-stu-id="c0a4a-p116">Confirm that the agent group is created. Run:</span></span>
    
        Get-CsRgsAgentGroup -Name "Help Desk"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c0a4a-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c0a4a-171">See Also</span></span>


[<span data-ttu-id="c0a4a-172">在 Lync Server 2013 中删除代理组</span><span class="sxs-lookup"><span data-stu-id="c0a4a-172">Delete an agent group in Lync Server 2013</span></span>](lync-server-2013-delete-an-agent-group.md)  


[<span data-ttu-id="c0a4a-173">在 Lync Server 2013 中管理响应组代理组</span><span class="sxs-lookup"><span data-stu-id="c0a4a-173">Managing Response Group agent groups in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-agent-groups.md)  
[<span data-ttu-id="c0a4a-174">CsService</span><span class="sxs-lookup"><span data-stu-id="c0a4a-174">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="c0a4a-175">新-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="c0a4a-175">New-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup)  
[<span data-ttu-id="c0a4a-176">Set-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="c0a4a-176">Set-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsAgentGroup)  
[<span data-ttu-id="c0a4a-177">CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="c0a4a-177">Get-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsAgentGroup)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

