---
title: 'Lync Server 2013: 扫描病毒并检查病毒定义'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scanning for viruses and checking virus definitions
ms:assetid: 287c0f43-82d1-4c1d-b08f-77112fcb5bfa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720909(v=OCS.15)
ms:contentKeyID: 63969589
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 357c2c2053aca6b7b18a966756ece2768a8e71c6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822172"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scanning-for-viruses-and-checking-virus-definitions-in-lync-server-2013"></a><span data-ttu-id="f2a93-102">在 Lync Server 2013 中扫描病毒和检查病毒定义</span><span class="sxs-lookup"><span data-stu-id="f2a93-102">Scanning for viruses and checking virus definitions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2a93-103">_**主题上次修改时间:** 2014-05-01_</span><span class="sxs-lookup"><span data-stu-id="f2a93-103">_**Topic Last Modified:** 2014-05-01_</span></span>

<span data-ttu-id="f2a93-104">强烈建议安装 IM 级防病毒产品。</span><span class="sxs-lookup"><span data-stu-id="f2a93-104">We highly recommend installing an IM-level antivirus product.</span></span> <span data-ttu-id="f2a93-105">IM 是一个众所周知的来源, 可在整个组织中快速传播病毒和恶意软件。</span><span class="sxs-lookup"><span data-stu-id="f2a93-105">IM is a well-known source for quickly spreading both virus and malicious software throughout an organization.</span></span> <span data-ttu-id="f2a93-106">Microsoft Forefront® Lync Server 安全性提供多引擎扫描, 包含病毒、恶意软件、文件和关键字筛选器保护, 以及与 Office 通信服务器的无缝集成。</span><span class="sxs-lookup"><span data-stu-id="f2a93-106">Microsoft Forefront® Security for Lync Server provides multi-engine scanning with virus, malicious software, file and keyword filter protection and seamless integration with Office Communications Server.</span></span>

<span data-ttu-id="f2a93-107">除了 Lync Server 的 Forefront Security, 我们还强烈建议安装文件级防病毒解决方案来保护服务器的文件系统。</span><span class="sxs-lookup"><span data-stu-id="f2a93-107">In addition to Forefront Security for Lync Server, we also highly recommend installing a file-level, antivirus solution to protect the server’s file system.</span></span>

<span data-ttu-id="f2a93-108">保持扫描仪引擎和病毒定义的更新非常重要。</span><span class="sxs-lookup"><span data-stu-id="f2a93-108">Keeping scanner engines and virus definitions updated is very important.</span></span> <span data-ttu-id="f2a93-109">配置和监视更新的运行状况可确保使用最新的扫描信息来保护 Office 通信服务器和文件系统。</span><span class="sxs-lookup"><span data-stu-id="f2a93-109">Configuring and monitoring the health of the updates makes sure that the most current scanning information is being used to protect both Office Communications Server and file-system.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f2a93-110">在运行 lync server 2013 和 Lync server 的 Forefront Security 的服务器上使用第三方文件级防病毒软件时, 请确保未扫描 Lync Server 和 Lync Server 的 Forefront Security 所安装到的文件夹, 以防止他们的损坏。</span><span class="sxs-lookup"><span data-stu-id="f2a93-110">When using a third-party, file-level antivirus software on a server that runs Lync Server 2013 and Forefront Security for Lync Server, make sure that the folders in which Forefront Security for Lync Server and the Lync Server are installed are not scanned, to prevent their corruption.</span></span> <span data-ttu-id="f2a93-111">有关排除项的完整列表, 请<A class=uri href="http://support.microsoft.com/kb/943620">http://support.microsoft.com/kb/943620</A>参阅。</span><span class="sxs-lookup"><span data-stu-id="f2a93-111">For the full list of exclusions, see <A class=uri href="http://support.microsoft.com/kb/943620">http://support.microsoft.com/kb/943620</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

