---
title: 'Skype for business Server 2019 的虚拟化支持 '
ms.reviewer: corbinm
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 06/04/2020
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 摘要：了解 Skype for business Server 2019 的虚拟化支持。
ms.openlocfilehash: edced9b0f884cbf76b224c9049cf3498c8f8b45c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509029"
---
# <a name="virtualization-support-for-skype-for-business-server-2019"></a><span data-ttu-id="6d68d-103">Skype for business Server 2019 的虚拟化支持</span><span class="sxs-lookup"><span data-stu-id="6d68d-103">Virtualization support for Skype for Business Server 2019</span></span>

<span data-ttu-id="6d68d-104">Skype for business Server 2019 在虚拟化中受支持。</span><span class="sxs-lookup"><span data-stu-id="6d68d-104">Skype for Business Server 2019 is supported on virtualization.</span></span>

<span data-ttu-id="6d68d-105">虽然虚拟化受支持，但有一些要点需要注意：</span><span class="sxs-lookup"><span data-stu-id="6d68d-105">While virtualization is supported, there are some key points to remember:</span></span>

- <span data-ttu-id="6d68d-106">将虚拟 CPU 的1:1 比率维护为物理 CPU。</span><span class="sxs-lookup"><span data-stu-id="6d68d-106">Maintain a 1:1 ratio of virtual CPU to physical CPU.</span></span>
- <span data-ttu-id="6d68d-107">请勿在来宾服务器运行时移动它。</span><span class="sxs-lookup"><span data-stu-id="6d68d-107">Don't move a guest server while it's operating.</span></span>
- <span data-ttu-id="6d68d-108">不支持迁移实时系统和虚拟机的可移植性。</span><span class="sxs-lookup"><span data-stu-id="6d68d-108">Migration of a live system and portability of a virtual machine aren't supported.</span></span>
- <span data-ttu-id="6d68d-109">在所有主机上禁用超线程。</span><span class="sxs-lookup"><span data-stu-id="6d68d-109">Disable hyper-threading on all hosts.</span></span>
- <span data-ttu-id="6d68d-110">不要在主机服务器上配置动态内存。</span><span class="sxs-lookup"><span data-stu-id="6d68d-110">Don't configure dynamic memory on host servers.</span></span>
- <span data-ttu-id="6d68d-111">使用固定磁盘或传递磁盘，而不是动态磁盘。</span><span class="sxs-lookup"><span data-stu-id="6d68d-111">Use fixed or pass-through disks rather than dynamic disks.</span></span>
- <span data-ttu-id="6d68d-112">允许不超过虚拟来宾所需的虚拟机监控程序6-10% 的开销。</span><span class="sxs-lookup"><span data-stu-id="6d68d-112">Allow for 6-10 percent overhead for hypervisors beyond what the virtual guest requires.</span></span>

## <a name="supported-hypervisors"></a><span data-ttu-id="6d68d-113">支持的虚拟机监控程序</span><span class="sxs-lookup"><span data-stu-id="6d68d-113">Supported hypervisors</span></span>

<span data-ttu-id="6d68d-114">Windows Server 2016 和 Windows Server 2019 支持 SfB Server 2019。</span><span class="sxs-lookup"><span data-stu-id="6d68d-114">SfB Server 2019 is supported on Windows Server 2016 and Windows Server 2019.</span></span>

<span data-ttu-id="6d68d-115">对于第三方虚拟机管理程序，您需要一个已通过服务器虚拟化验证程序的虚拟机监控程序 (SVVP) 测试相关操作系统。</span><span class="sxs-lookup"><span data-stu-id="6d68d-115">For third-party hypervisors, you need a hypervisor that has passed the Server Virtualization Validation Program (SVVP) testing for the relevant OS.</span></span>

- <span data-ttu-id="6d68d-116">请参阅 SVVP 列表中的 [Windows Server 2016 版本](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) 。</span><span class="sxs-lookup"><span data-stu-id="6d68d-116">See the [Windows Server 2016 versions](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) in the SVVP list.</span></span>
- <span data-ttu-id="6d68d-117">请参阅 SVVP 列表中的 [Windows Server 2019 版本](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) 。</span><span class="sxs-lookup"><span data-stu-id="6d68d-117">See the [Windows Server 2019 versions](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) in the SVVP list.</span></span>

## <a name="stress-and-performance-tool"></a><span data-ttu-id="6d68d-118">压力和性能工具</span><span class="sxs-lookup"><span data-stu-id="6d68d-118">Stress and performance tool</span></span>

<span data-ttu-id="6d68d-119">Skype for Business Server 2019 压力和性能工具包括简化 Skype for business Server 2019 容量规划的工具。</span><span class="sxs-lookup"><span data-stu-id="6d68d-119">The Skype for Business Server 2019 Stress and Performance Tool includes tools that simplify capacity planning for Skype for Business Server 2019.</span></span> <span data-ttu-id="6d68d-120">Skype for Business Server 2019 的压力和性能工具将帮助你执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6d68d-120">The Skype for Business Server 2019 Stress and Performance Tool will help you to:</span></span>

- <span data-ttu-id="6d68d-121">简化对 Skype for Business Server 2019 的硬件规划</span><span class="sxs-lookup"><span data-stu-id="6d68d-121">Simplify your hardware planning for Skype for Business Server 2019</span></span>
- <span data-ttu-id="6d68d-122">为您提供更多的知识和最佳做法以优化性能</span><span class="sxs-lookup"><span data-stu-id="6d68d-122">Provide you with increased knowledge and best practices for performance tuning</span></span>
- <span data-ttu-id="6d68d-123">衡量预期的 Skype for business Server 2019 部署的性能</span><span class="sxs-lookup"><span data-stu-id="6d68d-123">Measure the performance of your intended Skype for Business Server 2019 deployments</span></span>
 
<span data-ttu-id="6d68d-124">您可以从 [此处](https://www.microsoft.com/download/details.aspx?id=101447)下载该工具。</span><span class="sxs-lookup"><span data-stu-id="6d68d-124">You can download the tool from [here](https://www.microsoft.com/download/details.aspx?id=101447).</span></span>
