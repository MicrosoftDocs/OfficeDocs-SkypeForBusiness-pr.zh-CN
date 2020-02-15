---
title: Skype for business Server 2015 压力和性能工具的性能方案
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: 使用压力和性能工具配置 Skype for Business Server 2015 以执行性能和负载测试时需要执行的任务。
ms.openlocfilehash: 5531627ab7d5072d32dfcf60fed41eac47f5373f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "41983847"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="ee6c3-103">Skype for business Server 2015 压力和性能工具的性能方案</span><span class="sxs-lookup"><span data-stu-id="ee6c3-103">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="ee6c3-104">使用压力和性能工具配置 Skype for Business Server 2015 以执行性能和负载测试时需要执行的任务。</span><span class="sxs-lookup"><span data-stu-id="ee6c3-104">Tasks you'll need to do to configure Skype for Business Server 2015 to do performance and load-testing, using the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="ee6c3-105">若要运行 Skype for Business Server 2015 压力和性能工具（LyncPerfTool），必须首先为与您相关的方案配置 Skype for business Server 2015 拓扑。</span><span class="sxs-lookup"><span data-stu-id="ee6c3-105">To run the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool), the Skype for Business Server 2015 topology must first be configured for scenarios relevant to you.</span></span> <span data-ttu-id="ee6c3-106">如果未配置 Skype for Business Server 2015 或配置不正确，则负载模拟很可能会失败。</span><span class="sxs-lookup"><span data-stu-id="ee6c3-106">If Skype for Business Server 2015 isn't configured, or is configured incorrectly, your load simulation is very likely to fail.</span></span> <span data-ttu-id="ee6c3-107">使用 Skype for Business Server 2015 压力和性能工具，我们将提供示例 Skype for business Server 命令行管理程序脚本和基本资源文件（作为[工具下载](https://www.microsoft.com/download/details.aspx?id=50367)的一部分）。</span><span class="sxs-lookup"><span data-stu-id="ee6c3-107">With the Skype for Business Server 2015 Stress and Performance Tool, we're providing example Skype for Business Server Management Shell scripts and basic resource files as part of the [tool download](https://www.microsoft.com/download/details.aspx?id=50367).</span></span> <span data-ttu-id="ee6c3-108">这些可用作配置 Skype for Business Server 部署的起始点。</span><span class="sxs-lookup"><span data-stu-id="ee6c3-108">These can be used as a starting point for configuring your Skype for Business Server deployment.</span></span> <span data-ttu-id="ee6c3-109">本文介绍了提供的 Windows PowerShell 示例。</span><span class="sxs-lookup"><span data-stu-id="ee6c3-109">This article describes the Windows PowerShell examples provided.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ee6c3-110">本主题不会帮助您介绍如何配置 Skype for Business Server 2015。通常，我们还提供了其他规划和部署主题。</span><span class="sxs-lookup"><span data-stu-id="ee6c3-110">This topic won't help you describe how to configure Skype for Business Server 2015 generally, we have other Planning and Deployment topics for that.</span></span> <span data-ttu-id="ee6c3-111">有关在 Skype for business Server 2015 中使用 Windows PowerShell 的详细信息，请参阅此处的插入简介中的 Skype for Business Server 命令行管理程序文档。</span><span class="sxs-lookup"><span data-stu-id="ee6c3-111">For details about working with Windows PowerShell in Skype for Business Server 2015, see the Skype for Business Server Management Shell documentation at Insert introduction HERE.</span></span> 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a><span data-ttu-id="ee6c3-112">关于运行 Skype for Business Server 命令行管理程序脚本</span><span class="sxs-lookup"><span data-stu-id="ee6c3-112">About running Skype for Business Server management shell scripts</span></span>

<span data-ttu-id="ee6c3-113">我们正在提供可用于准备负载模拟的示例 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="ee6c3-113">We're providing sample PowerShell scripts you can use to prepare for your load simulations.</span></span> <span data-ttu-id="ee6c3-114">由于这些脚本是为进行负载模拟而设计的，因此您会发现它们非常简单且是可许可的。</span><span class="sxs-lookup"><span data-stu-id="ee6c3-114">Because these scripts are intended for load simulation, you'll find them to be simple and permissive.</span></span> <span data-ttu-id="ee6c3-115">这可能不适合您的生产环境。</span><span class="sxs-lookup"><span data-stu-id="ee6c3-115">That may not be appropriate for your production environment.</span></span> <span data-ttu-id="ee6c3-116">再次强调，这些脚本是示例，您需要对其进行检查，并且在很多情况下，在能够实用地使用您的环境之前对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="ee6c3-116">Again we stress that these scripts are samples, you'll need to review them and in many cases make changes relevant to your environment before being able to make practical use of them.</span></span> <span data-ttu-id="ee6c3-117">至少，我们预计您需要在您的拓扑中修改响应服务组（RSG）脚本（以指定分配给代理组的代理）。</span><span class="sxs-lookup"><span data-stu-id="ee6c3-117">At a minimum, we'd expect you'd need to modify the Response Service Group (RSG) script with your topology in mind (to specify the agents assigned to the agent groups).</span></span> <span data-ttu-id="ee6c3-118">但如果不需要，则无需运行该程序。</span><span class="sxs-lookup"><span data-stu-id="ee6c3-118">But you don't have to run that, if you don't need to.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="ee6c3-119">请注意查看和理解这些示例。</span><span class="sxs-lookup"><span data-stu-id="ee6c3-119">Please take care in reviewing and understanding these samples.</span></span> <span data-ttu-id="ee6c3-120">脚本将在运行时覆盖拓扑中的任何现有设置。</span><span class="sxs-lookup"><span data-stu-id="ee6c3-120">Scripts will overwrite any existing settings in the topology when run.</span></span> 
  
## <a name="stress-and-performance-tool-client-version-names"></a><span data-ttu-id="ee6c3-121">压力和性能工具客户端版本名称</span><span class="sxs-lookup"><span data-stu-id="ee6c3-121">Stress and Performance Tool client version names</span></span>

<span data-ttu-id="ee6c3-122">如果以前更改了默认值中的设置，则可能需要配置客户端版本检查策略。</span><span class="sxs-lookup"><span data-stu-id="ee6c3-122">You might need to configure the Client Version Check policy if you've previously changed the settings from the default values.</span></span> <span data-ttu-id="ee6c3-123">如果你不确定这一点，请查看[客户端版本检查文档](https://msdn.microsoft.com/vsto/jj923060)。</span><span class="sxs-lookup"><span data-stu-id="ee6c3-123">If you're unsure about this, check the [Client Version Check documentation](https://msdn.microsoft.com/vsto/jj923060).</span></span>
  
<span data-ttu-id="ee6c3-124">与 Skype for Business Server 2015 通信时，压力和性能工具默认使用以下用户代理版本：</span><span class="sxs-lookup"><span data-stu-id="ee6c3-124">The Stress and Performance Tool uses the following User Agent versions by default when communicating with Skype for Business Server 2015:</span></span>
  
- <span data-ttu-id="ee6c3-125">LSPT/15.0.0.0 （Skype for Business Server 2015 压力和性能工具）</span><span class="sxs-lookup"><span data-stu-id="ee6c3-125">LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)</span></span>
    
- <span data-ttu-id="ee6c3-126">OCPHONE/.0.522</span><span class="sxs-lookup"><span data-stu-id="ee6c3-126">OCPHONE/.0.522</span></span>
    
<span data-ttu-id="ee6c3-127">对于 LyncPerfTool 中的移动性（UCWA）客户端：</span><span class="sxs-lookup"><span data-stu-id="ee6c3-127">For the Mobility (UCWA) client in LyncPerfTool:</span></span>
  
- <span data-ttu-id="ee6c3-128">UCWA Perf 工具/Web 会议</span><span class="sxs-lookup"><span data-stu-id="ee6c3-128">UCWA Perf Tool/Web Conference</span></span>
    
- <span data-ttu-id="ee6c3-129">UCWA Perf 工具/移动</span><span class="sxs-lookup"><span data-stu-id="ee6c3-129">UCWA Perf Tool/Mobile</span></span>
    

