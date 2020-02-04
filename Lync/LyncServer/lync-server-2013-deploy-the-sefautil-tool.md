---
title: Lync Server 2013：部署 SEFAUtil 工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy the SEFAUtil tool
ms:assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945659(v=OCS.15)
ms:contentKeyID: 51541534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dcd995a99514fa54a221e17f1ea556565cbebdcb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729612"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-the-sefautil-tool-in-lync-server-2013"></a><span data-ttu-id="9792e-102">Deploy the SEFAUtil tool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9792e-102">Deploy the SEFAUtil tool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9792e-103">_**主题上次修改时间：** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="9792e-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="9792e-104">若要部署和管理组呼叫装货，需要使用 SEFAUtil 资源工具包工具。</span><span class="sxs-lookup"><span data-stu-id="9792e-104">To deploy and manage Group Call Pickup, you need to use the SEFAUtil resource kit tool.</span></span> <span data-ttu-id="9792e-105">该工具是 Lync Server 2013 资源工具包工具的一部分。</span><span class="sxs-lookup"><span data-stu-id="9792e-105">The tool is part of the Lync Server 2013 resource kit tools.</span></span> <span data-ttu-id="9792e-106">在安装 SEFAUtil 之前，你必须在拓扑中拥有受信任的应用程序池，将 SEFAUtil 指定为受信任的应用程序，并启用拓扑。</span><span class="sxs-lookup"><span data-stu-id="9792e-106">Before you can install SEFAUtil, you must have a trusted application pool in your topology, specify SEFAUtil as a trusted application, and enable the topology.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9792e-107">Microsoft 统一通信托管 API (UCMA) 3.0 核心 SDK 必须安装在您计划运行 SEFAUtil 工具的任何计算机上。</span><span class="sxs-lookup"><span data-stu-id="9792e-107">Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK must be installed on any computer where you plan to run the SEFAUtil tool.</span></span>



</div>

<span data-ttu-id="9792e-108">你可以在部署中的任何前端池中运行 SEFAUtil。</span><span class="sxs-lookup"><span data-stu-id="9792e-108">You can run the SEFAUtil in any Front End pool in your deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9792e-109">有关运行 SEFAUtil 的更多详细信息，请参阅 Technet 博客文章 "如何获取 SEFAutil 运行？"</span><span class="sxs-lookup"><span data-stu-id="9792e-109">For more details about running SEFAUtil, see the Technet blog article, "How to get SEFAutil running?"</span></span> <span data-ttu-id="9792e-110"><A href="http://go.microsoft.com/fwlink/?linkid=278940">http://go.microsoft.com/fwlink/?LinkId=278940</A>。</span><span class="sxs-lookup"><span data-stu-id="9792e-110">at <A href="http://go.microsoft.com/fwlink/?linkid=278940">http://go.microsoft.com/fwlink/?LinkId=278940</A>.</span></span>



</div>

<div>

## <a name="to-deploy-sefautil"></a><span data-ttu-id="9792e-111">部署 SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="9792e-111">To deploy SEFAUtil</span></span>

1.  <span data-ttu-id="9792e-112">以 RTCUniversalServerAdmins 组成员的身份或必要的用户权限登录到安装了 Lync Server 管理外壳的计算机，如在[Lync Server 2013 中的 "委派设置权限](lync-server-2013-delegate-setup-permissions.md)" 中所述。</span><span class="sxs-lookup"><span data-stu-id="9792e-112">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="9792e-113">启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="9792e-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="9792e-114">SEFAUtil 工具只能在属于受信任应用程序池的一部分的计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="9792e-114">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="9792e-115">如果需要，请为计划运行 SEFAUtil 的前端池定义受信任的应用程序池。</span><span class="sxs-lookup"><span data-stu-id="9792e-115">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="9792e-116">在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="9792e-116">At the command line, run:</span></span>
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>

4.  <span data-ttu-id="9792e-p104">将 SEFAUtil 工具定义为受信任应用程序。在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="9792e-p104">Define the SEFAUtil tool as a trusted application. At the command line, run:</span></span>
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9792e-119">如有需要，您可以使用其他端口。</span><span class="sxs-lookup"><span data-stu-id="9792e-119">You can use a different port if needed.</span></span>

    
    </div>

5.  <span data-ttu-id="9792e-p105">启用包含您的更改的拓扑。在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="9792e-p105">Enable the topology with your changes. At the command line, run:</span></span>
    
        Enable-CsTopology

6.  <span data-ttu-id="9792e-122">在您在步骤3中创建的受信任的应用程序池中的前端服务器上安装 Lync Server 2013 资源工具包工具。</span><span class="sxs-lookup"><span data-stu-id="9792e-122">Install the Lync Server 2013 resource kit tools on a Front End Server that is in the trusted application pool that you created in step 3.</span></span>

7.  <span data-ttu-id="9792e-123">验证 SEFAUtil 工具是否正常运行，如下所示：</span><span class="sxs-lookup"><span data-stu-id="9792e-123">Verify that the SEFAUtil tool is running correctly, as follows:</span></span>
    
    1.  <span data-ttu-id="9792e-124">使用管理员权限从 Windows 命令提示符处运行该工具以在您的部署中显示用户的呼叫转接设置。</span><span class="sxs-lookup"><span data-stu-id="9792e-124">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="9792e-125">该工具位于 \Program Files\Microsoft Lync Server 2013 \ Reskit。</span><span class="sxs-lookup"><span data-stu-id="9792e-125">The tool is located at \Program Files\Microsoft Lync Server 2013\Reskit.</span></span>

        
        </div>
    
    2.  <span data-ttu-id="9792e-p106">显示用户的呼叫转接设置。在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="9792e-p106">Display the call forwarding settings of a user. At the command line, run:</span></span>
        
            SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
        
        <span data-ttu-id="9792e-128">将显示用户的呼叫转接设置。</span><span class="sxs-lookup"><span data-stu-id="9792e-128">The call forwarding settings for the user will be displayed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

