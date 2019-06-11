---
title: 'Lync Server 2013: 最佳做法分析器概述'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of Best Practices Analyzer
ms:assetid: c5fcaa05-eb1c-4092-90ad-177b127e795b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591349(v=OCS.15)
ms:contentKeyID: 48185364
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a304f33071b8be13c61c3f930f196113ac3af6de
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825686"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="37c34-102">Lync Server 2013 中的最佳做法分析器概述</span><span class="sxs-lookup"><span data-stu-id="37c34-102">Overview of Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37c34-103">_**主题上次修改时间:** 2012-09-19_</span><span class="sxs-lookup"><span data-stu-id="37c34-103">_**Topic Last Modified:** 2012-09-19_</span></span>

<span data-ttu-id="37c34-104">你可以使用 Lync Server 2013、最佳做法分析器识别和解决 Lync Server 2013 部署问题。</span><span class="sxs-lookup"><span data-stu-id="37c34-104">You can use Lync Server 2013, Best Practices Analyzer to identify and resolve problems with your Lync Server 2013 deployment.</span></span> <span data-ttu-id="37c34-105">Lync Server 2013, 最佳做法分析器从 Lync Server 2013 组件收集配置信息。</span><span class="sxs-lookup"><span data-stu-id="37c34-105">The Lync Server 2013, Best Practices Analyzer gathers configuration information from Lync Server 2013 components.</span></span>

<span data-ttu-id="37c34-106">使用正确的网络访问, 最佳做法分析器可以检查运行 Active Directory 域服务、Exchange Server 统一消息 (UM) 和 Lync Server 2013 的服务器。</span><span class="sxs-lookup"><span data-stu-id="37c34-106">With the proper network access, the Best Practices Analyzer can examine servers running Active Directory Domain Services, Exchange Server Unified Messaging (UM), and Lync Server 2013.</span></span> <span data-ttu-id="37c34-107">可以使用最佳做法分析程序执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="37c34-107">You can use Best Practices Analyzer to do the following:</span></span>

  - <span data-ttu-id="37c34-108">主动执行检查, 验证是否根据推荐的最佳做法设置了配置。</span><span class="sxs-lookup"><span data-stu-id="37c34-108">Proactively perform checks, verifying that the configuration is set according to recommended best practices.</span></span>

  - <span data-ttu-id="37c34-109">自动检测 Lync Server 2013 所需的更新。</span><span class="sxs-lookup"><span data-stu-id="37c34-109">Automatically detect required updates to Lync Server 2013.</span></span>

  - <span data-ttu-id="37c34-110">生成问题列表, 例如不推荐的配置设置、不支持的选项、缺少的更新或不推荐的做法。</span><span class="sxs-lookup"><span data-stu-id="37c34-110">Generate a list of issues, such as suboptimal configuration settings, unsupported options, missing updates, or practices that we do not recommend.</span></span>

  - <span data-ttu-id="37c34-111">帮助你解决和解决特定问题。</span><span class="sxs-lookup"><span data-stu-id="37c34-111">Help you troubleshoot and fix specific problems.</span></span>

<span data-ttu-id="37c34-112">最佳做法分析器提供以下功能:</span><span class="sxs-lookup"><span data-stu-id="37c34-112">Best Practices Analyzer provides the following features:</span></span>

  - <span data-ttu-id="37c34-113">最低安装必备条件。</span><span class="sxs-lookup"><span data-stu-id="37c34-113">Minimal installation prerequisites.</span></span>

  - <span data-ttu-id="37c34-114">有关报告的问题 (包括疑难解答提示) 的联机文档。</span><span class="sxs-lookup"><span data-stu-id="37c34-114">Online documentation about reported issues, including troubleshooting tips.</span></span>

  - <span data-ttu-id="37c34-115">可以保存供以后查看的配置信息。</span><span class="sxs-lookup"><span data-stu-id="37c34-115">Configuration information that you can save for later review.</span></span>

  - <span data-ttu-id="37c34-116">一流的系统分析。</span><span class="sxs-lookup"><span data-stu-id="37c34-116">State-of-the-art system analysis.</span></span>

<span data-ttu-id="37c34-117">最佳做法分析器使用一组 XML 配置文件来确定要从 Lync Server 2013 环境中收集的信息。</span><span class="sxs-lookup"><span data-stu-id="37c34-117">Best Practices Analyzer uses a set of XML configuration files to determine the information to gather from your Lync Server 2013 environment.</span></span> <span data-ttu-id="37c34-118">除了检查 Active Directory 域服务, 它还检查源, 例如 windows Server 操作系统注册表和 Windows Management Instrumentation (WMI) 中的设置。</span><span class="sxs-lookup"><span data-stu-id="37c34-118">In addition to checking Active Directory Domain Services, it checks sources such as the Windows Server operating system registry and settings in Windows Management Instrumentation (WMI).</span></span>

<span data-ttu-id="37c34-119">最佳做法分析器将收集的数据与 Lync Server 2013 部署的设置和配置的一组预定义规则进行比较。</span><span class="sxs-lookup"><span data-stu-id="37c34-119">Best Practices Analyzer compares the data it gathers with a set of predefined rules for the settings and configurations of Lync Server 2013 deployments.</span></span>

<span data-ttu-id="37c34-120">将收集的数据与预定义的规则进行比较之后, 该工具将报告问题。</span><span class="sxs-lookup"><span data-stu-id="37c34-120">After comparing the collected data with the predefined rules, the tool reports issues.</span></span> <span data-ttu-id="37c34-121">对于它报告的每个问题, 最佳做法分析器提供有关在扫描的 Lync Server 2013 环境中找到的内容和建议的配置的信息。</span><span class="sxs-lookup"><span data-stu-id="37c34-121">For every issue that it reports, Best Practices Analyzer provides information about what was found in the scanned Lync Server 2013 environment and the recommended configuration.</span></span> <span data-ttu-id="37c34-122">最佳做法分析器还提供有关特定问题的更多详细信息的链接。</span><span class="sxs-lookup"><span data-stu-id="37c34-122">Best Practices Analyzer also provides links to more detailed information about the specific issues.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="37c34-123">Lync Server 2013, 最佳做法分析器仅收集 Lync Server 2013 组件的配置信息。</span><span class="sxs-lookup"><span data-stu-id="37c34-123">The Lync Server 2013, Best Practices Analyzer gathers configuration information only from Lync Server 2013 components.</span></span> <span data-ttu-id="37c34-124">你可以使用该工具的以前版本来扫描以前的环境。</span><span class="sxs-lookup"><span data-stu-id="37c34-124">You can use the previous versions of the tool to scan previous environments.</span></span> <span data-ttu-id="37c34-125">有关详细信息, 请参阅<A href="lync-server-2013-requirements-for-running-best-practices-analyzer.md">在 Lync Server 2013 中运行最佳做法分析器的要求</A>。</span><span class="sxs-lookup"><span data-stu-id="37c34-125">For details, see <A href="lync-server-2013-requirements-for-running-best-practices-analyzer.md">Requirements for running Best Practices Analyzer in Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

