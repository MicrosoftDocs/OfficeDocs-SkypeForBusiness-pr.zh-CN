---
title: 验证边缘部署中 Skype 业务服务器
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: 摘要： 了解如何验证边缘服务器或边缘服务器池的部署中 Skype 工作业务服务器。
ms.openlocfilehash: 63c4cb1af599da191d0e0f4b95cfdaa775a64ba4
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223787"
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a><span data-ttu-id="8ec41-103">验证边缘部署中 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="8ec41-103">Validate your Edge deployment in Skype for Business Server</span></span>
 
<span data-ttu-id="8ec41-104">**摘要：** 了解如何验证边缘服务器或边缘服务器池的部署中 Skype 工作业务服务器。</span><span class="sxs-lookup"><span data-stu-id="8ec41-104">**Summary:** Learn how to verify that your deployment of Edge Server or Edge Server pool is working in Skype for Business Server.</span></span>
  
<span data-ttu-id="8ec41-105">一旦您已经部署了边缘服务器或边缘服务器池，您需要知道正常运行。</span><span class="sxs-lookup"><span data-stu-id="8ec41-105">Once you've deployed your Edge Server or Edge Server pool, you need to know if it's working properly.</span></span> <span data-ttu-id="8ec41-106">下面是一些可帮助进行确认连接边缘环境的操作的内部服务器，而且还需要的外部用户可以连接到业务服务器环境您 Skype 通过您的边缘。</span><span class="sxs-lookup"><span data-stu-id="8ec41-106">Here are a couple of things that can help with confirming your Edge environment is connected to your internal servers, and also that your external users can connect to your Skype for Business Server environment through your Edge.</span></span>
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a><span data-ttu-id="8ec41-107">验证内部服务器与边缘服务器之间的连接</span><span class="sxs-lookup"><span data-stu-id="8ec41-107">Verify connectivity between your internal servers and your Edge servers</span></span>

<span data-ttu-id="8ec41-108">时的连接验证自动完成边缘服务器或边缘服务器池中安装边缘服务器时，您可以仍确认为自己使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="8ec41-108">While validation of connectivity is done automatically in Edge Server or Edge Server pool when the Edge Servers are installed, you can still confirm this for yourself with Windows PowerShell.</span></span> <span data-ttu-id="8ec41-109">安装任何域联接的计算机上的业务 Server 核心组件 (OcsCore.msi) 的 Skype 或包含中央管理存储、 的内部服务器上运行 Get-csmanagementstorereplicationstatus cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8ec41-109">Run the Get-CsManagementStoreReplicationStatus cmdlet on the internal server which has the Central Management store, or any domain joined computer on which Skype for Business Server Core Components (OcsCore.msi) are installed.</span></span>
  
<span data-ttu-id="8ec41-p103">初次运行此命令的结果可能给出复制状态为 False，而不是 True。如果发生这种情况，请运行 Invoke-CsManagementStoreReplication cmdlet。留些时间让其完成复制，然后再次运行 Get-CsManagementStoreReplicationStatus cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8ec41-p103">The initial result of running this command may give a False status, rather than True, for replication. If that happens run the Invoke-CsManagementStoreReplication cmdlet. Give it some time to complete the replication, and then run the Get-CsManagementStoreReplicationStatus cmdlet again.</span></span>
  
## <a name="verify-connectivity-for-your-external-users"></a><span data-ttu-id="8ec41-113">验证外部用户连接</span><span class="sxs-lookup"><span data-stu-id="8ec41-113">Verify connectivity for your external users</span></span>

<span data-ttu-id="8ec41-114">我们用于确认您的边缘服务器配置，并能够连接、 发送和接收的边缘服务器方案的正确消息的绝佳工具。</span><span class="sxs-lookup"><span data-stu-id="8ec41-114">We do have a great tool for confirming your Edge Server configuration, and the ability to connect, send and receive the correct messages for Edge Server scenarios.</span></span> <span data-ttu-id="8ec41-115">它是[远程连接 Anaylzer 网站](https://testconnectivity.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="8ec41-115">It's the [Remote Connectivity Anaylzer site](https://testconnectivity.microsoft.com/).</span></span> <span data-ttu-id="8ec41-116">这是由 Microsoft 管理和维护的站点。</span><span class="sxs-lookup"><span data-stu-id="8ec41-116">This is a site that's managed and maintained by Microsoft Support.</span></span> <span data-ttu-id="8ec41-117">若要使用此工具，请通过浏览找到该网站，然后按照指示选择适合你的正确方案。</span><span class="sxs-lookup"><span data-stu-id="8ec41-117">To use this tool, browse to the website and follow the instructions to choose the right scenario for you.</span></span>
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a><span data-ttu-id="8ec41-118">测试外部用户连接时应考虑的事项</span><span class="sxs-lookup"><span data-stu-id="8ec41-118">Things to consider when testing external user connectivity</span></span>

<span data-ttu-id="8ec41-119">任何外部用户访问测试应包括贵组织支持的每种类型的内部用户，这可能包括下列任意部分或全部用户：</span><span class="sxs-lookup"><span data-stu-id="8ec41-119">Any test for external user access needs to include each type of internal user your organization supports, which could include any or all of the following:</span></span>
  
- <span data-ttu-id="8ec41-120">来自至少一个联盟域的用户（尽管我们建议测试所有这些域）。</span><span class="sxs-lookup"><span data-stu-id="8ec41-120">Users from at least one federated domain (we do recommend testing them all though).</span></span>
    
- <span data-ttu-id="8ec41-121">匿名用户。</span><span class="sxs-lookup"><span data-stu-id="8ec41-121">Anonymous users.</span></span>
    
- <span data-ttu-id="8ec41-122">组织中的用户，在远程登录到 for Business 的 Skype 但不使用 VPN。</span><span class="sxs-lookup"><span data-stu-id="8ec41-122">Users in your organization who are logged into Skype for Business remotely, but aren't using VPN.</span></span>
    
<span data-ttu-id="8ec41-123">这些测试将确定是否边缘服务器：</span><span class="sxs-lookup"><span data-stu-id="8ec41-123">These tests will determine whether your Edge Server is:</span></span>
  
- <span data-ttu-id="8ec41-124">使用 Telnet 客户端从网络外侦听所需端口。</span><span class="sxs-lookup"><span data-stu-id="8ec41-124">Listening on the necessary ports by using a telnet client from outside your network.</span></span>
    
  - <span data-ttu-id="8ec41-125">例如：telnet sip.contoso.com 443</span><span class="sxs-lookup"><span data-stu-id="8ec41-125">For example: telnet sip.contoso.com 443</span></span>
    
  - <span data-ttu-id="8ec41-126">您应在您将在边缘服务器或边缘服务器池，具体取决于您的部署的端口执行上述测试。</span><span class="sxs-lookup"><span data-stu-id="8ec41-126">You should perform the preceding test on the ports you're using on your Edge Server or Edge Server pool, depending on your deployment.</span></span>
    
- <span data-ttu-id="8ec41-127">执行准确的外部 DNS 解析。</span><span class="sxs-lookup"><span data-stu-id="8ec41-127">Performing accurate external DNS resolution.</span></span>
    
  - <span data-ttu-id="8ec41-128">从在网络外部 ping 每个边缘服务器或边缘服务器池的外部 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="8ec41-128">From outside your network, ping each of the external FQDNs of your Edge Server or Edge Server pool.</span></span> <span data-ttu-id="8ec41-129">即使 ping 失败，您将看到的 IP 地址，它可以比较之前已分配的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="8ec41-129">Even if the ping fails, you'll see the IP addresses, which you can compare the IP addresses you've previously assigned.</span></span>
    

