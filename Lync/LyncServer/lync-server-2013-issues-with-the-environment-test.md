---
title: Lync Server 2013：环境测试的问题
description: Lync Server 2013：环境测试的问题。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Issues with the environment test
ms:assetid: ff1fe0d3-35b2-41ef-87e7-6a61e9e1d2ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205421(v=OCS.15)
ms:contentKeyID: 48185970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 551d7e914480e178e0558c1d17eefcf060c0688e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574968"
---
# <a name="issues-with-the-environment-test-in-lync-server-2013"></a><span data-ttu-id="78e6b-103">Lync Server 2013 中的环境测试问题</span><span class="sxs-lookup"><span data-stu-id="78e6b-103">Issues with the environment test in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78e6b-104">_**上次修改的主题：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="78e6b-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="78e6b-105">最佳实践分析工具提供了一种方法，用于验证 Lync Server 2013 环境是否受支持的配置。</span><span class="sxs-lookup"><span data-stu-id="78e6b-105">Best Practices Analyzer provides a way for you to verify that your Lync Server 2013 environment is a supported configuration.</span></span> <span data-ttu-id="78e6b-106">作为 Active Directory 域服务检查的一部分，最佳做法分析器可执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="78e6b-106">As part of the Active Directory Domain Services check, Best Practices Analyzer does the following:</span></span>

  - <span data-ttu-id="78e6b-107">验证 Active Directory 域服务林和架构准备。</span><span class="sxs-lookup"><span data-stu-id="78e6b-107">Verifies the Active Directory Domain Services forest and schema preparation.</span></span>

  - <span data-ttu-id="78e6b-108">标识部署中 Active Directory 域服务站点和域的数量。</span><span class="sxs-lookup"><span data-stu-id="78e6b-108">Identifies the number of Active Directory Domain Services sites and domains in the deployment.</span></span>

  - <span data-ttu-id="78e6b-109">检查林和域级别。</span><span class="sxs-lookup"><span data-stu-id="78e6b-109">Checks the forest and domain levels.</span></span>

  - <span data-ttu-id="78e6b-110">检查域控制器版本。</span><span class="sxs-lookup"><span data-stu-id="78e6b-110">Checks the domain controller version.</span></span>

  - <span data-ttu-id="78e6b-111">标识域、配置和架构命名上下文。</span><span class="sxs-lookup"><span data-stu-id="78e6b-111">Identifies the domain, configuration, and schema naming context.</span></span>

  - <span data-ttu-id="78e6b-112">标识启用的用户的数量。</span><span class="sxs-lookup"><span data-stu-id="78e6b-112">Identifies the number of enabled users.</span></span>

  - <span data-ttu-id="78e6b-113">检查全局 Active Directory 域服务设置存储的位置。</span><span class="sxs-lookup"><span data-stu-id="78e6b-113">Checks where the global Active Directory Domain Services settings are stored.</span></span>

  - <span data-ttu-id="78e6b-114">检查 Lync Server (SCPs) 的服务连接点。</span><span class="sxs-lookup"><span data-stu-id="78e6b-114">Checks for the service connection points (SCPs) for Lync Server.</span></span>

  - <span data-ttu-id="78e6b-115">标识数据库版本。</span><span class="sxs-lookup"><span data-stu-id="78e6b-115">Identifies the database version.</span></span>

<div>

## <a name="resolving-issues-with-the-environment"></a><span data-ttu-id="78e6b-116">解决环境问题</span><span class="sxs-lookup"><span data-stu-id="78e6b-116">Resolving Issues with the Environment</span></span>

<span data-ttu-id="78e6b-p102">如果环境测试发现您的环境存在问题，则这些问题可能是 Active Directory 配置或特定服务器上运行的软件级别问题造成的。例如，如果最佳做法分析器标识运行 Windows Server 2000 的环境中的任何域控制器，则系统将发出一个警告，且您将需要将这些域控制器升级到受支持的 Windows Server 版本。</span><span class="sxs-lookup"><span data-stu-id="78e6b-p102">If the environment test found problems with your environment, these problems are probably caused by issues with your Active Directory configuration or the level of software running on specific servers. For example, if Best Practices Analyzer identifies any domain controllers in your environment that are running Windows Server 2000, it will issue a warning and you will need to upgrade those domain controllers to a supported version of Windows Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

