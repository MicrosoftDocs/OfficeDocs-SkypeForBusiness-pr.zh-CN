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
description: 有关使用 Skype 业务服务器 2015年规划工具的指南。
ms.openlocfilehash: 9995b17274377025f2531ca53966859d1ca716b6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="skype-for-business-server-2015-planning-tool"></a><span data-ttu-id="1ce75-103">Skype for Business Server 2015 规划工具</span><span class="sxs-lookup"><span data-stu-id="1ce75-103">Skype for Business Server 2015 Planning Tool</span></span>
 
<span data-ttu-id="1ce75-104">有关使用 Skype 业务服务器 2015年规划工具的指南。</span><span class="sxs-lookup"><span data-stu-id="1ce75-104">Guidance on using the Skype for Business Server 2015 Planning Tool.</span></span>
  
<span data-ttu-id="1ce75-105">商业服务器 2015年计划工具 Skype 是向导驱动的、 类似于面试的工具，为您设计的业务服务器 2015年拓扑询问有关 Skype 的问题。</span><span class="sxs-lookup"><span data-stu-id="1ce75-105">The Skype for Business Server 2015 Planning Tool is a wizard driven, interview-like tool that asks questions about the Skype for Business Server 2015 topology that you are designing.</span></span> <span data-ttu-id="1ce75-106">使用拓扑的设计和容量，以提供建议的拓扑结构，根据提供的回答的首选做法加以信息提供的使用的规划工具。</span><span class="sxs-lookup"><span data-stu-id="1ce75-106">The Planning Tool uses the information supplied, coupled with preferred practices for topology design and capacity, to present a recommended topology based on the answers supplied.</span></span> <span data-ttu-id="1ce75-107">您可以从[Microsoft 下载中心](https://go.microsoft.com/fwlink/p/?LinkID=282725)下载规划工具。</span><span class="sxs-lookup"><span data-stu-id="1ce75-107">You can download the Planning Tool from the [Microsoft Downloads Center](https://go.microsoft.com/fwlink/p/?LinkID=282725).</span></span>
  
<span data-ttu-id="1ce75-108">从根本上讲，规划工具的目的是为了简化设计业务服务器 2015年拓扑完成 Skype 的潜在复杂性。</span><span class="sxs-lookup"><span data-stu-id="1ce75-108">Ultimately, the goal of the Planning Tool is to ease the potential complexity of designing a complete Skype for Business Server 2015 topology.</span></span> <span data-ttu-id="1ce75-109">如果可以通过 Internet 连接来连接到 Microsoft TechNet 网站，该工具还会提供对工具内规划文档和部署文档的上下文引用。</span><span class="sxs-lookup"><span data-stu-id="1ce75-109">The tool also provides contextual references to planning and deployment documentation inside the tool, provided that an Internet connection is available to connect to the Microsoft TechNet website.</span></span>
  
<span data-ttu-id="1ce75-110">自定义拓扑结构中基础结构的 TCP/IP 地址和完全限定的域名 (Fqdn) 之后, 规划工具可报告涵盖了域名系统 (DNS) 命名、 防火墙规则、 证书，以及其他一系列。</span><span class="sxs-lookup"><span data-stu-id="1ce75-110">After customizing the topology with the infrastructure's TCP/IP addresses and fully qualified domain names (FQDNs), the Planning Tool makes available a series of reports that cover Domain Name System (DNS) naming, firewall rules, certificates, and more.</span></span> 
  
<span data-ttu-id="1ce75-111">使用此工具是规划你的实施的第一步。</span><span class="sxs-lookup"><span data-stu-id="1ce75-111">Using this tool is the first step in planning your implementation.</span></span> <span data-ttu-id="1ce75-112">下一步就是[Skype 业务服务器 2015年容量计算器](https://www.microsoft.com/en-us/download/details.aspx?id=51196)中输入您站点信息的具体内容，根据需要调整然后使用[Skype 业务服务器 2015年的压力和性能工具](https://www.microsoft.com/en-us/download/details.aspx?id=50367)进行模拟和验证实现将满足您的需求。</span><span class="sxs-lookup"><span data-stu-id="1ce75-112">The next step would be to input your site information specifics into the [Skype for Business Server 2015 Capacity Calculator](https://www.microsoft.com/en-us/download/details.aspx?id=51196), adjust as needed, then use the [Skype for Business Server 2015 Stress and Performance Tool](https://www.microsoft.com/en-us/download/details.aspx?id=50367) to simulate and verify the implementation will serve your needs.</span></span>
  
<span data-ttu-id="1ce75-113">规划工具还提供导出两种格式的信息的能力：</span><span class="sxs-lookup"><span data-stu-id="1ce75-113">The Planning Tool also provides the ability to export information in two formats:</span></span>
  
- <span data-ttu-id="1ce75-114">Microsoft Excel（.xml 电子表格）</span><span class="sxs-lookup"><span data-stu-id="1ce75-114">Microsoft Excel (.xml spreadsheet)</span></span>
    
- <span data-ttu-id="1ce75-115">Microsoft Visio (.vdx)</span><span class="sxs-lookup"><span data-stu-id="1ce75-115">Microsoft Visio (.vdx)</span></span>
    
<span data-ttu-id="1ce75-116">下列主题介绍并详细说明了规划工具。</span><span class="sxs-lookup"><span data-stu-id="1ce75-116">The following topics introduce and detail the Planning Tool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="1ce75-117">本节内容</span><span class="sxs-lookup"><span data-stu-id="1ce75-117">In this section</span></span>

- [<span data-ttu-id="1ce75-118">在 Skype 业务服务器 2015年安装规划工具</span><span class="sxs-lookup"><span data-stu-id="1ce75-118">Install the Planning Tool in Skype for Business Server 2015</span></span>](install.md)
    
- [<span data-ttu-id="1ce75-119">Optional Software</span><span class="sxs-lookup"><span data-stu-id="1ce75-119">Optional Software</span></span>](install.md#Optional_Software)
    
- [<span data-ttu-id="1ce75-120">导航业务服务器 2015 Skype 的规划工具</span><span class="sxs-lookup"><span data-stu-id="1ce75-120">Navigate the Planning Tool in Skype for Business Server 2015</span></span>](navigate.md)
    
- [<span data-ttu-id="1ce75-121">创建业务服务器 2015年的 Skype 的初始拓扑结构设计</span><span class="sxs-lookup"><span data-stu-id="1ce75-121">Create the initial topology design for Skype for Business Server 2015</span></span>](create-the-initial-design.md)
    
- [<span data-ttu-id="1ce75-122">编辑业务服务器 2015 Skype 中的拓扑</span><span class="sxs-lookup"><span data-stu-id="1ce75-122">Edit the topology in Skype for Business Server 2015</span></span>](edit-the-topology.md)
    
- [<span data-ttu-id="1ce75-123">Edit the network configuration diagram</span><span class="sxs-lookup"><span data-stu-id="1ce75-123">Edit the network configuration diagram</span></span>](edit-the-topology.md#Edit_Network_diagram)
    
- [<span data-ttu-id="1ce75-124">在 Skype 的管理员报告审查业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="1ce75-124">Review the Administrator Reports in Skype for Business Server 2015</span></span>](review-the-administrator-reports.md)
    
## <a name="see-also"></a><span data-ttu-id="1ce75-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1ce75-125">See also</span></span>

#### 

[<span data-ttu-id="1ce75-126">为业务服务器 2015年安装 Skype</span><span class="sxs-lookup"><span data-stu-id="1ce75-126">Install Skype for Business Server 2015</span></span>](../../deploy/install/install.md)
  
[<span data-ttu-id="1ce75-127">即时消息和 Skype 在规划业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="1ce75-127">Plan for instant messaging and presence in Skype for Business Server 2015</span></span>](../../plan-your-deployment/instant-messaging-and-presence.md)

