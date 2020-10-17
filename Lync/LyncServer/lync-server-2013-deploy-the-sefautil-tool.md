---
title: Lync Server 2013：部署 SEFAUtil 工具
description: Lync Server 2013：部署 SEFAUtil 工具。
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
ms.openlocfilehash: 311f14f33dff30b388836a7f02483c4afe5da1b1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558608"
---
# <a name="deploy-the-sefautil-tool-in-lync-server-2013"></a><span data-ttu-id="9f78c-103">在 Lync Server 2013 中部署 SEFAUtil 工具</span><span class="sxs-lookup"><span data-stu-id="9f78c-103">Deploy the SEFAUtil tool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f78c-104">_**上次修改的主题：** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="9f78c-104">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="9f78c-105">若要部署和管理组呼叫应答，您需要使用 SEFAUtil 资源工具包工具。</span><span class="sxs-lookup"><span data-stu-id="9f78c-105">To deploy and manage Group Call Pickup, you need to use the SEFAUtil resource kit tool.</span></span> <span data-ttu-id="9f78c-106">该工具是 Lync Server 2013 资源工具包工具的一部分。</span><span class="sxs-lookup"><span data-stu-id="9f78c-106">The tool is part of the Lync Server 2013 resource kit tools.</span></span> <span data-ttu-id="9f78c-107">在安装 SEFAUtil 之前，您的拓扑中必须有一个受信任的应用程序池，将 SEFAUtil 指定为受信任的应用程序，并启用拓扑。</span><span class="sxs-lookup"><span data-stu-id="9f78c-107">Before you can install SEFAUtil, you must have a trusted application pool in your topology, specify SEFAUtil as a trusted application, and enable the topology.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9f78c-108">Microsoft 统一通信托管 API (UCMA) 3.0 Core SDK 必须安装在您计划运行 SEFAUtil 工具的任何计算机上。</span><span class="sxs-lookup"><span data-stu-id="9f78c-108">Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK must be installed on any computer where you plan to run the SEFAUtil tool.</span></span>



</div>

<span data-ttu-id="9f78c-109">您可以在部署中的任何前端池中运行 SEFAUtil。</span><span class="sxs-lookup"><span data-stu-id="9f78c-109">You can run the SEFAUtil in any Front End pool in your deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9f78c-110">有关运行 SEFAUtil 的更多详细信息，请参阅 Technet 博客文章 "how to get SEFAutil 正在运行吗？"</span><span class="sxs-lookup"><span data-stu-id="9f78c-110">For more details about running SEFAUtil, see the Technet blog article, "How to get SEFAutil running?"</span></span> <span data-ttu-id="9f78c-111">at <A href="https://go.microsoft.com/fwlink/?linkid=278940">https://go.microsoft.com/fwlink/?LinkId=278940</A> 。</span><span class="sxs-lookup"><span data-stu-id="9f78c-111">at <A href="https://go.microsoft.com/fwlink/?linkid=278940">https://go.microsoft.com/fwlink/?LinkId=278940</A>.</span></span>



</div>

<div>

## <a name="to-deploy-sefautil"></a><span data-ttu-id="9f78c-112">部署 SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="9f78c-112">To deploy SEFAUtil</span></span>

1.  <span data-ttu-id="9f78c-113">登录到安装了 Lync Server 命令行管理程序的计算机，作为 RTCUniversalServerAdmins 组的成员或具有必要的用户权限（如在 [Lync Server 2013 中委派安装权限](lync-server-2013-delegate-setup-permissions.md)中所述）。</span><span class="sxs-lookup"><span data-stu-id="9f78c-113">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="9f78c-114">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9f78c-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="9f78c-115">SEFAUtil 工具只能在属于受信任应用程序池一部分的计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="9f78c-115">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="9f78c-116">如果需要，请为计划运行 SEFAUtil 的前端池定义受信任的应用程序池。</span><span class="sxs-lookup"><span data-stu-id="9f78c-116">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="9f78c-117">在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="9f78c-117">At the command line, run:</span></span>
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>

4.  <span data-ttu-id="9f78c-118">将 SEFAUtil 工具定义为受信任的应用程序。</span><span class="sxs-lookup"><span data-stu-id="9f78c-118">Define the SEFAUtil tool as a trusted application.</span></span> <span data-ttu-id="9f78c-119">在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="9f78c-119">At the command line, run:</span></span>
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9f78c-120">如果需要，可以使用其他端口。</span><span class="sxs-lookup"><span data-stu-id="9f78c-120">You can use a different port if needed.</span></span>

    
    </div>

5.  <span data-ttu-id="9f78c-121">使用您的更改启用拓扑。</span><span class="sxs-lookup"><span data-stu-id="9f78c-121">Enable the topology with your changes.</span></span> <span data-ttu-id="9f78c-122">在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="9f78c-122">At the command line, run:</span></span>
    
        Enable-CsTopology

6.  <span data-ttu-id="9f78c-123">在您在步骤3中创建的受信任应用程序池中的前端服务器上安装 Lync Server 2013 资源工具包工具。</span><span class="sxs-lookup"><span data-stu-id="9f78c-123">Install the Lync Server 2013 resource kit tools on a Front End Server that is in the trusted application pool that you created in step 3.</span></span>

7.  <span data-ttu-id="9f78c-124">验证 SEFAUtil 工具是否正常运行，如下所示：</span><span class="sxs-lookup"><span data-stu-id="9f78c-124">Verify that the SEFAUtil tool is running correctly, as follows:</span></span>
    
    1.  <span data-ttu-id="9f78c-125">从带有管理员权限的 Windows 命令提示符处运行该工具，以在部署中显示用户的呼叫转接设置。</span><span class="sxs-lookup"><span data-stu-id="9f78c-125">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="9f78c-126">该工具位于 \Program Files\Microsoft Lync Server 2013 \ \Reskit。</span><span class="sxs-lookup"><span data-stu-id="9f78c-126">The tool is located at \Program Files\Microsoft Lync Server 2013\Reskit.</span></span>

        
        </div>
    
    2.  <span data-ttu-id="9f78c-127">显示用户的呼叫转接设置。</span><span class="sxs-lookup"><span data-stu-id="9f78c-127">Display the call forwarding settings of a user.</span></span> <span data-ttu-id="9f78c-128">在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="9f78c-128">At the command line, run:</span></span>
        
            SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
        
        <span data-ttu-id="9f78c-129">将显示用户的呼叫转接设置。</span><span class="sxs-lookup"><span data-stu-id="9f78c-129">The call forwarding settings for the user will be displayed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

