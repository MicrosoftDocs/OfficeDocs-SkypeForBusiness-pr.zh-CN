---
title: Lync Server 2013 可伸缩性测试
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scalability testing
ms:assetid: bf41bac6-d4ec-4de6-9a44-a82d01a87279
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205226(v=OCS.15)
ms:contentKeyID: 48185289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41e23cd1bf0382a392cba951d90cd9dfa80c4880
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511009"
---
# <a name="scalability-testing-in-lync-server-2013"></a><span data-ttu-id="85abe-102">Lync Server 2013 中的可伸缩性测试</span><span class="sxs-lookup"><span data-stu-id="85abe-102">Scalability testing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85abe-103">_**上次修改的主题：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="85abe-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="85abe-104">Lync Server 2013 为所有 Lync Server 实时通信（包括即时消息 (IM) 和状态、会议和企业语音）提供服务器基础结构。</span><span class="sxs-lookup"><span data-stu-id="85abe-104">Lync Server 2013 provides the server infrastructure for all Lync Server real-time communications, including instant messaging (IM) and presence, conferencing, and Enterprise Voice.</span></span> <span data-ttu-id="85abe-105">这包括使用 Lync Server 2013 池的硬件资源的所有功能，因此会影响性能和规模。</span><span class="sxs-lookup"><span data-stu-id="85abe-105">This includes any features that use the hardware resources of a Lync Server 2013 pool and, therefore, affect performance and scale.</span></span> <span data-ttu-id="85abe-106">所有组织并非均衡地使用所有功能。</span><span class="sxs-lookup"><span data-stu-id="85abe-106">All organizations do not use all features equally.</span></span>

<span data-ttu-id="85abe-107">例如，有些组织可能在会议中非常大量地使用视频，而其他组织的视频使用率可能很小或没有。</span><span class="sxs-lookup"><span data-stu-id="85abe-107">For example, some organizations might use video in conferences very heavily while others might have little or no video usage.</span></span> <span data-ttu-id="85abe-108">有些组织喜欢 PowerPoint 幻灯片共享而不喜欢应用程序共享，而其他组织的喜好则相反。</span><span class="sxs-lookup"><span data-stu-id="85abe-108">Some organizations prefer PowerPoint slide sharing to application sharing, while others prefer the opposite.</span></span> <span data-ttu-id="85abe-109">部署企业语音的组织可能会或不会频繁使用响应组应用程序。</span><span class="sxs-lookup"><span data-stu-id="85abe-109">Those organizations that deploy Enterprise Voice might or might not use the Response Group application heavily.</span></span> <span data-ttu-id="85abe-110">大多数组织都部署监控服务器，但不是许多部署存档服务器。</span><span class="sxs-lookup"><span data-stu-id="85abe-110">Most organizations deploy Monitoring Servers, but not many of them deploy Archiving Servers.</span></span> <span data-ttu-id="85abe-111">此外，并非所有组织都具有相同的基础结构，包括硬件容量、网络容量，以及所部署的池数目和池的规模。</span><span class="sxs-lookup"><span data-stu-id="85abe-111">Additionally, organizations do not all have the same infrastructures, including hardware capacities, network capacities, and the number of pools and size of pools deployed.</span></span> <span data-ttu-id="85abe-112">功能和基础结构的多样性为可伸缩性测试带来了挑战 – 无法模拟功能和基础结构的所有可能组合。</span><span class="sxs-lookup"><span data-stu-id="85abe-112">The diversity of features and infrastructures poses a challenge to scalability testing – it is not possible to simulate all possible combinations of features and infrastructures.</span></span>

<span data-ttu-id="85abe-113">为确定 Lync Server 的可伸缩性支持，我们将根据平均使用率模型 (用户模型) ，以并发方式使用所有 Lync Server 功能进行测试。</span><span class="sxs-lookup"><span data-stu-id="85abe-113">To determine scalability support for Lync Server, we conduct testing by using all Lync Server features concurrently, based on an average usage model (user model).</span></span> <span data-ttu-id="85abe-114">为了确定适用于 Lync Server 工作负荷的用户模型，我们分析了许多数据点，包括客户调查、Microsoft 客户体验改善计划的反馈、Microsoft 内部 IT 部门的 Lync Server 使用情况数据，以及从 Live Meeting 服务中挖掘的数据。</span><span class="sxs-lookup"><span data-stu-id="85abe-114">To determine an appropriate user model for Lync Server workloads, we analyze many data points, including customer surveys, feedback from the Microsoft customer experience improvement program, Lync Server usage data from the internal IT department at Microsoft, and data mined from our Live Meeting Service.</span></span> <span data-ttu-id="85abe-115">在许多情况下，用户模型都偏向于更大的负载，以便为在组织中使用提供充裕的余量。</span><span class="sxs-lookup"><span data-stu-id="85abe-115">In many cases, the user model has a bias towards heavier loads to provide a comfortable margin for usage within an organization.</span></span>

<span data-ttu-id="85abe-116">在我们的可伸缩性测试中，我们根据建议的硬件和软件规范（包括基础结构组件，如 Active Directory 域服务、硬件负载平衡器和防火墙）设置 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="85abe-116">In our scalability tests, we set up Lync Server 2013 pools according to the recommended hardware and software specifications, including infrastructure components, such as Active Directory Domain Services, hardware load balancers, and firewalls.</span></span> <span data-ttu-id="85abe-117">我们将 Lync Server 环境尽可能与典型的实际环境紧密建立。</span><span class="sxs-lookup"><span data-stu-id="85abe-117">We set up Lync Server environments as closely as possible to typical real-world environments.</span></span> <span data-ttu-id="85abe-118">然后，使用 Lync Server 2013 压力和性能工具模拟 Lync Server 2013 加载 (基于我们的用户模型) 。</span><span class="sxs-lookup"><span data-stu-id="85abe-118">We then use the Lync Server 2013 Stress and Performance Tool to simulate Lync Server 2013 loads (based on our user model).</span></span> <span data-ttu-id="85abe-119">.</span><span class="sxs-lookup"><span data-stu-id="85abe-119">.</span></span>

<span data-ttu-id="85abe-p105">我们多次反复执行可伸缩性测试（包括多次为期三周的测试运行）。同时利用所有测试结果帮助进行性能调整并确认支持用户模型中的可伸缩数目。</span><span class="sxs-lookup"><span data-stu-id="85abe-p105">We do multiple iterations of scalability tests (including multiple three-week test runs). We use the results of all tests to help with performance tuning and to verify support for the scalability numbers in our user model.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

