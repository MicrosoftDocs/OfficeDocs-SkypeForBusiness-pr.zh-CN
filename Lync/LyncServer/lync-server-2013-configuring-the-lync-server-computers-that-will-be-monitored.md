---
title: 'Lync Server 2013: 配置将监视的 Lync Server 计算机'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring the Lync Server computers that will be monitored
ms:assetid: 9f1b2b91-d5af-42ad-a27d-b0815f762ad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205118(v=OCS.15)
ms:contentKeyID: 48184927
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21a5d252035820f373183d1927b322a929340716
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837172"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-lync-server-computers-that-will-be-monitored-in-lync-server-2013"></a><span data-ttu-id="4a5c2-102">配置将在 Lync Server 2013 中监视的 Lync Server 计算机</span><span class="sxs-lookup"><span data-stu-id="4a5c2-102">Configuring the Lync Server computers that will be monitored in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a5c2-103">_**主题上次修改时间:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="4a5c2-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="4a5c2-104">由于 Lync Server 2013 不使用在 Microsoft Lync Server 2010 中使用的中央发现过程, 因此要监视的每个 Lync Server 2013 计算机必须能够自我报告它是否存在于管理服务器。</span><span class="sxs-lookup"><span data-stu-id="4a5c2-104">Because Lync Server 2013 does not use the central discovery process used in Microsoft Lync Server 2010, each Lync Server 2013 computer that you want to monitor must be able to self-report its existence to the management server.</span></span> <span data-ttu-id="4a5c2-105">若要实现此操作, 必须在要监视的每台计算机上安装 Operations Manager 代理文件。</span><span class="sxs-lookup"><span data-stu-id="4a5c2-105">To make this possible, you must install the Operations Manager agent files on each of the computers to be monitored.</span></span> <span data-ttu-id="4a5c2-106">安装代理文件后, 必须将计算机配置为充当 System Center proxy。</span><span class="sxs-lookup"><span data-stu-id="4a5c2-106">After the agent files have been installed, you must configure the computer to act as a System Center proxy.</span></span> <span data-ttu-id="4a5c2-107">请注意, 在这些计算机上安装和配置 Lync Server 之后, 应执行这些过程。</span><span class="sxs-lookup"><span data-stu-id="4a5c2-107">Note that these procedures should be carried out after you have installed and configured Lync Server on these computers.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

