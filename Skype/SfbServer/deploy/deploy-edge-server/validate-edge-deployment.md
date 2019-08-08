---
title: 在 Skype for Business 服务器中验证 Edge 部署
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
manager: serdars
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: '摘要: 了解如何验证 Edge 服务器或 Edge 服务器池的部署是否在 Skype for Business 服务器中工作。'
ms.openlocfilehash: 57994e4583a3424fc680c8dfb220aeb11668c6fc
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233872"
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a><span data-ttu-id="a563f-103">在 Skype for Business 服务器中验证 Edge 部署</span><span class="sxs-lookup"><span data-stu-id="a563f-103">Validate your Edge deployment in Skype for Business Server</span></span>
 
<span data-ttu-id="a563f-104">**摘要:** 了解如何验证 Edge 服务器或 Edge 服务器池的部署是否在 Skype for Business 服务器中工作。</span><span class="sxs-lookup"><span data-stu-id="a563f-104">**Summary:** Learn how to verify that your deployment of Edge Server or Edge Server pool is working in Skype for Business Server.</span></span>
  
<span data-ttu-id="a563f-105">部署 Edge 服务器或边缘服务器池后, 您需要知道它是否正常工作。</span><span class="sxs-lookup"><span data-stu-id="a563f-105">Once you've deployed your Edge Server or Edge Server pool, you need to know if it's working properly.</span></span> <span data-ttu-id="a563f-106">下面是一些可帮助确保你的边缘环境已连接到内部服务器, 并且你的外部用户可以通过你的边缘连接到 Skype for Business 服务器环境的一些内容。</span><span class="sxs-lookup"><span data-stu-id="a563f-106">Here are a couple of things that can help with confirming your Edge environment is connected to your internal servers, and also that your external users can connect to your Skype for Business Server environment through your Edge.</span></span>
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a><span data-ttu-id="a563f-107">验证内部服务器与边缘服务器之间的连接</span><span class="sxs-lookup"><span data-stu-id="a563f-107">Verify connectivity between your internal servers and your Edge servers</span></span>

<span data-ttu-id="a563f-108">在安装边缘服务器时自动在边缘服务器或边缘服务器池中完成连接验证时, 你仍然可以通过 Windows PowerShell 确认此操作。</span><span class="sxs-lookup"><span data-stu-id="a563f-108">While validation of connectivity is done automatically in Edge Server or Edge Server pool when the Edge Servers are installed, you can still confirm this for yourself with Windows PowerShell.</span></span> <span data-ttu-id="a563f-109">在具有中央管理存储的内部服务器上运行 CsManagementStoreReplicationStatus cmdlet, 或在已安装 Skype for business Server Core 组件 (OcsCore) 的任何加入域的计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="a563f-109">Run the Get-CsManagementStoreReplicationStatus cmdlet on the internal server which has the Central Management store, or any domain joined computer on which Skype for Business Server Core Components (OcsCore.msi) are installed.</span></span>
  
<span data-ttu-id="a563f-p103">初次运行此命令的结果可能给出复制状态为 False，而不是 True。如果发生这种情况，请运行 Invoke-CsManagementStoreReplication cmdlet。留些时间让其完成复制，然后再次运行 Get-CsManagementStoreReplicationStatus cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a563f-p103">The initial result of running this command may give a False status, rather than True, for replication. If that happens run the Invoke-CsManagementStoreReplication cmdlet. Give it some time to complete the replication, and then run the Get-CsManagementStoreReplicationStatus cmdlet again.</span></span>
  
## <a name="verify-connectivity-for-your-external-users"></a><span data-ttu-id="a563f-113">验证外部用户连接</span><span class="sxs-lookup"><span data-stu-id="a563f-113">Verify connectivity for your external users</span></span>

<span data-ttu-id="a563f-114">我们确实有一个很好的工具可用于确认你的 Edge 服务器配置, 并且能够为 Edge 服务器方案连接、发送和接收正确的消息。</span><span class="sxs-lookup"><span data-stu-id="a563f-114">We do have a great tool for confirming your Edge Server configuration, and the ability to connect, send and receive the correct messages for Edge Server scenarios.</span></span> <span data-ttu-id="a563f-115">这是[远程连接 Anaylzer 网站](https://testconnectivity.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="a563f-115">It's the [Remote Connectivity Anaylzer site](https://testconnectivity.microsoft.com/).</span></span> <span data-ttu-id="a563f-116">这是由 Microsoft 管理和维护的站点。</span><span class="sxs-lookup"><span data-stu-id="a563f-116">This is a site that's managed and maintained by Microsoft Support.</span></span> <span data-ttu-id="a563f-117">若要使用此工具，请通过浏览找到该网站，然后按照指示选择适合你的正确方案。</span><span class="sxs-lookup"><span data-stu-id="a563f-117">To use this tool, browse to the website and follow the instructions to choose the right scenario for you.</span></span>
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a><span data-ttu-id="a563f-118">测试外部用户连接时应考虑的事项</span><span class="sxs-lookup"><span data-stu-id="a563f-118">Things to consider when testing external user connectivity</span></span>

<span data-ttu-id="a563f-119">任何外部用户访问测试应包括贵组织支持的每种类型的内部用户，这可能包括下列任意部分或全部用户：</span><span class="sxs-lookup"><span data-stu-id="a563f-119">Any test for external user access needs to include each type of internal user your organization supports, which could include any or all of the following:</span></span>
  
- <span data-ttu-id="a563f-120">来自至少一个联盟域的用户（尽管我们建议测试所有这些域）。</span><span class="sxs-lookup"><span data-stu-id="a563f-120">Users from at least one federated domain (we do recommend testing them all though).</span></span>
    
- <span data-ttu-id="a563f-121">匿名用户。</span><span class="sxs-lookup"><span data-stu-id="a563f-121">Anonymous users.</span></span>
    
- <span data-ttu-id="a563f-122">您的组织中远程登录到 Skype for Business 但没有使用 VPN 的用户。</span><span class="sxs-lookup"><span data-stu-id="a563f-122">Users in your organization who are logged into Skype for Business remotely, but aren't using VPN.</span></span>
    
<span data-ttu-id="a563f-123">这些测试将确定你的边缘服务器是否:</span><span class="sxs-lookup"><span data-stu-id="a563f-123">These tests will determine whether your Edge Server is:</span></span>
  
- <span data-ttu-id="a563f-124">使用 Telnet 客户端从网络外侦听所需端口。</span><span class="sxs-lookup"><span data-stu-id="a563f-124">Listening on the necessary ports by using a telnet client from outside your network.</span></span>
    
  - <span data-ttu-id="a563f-125">例如：telnet sip.contoso.com 443</span><span class="sxs-lookup"><span data-stu-id="a563f-125">For example: telnet sip.contoso.com 443</span></span>
    
  - <span data-ttu-id="a563f-126">你应该针对你在 Edge 服务器或 Edge 服务器池中使用的端口执行上述测试, 具体取决于你的部署。</span><span class="sxs-lookup"><span data-stu-id="a563f-126">You should perform the preceding test on the ports you're using on your Edge Server or Edge Server pool, depending on your deployment.</span></span>
    
- <span data-ttu-id="a563f-127">执行准确的外部 DNS 解析。</span><span class="sxs-lookup"><span data-stu-id="a563f-127">Performing accurate external DNS resolution.</span></span>
    
  - <span data-ttu-id="a563f-128">从您的网络外部, ping 一下 Edge 服务器或边缘服务器池中的每个外部 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="a563f-128">From outside your network, ping each of the external FQDNs of your Edge Server or Edge Server pool.</span></span> <span data-ttu-id="a563f-129">即使 ping 失败, 您也可以看到 IP 地址, 您可以比较以前分配的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="a563f-129">Even if the ping fails, you'll see the IP addresses, which you can compare the IP addresses you've previously assigned.</span></span>
    

