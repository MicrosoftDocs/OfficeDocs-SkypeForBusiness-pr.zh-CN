---
title: Skype for Business Server 2015 规划工具
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 2a352f62-c5cb-4ef1-9aa9-7f0c1ab47455
description: 有关使用 Skype 业务 Server 2015 规划工具的指南。
ms.openlocfilehash: 6780e69c5a547a96ca9b1b9dc2b3ee54386f1b9b
ms.sourcegitcommit: 1b4e93727f65b120068a74064b4144f0117f230c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/07/2018
ms.locfileid: "19691229"
---
# <a name="skype-for-business-server-2015-planning-tool"></a><span data-ttu-id="6b768-103">Skype for Business Server 2015 规划工具</span><span class="sxs-lookup"><span data-stu-id="6b768-103">Skype for Business Server 2015 Planning Tool</span></span>
 
<span data-ttu-id="6b768-104">有关使用 Skype 业务 Server 2015 规划工具的指南。</span><span class="sxs-lookup"><span data-stu-id="6b768-104">Guidance on using the Skype for Business Server 2015 Planning Tool.</span></span>
  
<span data-ttu-id="6b768-105">Skype 业务服务器 2015年规划工具是一个向导，驱动，类似于面试的工具对于您正在设计的业务服务器 2015年拓扑询问有关 Skype 的问题。</span><span class="sxs-lookup"><span data-stu-id="6b768-105">The Skype for Business Server 2015 Planning Tool is a wizard driven, interview-like tool that asks questions about the Skype for Business Server 2015 topology that you are designing.</span></span> <span data-ttu-id="6b768-106">提供的信息，规划工具使用结合首选做法拓扑设计和容量，演示根据提供的回答推荐的拓扑。</span><span class="sxs-lookup"><span data-stu-id="6b768-106">The Planning Tool uses the information supplied, coupled with preferred practices for topology design and capacity, to present a recommended topology based on the answers supplied.</span></span> <span data-ttu-id="6b768-107">您可以从[业务 Server 2015 规划工具的 Skype](https://go.microsoft.com/fwlink/p/?LinkID=282725)下载规划工具。</span><span class="sxs-lookup"><span data-stu-id="6b768-107">You can download the Planning Tool from the [Skype for Business Server 2015 Planning Tool](https://go.microsoft.com/fwlink/p/?LinkID=282725).</span></span>
  
<span data-ttu-id="6b768-108">最终，规划工具的目标是简化设计业务服务器 2015年拓扑的完整 Skype 的潜在复杂性。</span><span class="sxs-lookup"><span data-stu-id="6b768-108">Ultimately, the goal of the Planning Tool is to ease the potential complexity of designing a complete Skype for Business Server 2015 topology.</span></span> <span data-ttu-id="6b768-109">如果可以通过 Internet 连接来连接到 Microsoft TechNet 网站，该工具还会提供对工具内规划文档和部署文档的上下文引用。</span><span class="sxs-lookup"><span data-stu-id="6b768-109">The tool also provides contextual references to planning and deployment documentation inside the tool, provided that an Internet connection is available to connect to the Microsoft TechNet website.</span></span>
  
<span data-ttu-id="6b768-110">自定义后与基础结构的 TCP/IP 地址和完全限定的域名 (Fqdn) 的拓扑，规划工具进行提供一系列介绍域名系统 (DNS) 命名、 防火墙规则、 证书和详细的报告。</span><span class="sxs-lookup"><span data-stu-id="6b768-110">After customizing the topology with the infrastructure's TCP/IP addresses and fully qualified domain names (FQDNs), the Planning Tool makes available a series of reports that cover Domain Name System (DNS) naming, firewall rules, certificates, and more.</span></span> 
  
<span data-ttu-id="6b768-111">使用此工具是规划你的实施的第一步。</span><span class="sxs-lookup"><span data-stu-id="6b768-111">Using this tool is the first step in planning your implementation.</span></span> <span data-ttu-id="6b768-112">下一步将是您网站信息细节输入[业务 Server 2015 容量计算器的 Skype](https://www.microsoft.com/en-us/download/details.aspx?id=51196)，根据需要调整，然后使用[Skype 的业务服务器 2015年压力和性能工具](https://www.microsoft.com/en-us/download/details.aspx?id=50367)模拟，并验证实现将满足您的需求。</span><span class="sxs-lookup"><span data-stu-id="6b768-112">The next step would be to input your site information specifics into the [Skype for Business Server 2015 Capacity Calculator](https://www.microsoft.com/en-us/download/details.aspx?id=51196), adjust as needed, then use the [Skype for Business Server 2015 Stress and Performance Tool](https://www.microsoft.com/en-us/download/details.aspx?id=50367) to simulate and verify the implementation will serve your needs.</span></span>
  
<span data-ttu-id="6b768-113">规划工具还提供导出中两种格式信息的功能：</span><span class="sxs-lookup"><span data-stu-id="6b768-113">The Planning Tool also provides the ability to export information in two formats:</span></span>
  
- <span data-ttu-id="6b768-114">Microsoft Excel（.xml 电子表格）</span><span class="sxs-lookup"><span data-stu-id="6b768-114">Microsoft Excel (.xml spreadsheet)</span></span>
    
- <span data-ttu-id="6b768-115">Microsoft Visio (.vdx)</span><span class="sxs-lookup"><span data-stu-id="6b768-115">Microsoft Visio (.vdx)</span></span>
    
<span data-ttu-id="6b768-116">以下主题介绍并规划工具的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6b768-116">The following topics introduce and detail the Planning Tool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="6b768-117">本节内容</span><span class="sxs-lookup"><span data-stu-id="6b768-117">In this section</span></span>

- [<span data-ttu-id="6b768-118">为业务 Server 2015 Skype 中安装规划工具</span><span class="sxs-lookup"><span data-stu-id="6b768-118">Install the Planning Tool in Skype for Business Server 2015</span></span>](install.md)
    
- [<span data-ttu-id="6b768-119">Optional Software</span><span class="sxs-lookup"><span data-stu-id="6b768-119">Optional Software</span></span>](install.md#Optional_Software)
    
- [<span data-ttu-id="6b768-120">为业务服务器 2015年导航 Skype 的规划工具</span><span class="sxs-lookup"><span data-stu-id="6b768-120">Navigate the Planning Tool in Skype for Business Server 2015</span></span>](navigate.md)
    
- [<span data-ttu-id="6b768-121">为业务服务器 2015 Skype 创建初始拓扑设计</span><span class="sxs-lookup"><span data-stu-id="6b768-121">Create the initial topology design for Skype for Business Server 2015</span></span>](create-the-initial-design.md)
    
- [<span data-ttu-id="6b768-122">编辑业务服务器 2015 Skype 中的拓扑</span><span class="sxs-lookup"><span data-stu-id="6b768-122">Edit the topology in Skype for Business Server 2015</span></span>](edit-the-topology.md)
    
- [<span data-ttu-id="6b768-123">Edit the network configuration diagram</span><span class="sxs-lookup"><span data-stu-id="6b768-123">Edit the network configuration diagram</span></span>](edit-the-topology.md#Edit_Network_diagram)
    
- [<span data-ttu-id="6b768-124">为业务 Server 2015 查看 Skype 中的管理员报表</span><span class="sxs-lookup"><span data-stu-id="6b768-124">Review the Administrator Reports in Skype for Business Server 2015</span></span>](review-the-administrator-reports.md)
    
## <a name="see-also"></a><span data-ttu-id="6b768-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6b768-125">See also</span></span>

[<span data-ttu-id="6b768-126">安装 Business 服务器 2015 Skype</span><span class="sxs-lookup"><span data-stu-id="6b768-126">Install Skype for Business Server 2015</span></span>](../../deploy/install/install.md)
  
[<span data-ttu-id="6b768-127">规划即时消息和状态 Skype 业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="6b768-127">Plan for instant messaging and presence in Skype for Business Server 2015</span></span>](../../plan-your-deployment/instant-messaging-and-presence.md)