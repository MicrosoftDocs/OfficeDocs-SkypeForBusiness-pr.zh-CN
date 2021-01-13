---
title: Skype for Business Server 2015 规划工具
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: aef46fac65ba1d5651cada81bc79cfc21021bf54
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832382"
---
# <a name="skype-for-business-server-2015-planning-tool"></a><span data-ttu-id="aee19-103">Skype for Business Server 2015 规划工具</span><span class="sxs-lookup"><span data-stu-id="aee19-103">Skype for Business Server 2015 Planning Tool</span></span>
 
<span data-ttu-id="aee19-104">有关使用 Skype for Business Server 2015 规划工具的指南。</span><span class="sxs-lookup"><span data-stu-id="aee19-104">Guidance on using the Skype for Business Server 2015 Planning Tool.</span></span>
  
<span data-ttu-id="aee19-105">Skype for Business Server 2015 规划工具是向导驱动的、类似访谈式的工具，可询问有关您设计的 Skype for Business Server 2015 拓扑的问题。</span><span class="sxs-lookup"><span data-stu-id="aee19-105">The Skype for Business Server 2015 Planning Tool is a wizard driven, interview-like tool that asks questions about the Skype for Business Server 2015 topology that you are designing.</span></span> <span data-ttu-id="aee19-106">规划工具使用所提供的信息以及拓扑设计和容量的首选做法，根据提供的答案提供建议的拓扑。</span><span class="sxs-lookup"><span data-stu-id="aee19-106">The Planning Tool uses the information supplied, coupled with preferred practices for topology design and capacity, to present a recommended topology based on the answers supplied.</span></span> <span data-ttu-id="aee19-107">可以从 Skype for Business [Server 2015 规划工具下载规划工具](https://go.microsoft.com/fwlink/p/?LinkID=282725)。</span><span class="sxs-lookup"><span data-stu-id="aee19-107">You can download the Planning Tool from the [Skype for Business Server 2015 Planning Tool](https://go.microsoft.com/fwlink/p/?LinkID=282725).</span></span>
  
<span data-ttu-id="aee19-108">最后，规划工具的目标是降低设计完整的 Skype for Business Server 2015 拓扑的复杂性。</span><span class="sxs-lookup"><span data-stu-id="aee19-108">Ultimately, the goal of the Planning Tool is to ease the potential complexity of designing a complete Skype for Business Server 2015 topology.</span></span> <span data-ttu-id="aee19-109">如果 Internet 连接可用于连接到 Microsoft 网站，该工具还提供对工具内规划和部署文档的上下文引用。</span><span class="sxs-lookup"><span data-stu-id="aee19-109">The tool also provides contextual references to planning and deployment documentation inside the tool, provided that an Internet connection is available to connect to the Microsoft  website.</span></span>
  
<span data-ttu-id="aee19-110">使用基础结构的 TCP/IP 地址和完全限定域名 (FQDN) 自定义拓扑后，规划工具会提供一系列报告，包括域名系统 (DNS) 命名、防火墙规则、证书等。</span><span class="sxs-lookup"><span data-stu-id="aee19-110">After customizing the topology with the infrastructure's TCP/IP addresses and fully qualified domain names (FQDNs), the Planning Tool makes available a series of reports that cover Domain Name System (DNS) naming, firewall rules, certificates, and more.</span></span> 
  
<span data-ttu-id="aee19-111">使用此工具是规划实现的第一步。</span><span class="sxs-lookup"><span data-stu-id="aee19-111">Using this tool is the first step in planning your implementation.</span></span> <span data-ttu-id="aee19-112">下一步是将你的站点信息详细信息输入到 [Skype for Business Server 2015](https://www.microsoft.com/download/details.aspx?id=51196)容量计算器中，根据需要进行调整，然后使用 Skype for Business Server [2015 压力](https://www.microsoft.com/download/details.aspx?id=50367) 和性能工具模拟和验证实现是否满足你的需求。</span><span class="sxs-lookup"><span data-stu-id="aee19-112">The next step would be to input your site information specifics into the [Skype for Business Server 2015 Capacity Calculator](https://www.microsoft.com/download/details.aspx?id=51196), adjust as needed, then use the [Skype for Business Server 2015 Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367) to simulate and verify the implementation will serve your needs.</span></span>
  
<span data-ttu-id="aee19-113">规划工具还提供了以两种格式导出信息的能力：</span><span class="sxs-lookup"><span data-stu-id="aee19-113">The Planning Tool also provides the ability to export information in two formats:</span></span>
  
- <span data-ttu-id="aee19-114">Microsoft Excel (.xml 电子表格) </span><span class="sxs-lookup"><span data-stu-id="aee19-114">Microsoft Excel (.xml spreadsheet)</span></span>
    
- <span data-ttu-id="aee19-115">Microsoft Visio (.vdx) </span><span class="sxs-lookup"><span data-stu-id="aee19-115">Microsoft Visio (.vdx)</span></span>
    
<span data-ttu-id="aee19-116">以下主题介绍并详细介绍了规划工具。</span><span class="sxs-lookup"><span data-stu-id="aee19-116">The following topics introduce and detail the Planning Tool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="aee19-117">本节内容</span><span class="sxs-lookup"><span data-stu-id="aee19-117">In this section</span></span>

- [<span data-ttu-id="aee19-118">在 Skype for Business Server 2015 中安装规划工具</span><span class="sxs-lookup"><span data-stu-id="aee19-118">Install the Planning Tool in Skype for Business Server 2015</span></span>](install.md)
    
- [<span data-ttu-id="aee19-119">可选软件</span><span class="sxs-lookup"><span data-stu-id="aee19-119">Optional Software</span></span>](install.md#Optional_Software)
    
- [<span data-ttu-id="aee19-120">在 Skype for Business Server 2015 中导航规划工具</span><span class="sxs-lookup"><span data-stu-id="aee19-120">Navigate the Planning Tool in Skype for Business Server 2015</span></span>](navigate.md)
    
- [<span data-ttu-id="aee19-121">为 Skype for Business Server 2015 创建初始拓扑设计</span><span class="sxs-lookup"><span data-stu-id="aee19-121">Create the initial topology design for Skype for Business Server 2015</span></span>](create-the-initial-design.md)
    
- [<span data-ttu-id="aee19-122">在 Skype for Business Server 2015 中编辑拓扑</span><span class="sxs-lookup"><span data-stu-id="aee19-122">Edit the topology in Skype for Business Server 2015</span></span>](edit-the-topology.md)
    
- [<span data-ttu-id="aee19-123">编辑网络配置图</span><span class="sxs-lookup"><span data-stu-id="aee19-123">Edit the network configuration diagram</span></span>](edit-the-topology.md#Edit_Network_diagram)
    
- [<span data-ttu-id="aee19-124">查看 Skype for Business Server 2015 中的管理员报告</span><span class="sxs-lookup"><span data-stu-id="aee19-124">Review the Administrator Reports in Skype for Business Server 2015</span></span>](review-the-administrator-reports.md)
    
## <a name="see-also"></a><span data-ttu-id="aee19-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aee19-125">See also</span></span>

[<span data-ttu-id="aee19-126">安装 Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="aee19-126">Install Skype for Business Server 2015</span></span>](../../deploy/install/install.md)
  
[<span data-ttu-id="aee19-127">在 Skype for Business Server 2015 中规划即时消息和状态</span><span class="sxs-lookup"><span data-stu-id="aee19-127">Plan for instant messaging and presence in Skype for Business Server 2015</span></span>](../../plan-your-deployment/instant-messaging-and-presence.md)
