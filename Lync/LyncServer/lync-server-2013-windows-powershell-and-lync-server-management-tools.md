---
title: Lync Server 2013：Windows PowerShell 和 Lync Server 管理工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Windows PowerShell and Lync Server 2013 management tools
ms:assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481130(v=OCS.15)
ms:contentKeyID: 59893869
ms.date: 07/20/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbfd15ff3c1047f04a6878b65a3d16e63bac490b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727742"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="windows-powershell-and-lync-server-2013-management-tools"></a><span data-ttu-id="fc6e0-102">Windows PowerShell 和 Lync Server 2013 管理工具</span><span class="sxs-lookup"><span data-stu-id="fc6e0-102">Windows PowerShell and Lync Server 2013 management tools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc6e0-103">_**主题上次修改时间：** 2016-07-20_</span><span class="sxs-lookup"><span data-stu-id="fc6e0-103">_**Topic Last Modified:** 2016-07-20_</span></span>

<span data-ttu-id="fc6e0-104">在 Microsoft Lync Server 2013 中，管理工具是使用 Windows PowerShell 实现的。</span><span class="sxs-lookup"><span data-stu-id="fc6e0-104">In Microsoft Lync Server 2013, management tools are implemented using Windows PowerShell.</span></span> <span data-ttu-id="fc6e0-105">Windows PowerShell 包含命令行环境、特定于产品的命令和完整的脚本语言。</span><span class="sxs-lookup"><span data-stu-id="fc6e0-105">Windows PowerShell includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="fc6e0-106">使用 Windows PowerShell 实现的 Lync Server 2013 工具包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="fc6e0-106">Lync Server 2013 tools that are implemented using Windows PowerShell include the following:</span></span>

  - <span data-ttu-id="fc6e0-107">**拓扑生成器**。</span><span class="sxs-lookup"><span data-stu-id="fc6e0-107">**Topology Builder**.</span></span> <span data-ttu-id="fc6e0-108">你可以使用拓扑生成器来创建、调整和发布你的计划拓扑，并在开始服务器安装之前验证你的拓扑。</span><span class="sxs-lookup"><span data-stu-id="fc6e0-108">You use Topology Builder to create, adjust, and publish your planned topology, and it validates your topology before you begin server installations.</span></span> <span data-ttu-id="fc6e0-109">在单个服务器上安装 Lync Server 2013 时，服务器会将已发布的拓扑作为安装过程的一部分进行读取，安装程序将按照拓扑中的指示部署该服务器。</span><span class="sxs-lookup"><span data-stu-id="fc6e0-109">When you install Lync Server 2013 on individual servers, the servers read the published topology as part of the installation process, and the installation program deploys the server as directed in the topology.</span></span> <span data-ttu-id="fc6e0-110">After setup, configuration information is automatically replicated to all servers.</span><span class="sxs-lookup"><span data-stu-id="fc6e0-110">After setup, configuration information is automatically replicated to all servers.</span></span> <span data-ttu-id="fc6e0-111">Components can be added to your deployment only by using Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="fc6e0-111">Components can be added to your deployment only by using Topology Builder.</span></span>

  - <span data-ttu-id="fc6e0-112">**Lync Server 命令行管理**程序。</span><span class="sxs-lookup"><span data-stu-id="fc6e0-112">**Lync Server Management Shell**.</span></span> <span data-ttu-id="fc6e0-113">你可以使用 Lync Server 命令行管理程序执行部署的完整命令行管理。</span><span class="sxs-lookup"><span data-stu-id="fc6e0-113">You can use Lync Server Management Shell for full command-line management of your deployment.</span></span>

  - <span data-ttu-id="fc6e0-114">**Lync Server "控制面板"**。</span><span class="sxs-lookup"><span data-stu-id="fc6e0-114">**Lync Server Control Panel**.</span></span> <span data-ttu-id="fc6e0-115">你可以使用 Microsoft Lync Server 2013 控制面板用户界面管理你的部署中的最常见任务。</span><span class="sxs-lookup"><span data-stu-id="fc6e0-115">You can use the Microsoft Lync Server 2013 Control Panel user interface to manage the most common tasks in your deployment.</span></span>

<span data-ttu-id="fc6e0-116">这些工具使用 Windows PowerShell cmdlet 管理你的部署，包括靠近550产品的特定 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fc6e0-116">These tools use Windows PowerShell cmdlets for management of your deployment, including close to 550 product-specific cmdlets.</span></span> <span data-ttu-id="fc6e0-117">Lync Server 2013 中包含的安全 cmdlet 主要用于管理身份验证以及用户权利和权限。</span><span class="sxs-lookup"><span data-stu-id="fc6e0-117">The security cmdlets included in Lync Server 2013 are primarily used to manage authentication, and user rights and permissions.</span></span> <span data-ttu-id="fc6e0-118">多种 cmdlet 可用于管理身份验证，包括用于证书和个人标识号 (PIN) 身份验证的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fc6e0-118">A wide variety of cmdlets are available for managing authentication, including cmdlets for certificate and personal identification number (PIN) authentication.</span></span> <span data-ttu-id="fc6e0-119">此外，你可以使用一些 cmdlet 来使用新的基于角色的访问控制（RBAC）功能来委派 Lync Server 2013 的管理控制。</span><span class="sxs-lookup"><span data-stu-id="fc6e0-119">In addition, a number of cmdlets enable you to use the new Role-Based Access Control (RBAC) feature to delegate administrative control of Lync Server 2013.</span></span> <span data-ttu-id="fc6e0-120">有关 Lync Server cmdlet 的详细信息，请参阅[Lync server 2013 命令行管理](lync-server-2013-lync-server-management-shell.md)程序。</span><span class="sxs-lookup"><span data-stu-id="fc6e0-120">For details about the Lync Server cmdlets, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span></span>

<span data-ttu-id="fc6e0-121">Windows PowerShell 的脚本安全功能专门设计用于帮助避免较旧技术（包括 Microsoft Visual Basic 脚本编写 Edition （VBScript））的某些脚本相关安全问题。</span><span class="sxs-lookup"><span data-stu-id="fc6e0-121">The script security features for Windows PowerShell are specifically designed to help prevent some of the scripting-related security problems of older technologies, including Microsoft Visual Basic Scripting Edition (VBScript).</span></span> <span data-ttu-id="fc6e0-122">Windows PowerShell 安全功能旨在创建用户无法轻松或不知不觉地运行脚本的环境。</span><span class="sxs-lookup"><span data-stu-id="fc6e0-122">The Windows PowerShell security features are intended to create an environment in which users cannot easily or unknowingly run scripts.</span></span> <span data-ttu-id="fc6e0-123">默认情况下，Windows PowerShell 安全功能已启用。</span><span class="sxs-lookup"><span data-stu-id="fc6e0-123">By default, Windows PowerShell security features are enabled.</span></span> <span data-ttu-id="fc6e0-124">你可以修改这些功能的状态，以满足你的脚本需求和各种安全目标。</span><span class="sxs-lookup"><span data-stu-id="fc6e0-124">You can modify the state of those features to accommodate your scripting needs and a variety of security goals.</span></span> <span data-ttu-id="fc6e0-125">这并不是说外壳程序使用户无法运行脚本。</span><span class="sxs-lookup"><span data-stu-id="fc6e0-125">This is not to say that the shell makes it impossible for users to run scripts.</span></span> <span data-ttu-id="fc6e0-126">相反，shell 使用户在运行脚本时无需意识到这样做会很困难———默认情况下。</span><span class="sxs-lookup"><span data-stu-id="fc6e0-126">Rather, the shell makes it difficult—by default—for users to run scripts without realizing they are doing so.</span></span> <span data-ttu-id="fc6e0-127">有关详细信息，请参阅中的 Windows [http://go.microsoft.com/fwlink/p/?LinkId=213145](http://go.microsoft.com/fwlink/p/?linkid=213145)PowerShell 脚本安全性。</span><span class="sxs-lookup"><span data-stu-id="fc6e0-127">For details, see Windows PowerShell Script Security at [http://go.microsoft.com/fwlink/p/?LinkId=213145](http://go.microsoft.com/fwlink/p/?linkid=213145).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

