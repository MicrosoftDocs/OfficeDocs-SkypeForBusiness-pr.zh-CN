---
title: Lync Server 2013：所需任务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: As-needed tasks
ms:assetid: b66bc6fe-f138-4cf4-ba7f-aee9a3e0497e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722431(v=OCS.15)
ms:contentKeyID: 63969643
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 344512a1dd4db44b8290efdcc726275b4a6898de
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738402"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="as-needed-tasks-in-lync-server-2013"></a><span data-ttu-id="86035-102">Lync Server 2013 中的 "需要" 任务</span><span class="sxs-lookup"><span data-stu-id="86035-102">As-needed tasks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86035-103">_**主题上次修改时间：** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="86035-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="86035-104">根据需要执行以下任务。</span><span class="sxs-lookup"><span data-stu-id="86035-104">Perform the following tasks as necessary.</span></span> <span data-ttu-id="86035-105">标准过程中也经常包含它们：</span><span class="sxs-lookup"><span data-stu-id="86035-105">They are frequently also covered by standard procedures:</span></span>

  - <span data-ttu-id="86035-106">**完整的安全审核   **你可以定期执行此审核，以响应邮件系统的升级或重新设计，或者响应已尝试（或成功）的安全漏洞。</span><span class="sxs-lookup"><span data-stu-id="86035-106">**Full Security Auditing   **You can perform this audit regularly, in response to an upgrade or redesign of the messaging system, or in response to an attempted (or successful) security breach.</span></span> <span data-ttu-id="86035-107">该过程可能涉及服务器和防火墙上的端口扫描、安全修补程序审核以及第三方渗透测试。</span><span class="sxs-lookup"><span data-stu-id="86035-107">The procedure may involve port scans on servers and firewalls, audits of security fixes, and third-party penetration tests.</span></span>

  - <span data-ttu-id="86035-108">**将证书替换为过期**   检查 Lync Server 证书是一种常规的周任务，并且作为管理员应记录所有证书到期日期的过程的一部分。</span><span class="sxs-lookup"><span data-stu-id="86035-108">**Replace Certificates about to Expire**   Checking Lync Server Certificates is one of regular weekly tasks, and as part of the procedure an administrator should have a record of all certificates’ expiry dates.</span></span> <span data-ttu-id="86035-109">此记录使管理员能够在特定证书即将到期并根据需要替换时创建通知。</span><span class="sxs-lookup"><span data-stu-id="86035-109">This record enables an administrator to create a notification when a particular certificate is about to be expired and replaced as needed.</span></span>

  - <span data-ttu-id="86035-110">**更新性能基线**   会在升级或配置更改后更新性能基线。</span><span class="sxs-lookup"><span data-stu-id="86035-110">**Updating Performance Baselines**   Update performance baselines after an upgrade or configuration change.</span></span> <span data-ttu-id="86035-111">你的组织可以使用比较基准衡量性能更改并检测影响系统性能的问题。</span><span class="sxs-lookup"><span data-stu-id="86035-111">Your organization can use baselines to measure performance changes and to detect issues that affect system performance.</span></span>

  - <span data-ttu-id="86035-112">**管理**   企业版池初始配置企业版池、标准版服务器以及组织环境中的任何其他服务器在部署各个服务器的过程中完成。</span><span class="sxs-lookup"><span data-stu-id="86035-112">**Managing Enterprise Pool**   Initial configuration of Enterprise pools, Standard Edition servers, and any other servers in your organization's environment were done during deployment of the individual servers.</span></span> <span data-ttu-id="86035-113">适用于标准版服务器和企业版池的服务器和池的部署后管理包括以下任务：</span><span class="sxs-lookup"><span data-stu-id="86035-113">Post-deployment management of servers and pools for Standard Edition servers and Enterprise pools includes the following tasks:</span></span>
    
      - <span data-ttu-id="86035-114">管理前端服务器</span><span class="sxs-lookup"><span data-stu-id="86035-114">Managing Front End Servers</span></span>
    
      - <span data-ttu-id="86035-115">管理 Web 会议</span><span class="sxs-lookup"><span data-stu-id="86035-115">Managing Web Conferencing</span></span>
    
      - <span data-ttu-id="86035-116">管理会议</span><span class="sxs-lookup"><span data-stu-id="86035-116">Managing Conferencing</span></span>
    
      - <span data-ttu-id="86035-117">更改服务帐户凭据</span><span class="sxs-lookup"><span data-stu-id="86035-117">Changing Service Account Credentials</span></span>
    
      - <span data-ttu-id="86035-118">管理数据库</span><span class="sxs-lookup"><span data-stu-id="86035-118">Managing Databases</span></span>
    
      - <span data-ttu-id="86035-119">启动和停止服务并停用服务器角色</span><span class="sxs-lookup"><span data-stu-id="86035-119">Starting and Stopping Services and Deactivating Server Roles</span></span>
    
      - <span data-ttu-id="86035-120">删除服务器和服务器角色、删除池以及解除服务器和池的授权</span><span class="sxs-lookup"><span data-stu-id="86035-120">Removing Servers and Server Roles, Removing Pools, and Decommissioning Servers and Pools</span></span>

  - <span data-ttu-id="86035-121">**管理使用情况**   你可以配置 Lync Server 2013 以提供最适合你的组织的功能和功能。</span><span class="sxs-lookup"><span data-stu-id="86035-121">**Managing Usage**   You can configure Lync Server 2013 to provide the features and functionality that are most appropriate for your organization.</span></span> <span data-ttu-id="86035-122">这包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="86035-122">This includes the following:</span></span>
    
      - <span data-ttu-id="86035-123">管理对本地 Web 会议会议的支持</span><span class="sxs-lookup"><span data-stu-id="86035-123">Managing Support for On-Premise Web Conferencing Meetings</span></span>
    
      - <span data-ttu-id="86035-124">管理通讯组的使用以发送即时消息</span><span class="sxs-lookup"><span data-stu-id="86035-124">Managing the Use of Distribution Groups to Send Instant Messages</span></span>
    
      - <span data-ttu-id="86035-125">管理联系人、状态和查询</span><span class="sxs-lookup"><span data-stu-id="86035-125">Managing Contacts, Presence, and Queries</span></span>
    
      - <span data-ttu-id="86035-126">配置客户端版本筛选</span><span class="sxs-lookup"><span data-stu-id="86035-126">Configuring Client Version Filtering</span></span>
    
      - <span data-ttu-id="86035-127">配置智能 IM 筛选</span><span class="sxs-lookup"><span data-stu-id="86035-127">Configuring Intelligent IM Filtering</span></span>
    
      - <span data-ttu-id="86035-128">配置存档、呼叫详细记录和满足合规性</span><span class="sxs-lookup"><span data-stu-id="86035-128">Configuring Archiving, Call Detail Recording, and Meeting Compliance</span></span>

  - <span data-ttu-id="86035-129">**管理边缘服务器连接**   对提供外部连接所需的服务器和设置的持续管理包括以下几项：</span><span class="sxs-lookup"><span data-stu-id="86035-129">**Managing Edge Server Connectivity**   Ongoing management of the servers and settings required to provide external connectivity includes the following:</span></span>
    
      - <span data-ttu-id="86035-130">管理内部服务器和边缘服务器之间的连接</span><span class="sxs-lookup"><span data-stu-id="86035-130">Managing Connectivity between Internal Servers and Edge Servers</span></span>
    
      - <span data-ttu-id="86035-131">为边缘服务器配置内部和外部接口和证书</span><span class="sxs-lookup"><span data-stu-id="86035-131">Configuring Internal and External Interfaces and Certificates for Edge Servers</span></span>
    
      - <span data-ttu-id="86035-132">管理联盟伙伴访问</span><span class="sxs-lookup"><span data-stu-id="86035-132">Managing Federated Partner Access</span></span>

  - <span data-ttu-id="86035-133">**管理通讯簿**   管理通讯簿服务器包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="86035-133">**Administering the Address Book**   Administering Address Book Servers includes the following:</span></span>
    
      - <span data-ttu-id="86035-134">配置通讯簿服务器电话规范化</span><span class="sxs-lookup"><span data-stu-id="86035-134">Configuring Address Book Server phone normalization</span></span>
    
      - <span data-ttu-id="86035-135">从命令行管理通讯簿服务器</span><span class="sxs-lookup"><span data-stu-id="86035-135">Managing the Address Book Server from the command line</span></span>

  - <span data-ttu-id="86035-136">**管理**   用户帐户的用户帐户管理包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="86035-136">**Managing User Accounts**   Management of user accounts includes the following:</span></span>
    
      - <span data-ttu-id="86035-137">为 Lync Server 启用用户帐户</span><span class="sxs-lookup"><span data-stu-id="86035-137">Enabling User Accounts for Lync Server</span></span>
    
      - <span data-ttu-id="86035-138">使用向导配置 Lync Server 用户</span><span class="sxs-lookup"><span data-stu-id="86035-138">Configuring Lync Server Users using the Wizard</span></span>
    
      - <span data-ttu-id="86035-139">配置单个 Lync Server 用户帐户属性</span><span class="sxs-lookup"><span data-stu-id="86035-139">Configuring Individual Lync Server User Account Properties</span></span>
    
      - <span data-ttu-id="86035-140">正在搜索 Lync Server 用户</span><span class="sxs-lookup"><span data-stu-id="86035-140">Searching for Lync Server Users</span></span>
    
      - <span data-ttu-id="86035-141">移动 Lync Server 用户</span><span class="sxs-lookup"><span data-stu-id="86035-141">Moving Lync Server Users</span></span>
    
      - <span data-ttu-id="86035-142">删除 Lync Server 用户</span><span class="sxs-lookup"><span data-stu-id="86035-142">Deleting Lync Server Users</span></span>

  - <span data-ttu-id="86035-143">**分析 Lync server 2013 日志文件**   一种非常有用的工具，通常用于疑难解答，是在[使用 lync server 2013 日志记录工具](http://technet.microsoft.com/en-us/library/gg558599.aspx)时详细介绍的 Lync server 2013 日志记录工具。</span><span class="sxs-lookup"><span data-stu-id="86035-143">**Analyzing Lync Server 2013 Log Files**   One very helpful tool, generally used for troubleshooting, is the Lync Server 2013 Logging Tool described in detail in [Using Lync Server 2013 Logging Tool](http://technet.microsoft.com/en-us/library/gg558599.aspx).</span></span>

<span data-ttu-id="86035-144">由于日志记录工具生成日志文件（基于每台服务器），如果计算机上安装了 Microsoft Office Server 12 资源工具包工具，则可以使用 Snooper 工具查看和分析这些日志文件。</span><span class="sxs-lookup"><span data-stu-id="86035-144">Because the Logging Tool generates log files (on a per-server basis), these log files can be viewed and analyzed by using the Snooper tool, if the Microsoft Office Server 12 Resource Kit Tools are installed on the computer.</span></span> <span data-ttu-id="86035-145">否则，还可以通过使用文本编辑器来分析日志，该编辑器比使用 Snooper 实用工具更透明且更复杂。</span><span class="sxs-lookup"><span data-stu-id="86035-145">Otherwise, logs can also be analyzed by using a text editor, which is much less transparent and more complex than using the Snooper utility.</span></span>

<span data-ttu-id="86035-146">查看和分析协议消息</span><span class="sxs-lookup"><span data-stu-id="86035-146">To View and Analyze Protocol Messages</span></span>

<span data-ttu-id="86035-147">在日志记录工具中，当你结束调试会话时，单击 "分析日志文件" 以使用 Snooper 工具查看日志文件。</span><span class="sxs-lookup"><span data-stu-id="86035-147">In the Logging Tool, when you have ended the debug session, click Analyze Log Files to view the log files by using the Snooper tool.</span></span> <span data-ttu-id="86035-148">你可以分析以下组件的协议日志：</span><span class="sxs-lookup"><span data-stu-id="86035-148">You can analyze protocol logs for the following components:</span></span>

  - <span data-ttu-id="86035-149">Lync Server SipStack （SIP）</span><span class="sxs-lookup"><span data-stu-id="86035-149">Lync Server SipStack (SIP)</span></span>

  - <span data-ttu-id="86035-150">Lync Server S4 （SIP）</span><span class="sxs-lookup"><span data-stu-id="86035-150">Lync Server S4 (SIP)</span></span>

  - <span data-ttu-id="86035-151">Lync Server 会议信号流量（C3P），包括 MCU 基础 C3P 和重点 C3P</span><span class="sxs-lookup"><span data-stu-id="86035-151">Lync Server Conferencing signaling traffic (C3P), including MCU Infra C3P and Focus C3P</span></span>

  - <span data-ttu-id="86035-152">Lync Server Web 会议流量（PSOM）</span><span class="sxs-lookup"><span data-stu-id="86035-152">Lync Server Web conferencing traffic (PSOM)</span></span>

  - <span data-ttu-id="86035-153">Lync Server 统一通信客户端平台客户端（UCCP）</span><span class="sxs-lookup"><span data-stu-id="86035-153">Lync Server Unified Communications Client Platform client (UCCP)</span></span>

  - <span data-ttu-id="86035-154">存档数据库中的错误报告</span><span class="sxs-lookup"><span data-stu-id="86035-154">Error reports from the archiving database</span></span>

<span data-ttu-id="86035-155">若要帮助组织按需任务的性能，请参阅所需操作清单。</span><span class="sxs-lookup"><span data-stu-id="86035-155">To help organize the performance of as-needed tasks, see As-Needed Operations Checklist.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="86035-156">有关详细的管理和管理过程，请参阅 Microsoft Lync Server 2013 管理指南。</span><span class="sxs-lookup"><span data-stu-id="86035-156">For detailed administration and management procedures, see the Microsoft Lync Server 2013 Administration Guide.</span></span>



</div>

<div>

## <a name="backup-and-restore-policies-or-configuration-settings"></a><span data-ttu-id="86035-157">备份（和还原）策略或配置设置</span><span class="sxs-lookup"><span data-stu-id="86035-157">Backup (and restore) policies or configuration settings</span></span>

<span data-ttu-id="86035-158">Lync Server 2013 允许您备份和还原整个系统。</span><span class="sxs-lookup"><span data-stu-id="86035-158">Lync Server 2013 lets you back up and restore the whole system.</span></span> <span data-ttu-id="86035-159">要备份的 Iif （也可能是天还原）单个策略或单个配置设置集合，检索相应的策略，然后将该对象管道到 Clixml cmdlet，该 cmdlet 将策略信息另存为 XML 文件：</span><span class="sxs-lookup"><span data-stu-id="86035-159">Iif you want to back up (and then maybe someday restore) a single policy or a single collection of configuration settings, retrieve the appropriate policy, and then pipe that object to the Export-Clixml cmdlet, which saves the policy information as an XML file:</span></span>

`Get-CsClientPolicy -Identity "RedmondClientPolicy" | Export-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

<span data-ttu-id="86035-160">您现在可以试用 RedmondClientPolicy 并更改许多设置。</span><span class="sxs-lookup"><span data-stu-id="86035-160">You may now experiment with RedmondClientPolicy and change lots of the settings.</span></span> <span data-ttu-id="86035-161">如果您决定改为还原旧策略，请输入：</span><span class="sxs-lookup"><span data-stu-id="86035-161">If you decide instead to restore the old policy, enter:</span></span>

`$x = Import-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

`Set-CsClientPolicy -Instance $x`

<span data-ttu-id="86035-162">请注意，此方法适用于大多数策略和设置，但不能处理某些较复杂的项目：包含多个子对象的项目（如路由配置设置，其中包含许多单独的语音路由）。</span><span class="sxs-lookup"><span data-stu-id="86035-162">Note that this approach will work for most policies and settings but it won't work with some of the more complex items—items that contain multiple sub-objects (like routing configuration settings, which contain many separate voice routes).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

