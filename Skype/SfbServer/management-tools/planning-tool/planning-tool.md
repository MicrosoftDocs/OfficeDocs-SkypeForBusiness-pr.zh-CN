---
title: Skype for Business Server 2015 规划工具
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 2a352f62-c5cb-4ef1-9aa9-7f0c1ab47455
description: 有关使用 Skype 业务 Server 2015 规划工具的指南。
ms.openlocfilehash: faaa4a334fc04be44dce2a753804bf3e7f2b52b0
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20998586"
---
# <a name="skype-for-business-server-2015-planning-tool"></a><span data-ttu-id="43a6b-103">Skype for Business Server 2015 规划工具</span><span class="sxs-lookup"><span data-stu-id="43a6b-103">Skype for Business Server 2015 Planning Tool</span></span>
 
<span data-ttu-id="43a6b-104">有关使用 Skype 业务 Server 2015 规划工具的指南。</span><span class="sxs-lookup"><span data-stu-id="43a6b-104">Guidance on using the Skype for Business Server 2015 Planning Tool.</span></span>
  
<span data-ttu-id="43a6b-105">Skype 业务服务器 2015年规划工具是一个向导，驱动，类似于面试的工具对于您正在设计的业务服务器 2015年拓扑询问有关 Skype 的问题。</span><span class="sxs-lookup"><span data-stu-id="43a6b-105">The Skype for Business Server 2015 Planning Tool is a wizard driven, interview-like tool that asks questions about the Skype for Business Server 2015 topology that you are designing.</span></span> <span data-ttu-id="43a6b-106">提供的信息，规划工具使用结合首选做法拓扑设计和容量，演示根据提供的回答推荐的拓扑。</span><span class="sxs-lookup"><span data-stu-id="43a6b-106">The Planning Tool uses the information supplied, coupled with preferred practices for topology design and capacity, to present a recommended topology based on the answers supplied.</span></span> <span data-ttu-id="43a6b-107">您可以从[业务 Server 2015 规划工具的 Skype](https://go.microsoft.com/fwlink/p/?LinkID=282725)下载规划工具。</span><span class="sxs-lookup"><span data-stu-id="43a6b-107">You can download the Planning Tool from the [Skype for Business Server 2015 Planning Tool](https://go.microsoft.com/fwlink/p/?LinkID=282725).</span></span>
  
<span data-ttu-id="43a6b-108">最终，规划工具的目标是简化设计业务服务器 2015年拓扑的完整 Skype 的潜在复杂性。</span><span class="sxs-lookup"><span data-stu-id="43a6b-108">Ultimately, the goal of the Planning Tool is to ease the potential complexity of designing a complete Skype for Business Server 2015 topology.</span></span> <span data-ttu-id="43a6b-109">该工具还提供了工具，在规划和部署文档的上下文引用提供 Internet 连接的可连接到 Microsoft 网站。</span><span class="sxs-lookup"><span data-stu-id="43a6b-109">The tool also provides contextual references to planning and deployment documentation inside the tool, provided that an Internet connection is available to connect to the Microsoft  website.</span></span>
  
<span data-ttu-id="43a6b-110">自定义后与基础结构的 TCP/IP 地址和完全限定的域名 (Fqdn) 的拓扑，规划工具进行提供一系列介绍域名系统 (DNS) 命名、 防火墙规则、 证书和详细的报告。</span><span class="sxs-lookup"><span data-stu-id="43a6b-110">After customizing the topology with the infrastructure's TCP/IP addresses and fully qualified domain names (FQDNs), the Planning Tool makes available a series of reports that cover Domain Name System (DNS) naming, firewall rules, certificates, and more.</span></span> 
  
<span data-ttu-id="43a6b-111">使用此工具是规划你的实施的第一步。</span><span class="sxs-lookup"><span data-stu-id="43a6b-111">Using this tool is the first step in planning your implementation.</span></span> <span data-ttu-id="43a6b-112">下一步将是您网站信息细节输入[业务 Server 2015 容量计算器的 Skype](https://www.microsoft.com/en-us/download/details.aspx?id=51196)，根据需要调整，然后使用[Skype 的业务服务器 2015年压力和性能工具](https://www.microsoft.com/en-us/download/details.aspx?id=50367)模拟，并验证实现将满足您的需求。</span><span class="sxs-lookup"><span data-stu-id="43a6b-112">The next step would be to input your site information specifics into the [Skype for Business Server 2015 Capacity Calculator](https://www.microsoft.com/en-us/download/details.aspx?id=51196), adjust as needed, then use the [Skype for Business Server 2015 Stress and Performance Tool](https://www.microsoft.com/en-us/download/details.aspx?id=50367) to simulate and verify the implementation will serve your needs.</span></span>
  
<span data-ttu-id="43a6b-113">规划工具还提供导出中两种格式信息的功能：</span><span class="sxs-lookup"><span data-stu-id="43a6b-113">The Planning Tool also provides the ability to export information in two formats:</span></span>
  
- <span data-ttu-id="43a6b-114">Microsoft Excel（.xml 电子表格）</span><span class="sxs-lookup"><span data-stu-id="43a6b-114">Microsoft Excel (.xml spreadsheet)</span></span>
    
- <span data-ttu-id="43a6b-115">Microsoft Visio (.vdx)</span><span class="sxs-lookup"><span data-stu-id="43a6b-115">Microsoft Visio (.vdx)</span></span>
    
<span data-ttu-id="43a6b-116">以下主题介绍并规划工具的详细信息。</span><span class="sxs-lookup"><span data-stu-id="43a6b-116">The following topics introduce and detail the Planning Tool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="43a6b-117">本节内容</span><span class="sxs-lookup"><span data-stu-id="43a6b-117">In this section</span></span>

- [<span data-ttu-id="43a6b-118">在 Skype for Business Server 2015 中安装规划工具</span><span class="sxs-lookup"><span data-stu-id="43a6b-118">Install the Planning Tool in Skype for Business Server 2015</span></span>](install.md)
    
- [<span data-ttu-id="43a6b-119">Optional Software</span><span class="sxs-lookup"><span data-stu-id="43a6b-119">Optional Software</span></span>](install.md#Optional_Software)
    
- [<span data-ttu-id="43a6b-120">在 Skype for Business Server 2015 中导航规划工具</span><span class="sxs-lookup"><span data-stu-id="43a6b-120">Navigate the Planning Tool in Skype for Business Server 2015</span></span>](navigate.md)
    
- [<span data-ttu-id="43a6b-121">为 Skype for Business Server 2015 创建初始拓扑设计</span><span class="sxs-lookup"><span data-stu-id="43a6b-121">Create the initial topology design for Skype for Business Server 2015</span></span>](create-the-initial-design.md)
    
- [<span data-ttu-id="43a6b-122">在 Skype for Business Server 2015 中编辑拓扑</span><span class="sxs-lookup"><span data-stu-id="43a6b-122">Edit the topology in Skype for Business Server 2015</span></span>](edit-the-topology.md)
    
- [<span data-ttu-id="43a6b-123">Edit the network configuration diagram</span><span class="sxs-lookup"><span data-stu-id="43a6b-123">Edit the network configuration diagram</span></span>](edit-the-topology.md#Edit_Network_diagram)
    
- [<span data-ttu-id="43a6b-124">在 Skype for Business Server 2015 中查看管理员报告</span><span class="sxs-lookup"><span data-stu-id="43a6b-124">Review the Administrator Reports in Skype for Business Server 2015</span></span>](review-the-administrator-reports.md)
    
## <a name="see-also"></a><span data-ttu-id="43a6b-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="43a6b-125">See also</span></span>

[<span data-ttu-id="43a6b-126">安装 Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="43a6b-126">Install Skype for Business Server 2015</span></span>](../../deploy/install/install.md)
  
[<span data-ttu-id="43a6b-127">规划 Skype for Business Server 2015 中的即时消息和状态</span><span class="sxs-lookup"><span data-stu-id="43a6b-127">Plan for instant messaging and presence in Skype for Business Server 2015</span></span>](../../plan-your-deployment/instant-messaging-and-presence.md)