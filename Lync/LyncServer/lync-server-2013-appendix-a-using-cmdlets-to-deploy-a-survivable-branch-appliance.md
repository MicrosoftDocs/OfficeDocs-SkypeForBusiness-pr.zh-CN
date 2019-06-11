---
title: Lync Server 2013：附录 A：使用 Cmdlet 部署 Survivable Branch Appliance
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: 'Appendix A: Using cmdlets to deploy a Survivable Branch Appliance'
ms:assetid: 796a26cf-7ec9-453b-8757-6153a6dd86c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398598(v=OCS.15)
ms:contentKeyID: 48184569
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9541e6cb63cee91a6bfd1072695fb3ce09a0134
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838034"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appendix-a-using-cmdlets-to-deploy-a-survivable-branch-appliance-in-lync-server-2013"></a><span data-ttu-id="4aae7-102">附录 A：在 Lync Server 2013 中使用 Cmdlet 部署 Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="4aae7-102">Appendix A: Using cmdlets to deploy a Survivable Branch Appliance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4aae7-103">_**主题上次修改时间:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="4aae7-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="4aae7-104">本主题介绍了如何使用 Lync Server 命令行管理程序部署 Survivable 分支装置。</span><span class="sxs-lookup"><span data-stu-id="4aae7-104">This topic describes how to deploy a Survivable Branch Appliance using the Lync Server Management Shell.</span></span> <span data-ttu-id="4aae7-105">在中心站点执行此过程。</span><span class="sxs-lookup"><span data-stu-id="4aae7-105">Perform this procedure at the central site.</span></span>

<div>

## <a name="to-deploy-a-survivable-branch-appliance-remotely"></a><span data-ttu-id="4aae7-106">远程部署 Survivable 分支装置</span><span class="sxs-lookup"><span data-stu-id="4aae7-106">To deploy a Survivable Branch Appliance remotely</span></span>

1.  <span data-ttu-id="4aae7-107">按照在[Lync Server 2013 中将分支站点添加到拓扑](lync-server-2013-add-branch-sites-to-your-topology.md)中的过程添加新的分支站点。</span><span class="sxs-lookup"><span data-stu-id="4aae7-107">Follow the procedure in [Add branch sites to your topology in Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md) to add a new branch site.</span></span>

2.  <span data-ttu-id="4aae7-108">将分支站点加入域。</span><span class="sxs-lookup"><span data-stu-id="4aae7-108">Join the branch site to the domain.</span></span>

3.  <span data-ttu-id="4aae7-109">将 RTCUniversalSBATechnicians 组添加到本地管理员组。</span><span class="sxs-lookup"><span data-stu-id="4aae7-109">Add the RTCUniversalSBATechnicians group to the local Administrators group.</span></span>

4.  <span data-ttu-id="4aae7-110">重新启动服务器, 并以 RTCUniversalSBATechnicians 组成员的身份登录到该服务器。</span><span class="sxs-lookup"><span data-stu-id="4aae7-110">Restart the server, and log on to it as a member of the RTCUniversalSBATechnicians group.</span></span>

5.  <span data-ttu-id="4aae7-111">在 Lync Server Management Shell 中, 键入以下命令, 将占位符替换为您的组织的正确信息:</span><span class="sxs-lookup"><span data-stu-id="4aae7-111">In the Lync Server Management Shell, type the following commands, replacing the placeholders with the correct information for your organization:</span></span>
    
        Export-CsConfiguration -FileName C:\CSConfig.zip
        Import-CsConfiguration -LocalStore -FileName C:\CSConfig.zip -Verbose
        Enable-CSReplica -Verbose
        Enable-CsComputer -Verbose
        Request-CsCertificate -New -Type default -CA <YourCA> -Verbose
        Set-CsCertificate -Type Default -Thumbprint <YourCertThumbprint>
        Start-cswindowsservice -verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

