---
title: 为业务服务器 2015年的压力和性能工具 Skype 的性能情况
ms.author: heidip
author: microsoftheidi
ms.date: 12/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: 您将需要执行配置 Skype 的业务服务器 2015 做性能和负载测试使用的压力和性能工具的任务。
ms.openlocfilehash: 6b60d403e0a440e544874a8ed877a0b98e3e92ae
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="854b3-103">为业务服务器 2015年的压力和性能工具 Skype 的性能情况</span><span class="sxs-lookup"><span data-stu-id="854b3-103">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="854b3-104">您将需要执行配置 Skype 的业务服务器 2015 做性能和负载测试使用的压力和性能工具的任务。</span><span class="sxs-lookup"><span data-stu-id="854b3-104">Tasks you'll need to do to configure Skype for Business Server 2015 to do performance and load-testing, using the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="854b3-105">若要运行 Skype 业务服务器 2015年的压力和性能工具 (LyncPerfTool)，必须首先配置方案与您相关业务服务器 2015年拓扑 Skype。</span><span class="sxs-lookup"><span data-stu-id="854b3-105">To run the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool), the Skype for Business Server 2015 topology must first be configured for scenarios relevant to you.</span></span> <span data-ttu-id="854b3-106">如果业务服务器 2015年的 Skype 不配置，或配置不正确，负载模拟是非常失败的可能性。</span><span class="sxs-lookup"><span data-stu-id="854b3-106">If Skype for Business Server 2015 isn't configured, or is configured incorrectly, your load simulation is very likely to fail.</span></span> <span data-ttu-id="854b3-107">具有的业务服务器 2015年压力和性能工具 Skype，我们提供的示例 Skype 业务服务器管理 Shell 脚本和基本资源文件作为[工具下载](https://www.microsoft.com/download/details.aspx?id=50367)的一部分。</span><span class="sxs-lookup"><span data-stu-id="854b3-107">With the Skype for Business Server 2015 Stress and Performance Tool, we're providing example Skype for Business Server Management Shell scripts and basic resource files as part of the [tool download](https://www.microsoft.com/download/details.aspx?id=50367).</span></span> <span data-ttu-id="854b3-108">这些可作为起始点来配置您的 Skype 业务服务器部署。</span><span class="sxs-lookup"><span data-stu-id="854b3-108">These can be used as a starting point for configuring your Skype for Business Server deployment.</span></span> <span data-ttu-id="854b3-109">本文介绍了提供的 Windows PowerShell 示例。</span><span class="sxs-lookup"><span data-stu-id="854b3-109">This article describes the Windows PowerShell examples provided.</span></span>
  
> [!NOTE]
> <span data-ttu-id="854b3-110">本主题不能帮助您介绍了如何配置 Skype 业务服务器 2015年通常，我们该有的规划和部署的其他主题。</span><span class="sxs-lookup"><span data-stu-id="854b3-110">This topic won't help you describe how to configure Skype for Business Server 2015 generally, we have other Planning and Deployment topics for that.</span></span> <span data-ttu-id="854b3-111">有关使用 Windows PowerShell 在 Skype 的业务服务器 2015年的详细信息，请参阅在此处插入介绍业务服务器管理外壳程序文档用于 Skype。</span><span class="sxs-lookup"><span data-stu-id="854b3-111">For details about working with Windows PowerShell in Skype for Business Server 2015, see the Skype for Business Server Management Shell documentation at Insert introduction HERE.</span></span> 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a><span data-ttu-id="854b3-112">有关运行 Skype 业务服务器管理外壳脚本</span><span class="sxs-lookup"><span data-stu-id="854b3-112">About running Skype for Business Server management shell scripts</span></span>

<span data-ttu-id="854b3-113">我们提供的示例 PowerShell 脚本可用来准备您的负载模拟。</span><span class="sxs-lookup"><span data-stu-id="854b3-113">We're providing sample PowerShell scripts you can use to prepare for your load simulations.</span></span> <span data-ttu-id="854b3-114">因为这些脚本适用于负载模拟，您会发现它们是简单和宽松。</span><span class="sxs-lookup"><span data-stu-id="854b3-114">Because these scripts are intended for load simulation, you'll find them to be simple and permissive.</span></span> <span data-ttu-id="854b3-115">这可能不适合您的生产环境。</span><span class="sxs-lookup"><span data-stu-id="854b3-115">That may not be appropriate for your production environment.</span></span> <span data-ttu-id="854b3-116">我们再次强调，这些脚本示例，您将需要查看它们并在许多情况下进行的更改与您的环境相关后才能实际使用。</span><span class="sxs-lookup"><span data-stu-id="854b3-116">Again we stress that these scripts are samples, you'll need to review them and in many cases make changes relevant to your environment before being able to make practical use of them.</span></span> <span data-ttu-id="854b3-117">至少我们希望如此需要修改带有一点 （可以指定分配给代理组的代理） 拓扑结构的响应服务组 (RSG) 脚本。</span><span class="sxs-lookup"><span data-stu-id="854b3-117">At a minimum, we'd expect you'd need to modify the Response Service Group (RSG) script with your topology in mind (to specify the agents assigned to the agent groups).</span></span> <span data-ttu-id="854b3-118">但是，您不需要运行的如果不需要。</span><span class="sxs-lookup"><span data-stu-id="854b3-118">But you don't have to run that, if you don't need to.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="854b3-119">请小心地查看并理解这些示例。</span><span class="sxs-lookup"><span data-stu-id="854b3-119">Please take care in reviewing and understanding these samples.</span></span> <span data-ttu-id="854b3-120">脚本将覆盖任何现有设置运行时拓扑中。</span><span class="sxs-lookup"><span data-stu-id="854b3-120">Scripts will overwrite any existing settings in the topology when run.</span></span> 
  
## <a name="stress-and-performance-tool-client-version-names"></a><span data-ttu-id="854b3-121">压力和性能工具的客户端版本名称</span><span class="sxs-lookup"><span data-stu-id="854b3-121">Stress and Performance Tool client version names</span></span>

<span data-ttu-id="854b3-122">您可能需要配置客户端版本检查策略，如果您以前已从默认值更改设置。</span><span class="sxs-lookup"><span data-stu-id="854b3-122">You might need to configure the Client Version Check policy if you've previously changed the settings from the default values.</span></span> <span data-ttu-id="854b3-123">如果您不确定有关此，检查[客户端版本检查文档](https://msdn.microsoft.com/en-us/vsto/jj923060)。</span><span class="sxs-lookup"><span data-stu-id="854b3-123">If you're unsure about this, check the [Client Version Check documentation](https://msdn.microsoft.com/en-us/vsto/jj923060).</span></span>
  
<span data-ttu-id="854b3-124">压力和性能工具默认使用以下用户代理版本与 Skype 通信的业务服务器 2015年时：</span><span class="sxs-lookup"><span data-stu-id="854b3-124">The Stress and Performance Tool uses the following User Agent versions by default when communicating with Skype for Business Server 2015:</span></span>
  
- <span data-ttu-id="854b3-125">LSPT/15.0.0.0 (Skype 业务服务器 2015年的压力和性能工具)</span><span class="sxs-lookup"><span data-stu-id="854b3-125">LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)</span></span>
    
- <span data-ttu-id="854b3-126">OCPHONE/.0.522</span><span class="sxs-lookup"><span data-stu-id="854b3-126">OCPHONE/.0.522</span></span>
    
<span data-ttu-id="854b3-127">在 LyncPerfTool 行动 (UCWA) 客户端：</span><span class="sxs-lookup"><span data-stu-id="854b3-127">For the Mobility (UCWA) client in LyncPerfTool:</span></span>
  
- <span data-ttu-id="854b3-128">UCWA 性能工具/网络会议</span><span class="sxs-lookup"><span data-stu-id="854b3-128">UCWA Perf Tool/Web Conference</span></span>
    
- <span data-ttu-id="854b3-129">UCWA 性能工具/移动</span><span class="sxs-lookup"><span data-stu-id="854b3-129">UCWA Perf Tool/Mobile</span></span>
    

