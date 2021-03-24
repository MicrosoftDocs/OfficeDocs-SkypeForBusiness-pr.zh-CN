---
title: Skype for Business Server 2015 压力和性能工具的性能方案
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 使用压力和性能工具配置 Skype for Business Server 2015 以执行性能和负载测试需要执行的任务。
ms.openlocfilehash: e0a3cc3767cf7652bda9bfacb14ced6632e32d87
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105368"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="ee447-103">Skype for Business Server 2015 压力和性能工具的性能方案</span><span class="sxs-lookup"><span data-stu-id="ee447-103">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="ee447-104">使用压力和性能工具配置 Skype for Business Server 2015 以执行性能和负载测试需要执行的任务。</span><span class="sxs-lookup"><span data-stu-id="ee447-104">Tasks you'll need to do to configure Skype for Business Server 2015 to do performance and load-testing, using the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="ee447-105">若要运行 Skype for Business Server 2015 压力和性能工具 (LyncPerfTool) ，必须先针对与您相关的方案配置 Skype for Business Server 2015 拓扑。</span><span class="sxs-lookup"><span data-stu-id="ee447-105">To run the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool), the Skype for Business Server 2015 topology must first be configured for scenarios relevant to you.</span></span> <span data-ttu-id="ee447-106">如果未配置 Skype for Business Server 2015 或配置不正确，则你的负载模拟很可能失败。</span><span class="sxs-lookup"><span data-stu-id="ee447-106">If Skype for Business Server 2015 isn't configured, or is configured incorrectly, your load simulation is very likely to fail.</span></span> <span data-ttu-id="ee447-107">使用 Skype for Business Server 2015 压力和性能工具，我们提供了示例 Skype for Business Server 命令行管理程序脚本和基本资源文件作为工具下载的一 [部分](https://www.microsoft.com/download/details.aspx?id=50367)。</span><span class="sxs-lookup"><span data-stu-id="ee447-107">With the Skype for Business Server 2015 Stress and Performance Tool, we're providing example Skype for Business Server Management Shell scripts and basic resource files as part of the [tool download](https://www.microsoft.com/download/details.aspx?id=50367).</span></span> <span data-ttu-id="ee447-108">它们可用作配置 Skype for Business Server 部署的起点。</span><span class="sxs-lookup"><span data-stu-id="ee447-108">These can be used as a starting point for configuring your Skype for Business Server deployment.</span></span> <span data-ttu-id="ee447-109">本文介绍Windows PowerShell的示例。</span><span class="sxs-lookup"><span data-stu-id="ee447-109">This article describes the Windows PowerShell examples provided.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ee447-110">本主题通常不会帮助你介绍如何配置 Skype for Business Server 2015，我们还有其他有关规划和部署的主题。</span><span class="sxs-lookup"><span data-stu-id="ee447-110">This topic won't help you describe how to configure Skype for Business Server 2015 generally, we have other Planning and Deployment topics for that.</span></span> <span data-ttu-id="ee447-111">有关在 Skype for Business Server 2015 中使用 Windows PowerShell 的详细信息，请参阅插入简介 HERE 中的 Skype for Business Server 命令行管理程序文档。</span><span class="sxs-lookup"><span data-stu-id="ee447-111">For details about working with Windows PowerShell in Skype for Business Server 2015, see the Skype for Business Server Management Shell documentation at Insert introduction HERE.</span></span> 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a><span data-ttu-id="ee447-112">关于运行 Skype for Business Server 命令行管理程序脚本</span><span class="sxs-lookup"><span data-stu-id="ee447-112">About running Skype for Business Server management shell scripts</span></span>

<span data-ttu-id="ee447-113">我们提供了可用于准备负载模拟的示例 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="ee447-113">We're providing sample PowerShell scripts you can use to prepare for your load simulations.</span></span> <span data-ttu-id="ee447-114">由于这些脚本旨在进行负载模拟，因此你会发现它们简单和宽松。</span><span class="sxs-lookup"><span data-stu-id="ee447-114">Because these scripts are intended for load simulation, you'll find them to be simple and permissive.</span></span> <span data-ttu-id="ee447-115">这可能不适合您的生产环境。</span><span class="sxs-lookup"><span data-stu-id="ee447-115">That may not be appropriate for your production environment.</span></span> <span data-ttu-id="ee447-116">我们再次强调，这些脚本是示例，你需要查看它们，并且在许多情况下，需要先对环境进行更改，然后才能实际使用它们。</span><span class="sxs-lookup"><span data-stu-id="ee447-116">Again we stress that these scripts are samples, you'll need to review them and in many cases make changes relevant to your environment before being able to make practical use of them.</span></span> <span data-ttu-id="ee447-117">我们预计您至少需要修改响应服务组 (RSG) 脚本，同时记住拓扑 (以指定分配给代理组) 的代理。</span><span class="sxs-lookup"><span data-stu-id="ee447-117">At a minimum, we'd expect you'd need to modify the Response Service Group (RSG) script with your topology in mind (to specify the agents assigned to the agent groups).</span></span> <span data-ttu-id="ee447-118">但是，如果不需要，则无需运行它。</span><span class="sxs-lookup"><span data-stu-id="ee447-118">But you don't have to run that, if you don't need to.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="ee447-119">请谨慎查看和了解这些示例。</span><span class="sxs-lookup"><span data-stu-id="ee447-119">Please take care in reviewing and understanding these samples.</span></span> <span data-ttu-id="ee447-120">脚本将在运行时覆盖拓扑中任何现有设置。</span><span class="sxs-lookup"><span data-stu-id="ee447-120">Scripts will overwrite any existing settings in the topology when run.</span></span> 
  
## <a name="stress-and-performance-tool-client-version-names"></a><span data-ttu-id="ee447-121">压力和性能工具客户端版本名称</span><span class="sxs-lookup"><span data-stu-id="ee447-121">Stress and Performance Tool client version names</span></span>

<span data-ttu-id="ee447-122">如果之前更改了默认值的设置，可能需要配置客户端版本检查策略。</span><span class="sxs-lookup"><span data-stu-id="ee447-122">You might need to configure the Client Version Check policy if you've previously changed the settings from the default values.</span></span> <span data-ttu-id="ee447-123">如果你不确定这一点，请查看客户端 [版本检查文档](/previous-versions/office/lync-server-2013/lync-server-2013-view-client-version-policy-rules)。</span><span class="sxs-lookup"><span data-stu-id="ee447-123">If you're unsure about this, check the [Client Version Check documentation](/previous-versions/office/lync-server-2013/lync-server-2013-view-client-version-policy-rules).</span></span>
  
<span data-ttu-id="ee447-124">与 Skype for Business Server 2015 通信时，压力和性能工具默认使用下列用户代理版本：</span><span class="sxs-lookup"><span data-stu-id="ee447-124">The Stress and Performance Tool uses the following User Agent versions by default when communicating with Skype for Business Server 2015:</span></span>
  
- <span data-ttu-id="ee447-125">LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool) </span><span class="sxs-lookup"><span data-stu-id="ee447-125">LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)</span></span>
    
- <span data-ttu-id="ee447-126">OCPHONE/.0.522</span><span class="sxs-lookup"><span data-stu-id="ee447-126">OCPHONE/.0.522</span></span>
    
<span data-ttu-id="ee447-127">对于 LyncPerfTool (移动) UCWA 客户端：</span><span class="sxs-lookup"><span data-stu-id="ee447-127">For the Mobility (UCWA) client in LyncPerfTool:</span></span>
  
- <span data-ttu-id="ee447-128">UCWA Perf 工具/Web 会议</span><span class="sxs-lookup"><span data-stu-id="ee447-128">UCWA Perf Tool/Web Conference</span></span>
    
- <span data-ttu-id="ee447-129">UCWA Perf 工具/移动</span><span class="sxs-lookup"><span data-stu-id="ee447-129">UCWA Perf Tool/Mobile</span></span>
