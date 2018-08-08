---
title: 规划 Business Server Skype 中的响应组应用程序
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6cc333e7-4029-4372-86b2-016040c415fb
description: 规划业务 Server 企业语音的 Skype 响应组，这样可使您可以设置呼叫路由到用户组。 包括音频文件要求。
ms.openlocfilehash: 4fbdfd1428d66865f3f704c4005935deefd370f2
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20970182"
---
# <a name="plan-for-the-response-group-application-in-skype-for-business-server"></a><span data-ttu-id="40489-104">规划 Business Server Skype 中的响应组应用程序</span><span class="sxs-lookup"><span data-stu-id="40489-104">Plan for the Response Group application in Skype for Business Server</span></span>
 
<span data-ttu-id="40489-105">规划业务 Server 企业语音的 Skype 响应组，这样可使您可以设置呼叫路由到用户组。</span><span class="sxs-lookup"><span data-stu-id="40489-105">Planning for response groups in Skype for Business Server Enterprise Voice, which enables you to set up call routing to groups of users.</span></span> <span data-ttu-id="40489-106">包括音频文件要求。</span><span class="sxs-lookup"><span data-stu-id="40489-106">Includes audio file requirements.</span></span>
  
<span data-ttu-id="40489-107">如果贵组织拥有的应答和管理特定类型的呼叫的人员的组，如客户服务、 内部技术支持或常规的电话支持用于部门，则可以部署要管理这些类型的呼叫的响应组应用程序。</span><span class="sxs-lookup"><span data-stu-id="40489-107">If your organization has groups of people who answer and manage certain types of calls, such as for customer service, an internal help desk, or general telephone support for a department, you can deploy the Response Group application to manage these types of calls.</span></span> <span data-ttu-id="40489-108">响应组应用程序传送和传入呼叫排队至指定称为代理的人员。</span><span class="sxs-lookup"><span data-stu-id="40489-108">The Response Group application routes and queues incoming calls to designated persons, who are known as agents.</span></span> <span data-ttu-id="40489-109">您可以通过响应组来增加电话支持服务的使用并降低运行这些服务的开销。</span><span class="sxs-lookup"><span data-stu-id="40489-109">You can increase the use of telephone support services and reduce the overhead of running these services by using response groups.</span></span>
  
<span data-ttu-id="40489-110">当呼叫者呼叫响应组时，呼叫会基于智能寻线或呼叫者对互动语音响应 (IVR) 问题的回答路由至代理。</span><span class="sxs-lookup"><span data-stu-id="40489-110">When a caller calls a response group, the call is routed to an agent based on a hunt group or the caller's answers to interactive voice response (IVR) questions.</span></span> <span data-ttu-id="40489-111">响应组应用程序使用标准响应组路由方法将呼叫路由到下一个空闲的代理。</span><span class="sxs-lookup"><span data-stu-id="40489-111">The Response Group application uses standard response group routing methods to route the call to the next available agent.</span></span> <span data-ttu-id="40489-112">支持的呼叫路由方法包括串行、最长闲置、并行、循环以及助理路由（即每次传入呼叫时都将同时呼叫所有代理，无论其当前状态如何）。</span><span class="sxs-lookup"><span data-stu-id="40489-112">Supported call routing methods include serial, longest-idle, parallel, round robin, and Attendant routing (that is, all agents are called at the same time for every incoming call, regardless of their current presence).</span></span> 
  
<span data-ttu-id="40489-p105">如果没有可用的代理，呼叫将保留在一个队列中，直到代理可用为止。在队列中时，呼叫者将听到音乐，直到可用代理接受呼叫为止。如果队列已满，或者呼叫在队列中已超时，则呼叫者可能会听到一则消息，然后呼叫将断开连接或转接到其他目标，例如其他电话号码或语音信箱。当代理接受呼叫时，呼叫者可能会（也可能不会）看到代理的身份，具体取决于管理员如何配置响应组。代理可以是正式的，这意味着他们必须登录到组，然后才能接受路由至该组的呼叫；也可以是非正式的，这意味着他们无需登录到组，在组外即可接受呼叫。</span><span class="sxs-lookup"><span data-stu-id="40489-p105">If no agents are available, the call is held in a queue until an agent is available. While in the queue, the caller hears music until an available agent accepts the call. If the queue is full, or if the call times out while in the queue, the caller might hear a message and then is either disconnected or transferred to a different destination, such as a different phone number or voicemail. When an agent accepts the call, the caller might or might not be able to see the agent's identity, depending on how the administrator configures the response group. Agents can either be formal, which means that they must sign in to the group before they can accept calls routed to the group, or informal, which means that they do not sign into and out of the group to accept calls.</span></span>
  
> [!NOTE]
> <span data-ttu-id="40489-118">仅本地用户可成为代理。</span><span class="sxs-lookup"><span data-stu-id="40489-118">Only on-premises users can be agents.</span></span> <span data-ttu-id="40489-119">如果代理从内部部署移到 online 时，响应组呼叫将不会被路由到的代理。</span><span class="sxs-lookup"><span data-stu-id="40489-119">If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="40489-120">响应组应用程序使用名为匹配配对的内部服务队列呼叫并找到空闲的代理。</span><span class="sxs-lookup"><span data-stu-id="40489-120">The Response Group application uses an internal service, called Match Making, to queue calls and find available agents.</span></span> <span data-ttu-id="40489-121">运行响应组应用程序的每台计算机运行 Match Making 服务，但只有一个 Match Making 服务每个池每次-处于活动状态其他为被动。</span><span class="sxs-lookup"><span data-stu-id="40489-121">Each computer that runs the Response Group application runs the Match Making service, but only one Match Making service per pool is active at a time--the others are passive.</span></span> <span data-ttu-id="40489-122">如果在计划外中断期间，活动 Match Making 服务变得不可用，则某一个非活动 Match Making 服务将变成活动状态。</span><span class="sxs-lookup"><span data-stu-id="40489-122">If the active Match Making service becomes unavailable during an unplanned outage, one of the passive Match Making services becomes active.</span></span> <span data-ttu-id="40489-123">响应组应用程序会尽力确保该呼叫路由和队列尽力。</span><span class="sxs-lookup"><span data-stu-id="40489-123">The Response Group application does its best to make sure that call routing and queuing continues uninterrupted.</span></span> <span data-ttu-id="40489-124">但是，当转换 Match Making 服务时，会丢失此时正在传输的所有呼叫。</span><span class="sxs-lookup"><span data-stu-id="40489-124">However, when a Match Making service transition occurs, any calls that are in transfer at the time are lost.</span></span> <span data-ttu-id="40489-125">例如，如果由于前端服务器将要向下，当前正在处理的活动 Match Making 服务上的任何呼叫转换为前端服务器也会丢失。</span><span class="sxs-lookup"><span data-stu-id="40489-125">For example, if the transition is due to the Front End Server going down, any calls currently being handled by the active Match Making service on that Front End Server are also lost.</span></span> 
  
## <a name="response-group-workflows"></a><span data-ttu-id="40489-126">响应组工作流</span><span class="sxs-lookup"><span data-stu-id="40489-126">Response group workflows</span></span>

<span data-ttu-id="40489-p108">工作流定义了从电话响铃到有人接听电话这段时间内呼叫的行为。工作流指定用于保留呼叫的队列，并指定用于智能寻线的路由方法或用于互动响应组的问题和答案。工作流还定义了诸如欢迎消息、保持音乐、工作时间和假日等设置。</span><span class="sxs-lookup"><span data-stu-id="40489-p108">A workflow defines the behavior of a call from the time that the phone rings to the time that someone answers the call. The workflow specifies the queue to use for holding the call, and specifies the routing method to use for hunt groups or the questions and answers to use for interactive response groups. A workflow also defines settings such as a welcome message, music on hold, business hours, and holidays.</span></span>
  
> [!NOTE]
> <span data-ttu-id="40489-130">必须先创建代理组和队列，然后再创建使用这些组和队列的工作流。</span><span class="sxs-lookup"><span data-stu-id="40489-130">You must create agent groups and queues before you create a workflow that uses them.</span></span> 
  
## <a name="management-of-response-groups"></a><span data-ttu-id="40489-131">响应组的管理</span><span class="sxs-lookup"><span data-stu-id="40489-131">Management of response groups</span></span>

<span data-ttu-id="40489-132">Skype 业务服务器，在两个管理角色是可用于管理响应组： 响应组管理器和响应组管理员。</span><span class="sxs-lookup"><span data-stu-id="40489-132">In Skype for Business Server, two management roles are available for managing response groups: Response Group Manager and Response Group Administrator.</span></span> <span data-ttu-id="40489-133">响应组管理员可以管理任何响应组的任何方面。</span><span class="sxs-lookup"><span data-stu-id="40489-133">Response Group Administrators can manage any aspect of any response group.</span></span> <span data-ttu-id="40489-134">响应组管理员可以管理只有某些方面，并仅用于响应组的他们所拥有。</span><span class="sxs-lookup"><span data-stu-id="40489-134">Response Group Managers can manage only certain aspects, and only for the response groups that they own.</span></span> <span data-ttu-id="40489-135">管理员角色可以帮助您降低管理成本，因为您可以委派的特定的响应组有限的到启用了企业语音的任何用户的责任。</span><span class="sxs-lookup"><span data-stu-id="40489-135">The Manager role can help you reduce your administration costs, because you can delegate limited responsibilities for specific response groups to any user who is enabled for Enterprise Voice.</span></span> <span data-ttu-id="40489-136">注意，用户可以同时是响应组 Manager 和响应组 Administrator。</span><span class="sxs-lookup"><span data-stu-id="40489-136">Note that a user can be both a Response Group Manager and a Response Group Administrator.</span></span> 
  
<span data-ttu-id="40489-137">若要容纳 Manager 角色，响应组应用程序，请使用托管或非托管**工作流类型**。</span><span class="sxs-lookup"><span data-stu-id="40489-137">To accommodate the Manager role, Response Group application uses a **Workflow Type** of Managed or Unmanaged.</span></span> <span data-ttu-id="40489-138">下表介绍了托管响应组和非托管响应组。</span><span class="sxs-lookup"><span data-stu-id="40489-138">The following table describes Managed and Unmanaged response groups.</span></span>
  
<span data-ttu-id="40489-139">**托管响应组和非托管响应组**</span><span class="sxs-lookup"><span data-stu-id="40489-139">**Managed and Unmanaged Response Groups**</span></span>

|<span data-ttu-id="40489-140">**响应组类型**</span><span class="sxs-lookup"><span data-stu-id="40489-140">**Response group type**</span></span>|<span data-ttu-id="40489-141">**说明**</span><span class="sxs-lookup"><span data-stu-id="40489-141">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="40489-142">非托管</span><span class="sxs-lookup"><span data-stu-id="40489-142">Unmanaged</span></span>  <br/> | <span data-ttu-id="40489-143">非托管响应组未分配有 Manager。</span><span class="sxs-lookup"><span data-stu-id="40489-143">Unmanaged response groups have no assigned Managers.</span></span> <span data-ttu-id="40489-144">只有响应组管理员可以配置这类响应组。</span><span class="sxs-lookup"><span data-stu-id="40489-144">Only the Response Group Administrator can configure these response groups.</span></span> <br/>  <span data-ttu-id="40489-145">多个非托管响应组可共享一个队列或代理组。</span><span class="sxs-lookup"><span data-stu-id="40489-145">Multiple unmanaged response groups can share a queue or agent group.</span></span> <br/>  <span data-ttu-id="40489-146">迁移响应组从早期版本到时 Skype 业务服务器，类型设置为非托管。</span><span class="sxs-lookup"><span data-stu-id="40489-146">When you migrate response groups from a prior version to Skype for Business Server, the type is set to Unmanaged.</span></span> <br/> |
|<span data-ttu-id="40489-147">托管</span><span class="sxs-lookup"><span data-stu-id="40489-147">Managed</span></span>  <br/> | <span data-ttu-id="40489-148">响应组管理员可以配置托管的响应任何的组方面。</span><span class="sxs-lookup"><span data-stu-id="40489-148">Response Group Administrators can configure any aspect of managed response groups.</span></span> <br/>  <span data-ttu-id="40489-149">响应组管理员无法查看或修改未显式分配给它们的响应组。</span><span class="sxs-lookup"><span data-stu-id="40489-149">Response Group Managers cannot view or modify response groups that are not explicitly assigned to them.</span></span> <br/>  <span data-ttu-id="40489-150">响应组管理员可以配置仅一些显式分配给它们的响应组设置。</span><span class="sxs-lookup"><span data-stu-id="40489-150">Response Group Managers can configure only some settings for the response groups that are explicitly assigned to them.</span></span> <br/>  <span data-ttu-id="40489-151">托管响应组无法与任何其他响应组（托管或非托管）共享任何队列或代理组。</span><span class="sxs-lookup"><span data-stu-id="40489-151">Managed response groups can't share any queues or agent groups with any other response group, managed or unmanaged.</span></span> <br/> |
   
<span data-ttu-id="40489-152">下表介绍了响应组管理员可以和无法分配给它们的响应组执行的操作。</span><span class="sxs-lookup"><span data-stu-id="40489-152">The following table describes the actions that Response Group Managers can and cannot perform for the response groups assigned to them.</span></span>
  
<span data-ttu-id="40489-153">**响应组 Manager 功能**</span><span class="sxs-lookup"><span data-stu-id="40489-153">**Response Group Manager Capabilities**</span></span>

|<span data-ttu-id="40489-154">**可以配置：**</span><span class="sxs-lookup"><span data-stu-id="40489-154">**Can configure:**</span></span>|<span data-ttu-id="40489-155">**可以创建、删除或配置：**</span><span class="sxs-lookup"><span data-stu-id="40489-155">**Can create, delete, or configure:**</span></span>|<span data-ttu-id="40489-156">**无法：**</span><span class="sxs-lookup"><span data-stu-id="40489-156">**Cannot:**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="40489-157">代理</span><span class="sxs-lookup"><span data-stu-id="40489-157">Agents</span></span> <br/>  <span data-ttu-id="40489-158">欢迎消息</span><span class="sxs-lookup"><span data-stu-id="40489-158">Welcome message</span></span> <br/>  <span data-ttu-id="40489-159">响应组名称</span><span class="sxs-lookup"><span data-stu-id="40489-159">Response Group name</span></span> <br/>  <span data-ttu-id="40489-160">说明</span><span class="sxs-lookup"><span data-stu-id="40489-160">Description</span></span> <br/>  <span data-ttu-id="40489-161">显示号码</span><span class="sxs-lookup"><span data-stu-id="40489-161">Display number</span></span> <br/>  <span data-ttu-id="40489-162">工作时间</span><span class="sxs-lookup"><span data-stu-id="40489-162">Business hours</span></span> <br/>  <span data-ttu-id="40489-163">保持音乐</span><span class="sxs-lookup"><span data-stu-id="40489-163">Music on hold</span></span> <br/>  <span data-ttu-id="40489-164">状态（活动/非活动）</span><span class="sxs-lookup"><span data-stu-id="40489-164">Status (active/inactive)</span></span> <br/>  <span data-ttu-id="40489-165">智能寻线工作流和互动语音响应 (IVR) 工作流</span><span class="sxs-lookup"><span data-stu-id="40489-165">Hunt group workflows or Interactive voice response (IVR) workflows</span></span> <br/> | <span data-ttu-id="40489-166">代理组</span><span class="sxs-lookup"><span data-stu-id="40489-166">Agent Groups</span></span> <br/>  <span data-ttu-id="40489-167">队列</span><span class="sxs-lookup"><span data-stu-id="40489-167">Queues</span></span> <br/>  <span data-ttu-id="40489-168">假日集</span><span class="sxs-lookup"><span data-stu-id="40489-168">Holiday sets</span></span> <br/> | <span data-ttu-id="40489-169">创建或删除任意类型的工作流</span><span class="sxs-lookup"><span data-stu-id="40489-169">Create or delete any type of workflow</span></span> <br/>  <span data-ttu-id="40489-170">修改核心响应组设置，如：“**SIP URI**”、“**电话号码**”或“**工作流类型**”。</span><span class="sxs-lookup"><span data-stu-id="40489-170">Modify core response group settings, such as: **SIP URI**, **Telephone Number**, or **Workflow Type**.</span></span>  <br/> |
   
<span data-ttu-id="40489-171">响应组管理员可以使用以下工具来管理其指定的响应组。</span><span class="sxs-lookup"><span data-stu-id="40489-171">Response Group Managers can use the following tools to manage their designated response groups.</span></span> 
  
- <span data-ttu-id="40489-172">Skype for Business Server 控制面板</span><span class="sxs-lookup"><span data-stu-id="40489-172">Skype for Business Server Control Panel</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="40489-173">响应组管理员只能管理响应组设置，使用此工具。</span><span class="sxs-lookup"><span data-stu-id="40489-173">Response Group Managers can only manage Response Group settings with this tool.</span></span> <span data-ttu-id="40489-174">业务服务器设置其他 Skype 不可用到经理。</span><span class="sxs-lookup"><span data-stu-id="40489-174">Other Skype for Business Server settings are not available to Managers.</span></span> 
  
- <span data-ttu-id="40489-175">响应组配置工具</span><span class="sxs-lookup"><span data-stu-id="40489-175">Response Group Configuration Tool</span></span>
    
- <span data-ttu-id="40489-176">Skype for Business Server 管理程序</span><span class="sxs-lookup"><span data-stu-id="40489-176">Skype for Business Server Management Shell</span></span>
    
<span data-ttu-id="40489-177">响应组扩展也到部门或工作组环境 （有关详细信息，请参阅[容量规划响应组](http://technet.microsoft.com/library/a2459a69-1f45-4f2f-bca5-d4f442708e44.aspx)），并且可以部署在全新的电话安装中。</span><span class="sxs-lookup"><span data-stu-id="40489-177">Response Group scales well to departmental or workgroup environments (for details, see [Capacity Planning for Response Group](http://technet.microsoft.com/library/a2459a69-1f45-4f2f-bca5-d4f442708e44.aspx)) and can be deployed in entirely new telephony installations.</span></span> <span data-ttu-id="40489-178">它支持从企业语音部署和当地运营商网络的传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="40489-178">It supports incoming calls from the Enterprise Voice deployment and from the local carrier network.</span></span> <span data-ttu-id="40489-179">代理可以使用适用于商务、 Lync 2013，Lync 2010，Lync 2010 Attendant 或 Lync Phone Edition 的 Skype 才能向其路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="40489-179">Agents can use Skype for Business, Lync 2013, Lync 2010, Lync 2010 Attendant, or Lync Phone Edition to take the calls routed to them.</span></span>
  
## <a name="deployment-and-requirements"></a><span data-ttu-id="40489-180">部署和要求</span><span class="sxs-lookup"><span data-stu-id="40489-180">Deployment and requirements</span></span>

<span data-ttu-id="40489-181">部署企业语音时，将自动启用响应组应用程序。</span><span class="sxs-lookup"><span data-stu-id="40489-181">The Response Group application is automatically enabled when you deploy Enterprise Voice.</span></span>
  
### <a name="hardware-and-software-requirements"></a><span data-ttu-id="40489-182">硬件和软件要求</span><span class="sxs-lookup"><span data-stu-id="40489-182">Hardware and software requirements</span></span>

<span data-ttu-id="40489-183">响应组应用程序与前端服务器具有相同的硬件要求、 操作系统要求和必备软件。</span><span class="sxs-lookup"><span data-stu-id="40489-183">The Response Group application has the same hardware requirements, operating system requirements and software prerequisites as Front End Servers.</span></span> 
  
<span data-ttu-id="40489-184">如果您使用的响应组音乐和公告的 Windows Media 音频 (.wma) 文件，运行响应组应用程序的所有前端服务器或 Standard 版本服务器必须运行 Windows 的服务器上安装 Windows Media Format RuntimeServer 2008 R2 或 Microsoft 媒体基础运行 Windows Server 2012 或 Windows Server 2012 R2 的服务器。</span><span class="sxs-lookup"><span data-stu-id="40489-184">If you use Windows Media Audio (.wma) files for Response Group music and announcements, all Front End Servers or Standard Editions servers that run the Response Group application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="40489-185">对于 Windows Server 2008 R2，作为 Windows 桌面体验的一部分安装 Windows Media Format Runtime。</span><span class="sxs-lookup"><span data-stu-id="40489-185">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span>
  
<span data-ttu-id="40489-186">响应组使用**的语言包**支持文本到语音转换和语音识别。</span><span class="sxs-lookup"><span data-stu-id="40489-186">Response Group uses **Language packs** to support text-to-speech and speech recognition.</span></span> <span data-ttu-id="40489-187">配置消息（例如欢迎消息以及其他提示、互动语音响应 (IVR) 问题和答案）时，会使用这些语音技术。</span><span class="sxs-lookup"><span data-stu-id="40489-187">These speech technologies are used when you configure messages, such as the welcome message and other prompts, and interactive voice response (IVR) questions and answers.</span></span> <span data-ttu-id="40489-188">默认情况下 26 支持 Skype 部署的 Business Server 时即会安装包的语言。</span><span class="sxs-lookup"><span data-stu-id="40489-188">By default, the 26 supported language packs are installed when you deploy Skype for Business Server.</span></span>
  
### <a name="port-requirements"></a><span data-ttu-id="40489-189">端口要求</span><span class="sxs-lookup"><span data-stu-id="40489-189">Port Requirements</span></span>

<span data-ttu-id="40489-190">响应组应用程序使用以下端口：</span><span class="sxs-lookup"><span data-stu-id="40489-190">The Response Group application uses the following ports:</span></span>
  
- <span data-ttu-id="40489-191">**端口 5071**用于 SIP 侦听请求</span><span class="sxs-lookup"><span data-stu-id="40489-191">**Port 5071**   for SIP listening requests</span></span>
    
- <span data-ttu-id="40489-192">**端口 8404**用于服务器间通信</span><span class="sxs-lookup"><span data-stu-id="40489-192">**Port 8404**   for interserver communications</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="40489-193">此端口用于 Match Making 服务，在具有多个前端服务器的池中部署响应组应用程序时需要。</span><span class="sxs-lookup"><span data-stu-id="40489-193">This port is used for the Match Making service and is required when the Response Group application is deployed in a pool that has more than one Front End Server.</span></span> 
  
   > [!NOTE]
   > <span data-ttu-id="40489-194">这些端口是您可以使用**集 CsApplicationServer** cmdlet 更改的默认设置。</span><span class="sxs-lookup"><span data-stu-id="40489-194">These ports are default settings that you can change by using the **Set-CsApplicationServer** cmdlet.</span></span> <span data-ttu-id="40489-195">有关此 cmdlet 的详细信息，请参阅 Business Server Management Shell 文档 Skype。</span><span class="sxs-lookup"><span data-stu-id="40489-195">For details about this cmdlet, see the Skype for Business Server Management Shell documentation.</span></span>
  
### <a name="audio-file-requirements"></a><span data-ttu-id="40489-196">音频文件要求</span><span class="sxs-lookup"><span data-stu-id="40489-196">Audio File Requirements</span></span>

<span data-ttu-id="40489-197">响应组应用程序支持 wave (.wav) 文件格式和 Windows Media 音频 (.wma) 文件格式的响应组消息、 保留音乐或互动语音响应 (IVR) 问题。</span><span class="sxs-lookup"><span data-stu-id="40489-197">The Response Group application supports wave (.wav) file format and Windows Media audio (.wma) file format for Response Group messages, on-hold music, or interactive voice response (IVR) questions.</span></span>
  
<span data-ttu-id="40489-198">Windows Media 音频文件格式要求前端服务器上运行 Windows Server 2008 R2 和 Windows Server 2008 安装 Windows Media Format Runtime。</span><span class="sxs-lookup"><span data-stu-id="40489-198">The Windows Media audio file format requires that the Windows Media Format Runtime is installed on Front End Servers running Windows Server 2008 R2 and Windows Server 2008.</span></span> <span data-ttu-id="40489-199">有关详细信息，请参阅上文中的“软件要求”。</span><span class="sxs-lookup"><span data-stu-id="40489-199">For more details, see "Software Requirements" earlier in this section.</span></span>
  
#### <a name="supported-wave-file-formats"></a><span data-ttu-id="40489-200">支持的 Wave 文件格式</span><span class="sxs-lookup"><span data-stu-id="40489-200">Supported Wave File Formats</span></span>

<span data-ttu-id="40489-201">所有 wave 文件必须符合以下要求：</span><span class="sxs-lookup"><span data-stu-id="40489-201">All wave files must meet the following requirements:</span></span>
  
- <span data-ttu-id="40489-202">8 位或 16 位文件</span><span class="sxs-lookup"><span data-stu-id="40489-202">8-bit or 16-bit file</span></span>
    
- <span data-ttu-id="40489-203">线性脉冲编码调制 (LPCM)，A-Law 或 mu-Law 格式</span><span class="sxs-lookup"><span data-stu-id="40489-203">Linear pulse code modulation (LPCM), A-Law, or mu-Law format</span></span>
    
- <span data-ttu-id="40489-204">单声道或立体声</span><span class="sxs-lookup"><span data-stu-id="40489-204">Mono or stereo</span></span>
    
- <span data-ttu-id="40489-205">4 MB 或更小</span><span class="sxs-lookup"><span data-stu-id="40489-205">4MB or less</span></span>
    
<span data-ttu-id="40489-206">为获得 wave 文件的最佳性能，建议使用 16 kHz、单声道、16 位的 wave 文件。</span><span class="sxs-lookup"><span data-stu-id="40489-206">For the best performance of wave files, a 16 kHz, mono, 16-bit Wave file is recommended.</span></span> 
  
#### <a name="supported-windows-media-audio-file-formats"></a><span data-ttu-id="40489-207">支持的 Windows Media 音频文件格式</span><span class="sxs-lookup"><span data-stu-id="40489-207">Supported Windows Media Audio File Formats</span></span>

<span data-ttu-id="40489-208">如果使用 Windows Media 音频文件，请考虑使用较低的比特率，并验证负载下的系统性能。</span><span class="sxs-lookup"><span data-stu-id="40489-208">If you use a Windows Media audio file, consider using low bit rates, and verify the performance of your system under load.</span></span>
  
<span data-ttu-id="40489-209">您可以使用 Microsoft Expression Encoder 4 将文件转换为 Windows Media 音频格式。</span><span class="sxs-lookup"><span data-stu-id="40489-209">You can use the Microsoft Expression Encoder 4 to convert a file to the Windows Media Audio format.</span></span> <span data-ttu-id="40489-210">若要下载表达式编码器 4，请参阅[https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkId=202843)。</span><span class="sxs-lookup"><span data-stu-id="40489-210">To download Expression Encoder 4, see [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkId=202843).</span></span>
  
### <a name="response-group-configuration-tool-requirements"></a><span data-ttu-id="40489-211">响应组配置工具要求</span><span class="sxs-lookup"><span data-stu-id="40489-211">Response Group Configuration Tool Requirements</span></span>

<span data-ttu-id="40489-212">响应组配置工具支持的操作系统和 web 浏览器下表中所述的组合。</span><span class="sxs-lookup"><span data-stu-id="40489-212">The Response Group Configuration Tool supports the combinations of operating systems and web browsers described in the following table.</span></span>
  
> [!NOTE]
> <span data-ttu-id="40489-p119">支持 32 位或 64 位版本的操作系统。仅支持 32 位版本的 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="40489-p119">32-bit or 64-bit versions of the operating systems are supported. Only 32-bit versions of Internet Explorer are supported.</span></span> 
  
<span data-ttu-id="40489-215">**支持的操作系统和 Web 浏览器**</span><span class="sxs-lookup"><span data-stu-id="40489-215">**Supported Operating Systems and Web Browsers**</span></span>

|<span data-ttu-id="40489-216">**操作系统**</span><span class="sxs-lookup"><span data-stu-id="40489-216">**Operating system**</span></span>|<span data-ttu-id="40489-217">**Web 浏览器**</span><span class="sxs-lookup"><span data-stu-id="40489-217">**Web browser**</span></span>|
|:-----|:-----|
|<span data-ttu-id="40489-218">Windows Vista Service Pack (SP) 2</span><span class="sxs-lookup"><span data-stu-id="40489-218">Windows Vista with Service Pack (SP) 2</span></span>  <br/> |<span data-ttu-id="40489-219">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="40489-219">Internet Explorer 7</span></span>  <br/> <span data-ttu-id="40489-220">Internet Explorer 8（本机模式）</span><span class="sxs-lookup"><span data-stu-id="40489-220">Internet Explorer 8 (native mode)</span></span>  <br/> <span data-ttu-id="40489-221">Internet Explorer 9（本机模式）</span><span class="sxs-lookup"><span data-stu-id="40489-221">Internet Explorer 9 (native mode)</span></span>  <br/> |
|<span data-ttu-id="40489-222">Windows 7</span><span class="sxs-lookup"><span data-stu-id="40489-222">Windows 7</span></span>  <br/> <span data-ttu-id="40489-223">Windows 7 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="40489-223">Windows 7 with Service Pack 1</span></span>  <br/> |<span data-ttu-id="40489-224">Internet Explorer 8（本机模式）</span><span class="sxs-lookup"><span data-stu-id="40489-224">Internet Explorer 8 (native mode)</span></span>  <br/> <span data-ttu-id="40489-225">Internet Explorer 9（本机模式）</span><span class="sxs-lookup"><span data-stu-id="40489-225">Internet Explorer 9 (native mode)</span></span>  <br/> |
|<span data-ttu-id="40489-226">Windows Server 2008 Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="40489-226">Windows Server 2008 with Service Pack 2</span></span>  <br/> |<span data-ttu-id="40489-227">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="40489-227">Internet Explorer 7</span></span>  <br/> <span data-ttu-id="40489-228">Internet Explorer 8（本机模式）</span><span class="sxs-lookup"><span data-stu-id="40489-228">Internet Explorer 8 (native mode)</span></span>  <br/> <span data-ttu-id="40489-229">Internet Explorer 9（本机模式）</span><span class="sxs-lookup"><span data-stu-id="40489-229">Internet Explorer 9 (native mode)</span></span>  <br/> |
|<span data-ttu-id="40489-230">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="40489-230">Windows Server 2008 R2</span></span>  <br/> <span data-ttu-id="40489-231">Windows Server 2008 R2 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="40489-231">Windows Server 2008 R2 with Service Pack 1</span></span>  <br/> |<span data-ttu-id="40489-232">Internet Explorer 8（本机模式）</span><span class="sxs-lookup"><span data-stu-id="40489-232">Internet Explorer 8 (native mode)</span></span>  <br/> <span data-ttu-id="40489-233">Internet Explorer 9（本机模式）</span><span class="sxs-lookup"><span data-stu-id="40489-233">Internet Explorer 9 (native mode)</span></span>  <br/> |
|<span data-ttu-id="40489-234">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="40489-234">Windows Server 2012</span></span>  <br/> ||
|<span data-ttu-id="40489-235">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="40489-235">Windows Server 2012 R2</span></span>  <br/> ||
   
### <a name="response-group-agent-console"></a><span data-ttu-id="40489-236">响应组代理控制台</span><span class="sxs-lookup"><span data-stu-id="40489-236">Response Group Agent Console</span></span>

<span data-ttu-id="40489-237">此代理控制台支持下表所述的操作系统和 Web 浏览器的组合。</span><span class="sxs-lookup"><span data-stu-id="40489-237">The agent console supports the combinations of operating systems and web browsers described in the following table.</span></span>
  
> [!NOTE]
> <span data-ttu-id="40489-p120">支持 32 位或 64 位版本的操作系统。仅支持 32 位版本的 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="40489-p120">32-bit or 64-bit versions of the operating systems are supported. Only 32-bit versions of Internet Explorer are supported.</span></span> 
  
<span data-ttu-id="40489-240">**支持的操作系统和 Web 浏览器**</span><span class="sxs-lookup"><span data-stu-id="40489-240">**Supported Operating Systems and Web Browsers**</span></span>

|<span data-ttu-id="40489-241">**操作系统**</span><span class="sxs-lookup"><span data-stu-id="40489-241">**Operating system**</span></span>|<span data-ttu-id="40489-242">**Web 浏览器**</span><span class="sxs-lookup"><span data-stu-id="40489-242">**Web browser**</span></span>|
|:-----|:-----|
|<span data-ttu-id="40489-243">Windows Vista Service Pack (SP) 2</span><span class="sxs-lookup"><span data-stu-id="40489-243">Windows Vista with Service Pack (SP) 2</span></span>  <br/> |<span data-ttu-id="40489-244">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="40489-244">Internet Explorer 7</span></span>  <br/> <span data-ttu-id="40489-245">Internet Explorer 8（本机模式）</span><span class="sxs-lookup"><span data-stu-id="40489-245">Internet Explorer 8 (native mode)</span></span>  <br/> <span data-ttu-id="40489-246">Internet Explorer 9（本机模式）</span><span class="sxs-lookup"><span data-stu-id="40489-246">Internet Explorer 9 (native mode)</span></span>  <br/> |
|<span data-ttu-id="40489-247">Windows 7</span><span class="sxs-lookup"><span data-stu-id="40489-247">Windows 7</span></span>  <br/> <span data-ttu-id="40489-248">Windows 7 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="40489-248">Windows 7 with Service Pack 1</span></span>  <br/> |<span data-ttu-id="40489-249">Internet Explorer 8（本机模式）</span><span class="sxs-lookup"><span data-stu-id="40489-249">Internet Explorer 8 (native mode)</span></span>  <br/> <span data-ttu-id="40489-250">Internet Explorer 9（本机模式）</span><span class="sxs-lookup"><span data-stu-id="40489-250">Internet Explorer 9 (native mode)</span></span>  <br/> <span data-ttu-id="40489-251">Firefox 10.0</span><span class="sxs-lookup"><span data-stu-id="40489-251">Firefox 10.0</span></span>  <br/> <span data-ttu-id="40489-252">Chrome 18.0</span><span class="sxs-lookup"><span data-stu-id="40489-252">Chrome 18.0</span></span>  <br/> |
|<span data-ttu-id="40489-253">Windows Server 2008 Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="40489-253">Windows Server 2008 with Service Pack 2</span></span>  <br/> |<span data-ttu-id="40489-254">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="40489-254">Internet Explorer 7</span></span>  <br/> <span data-ttu-id="40489-255">Internet Explorer 8（本机模式）</span><span class="sxs-lookup"><span data-stu-id="40489-255">Internet Explorer 8 (native mode)</span></span>  <br/> <span data-ttu-id="40489-256">Internet Explorer 9（本机模式）</span><span class="sxs-lookup"><span data-stu-id="40489-256">Internet Explorer 9 (native mode)</span></span>  <br/> |
|<span data-ttu-id="40489-257">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="40489-257">Windows Server 2008 R2</span></span>  <br/> <span data-ttu-id="40489-258">Windows Server 2008 R2 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="40489-258">Windows Server 2008 R2 with Service Pack 1</span></span>  <br/> |<span data-ttu-id="40489-259">Internet Explorer 8（本机模式）</span><span class="sxs-lookup"><span data-stu-id="40489-259">Internet Explorer 8 (native mode)</span></span>  <br/> <span data-ttu-id="40489-260">Internet Explorer 9（本机模式）</span><span class="sxs-lookup"><span data-stu-id="40489-260">Internet Explorer 9 (native mode)</span></span>  <br/> <span data-ttu-id="40489-261">Firefox 10.0</span><span class="sxs-lookup"><span data-stu-id="40489-261">Firefox 10.0</span></span>  <br/> <span data-ttu-id="40489-262">Chrome 18.0</span><span class="sxs-lookup"><span data-stu-id="40489-262">Chrome 18.0</span></span>  <br/> |
|<span data-ttu-id="40489-263">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="40489-263">Windows Server 2012</span></span>  <br/> |
|<span data-ttu-id="40489-264">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="40489-264">Windows Server 2012 R2</span></span>  <br/> |
   
## <a name="client-support"></a><span data-ttu-id="40489-265">客户端支持</span><span class="sxs-lookup"><span data-stu-id="40489-265">Client support</span></span>

<span data-ttu-id="40489-266">响应组应用程序支持以下客户端：</span><span class="sxs-lookup"><span data-stu-id="40489-266">The Response Group application supports the following clients:</span></span>
  
- <span data-ttu-id="40489-267">Skype 业务桌面客户端</span><span class="sxs-lookup"><span data-stu-id="40489-267">Skype for Business desktop client</span></span>
    
- <span data-ttu-id="40489-268">Lync 2013 桌面客户端</span><span class="sxs-lookup"><span data-stu-id="40489-268">Lync 2013 desktop client</span></span>
    
- <span data-ttu-id="40489-269">Lync 2010 桌面客户端</span><span class="sxs-lookup"><span data-stu-id="40489-269">Lync 2010 desktop client</span></span>
    
- <span data-ttu-id="40489-270">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="40489-270">Lync 2010 Attendant</span></span>
    
- <span data-ttu-id="40489-271">Office Communications Server 2007 R2 Attendant</span><span class="sxs-lookup"><span data-stu-id="40489-271">Office Communications Server 2007 R2 Attendant</span></span>
    
- <span data-ttu-id="40489-272">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="40489-272">Lync Phone Edition</span></span>
    
> [!NOTE]
> <span data-ttu-id="40489-273">Lync 移动客户端不支持响应组应用程序。</span><span class="sxs-lookup"><span data-stu-id="40489-273">The Response Group application is not supported on Lync mobile clients.</span></span> 
  
<span data-ttu-id="40489-274">您可以使用的特定客户端取决于您的响应组用户的类型：</span><span class="sxs-lookup"><span data-stu-id="40489-274">The specific client that you can use depends on the type of Response Group user that you are:</span></span> 
  
- <span data-ttu-id="40489-275">**呼叫者**可使用前面列出的任何客户端和公用电话交换网 (PSTN) 上的标准电话来呼叫响应组。</span><span class="sxs-lookup"><span data-stu-id="40489-275">**Callers** can call a response group by using any of the clients listed previously, and by using a standard telephone over the public switched telephone network (PSTN).</span></span>
    
- <span data-ttu-id="40489-276">**非正式代理**（不需要登录和注销其组以接受呼叫代理） 可以使用助理、 Lync 或 Lync Phone Edition 接受呼叫。</span><span class="sxs-lookup"><span data-stu-id="40489-276">**Informal agents** (agents who do not sign into and out of their groups to accept calls) can accept calls by using Attendant, Lync, or Lync Phone Edition.</span></span> <span data-ttu-id="40489-277">非正式代理自动登录到其组中，当用户登录到 Skype 业务服务器使用这些客户端之一。</span><span class="sxs-lookup"><span data-stu-id="40489-277">Informal agents are automatically signed into their groups when they sign in to Skype for Business Server by using one of these clients.</span></span>
    
- <span data-ttu-id="40489-278">**正式代理**（必须登录和注销其组以接受呼叫代理） 可以接受呼叫，通过使用 for Business 的 Skype 并从该菜单项，访问代理控制台或通过使用 Attendant 并直接从 Internet Explorer 访问此代理控制台。</span><span class="sxs-lookup"><span data-stu-id="40489-278">**Formal agents** (agents who must sign into and out of their groups to accept calls) can accept calls by using Skype for Business and accessing the agent console from the menu item, or by using Attendant and accessing the agent console directly from Internet Explorer.</span></span>
    
## <a name="capacity-planning"></a><span data-ttu-id="40489-279">容量规划</span><span class="sxs-lookup"><span data-stu-id="40489-279">Capacity planning</span></span>

<span data-ttu-id="40489-280">下表介绍可用作容量规划要求基础的响应组用户模型。</span><span class="sxs-lookup"><span data-stu-id="40489-280">The following table describes the Response Group user model that you can use as the basis for capacity planning requirements.</span></span>
  
> [!NOTE]
> <span data-ttu-id="40489-p122">下表中的数值假定所有响应组音频文件使用的是 16 kHz、单声道、16 位的 Wave (.wav) 文件。如果使用其他文件格式（如 Windows Media 音频 (.wma)），则数值可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="40489-p122">The numbers in the following table assume that you use 16 kHz, mono, 16-bit Wave (.wav) files for all response group audio files. If you use other file formats, such as Windows Media Audio (.wma), the numbers may vary.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="40489-283">请记住，对于灾难恢复容量规划，一对池中的每一个池都应能处理这两个池中的所有响应组的工作负荷。</span><span class="sxs-lookup"><span data-stu-id="40489-283">Keep in mind that for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for all the response groups in both pools.</span></span> 
  
<span data-ttu-id="40489-284">**响应组用户模型**</span><span class="sxs-lookup"><span data-stu-id="40489-284">**Response Group User Model**</span></span>

|<span data-ttu-id="40489-285">**指标**</span><span class="sxs-lookup"><span data-stu-id="40489-285">**Metric**</span></span>|<span data-ttu-id="40489-286">**每个企业版池<br/>（具有 8 前端服务器）**</span><span class="sxs-lookup"><span data-stu-id="40489-286">**Per Enterprise Edition pool  <br/> (With 8 Front End Servers)**</span></span>|<span data-ttu-id="40489-287">**每台 Standard Edition Server**</span><span class="sxs-lookup"><span data-stu-id="40489-287">**Per Standard Edition server**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="40489-288">每秒传入的呼叫数</span><span class="sxs-lookup"><span data-stu-id="40489-288">Incoming calls per second</span></span>  <br/> |<span data-ttu-id="40489-289">16</span><span class="sxs-lookup"><span data-stu-id="40489-289">16</span></span>  <br/> |<span data-ttu-id="40489-290">2</span><span class="sxs-lookup"><span data-stu-id="40489-290">2</span></span>  <br/> |
|<span data-ttu-id="40489-291">连接到 IVR 或 MoH 的并发呼叫数</span><span class="sxs-lookup"><span data-stu-id="40489-291">Concurrent calls connected to IVR or MoH</span></span>  <br/> |<span data-ttu-id="40489-292">480</span><span class="sxs-lookup"><span data-stu-id="40489-292">480</span></span>  <br/> |<span data-ttu-id="40489-293">60</span><span class="sxs-lookup"><span data-stu-id="40489-293">60</span></span>  <br/> |
|<span data-ttu-id="40489-294">并发的匿名会话数（无 IM）</span><span class="sxs-lookup"><span data-stu-id="40489-294">Concurrent anonymous sessions (without IM)</span></span>  <br/> |<span data-ttu-id="40489-295">224</span><span class="sxs-lookup"><span data-stu-id="40489-295">224</span></span>  <br/> |<span data-ttu-id="40489-296">28</span><span class="sxs-lookup"><span data-stu-id="40489-296">28</span></span>  <br/> |
|<span data-ttu-id="40489-297">并发的匿名会话数（具有 IM）</span><span class="sxs-lookup"><span data-stu-id="40489-297">Concurrent anonymous sessions (with IM)</span></span>  <br/> |<span data-ttu-id="40489-298">64</span><span class="sxs-lookup"><span data-stu-id="40489-298">64</span></span>  <br/> |<span data-ttu-id="40489-299">8</span><span class="sxs-lookup"><span data-stu-id="40489-299">8</span></span>  <br/> |
|<span data-ttu-id="40489-300">活动代理数（正式和非正式）</span><span class="sxs-lookup"><span data-stu-id="40489-300">Active agents (formal and informal)</span></span>  <br/> |<span data-ttu-id="40489-301">2400</span><span class="sxs-lookup"><span data-stu-id="40489-301">2400</span></span>  <br/> |<span data-ttu-id="40489-302">2400</span><span class="sxs-lookup"><span data-stu-id="40489-302">2400</span></span>  <br/> |
|<span data-ttu-id="40489-303">智能寻线数</span><span class="sxs-lookup"><span data-stu-id="40489-303">Number of hunt groups</span></span>  <br/> |<span data-ttu-id="40489-304">800</span><span class="sxs-lookup"><span data-stu-id="40489-304">800</span></span>  <br/> |<span data-ttu-id="40489-305">800</span><span class="sxs-lookup"><span data-stu-id="40489-305">800</span></span>  <br/> |
|<span data-ttu-id="40489-306">IVR 组数（使用语音识别）</span><span class="sxs-lookup"><span data-stu-id="40489-306">Number of IVR groups (use speech recognition)</span></span>  <br/> |<span data-ttu-id="40489-307">400</span><span class="sxs-lookup"><span data-stu-id="40489-307">400</span></span>  <br/> |<span data-ttu-id="40489-308">400</span><span class="sxs-lookup"><span data-stu-id="40489-308">400</span></span>  <br/> |
   

