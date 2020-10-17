---
title: Lync Server 2013：配置将受监视的 Lync Server 计算机
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the Lync Server computers that will be monitored
ms:assetid: 9f1b2b91-d5af-42ad-a27d-b0815f762ad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205118(v=OCS.15)
ms:contentKeyID: 48184927
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 39819a546d59d47b60f0c6dfca76cc6939a1cdf2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532346"
---
# <a name="configuring-the-lync-server-computers-that-will-be-monitored-in-lync-server-2013"></a><span data-ttu-id="95bac-102">配置将在 Lync Server 2013 中监视的 Lync Server 计算机</span><span class="sxs-lookup"><span data-stu-id="95bac-102">Configuring the Lync Server computers that will be monitored in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95bac-103">_**上次修改的主题：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="95bac-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="95bac-104">由于 Lync Server 2013 不使用 Microsoft Lync Server 2010 中使用的中央发现过程，因此每个 Lync Server 2013 要监视的计算机必须能够自我报告它是否存在于管理服务器上。</span><span class="sxs-lookup"><span data-stu-id="95bac-104">Because Lync Server 2013 does not use the central discovery process used in Microsoft Lync Server 2010, each Lync Server 2013 computer that you want to monitor must be able to self-report its existence to the management server.</span></span> <span data-ttu-id="95bac-105">为此，您必须在要监控的每台计算机上安装 Operations Manager 代理文件。</span><span class="sxs-lookup"><span data-stu-id="95bac-105">To make this possible, you must install the Operations Manager agent files on each of the computers to be monitored.</span></span> <span data-ttu-id="95bac-106">在安装这些代理文件后，您必须对计算机进行配置，以将其用作 System Center 代理。</span><span class="sxs-lookup"><span data-stu-id="95bac-106">After the agent files have been installed, you must configure the computer to act as a System Center proxy.</span></span> <span data-ttu-id="95bac-107">请注意，在这些计算机上安装并配置了 Lync Server 后，应执行这些过程。</span><span class="sxs-lookup"><span data-stu-id="95bac-107">Note that these procedures should be carried out after you have installed and configured Lync Server on these computers.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

