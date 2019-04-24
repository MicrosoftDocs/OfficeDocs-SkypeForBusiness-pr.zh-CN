---
title: 为业务服务器 2015年压力和性能工具 Skype 的性能方案
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.date: 12/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: 您需要执行的操作配置的业务服务器 2015 执行性能和负载测试的 Skype 使用压力和性能工具的任务。
ms.openlocfilehash: 53504b714304b4b3cd18e44397ce0f06fcc59b63
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32194616"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="86c8a-103">为业务服务器 2015年压力和性能工具 Skype 的性能方案</span><span class="sxs-lookup"><span data-stu-id="86c8a-103">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="86c8a-104">您需要执行的操作配置的业务服务器 2015 执行性能和负载测试的 Skype 使用压力和性能工具的任务。</span><span class="sxs-lookup"><span data-stu-id="86c8a-104">Tasks you'll need to do to configure Skype for Business Server 2015 to do performance and load-testing, using the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="86c8a-105">若要运行的业务 Server 2015 压力和性能工具 (LyncPerfTool) Skype，必须首先配置方案与您相关业务服务器 2015年拓扑的 Skype。</span><span class="sxs-lookup"><span data-stu-id="86c8a-105">To run the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool), the Skype for Business Server 2015 topology must first be configured for scenarios relevant to you.</span></span> <span data-ttu-id="86c8a-106">如果业务服务器 2015年的 Skype 未配置，或配置不正确，负载模拟为很有可能会失败。</span><span class="sxs-lookup"><span data-stu-id="86c8a-106">If Skype for Business Server 2015 isn't configured, or is configured incorrectly, your load simulation is very likely to fail.</span></span> <span data-ttu-id="86c8a-107">与业务 Server 2015 压力和性能工具 Skype，我们提供示例 Skype 的业务 Server 命令行管理程序脚本和基本资源文件作为[工具下载](https://www.microsoft.com/download/details.aspx?id=50367)的一部分。</span><span class="sxs-lookup"><span data-stu-id="86c8a-107">With the Skype for Business Server 2015 Stress and Performance Tool, we're providing example Skype for Business Server Management Shell scripts and basic resource files as part of the [tool download](https://www.microsoft.com/download/details.aspx?id=50367).</span></span> <span data-ttu-id="86c8a-108">这些可作为起点用于配置您 Skype 业务服务器部署。</span><span class="sxs-lookup"><span data-stu-id="86c8a-108">These can be used as a starting point for configuring your Skype for Business Server deployment.</span></span> <span data-ttu-id="86c8a-109">本文介绍提供的 Windows PowerShell 示例。</span><span class="sxs-lookup"><span data-stu-id="86c8a-109">This article describes the Windows PowerShell examples provided.</span></span>
  
> [!NOTE]
> <span data-ttu-id="86c8a-110">本主题不能帮助您介绍如何配置 Business Server 2015 通常 Skype，我们，必须规划和部署的其他主题。</span><span class="sxs-lookup"><span data-stu-id="86c8a-110">This topic won't help you describe how to configure Skype for Business Server 2015 generally, we have other Planning and Deployment topics for that.</span></span> <span data-ttu-id="86c8a-111">有关使用的业务服务器 2015 Skype 中的 Windows PowerShell 的详细信息，请参阅在此处插入简介业务 Server Management Shell 文档 Skype。</span><span class="sxs-lookup"><span data-stu-id="86c8a-111">For details about working with Windows PowerShell in Skype for Business Server 2015, see the Skype for Business Server Management Shell documentation at Insert introduction HERE.</span></span> 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a><span data-ttu-id="86c8a-112">有关运行 Skype 业务服务器管理命令行管理程序脚本</span><span class="sxs-lookup"><span data-stu-id="86c8a-112">About running Skype for Business Server management shell scripts</span></span>

<span data-ttu-id="86c8a-113">我们提供您可用来准备负载模拟的示例 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="86c8a-113">We're providing sample PowerShell scripts you can use to prepare for your load simulations.</span></span> <span data-ttu-id="86c8a-114">因为这些脚本供负载模拟，您会发现他们能够简单和宽松。</span><span class="sxs-lookup"><span data-stu-id="86c8a-114">Because these scripts are intended for load simulation, you'll find them to be simple and permissive.</span></span> <span data-ttu-id="86c8a-115">这可能不适合您的生产环境。</span><span class="sxs-lookup"><span data-stu-id="86c8a-115">That may not be appropriate for your production environment.</span></span> <span data-ttu-id="86c8a-116">再次我们压力，这些脚本示例，您需要其进行复查并在许多情况下进行更改与环境相关能够实际利用这些之前。</span><span class="sxs-lookup"><span data-stu-id="86c8a-116">Again we stress that these scripts are samples, you'll need to review them and in many cases make changes relevant to your environment before being able to make practical use of them.</span></span> <span data-ttu-id="86c8a-117">至少，我们期望需要修改与您的拓扑记住 （用于指定代理分配到代理组） 的响应组服务 (RSG) 脚本。</span><span class="sxs-lookup"><span data-stu-id="86c8a-117">At a minimum, we'd expect you'd need to modify the Response Service Group (RSG) script with your topology in mind (to specify the agents assigned to the agent groups).</span></span> <span data-ttu-id="86c8a-118">但是，您无需运行，如果您不需要。</span><span class="sxs-lookup"><span data-stu-id="86c8a-118">But you don't have to run that, if you don't need to.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="86c8a-119">请注意中查看和了解这些示例。</span><span class="sxs-lookup"><span data-stu-id="86c8a-119">Please take care in reviewing and understanding these samples.</span></span> <span data-ttu-id="86c8a-120">脚本将覆盖运行时的拓扑中的任何现有的设置。</span><span class="sxs-lookup"><span data-stu-id="86c8a-120">Scripts will overwrite any existing settings in the topology when run.</span></span> 
  
## <a name="stress-and-performance-tool-client-version-names"></a><span data-ttu-id="86c8a-121">压力和性能工具客户端版本名称</span><span class="sxs-lookup"><span data-stu-id="86c8a-121">Stress and Performance Tool client version names</span></span>

<span data-ttu-id="86c8a-122">您可能需要配置客户端版本检查策略，如果您先前已更改设置的默认值。</span><span class="sxs-lookup"><span data-stu-id="86c8a-122">You might need to configure the Client Version Check policy if you've previously changed the settings from the default values.</span></span> <span data-ttu-id="86c8a-123">如果您不确定有关此，检查[客户端版本检查的文档](https://msdn.microsoft.com/en-us/vsto/jj923060)。</span><span class="sxs-lookup"><span data-stu-id="86c8a-123">If you're unsure about this, check the [Client Version Check documentation](https://msdn.microsoft.com/en-us/vsto/jj923060).</span></span>
  
<span data-ttu-id="86c8a-124">压力和性能工具默认情况下使用以下的用户代理版本与 Skype 的业务服务器 2015年通信时：</span><span class="sxs-lookup"><span data-stu-id="86c8a-124">The Stress and Performance Tool uses the following User Agent versions by default when communicating with Skype for Business Server 2015:</span></span>
  
- <span data-ttu-id="86c8a-125">LSPT/15.0.0.0 (Skype 的业务服务器 2015年压力和性能工具)</span><span class="sxs-lookup"><span data-stu-id="86c8a-125">LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)</span></span>
    
- <span data-ttu-id="86c8a-126">OCPHONE/.0.522</span><span class="sxs-lookup"><span data-stu-id="86c8a-126">OCPHONE/.0.522</span></span>
    
<span data-ttu-id="86c8a-127">LyncPerfTool 中移动 (UCWA) 客户端：</span><span class="sxs-lookup"><span data-stu-id="86c8a-127">For the Mobility (UCWA) client in LyncPerfTool:</span></span>
  
- <span data-ttu-id="86c8a-128">UCWA 性能工具/Web 会议</span><span class="sxs-lookup"><span data-stu-id="86c8a-128">UCWA Perf Tool/Web Conference</span></span>
    
- <span data-ttu-id="86c8a-129">UCWA 性能工具/移动</span><span class="sxs-lookup"><span data-stu-id="86c8a-129">UCWA Perf Tool/Mobile</span></span>
    

