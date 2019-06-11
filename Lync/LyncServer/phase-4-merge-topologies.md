---
title: '第4阶段: 合并拓扑'
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: 'Phase 4: Merge topologies'
ms:assetid: 81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205044(v=OCS.15)
ms:contentKeyID: 48184668
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77987325d7ad03b107c0f98ccc1c12a6d5e863c2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845154"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phase-4-merge-topologies"></a><span data-ttu-id="8402c-102">第4阶段: 合并拓扑</span><span class="sxs-lookup"><span data-stu-id="8402c-102">Phase 4: Merge topologies</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8402c-103">_**主题上次修改时间:** 2012-03-29_</span><span class="sxs-lookup"><span data-stu-id="8402c-103">_**Topic Last Modified:** 2012-03-29_</span></span>

<span data-ttu-id="8402c-104">以下主题概述了将 Microsoft Office 通信服务器 2007 R2 池合并到 Microsoft Lync Server 2013 池所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="8402c-104">The following topics outline the steps needed to merge your Microsoft Office Communications Server 2007 R2 pools to Microsoft Lync Server 2013 pools.</span></span> <span data-ttu-id="8402c-105">首先, 使用拓扑结构生成器合并向导合并拓扑信息。</span><span class="sxs-lookup"><span data-stu-id="8402c-105">First, you use the Topology Builder Merge wizard to merge topology information.</span></span> <span data-ttu-id="8402c-106">此工具将收集有关 Office 通信服务器 2007 R2 环境的信息, 包括边缘服务器信息, 并将该信息发布到与 Lync Server 2013 共享的数据库中。</span><span class="sxs-lookup"><span data-stu-id="8402c-106">This tool collects information about your Office Communications Server 2007 R2 environment, including Edge Server information, and publishes that information to a database shared with Lync Server 2013.</span></span> <span data-ttu-id="8402c-107">发布合并拓扑后, 拓扑生成器用于查看 Office 通信服务器 2007 R2 拓扑信息以及有关新部署的 Lync Server 2013 拓扑的信息。</span><span class="sxs-lookup"><span data-stu-id="8402c-107">After you publish the merged topology, Topology Builder is used to view the Office Communications Server 2007 R2 topology information and information about the newly deployed Lync Server 2013 topology.</span></span> <span data-ttu-id="8402c-108">最后, 使用 Lync Server Management Shell cmdlet 导入策略和配置设置。</span><span class="sxs-lookup"><span data-stu-id="8402c-108">Finally, you use Lync Server Management Shell cmdlets to import policies and configuration settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8402c-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="8402c-109">In This Section</span></span>

  - [<span data-ttu-id="8402c-110">安装 WMI 向后兼容程序包</span><span class="sxs-lookup"><span data-stu-id="8402c-110">Install WMI Backward Compatibility package</span></span>](install-wmi-backward-compatibility-package.md)

  - [<span data-ttu-id="8402c-111">使用拓扑生成器合并向导合并</span><span class="sxs-lookup"><span data-stu-id="8402c-111">Merge using Topology Builder Merge wizard</span></span>](merge-using-topology-builder-merge-wizard.md)

  - [<span data-ttu-id="8402c-112">导入策略和设置</span><span class="sxs-lookup"><span data-stu-id="8402c-112">Import policies and settings</span></span>](import-policies-and-settings.md)

  - [<span data-ttu-id="8402c-113">验证拓扑信息</span><span class="sxs-lookup"><span data-stu-id="8402c-113">Verify topology information</span></span>](verify-topology-information.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

