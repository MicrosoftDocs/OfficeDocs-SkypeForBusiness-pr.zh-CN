---
title: 在 Skype for Business 中创建或修改代理组
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
description: 在 Skype for business Server 企业版中，在响应组中创建或修改代理组。
ms.openlocfilehash: 0b496160f00cde80364c0f81c150392405ef7768
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767755"
---
# <a name="create-or-modify-an-agent-group-in-skype-for-business"></a><span data-ttu-id="bb09f-103">在 Skype for Business 中创建或修改代理组</span><span class="sxs-lookup"><span data-stu-id="bb09f-103">Create or modify an agent group in Skype for Business</span></span>
 
<span data-ttu-id="bb09f-104">在 Skype for business Server 企业版中，在响应组中创建或修改代理组。</span><span class="sxs-lookup"><span data-stu-id="bb09f-104">Create or modify an agent group in Response Group, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="bb09f-105">创建代理组时要选择分配给该组的代理并指定其他组设置，如路由方法以及代理能否登录到组和从组注销。</span><span class="sxs-lookup"><span data-stu-id="bb09f-105">When you create an agent group, you select the agents that are assigned to the group and specify additional group settings, such as the routing method and whether an agent can sign in to and out of the group.</span></span> 
  
<span data-ttu-id="bb09f-106">必须登录和注销组（不同于登录或注销 Skype for Business）的代理称为正式代理。</span><span class="sxs-lookup"><span data-stu-id="bb09f-106">An agent who must sign in and out of the group, which is different from signing in or out of Skype for Business, is called a formal agent.</span></span> <span data-ttu-id="bb09f-107">正式代理必须登录到组，然后才能接收路由至该组的呼叫。</span><span class="sxs-lookup"><span data-stu-id="bb09f-107">Formal agents must be signed in to the group before they can receive calls routed to the group.</span></span> <span data-ttu-id="bb09f-108">这对于以兼职形式应答组中的呼叫的代理很有用。</span><span class="sxs-lookup"><span data-stu-id="bb09f-108">This can be useful for agents who answer calls from the group on a part-time basis.</span></span> <span data-ttu-id="bb09f-109">正式代理通过单击 Skype for Business 中的菜单项来登录和注销其组，打开 Windows Internet Explorer Internet 浏览器并显示网页控制台。</span><span class="sxs-lookup"><span data-stu-id="bb09f-109">Formal agents sign in and out of their groups by clicking a menu item in Skype for Business to open the Windows Internet Explorer Internet browser and display a webpage console.</span></span>
  
<span data-ttu-id="bb09f-110">不登录到组或从组注销的代理称为 非正式代理。</span><span class="sxs-lookup"><span data-stu-id="bb09f-110">An agent who does not sign in or out of the group is called an informal agent.</span></span> <span data-ttu-id="bb09f-111">当用户登录到 Skype for Business 时，非正式代理会自动登录到该组，并且不能注销该组。</span><span class="sxs-lookup"><span data-stu-id="bb09f-111">Informal agents are automatically signed in to the group when they sign in to Skype for Business, and they cannot sign out of the group.</span></span>
  
<span data-ttu-id="bb09f-112">仅本地用户可成为代理。</span><span class="sxs-lookup"><span data-stu-id="bb09f-112">Only on-premises users can be agents.</span></span> <span data-ttu-id="bb09f-113">如果代理从本地移动到联机，则响应组调用将不会路由到该代理。</span><span class="sxs-lookup"><span data-stu-id="bb09f-113">If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>
  
<span data-ttu-id="bb09f-114">使用下列过程之一可创建或修改代理组。</span><span class="sxs-lookup"><span data-stu-id="bb09f-114">Use one of the following procedures to create or modify an agent group.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="bb09f-p104">如果将用户分配为响应组代理，需告知用户，如果用户已启用隐私模式，则需搜索“RGS Presence Watcher”联系人并将其添加到联系人列表。已启用隐私模式但未将“RGS Presence Watcher”添加到联系人列表中的代理将无法接收拨打到响应组的呼叫。未启用隐私模式的代理不受影响。</span><span class="sxs-lookup"><span data-stu-id="bb09f-p104">When you assign users as response group agents, inform them that, if they have Privacy mode enabled, they need to search for "RGS Presence Watcher" contacts and add them to their Contacts list. Agents who have Privacy mode enabled, but who do not have "RGS Presence Watcher" in their Contacts list, cannot receive calls to the response group. Agents who do not have Privacy mode enabled are not affected.</span></span> 
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-an-agent-group"></a><span data-ttu-id="bb09f-118">使用 "Skype for Business 服务器" 控制面板创建或修改代理组</span><span class="sxs-lookup"><span data-stu-id="bb09f-118">To use Skype for Business Server Control Panel to create or modify an agent group</span></span>

1. <span data-ttu-id="bb09f-119">以 RTCUniversalServerAdmins 组成员的身份，或支持响应组的某个预定义管理角色的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="bb09f-119">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bb09f-120">如果您是托管工作流的委派响应组管理员之一，则可创建组并在管理的工作流中使用这些组。</span><span class="sxs-lookup"><span data-stu-id="bb09f-120">If you are one of the delegated Response Group Managers for a managed workflow, you can create groups and use them in the workflows that you manage.</span></span> 
  
2. <span data-ttu-id="bb09f-121">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="bb09f-121">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="bb09f-122">在左侧导航栏中，单击“响应组”\*\*\*\*，然后单击“组”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bb09f-122">In the left navigation bar, click **Response Groups**, and then click **Group**.</span></span>
    
4. <span data-ttu-id="bb09f-123">在“组”\*\*\*\* 页上执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="bb09f-123">On the **Group** page, do one of the following:</span></span>
    
   - <span data-ttu-id="bb09f-p105">要创建新的代理组，请单击“新建”\*\*\*\*。在“选择服务”\*\*\*\* 搜索字段中，键入要添加组的“ApplicationServer”\*\*\*\* 服务的全部或部分名称，在服务的结果列表中单击所需的服务，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bb09f-p105">To create a new agent group, click **New**. In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service where you want to add the group. In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
   - <span data-ttu-id="bb09f-p106">要修改现有的代理组，在搜索字段中键入代理组的全部或部分名称。在结果列表中，单击您需要的组，单击“编辑”\*\*\*\*，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bb09f-p106">To modify an existing agent group, type all or part of the name of the agent group in the search field. In the resulting list, click the group that you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="bb09f-129">在“名称”\*\*\*\* 中，键入代理组的标识名称。</span><span class="sxs-lookup"><span data-stu-id="bb09f-129">In **Name**, type an identifying name for the agent group.</span></span>
    
6. <span data-ttu-id="bb09f-130">在“说明”\*\*\*\* 中，键入对该组的说明。</span><span class="sxs-lookup"><span data-stu-id="bb09f-130">In **Description**, type a description for the group.</span></span>
    
7. <span data-ttu-id="bb09f-131">在“参与策略”\*\*\*\* 中，选择下列操作之一，从而设置组的登录行为：</span><span class="sxs-lookup"><span data-stu-id="bb09f-131">In the **Participation policy**, select one of the following to set up the sign-in behavior for the group:</span></span>
    
   - <span data-ttu-id="bb09f-132">选择“非正式”\*\*\*\* 指定组中的代理无需登录组和从组中注销。</span><span class="sxs-lookup"><span data-stu-id="bb09f-132">Select **Informal** to specify that agents in the group do not need to sign in and out of the group.</span></span> <span data-ttu-id="bb09f-133">当代理登录到 Skype for Business 时，会自动登录到该组。</span><span class="sxs-lookup"><span data-stu-id="bb09f-133">Agents are automatically signed in to the group when they sign in to Skype for Business.</span></span>
    
   - <span data-ttu-id="bb09f-134">选择“正式”\*\*\*\* 指定组中的代理必须登录到组和从组中注销。</span><span class="sxs-lookup"><span data-stu-id="bb09f-134">Select **Formal** to specify that agents in the group must sign in and out of the group.</span></span> <span data-ttu-id="bb09f-135">选择此选项时，代理将单击 Skype for Business 中的菜单项以打开 Internet Explorer，并显示用于登录和注销组的网页控制台。</span><span class="sxs-lookup"><span data-stu-id="bb09f-135">When you select this option, agents click a menu item in Skype for Business to open Internet Explorer and display a webpage console for signing in and out of the group.</span></span>
    
8. <span data-ttu-id="bb09f-136">在“警报时间(秒)”\*\*\*\* 中，指定将呼叫转至下一个空闲的代理之前，向某位代理响铃的秒数（默认为 20 秒）。</span><span class="sxs-lookup"><span data-stu-id="bb09f-136">In **Alert time (seconds)**, specify the number of seconds to ring an agent before offering the call to the next available agent (the default is 20 seconds).</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="bb09f-p109">代理警报时间设置不能超出 180 秒，如果代理警报时间超过 180 秒，客户端应用程序会拒绝呼叫，因为 SIP 事务计时器达到其最长等待时间。</span><span class="sxs-lookup"><span data-stu-id="bb09f-p109">The agent alert time setting cannot exceed 180 seconds. If the agent alert time exceeds 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span> 
  
9. <span data-ttu-id="bb09f-139">在“路由方法”\*\*\*\* 中，选择将呼叫路由至组中代理的方法，具体如下：</span><span class="sxs-lookup"><span data-stu-id="bb09f-139">In **Routing method**, select the method for routing calls to agents in the group as follows:</span></span>
    
   - <span data-ttu-id="bb09f-140">若要首先向已闲置时间最长的工程师（在 Skype for Business 中有最长的**可用**或**非活动**状态）提供新呼叫，请单击 "**最长空闲**"。</span><span class="sxs-lookup"><span data-stu-id="bb09f-140">To offer a new call first to the agent who has been idle the longest (has had a presence of **Available** or **Inactive** in Skype for Business the longest), click **Longest idle**.</span></span> 
    
   - <span data-ttu-id="bb09f-p110">若要将新呼叫同时路由至所有空闲的代理，请单击“并行”\*\*\*\*。呼叫将发往第一个接受该呼叫的代理。</span><span class="sxs-lookup"><span data-stu-id="bb09f-p110">To offer a new call to all available agents at the same time, click **Parallel**. The call is sent to the first agent who accepts it.</span></span>
    
   - <span data-ttu-id="bb09f-143">若要将新呼叫轮流路由至每个代理，请单击“循环”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bb09f-143">To offer a new call to each agent in turn, click **Round robin**.</span></span> 
    
   - <span data-ttu-id="bb09f-144">若要将新呼叫始终按照“代理”\*\*\*\* 列表中代理的排列顺序路由至代理，请单击“串行”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bb09f-144">To always offer a new call to the agents in the order in which they are listed in the **Agent** list, click **Serial**.</span></span> 
    
   - <span data-ttu-id="bb09f-145">若要为所有登录到 Skype for Business 和响应组应用程序的代理提供新的呼叫，而不考虑其当前状态，请单击 "**助理**"。</span><span class="sxs-lookup"><span data-stu-id="bb09f-145">To offer a new call to all agents who are signed into Skype for Business and the Response Group application at the same time, regardless of their current presence, click **Attendant**.</span></span> <span data-ttu-id="bb09f-146">配置为代理的用户可查看所有正在等待的呼叫，并可以按任意顺序应答等待中的呼叫。</span><span class="sxs-lookup"><span data-stu-id="bb09f-146">Users who are configured as agents can see all the calls that are waiting and answer waiting calls in any order.</span></span> <span data-ttu-id="bb09f-147">呼叫将发往第一个接受该呼叫的代理，之后，其他代理不会再看到此呼叫。</span><span class="sxs-lookup"><span data-stu-id="bb09f-147">The call is sent to the first agent who accepts it, after which the other agents no longer see the call.</span></span>
    
10. <span data-ttu-id="bb09f-148">在“代理”\*\*\*\* 中，指定创建代理列表要采用的方式：</span><span class="sxs-lookup"><span data-stu-id="bb09f-148">In **Agents**, specify how you want to create your agents list:</span></span>
    
    - <span data-ttu-id="bb09f-149">要使用自定义的代理列表，请单击“定义自定义代理组”\*\*\*\*，并执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="bb09f-149">To use a custom list of agents, click **Define a custom group of agents**, and do one of the following:</span></span>
    
    - <span data-ttu-id="bb09f-p112">要向代理组添加用户，请单击“选择”\*\*\*\*，然后在“选择代理”\*\*\*\* 搜索字段中，键入要添加到该组的用户的全部或部分名称，再单击“查找”\*\*\*\*。在结果代理列表中，单击该用户，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bb09f-p112">To add a user to the agent group, click **Select**, and then in the **Select Agents** search field, type all or part of the name of the user that you want to add to this group, and then click **Find**. In the resulting list of agents, click the user, and then click **OK**.</span></span>
    
    - <span data-ttu-id="bb09f-152">要从代理组中删除用户，请在代理列表中，单击要删除的用户，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bb09f-152">To remove a user from the agent group, in the list of agents, click the user you want to remove, and then click **Remove**.</span></span>
    
    - <span data-ttu-id="bb09f-153">对于使用循环路由或串行路由的组，要更改呼叫路由至该组中代理的顺序，请在代理列表中，单击用户，然后单击向上箭头或向下箭头。</span><span class="sxs-lookup"><span data-stu-id="bb09f-153">To change the order in which agents are offered calls in groups that use either round robin routing or serial routing, in the list of agents, click a user, and then click the up arrow or down arrow.</span></span> 
    
    - <span data-ttu-id="bb09f-154">要将 Microsoft Exchange Server 通讯组列表用作代理组，请单击“使用现有的电子邮件通讯组列表”\*\*\*\*，然后在“通讯组列表地址”\*\*\*\* 中键入该通讯组列表的电子邮件地址（例如 NetworkSupport@contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="bb09f-154">To use a Microsoft Exchange Server distribution list as your agent group, click **Use an existing email distribution list**, and then in **Distribution list address**, type the email address of the distribution list (for example, NetworkSupport@contoso.com).</span></span>
    
      <span data-ttu-id="bb09f-155">如果使用电子邮件通讯组列表，则将受到以下约束：</span><span class="sxs-lookup"><span data-stu-id="bb09f-155">If you use an email distribution list, you are subject to the following constraints:</span></span>
    
      - <span data-ttu-id="bb09f-p113">不能为代理组选择多个通讯组列表。每个组仅支持一个通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="bb09f-p113">You cannot select multiple distribution lists for the agent group. Each group supports only a single distribution list.</span></span>
    
      - <span data-ttu-id="bb09f-158">如果通讯组列表包含一个或多个通讯组列表，则不会将嵌套的通讯组列表的成员添加到代理列表。</span><span class="sxs-lookup"><span data-stu-id="bb09f-158">If the distribution list contains one or more distribution lists, members of the nested distribution lists are not added to the agent list.</span></span>
    
      - <span data-ttu-id="bb09f-159">如果选择串行路由或循环路由，则服务器会根据路由方法和通讯组列表中代理的排列顺序，将传入呼叫路由至相应的代理。</span><span class="sxs-lookup"><span data-stu-id="bb09f-159">If serial or round robin routing is selected, the server offers an incoming call to the appropriate agent according to the routing method and according to the order in which agents are listed in the distribution list.</span></span>
    
      - <span data-ttu-id="bb09f-p114">如果通讯组列表包含已启用 Lync Server 2010 但未启用企业语音的用户，它们将作为不正常的代理添加到代理组。确保通信组列表的所有成员已为其用户帐户启用企业语音。</span><span class="sxs-lookup"><span data-stu-id="bb09f-p114">If the distribution list contains users for which Lync Server 2010 is enabled but Enterprise Voice is not enabled, they will be added to the agent group as dysfunctional agents. Make sure that all members of the distribution list have Enterprise Voice enabled for their user accounts.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="bb09f-162">如果您使用电子邮件通讯组列表，响应组管理员或用户可能会看到隐藏的成员身份或隐藏的列表。</span><span class="sxs-lookup"><span data-stu-id="bb09f-162">If you use an email distribution list, hidden memberships or hidden lists might become visible to the Response Group administrator or users.</span></span> 
  
    <span data-ttu-id="bb09f-163">在下列情况中，可以看见隐藏成员身份或隐藏列表：</span><span class="sxs-lookup"><span data-stu-id="bb09f-163">Hidden memberships or hidden lists can become visible as follows:</span></span>
    
     - <span data-ttu-id="bb09f-164">如果配置了通讯组列表以使成员身份处于隐藏状态，并且响应组管理员将通讯组列表分配给代理列表，则用户可以调用该组以查明成员的成员。</span><span class="sxs-lookup"><span data-stu-id="bb09f-164">If a distribution list was configured so that the membership is hidden and the Response Group administrator assigns the distribution list to the agent list, users can call the group to find out who the members are.</span></span> 
    
     - <span data-ttu-id="bb09f-165">如果已将通讯组列表配置为在 Exchange 全局地址列表中隐藏，则响应组管理员可能能够查看通讯组列表并将其分配给代理列表（如果响应组进程具有相应的用户权限），并且权限，即使管理员没有相应的用户权利和权限也是如此。</span><span class="sxs-lookup"><span data-stu-id="bb09f-165">If a distribution list was configured so that it is hidden in the Exchange Global Address List, the Response Group administrator might be able to see the distribution list and assign it to the agent list if the Response Group process has the appropriate user rights and permissions, even if the administrator does not have the appropriate user rights and permissions.</span></span>
    
11. <span data-ttu-id="bb09f-166">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="bb09f-166">Click **Commit**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-agent-group"></a><span data-ttu-id="bb09f-167">使用 Skype for Business Server Management Shell 创建或修改代理组</span><span class="sxs-lookup"><span data-stu-id="bb09f-167">To use Skype for Business Server Management Shell to create or modify an agent group</span></span>

1. <span data-ttu-id="bb09f-168">以 RTCUniversalServerAdmins 组成员的身份，或支持响应组的某个预定义管理角色的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="bb09f-168">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="bb09f-169">启动 Skype for Business Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\* 和“Skype for Business 2015”\*\*\*\*，然后单击“Skype for Business Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bb09f-169">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="bb09f-170">使用  **New-CsRgsAgentGroup** 可创建新代理组。</span><span class="sxs-lookup"><span data-stu-id="bb09f-170">Use **New-CsRgsAgentGroup** to create a new agent group.</span></span> <span data-ttu-id="bb09f-171">使用  **Set-CsRgsAgentGroup** 可修改现有代理组。</span><span class="sxs-lookup"><span data-stu-id="bb09f-171">Use **Set-CsRgsAgentGroup** to modify an existing agent group.</span></span> <span data-ttu-id="bb09f-172">在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="bb09f-172">At the command line, run:</span></span>
    
   ```powershell
   New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
   ```

    <span data-ttu-id="bb09f-173">例如：</span><span class="sxs-lookup"><span data-stu-id="bb09f-173">For example:</span></span>
    
   ```powershell
   New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="bb09f-p116">代理警报时间设置不能超出 180 秒，如果代理警报时间超过 180 秒，客户端应用程序会拒绝呼叫，因为 SIP 事务计时器达到其最长等待时间。</span><span class="sxs-lookup"><span data-stu-id="bb09f-p116">The agent alert time setting cannot exceed 180 seconds. If the agent alert time is greater than 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span> 
  
4. <span data-ttu-id="bb09f-p117">确认是否已创建代理组。运行：</span><span class="sxs-lookup"><span data-stu-id="bb09f-p117">Confirm that the agent group is created. Run:</span></span>
    
   ```powershell
   Get-CsRgsAgentGroup -Name "Help Desk"
   ```

## <a name="see-also"></a><span data-ttu-id="bb09f-178">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bb09f-178">See also</span></span>

[<span data-ttu-id="bb09f-179">CsService</span><span class="sxs-lookup"><span data-stu-id="bb09f-179">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
  
[<span data-ttu-id="bb09f-180">新-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="bb09f-180">New-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)
  
[<span data-ttu-id="bb09f-181">Set-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="bb09f-181">Set-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csrgsagentgroup?view=skype-ps)
  
[<span data-ttu-id="bb09f-182">CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="bb09f-182">Get-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csrgsagentgroup?view=skype-ps)
