---
title: Skype for Business Server 2015 规划工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 2a352f62-c5cb-4ef1-9aa9-7f0c1ab47455
description: 有关使用 Skype for Business Server 2015 规划工具的指南。
ms.openlocfilehash: 8eec7865b74640cf6dfe4f5a5122f4c7091cc5ae
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050094"
---
# <a name="skype-for-business-server-2015-planning-tool"></a><span data-ttu-id="c146a-103">Skype for Business Server 2015 规划工具</span><span class="sxs-lookup"><span data-stu-id="c146a-103">Skype for Business Server 2015 Planning Tool</span></span>
 
<span data-ttu-id="c146a-104">有关使用 Skype for Business Server 2015 规划工具的指南。</span><span class="sxs-lookup"><span data-stu-id="c146a-104">Guidance on using the Skype for Business Server 2015 Planning Tool.</span></span>
  
<span data-ttu-id="c146a-105">Skype for Business Server 2015 规划工具是一个向导驱动的、类似于访谈的工具，它会询问有关您正在设计的 Skype for business Server 2015 拓扑的问题。</span><span class="sxs-lookup"><span data-stu-id="c146a-105">The Skype for Business Server 2015 Planning Tool is a wizard driven, interview-like tool that asks questions about the Skype for Business Server 2015 topology that you are designing.</span></span> <span data-ttu-id="c146a-106">规划工具使用提供的信息和拓扑设计和容量的首选做法，根据提供的答案提供建议的拓扑。</span><span class="sxs-lookup"><span data-stu-id="c146a-106">The Planning Tool uses the information supplied, coupled with preferred practices for topology design and capacity, to present a recommended topology based on the answers supplied.</span></span> <span data-ttu-id="c146a-107">您可以从[Skype For Business Server 2015 规划工具](https://go.microsoft.com/fwlink/p/?LinkID=282725)下载规划工具。</span><span class="sxs-lookup"><span data-stu-id="c146a-107">You can download the Planning Tool from the [Skype for Business Server 2015 Planning Tool](https://go.microsoft.com/fwlink/p/?LinkID=282725).</span></span>
  
<span data-ttu-id="c146a-108">最终，规划工具的目标是减轻设计完整的 Skype for Business Server 2015 拓扑的潜在复杂性。</span><span class="sxs-lookup"><span data-stu-id="c146a-108">Ultimately, the goal of the Planning Tool is to ease the potential complexity of designing a complete Skype for Business Server 2015 topology.</span></span> <span data-ttu-id="c146a-109">该工具还提供了工具内规划和部署文档的上下文参考，前提是 Internet 连接可用于连接到 Microsoft 网站。</span><span class="sxs-lookup"><span data-stu-id="c146a-109">The tool also provides contextual references to planning and deployment documentation inside the tool, provided that an Internet connection is available to connect to the Microsoft  website.</span></span>
  
<span data-ttu-id="c146a-110">使用基础结构的 TCP/IP 地址和完全限定的域名（Fqdn）自定义拓扑之后，规划工具会提供一系列涵盖域名系统（DNS）命名、防火墙规则、证书等的报告。</span><span class="sxs-lookup"><span data-stu-id="c146a-110">After customizing the topology with the infrastructure's TCP/IP addresses and fully qualified domain names (FQDNs), the Planning Tool makes available a series of reports that cover Domain Name System (DNS) naming, firewall rules, certificates, and more.</span></span> 
  
<span data-ttu-id="c146a-111">使用此工具是规划实施过程中的第一步。</span><span class="sxs-lookup"><span data-stu-id="c146a-111">Using this tool is the first step in planning your implementation.</span></span> <span data-ttu-id="c146a-112">下一步是将网站信息详细信息输入到[Skype For Business Server 2015 容量计算器](https://www.microsoft.com/download/details.aspx?id=51196)中，根据需要进行调整，然后使用[Skype for Business Server 2015 压力和性能工具](https://www.microsoft.com/download/details.aspx?id=50367)模拟并验证实施是否满足您的需求。</span><span class="sxs-lookup"><span data-stu-id="c146a-112">The next step would be to input your site information specifics into the [Skype for Business Server 2015 Capacity Calculator](https://www.microsoft.com/download/details.aspx?id=51196), adjust as needed, then use the [Skype for Business Server 2015 Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367) to simulate and verify the implementation will serve your needs.</span></span>
  
<span data-ttu-id="c146a-113">规划工具还提供了以两种格式导出信息的功能：</span><span class="sxs-lookup"><span data-stu-id="c146a-113">The Planning Tool also provides the ability to export information in two formats:</span></span>
  
- <span data-ttu-id="c146a-114">Microsoft Excel （.xml 电子表格）</span><span class="sxs-lookup"><span data-stu-id="c146a-114">Microsoft Excel (.xml spreadsheet)</span></span>
    
- <span data-ttu-id="c146a-115">Microsoft Visio （vdx）</span><span class="sxs-lookup"><span data-stu-id="c146a-115">Microsoft Visio (.vdx)</span></span>
    
<span data-ttu-id="c146a-116">以下主题介绍并详细说明规划工具。</span><span class="sxs-lookup"><span data-stu-id="c146a-116">The following topics introduce and detail the Planning Tool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="c146a-117">本节内容</span><span class="sxs-lookup"><span data-stu-id="c146a-117">In this section</span></span>

- [<span data-ttu-id="c146a-118">在 Skype for Business Server 2015 中安装规划工具</span><span class="sxs-lookup"><span data-stu-id="c146a-118">Install the Planning Tool in Skype for Business Server 2015</span></span>](install.md)
    
- [<span data-ttu-id="c146a-119">可选软件</span><span class="sxs-lookup"><span data-stu-id="c146a-119">Optional Software</span></span>](install.md#Optional_Software)
    
- [<span data-ttu-id="c146a-120">在 Skype for Business Server 2015 中导航规划工具</span><span class="sxs-lookup"><span data-stu-id="c146a-120">Navigate the Planning Tool in Skype for Business Server 2015</span></span>](navigate.md)
    
- [<span data-ttu-id="c146a-121">为 Skype for business Server 2015 创建初始拓扑设计</span><span class="sxs-lookup"><span data-stu-id="c146a-121">Create the initial topology design for Skype for Business Server 2015</span></span>](create-the-initial-design.md)
    
- [<span data-ttu-id="c146a-122">在 Skype for Business Server 2015 中编辑拓扑</span><span class="sxs-lookup"><span data-stu-id="c146a-122">Edit the topology in Skype for Business Server 2015</span></span>](edit-the-topology.md)
    
- [<span data-ttu-id="c146a-123">编辑网络配置图</span><span class="sxs-lookup"><span data-stu-id="c146a-123">Edit the network configuration diagram</span></span>](edit-the-topology.md#Edit_Network_diagram)
    
- [<span data-ttu-id="c146a-124">在 Skype for Business Server 2015 中查看管理员报告</span><span class="sxs-lookup"><span data-stu-id="c146a-124">Review the Administrator Reports in Skype for Business Server 2015</span></span>](review-the-administrator-reports.md)
    
## <a name="see-also"></a><span data-ttu-id="c146a-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c146a-125">See also</span></span>

[<span data-ttu-id="c146a-126">安装 Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c146a-126">Install Skype for Business Server 2015</span></span>](../../deploy/install/install.md)
  
[<span data-ttu-id="c146a-127">在 Skype for Business Server 2015 中规划即时消息和状态</span><span class="sxs-lookup"><span data-stu-id="c146a-127">Plan for instant messaging and presence in Skype for Business Server 2015</span></span>](../../plan-your-deployment/instant-messaging-and-presence.md)
