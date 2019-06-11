---
title: 'Lync Server 2013: 环境测试的问题'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Issues with the environment test
ms:assetid: ff1fe0d3-35b2-41ef-87e7-6a61e9e1d2ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205421(v=OCS.15)
ms:contentKeyID: 48185970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ed158c598b9dc5596df23cb845f0adac4c6fed3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829952"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="issues-with-the-environment-test-in-lync-server-2013"></a><span data-ttu-id="d25db-102">Lync Server 2013 中的环境测试问题</span><span class="sxs-lookup"><span data-stu-id="d25db-102">Issues with the environment test in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d25db-103">_**主题上次修改时间:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="d25db-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="d25db-104">最佳做法分析器为你提供一种验证 Lync Server 2013 环境是否支持配置的方法。</span><span class="sxs-lookup"><span data-stu-id="d25db-104">Best Practices Analyzer provides a way for you to verify that your Lync Server 2013 environment is a supported configuration.</span></span> <span data-ttu-id="d25db-105">作为 Active Directory 域服务检查的一部分, 最佳做法分析器将执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="d25db-105">As part of the Active Directory Domain Services check, Best Practices Analyzer does the following:</span></span>

  - <span data-ttu-id="d25db-106">验证 Active Directory 域服务林和架构准备。</span><span class="sxs-lookup"><span data-stu-id="d25db-106">Verifies the Active Directory Domain Services forest and schema preparation.</span></span>

  - <span data-ttu-id="d25db-107">标识部署中的 Active Directory 域服务站点和域的数量。</span><span class="sxs-lookup"><span data-stu-id="d25db-107">Identifies the number of Active Directory Domain Services sites and domains in the deployment.</span></span>

  - <span data-ttu-id="d25db-108">检查林和域级别。</span><span class="sxs-lookup"><span data-stu-id="d25db-108">Checks the forest and domain levels.</span></span>

  - <span data-ttu-id="d25db-109">检查域控制器版本。</span><span class="sxs-lookup"><span data-stu-id="d25db-109">Checks the domain controller version.</span></span>

  - <span data-ttu-id="d25db-110">标识域、配置和架构命名上下文。</span><span class="sxs-lookup"><span data-stu-id="d25db-110">Identifies the domain, configuration, and schema naming context.</span></span>

  - <span data-ttu-id="d25db-111">标识已启用的用户数。</span><span class="sxs-lookup"><span data-stu-id="d25db-111">Identifies the number of enabled users.</span></span>

  - <span data-ttu-id="d25db-112">检查全局 Active Directory 域服务设置的存储位置。</span><span class="sxs-lookup"><span data-stu-id="d25db-112">Checks where the global Active Directory Domain Services settings are stored.</span></span>

  - <span data-ttu-id="d25db-113">检查 Lync Server 的服务连接点 (SCPs)。</span><span class="sxs-lookup"><span data-stu-id="d25db-113">Checks for the service connection points (SCPs) for Lync Server.</span></span>

  - <span data-ttu-id="d25db-114">标识数据库版本。</span><span class="sxs-lookup"><span data-stu-id="d25db-114">Identifies the database version.</span></span>

<div>

## <a name="resolving-issues-with-the-environment"></a><span data-ttu-id="d25db-115">解决环境中的问题</span><span class="sxs-lookup"><span data-stu-id="d25db-115">Resolving Issues with the Environment</span></span>

<span data-ttu-id="d25db-116">如果环境测试发现你的环境存在问题, 这些问题可能是由于你的 Active Directory 配置或特定服务器上运行的软件级别的问题导致的。</span><span class="sxs-lookup"><span data-stu-id="d25db-116">If the environment test found problems with your environment, these problems are probably caused by issues with your Active Directory configuration or the level of software running on specific servers.</span></span> <span data-ttu-id="d25db-117">例如, 如果最佳做法分析器识别你的环境中运行 Windows Server 2000 的任何域控制器, 它将发出警告, 并且你需要将这些域控制器升级到受支持的 Windows Server 版本。</span><span class="sxs-lookup"><span data-stu-id="d25db-117">For example, if Best Practices Analyzer identifies any domain controllers in your environment that are running Windows Server 2000, it will issue a warning and you will need to upgrade those domain controllers to a supported version of Windows Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

