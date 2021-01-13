---
title: 在 Skype for Business Server 中验证边缘部署
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
manager: serdars
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: 摘要：了解如何验证边缘服务器或边缘服务器池的部署在 Skype for Business Server 中是否正常工作。
ms.openlocfilehash: 1da2bed1bc9df7cb118d47c2b27e190546838e1b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804352"
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a><span data-ttu-id="be505-103">在 Skype for Business Server 中验证边缘部署</span><span class="sxs-lookup"><span data-stu-id="be505-103">Validate your Edge deployment in Skype for Business Server</span></span>
 
<span data-ttu-id="be505-104">**摘要：** 了解如何验证边缘服务器或边缘服务器池的部署在 Skype for Business Server 中是否正常工作。</span><span class="sxs-lookup"><span data-stu-id="be505-104">**Summary:** Learn how to verify that your deployment of Edge Server or Edge Server pool is working in Skype for Business Server.</span></span>
  
<span data-ttu-id="be505-105">部署边缘服务器或边缘服务器池后，需要知道其是否正常工作。</span><span class="sxs-lookup"><span data-stu-id="be505-105">Once you've deployed your Edge Server or Edge Server pool, you need to know if it's working properly.</span></span> <span data-ttu-id="be505-106">下面是一些有助于确认边缘环境已连接到内部服务器，以及外部用户可以通过边缘连接到 Skype for Business Server 环境的一些内容。</span><span class="sxs-lookup"><span data-stu-id="be505-106">Here are a couple of things that can help with confirming your Edge environment is connected to your internal servers, and also that your external users can connect to your Skype for Business Server environment through your Edge.</span></span>
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a><span data-ttu-id="be505-107">验证内部服务器和边缘服务器之间的连接</span><span class="sxs-lookup"><span data-stu-id="be505-107">Verify connectivity between your internal servers and your Edge servers</span></span>

<span data-ttu-id="be505-108">在安装边缘服务器后，在边缘服务器或边缘服务器池中自动完成连接验证时，仍可以使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="be505-108">While validation of connectivity is done automatically in Edge Server or Edge Server pool when the Edge Servers are installed, you can still confirm this for yourself with Windows PowerShell.</span></span> <span data-ttu-id="be505-109">在具有中央Get-CsManagementStoreReplicationStatus存储的内部服务器上运行 Get-CsManagementStoreReplicationStatus cmdlet，或在安装了 Skype for Business Server 核心组件 (OcsCore.msi) 的任何加入域的计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="be505-109">Run the Get-CsManagementStoreReplicationStatus cmdlet on the internal server which has the Central Management store, or any domain joined computer on which Skype for Business Server Core Components (OcsCore.msi) are installed.</span></span>
  
<span data-ttu-id="be505-110">运行此命令的初始结果可能为复制提供 False 状态，而不是 True。</span><span class="sxs-lookup"><span data-stu-id="be505-110">The initial result of running this command may give a False status, rather than True, for replication.</span></span> <span data-ttu-id="be505-111">如果发生这种情况，运行 Invoke-CsManagementStoreReplication cmdlet。</span><span class="sxs-lookup"><span data-stu-id="be505-111">If that happens run the Invoke-CsManagementStoreReplication cmdlet.</span></span> <span data-ttu-id="be505-112">请给它一些时间来完成复制，然后再次运行 Get-CsManagementStoreReplicationStatus cmdlet。</span><span class="sxs-lookup"><span data-stu-id="be505-112">Give it some time to complete the replication, and then run the Get-CsManagementStoreReplicationStatus cmdlet again.</span></span>
  
## <a name="verify-connectivity-for-your-external-users"></a><span data-ttu-id="be505-113">验证外部用户的连接性</span><span class="sxs-lookup"><span data-stu-id="be505-113">Verify connectivity for your external users</span></span>

<span data-ttu-id="be505-114">我们提供了一个出色的工具，用于确认边缘服务器配置，以及连接、发送和接收边缘服务器方案的正确消息的能力。</span><span class="sxs-lookup"><span data-stu-id="be505-114">We do have a great tool for confirming your Edge Server configuration, and the ability to connect, send and receive the correct messages for Edge Server scenarios.</span></span> <span data-ttu-id="be505-115">它是远程 [连接分析分析站点](https://testconnectivity.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="be505-115">It's the [Remote Connectivity Anaylzer site](https://testconnectivity.microsoft.com/).</span></span> <span data-ttu-id="be505-116">这是一个由 Microsoft 支持人员管理和维护的网站。</span><span class="sxs-lookup"><span data-stu-id="be505-116">This is a site that's managed and maintained by Microsoft Support.</span></span> <span data-ttu-id="be505-117">若要使用此工具，请浏览到网站并按照说明选择适合你的方案。</span><span class="sxs-lookup"><span data-stu-id="be505-117">To use this tool, browse to the website and follow the instructions to choose the right scenario for you.</span></span>
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a><span data-ttu-id="be505-118">测试外部用户连接时要考虑的一些因素</span><span class="sxs-lookup"><span data-stu-id="be505-118">Things to consider when testing external user connectivity</span></span>

<span data-ttu-id="be505-119">任何外部用户访问测试都需要包括组织支持的每种类型的内部用户，其中可能包括以下任一或全部：</span><span class="sxs-lookup"><span data-stu-id="be505-119">Any test for external user access needs to include each type of internal user your organization supports, which could include any or all of the following:</span></span>
  
- <span data-ttu-id="be505-120">来自至少一个联盟域的用户 (我们建议通过这些域测试) 。</span><span class="sxs-lookup"><span data-stu-id="be505-120">Users from at least one federated domain (we do recommend testing them all though).</span></span>
    
- <span data-ttu-id="be505-121">匿名用户。</span><span class="sxs-lookup"><span data-stu-id="be505-121">Anonymous users.</span></span>
    
- <span data-ttu-id="be505-122">组织中远程登录到 Skype for Business 但没有使用 VPN 的用户。</span><span class="sxs-lookup"><span data-stu-id="be505-122">Users in your organization who are logged into Skype for Business remotely, but aren't using VPN.</span></span>
    
<span data-ttu-id="be505-123">这些测试将确定边缘服务器是否：</span><span class="sxs-lookup"><span data-stu-id="be505-123">These tests will determine whether your Edge Server is:</span></span>
  
- <span data-ttu-id="be505-124">使用 Telnet 客户端从网络外侦听所需端口。</span><span class="sxs-lookup"><span data-stu-id="be505-124">Listening on the necessary ports by using a telnet client from outside your network.</span></span>
    
  - <span data-ttu-id="be505-125">例如：telnet sip.contoso.com 443</span><span class="sxs-lookup"><span data-stu-id="be505-125">For example: telnet sip.contoso.com 443</span></span>
    
  - <span data-ttu-id="be505-126">您应对边缘服务器或边缘服务器池上使用的端口执行上述测试，具体取决于您的部署。</span><span class="sxs-lookup"><span data-stu-id="be505-126">You should perform the preceding test on the ports you're using on your Edge Server or Edge Server pool, depending on your deployment.</span></span>
    
- <span data-ttu-id="be505-127">执行准确的外部 DNS 解析。</span><span class="sxs-lookup"><span data-stu-id="be505-127">Performing accurate external DNS resolution.</span></span>
    
  - <span data-ttu-id="be505-128">从网络外部 ping 边缘服务器或边缘服务器池的每个外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="be505-128">From outside your network, ping each of the external FQDNs of your Edge Server or Edge Server pool.</span></span> <span data-ttu-id="be505-129">即使 ping 失败，您也会看到 IP 地址，可以比较之前分配的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="be505-129">Even if the ping fails, you'll see the IP addresses, which you can compare the IP addresses you've previously assigned.</span></span>
    

