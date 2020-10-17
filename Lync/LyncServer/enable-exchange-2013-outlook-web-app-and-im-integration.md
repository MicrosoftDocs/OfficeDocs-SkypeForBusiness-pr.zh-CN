---
title: 启用 Exchange 2013 Outlook Web App 和 IM 集成
description: 启用 Exchange 2013 Outlook Web App 和 IM 集成。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Exchange 2013 Outlook Web App and IM integration
ms:assetid: 44d08cf0-b17d-46e1-a4f0-fcc2fe96a958
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204857(v=OCS.15)
ms:contentKeyID: 48184027
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a7fd6e8600f255d6ac4dde52487776cdb5fe1a51
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551118"
---
# <a name="enable-exchange-2013-outlook-web-app-and-im-integration"></a><span data-ttu-id="1f0cb-103">启用 Exchange 2013 Outlook Web App 和 IM 集成</span><span class="sxs-lookup"><span data-stu-id="1f0cb-103">Enable Exchange 2013 Outlook Web App and IM integration</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f0cb-104">_**上次修改的主题：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="1f0cb-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="1f0cb-105">若要启用 Exchange 2013 Outlook Web Access (OWA) 和即时消息 (IM) 与 Lync Server 2013 集成，则必须将 Exchange 2013 客户端访问服务器 (CAS) server 作为受信任的应用程序服务器添加到 Lync Server 2013 拓扑中。</span><span class="sxs-lookup"><span data-stu-id="1f0cb-105">To enable Exchange 2013 Outlook Web Access (OWA) and instant messaging (IM) integration with Lync Server 2013, you must add the Exchange 2013 Client Access Server (CAS) server to the Lync Server 2013 topology as a trusted application server.</span></span>

<div>

## <a name="to-create-a-trusted-application-pool"></a><span data-ttu-id="1f0cb-106">创建受信任应用程序池</span><span class="sxs-lookup"><span data-stu-id="1f0cb-106">To create a trusted application pool</span></span>

1.  <span data-ttu-id="1f0cb-107">启动 Lync Server 2013 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="1f0cb-107">Start the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="1f0cb-108">运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="1f0cb-108">Run the following cmdlet:</span></span>
    
        Get-CsSite
    
    <span data-ttu-id="1f0cb-109">这将返回要在其中创建池的 siteName 的 siteID。</span><span class="sxs-lookup"><span data-stu-id="1f0cb-109">This returns the siteID for the siteName in which you are creating the pool.</span></span> <span data-ttu-id="1f0cb-110">有关详细信息，请参阅 Lync Server 2013 命令行管理程序文档中的 [get-cssite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) 。</span><span class="sxs-lookup"><span data-stu-id="1f0cb-110">For details, see [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) in the Lync Server 2013 Management Shell documentation.</span></span>

3.  <span data-ttu-id="1f0cb-111">运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="1f0cb-111">Run the following cmdlet:</span></span>
    
        New-CsTrustedApplicationPool -Identity <E14 CAS FQDN> -ThrottleAsServer $true -TreatAsAuthenticated $true -ComputerFQDN <E14 CAS FQDN> -Site <Site> -Registrar <Pool FQDN in the site> -RequiresReplication $false
    
    <span data-ttu-id="1f0cb-112">有关详细信息，请参阅 Lync Server 2013 命令行管理程序文档中的 [CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) 。</span><span class="sxs-lookup"><span data-stu-id="1f0cb-112">For details, see [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) in the Lync Server 2013 Management Shell documentation.</span></span>
    
    <span data-ttu-id="1f0cb-113">应将 Exchange Server FQDN 配置为 Exchange OWA 证书使用者名称 (SN) 或使用者替代名称 (SAN)。</span><span class="sxs-lookup"><span data-stu-id="1f0cb-113">The Exchange Server FQDN should be configured as the Exchange OWA certificate Subject Name (SN), or the Subject Alternate Name (SAN).</span></span>
    
    <span data-ttu-id="1f0cb-114">此外，在 Exchange OWA 中验证池的 FQDN 是否受信任。</span><span class="sxs-lookup"><span data-stu-id="1f0cb-114">In Exchange OWA, verify that the pool’s FQDN is trusted as well.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1f0cb-115">如果 CAS 服务器 <EM>未</EM> 在运行 Exchange 2013 统一消息 (UM) 的同一台服务器上并置，请跳过此过程中的其余步骤并执行本主题后面的 "为 EXCHANGE 2013 CAS 服务器创建受信任的应用程序" 过程。</span><span class="sxs-lookup"><span data-stu-id="1f0cb-115">If your CAS server is <EM>not</EM> collocated on the same server that is running Exchange 2013 Unified Messaging (UM), skip the remaining steps in this procedure and perform the “Create a trusted application for the Exchange 2013 CAS server” procedure later in this topic.</span></span> <span data-ttu-id="1f0cb-116">如果 CAS 服务器在运行 Exchange 2013 统一消息 (UM) 的同一台服务器上并置，请完成此过程中的步骤，不要执行本主题后面部分的 "为 Exchange 2013 CAS 服务器创建受信任的应用程序" 过程。</span><span class="sxs-lookup"><span data-stu-id="1f0cb-116">If your CAS server is collocated on the same server that is running Exchange 2013 Unified Messaging (UM), complete the steps in this procedure and do not perform the “Create a trusted application for the Exchange 2013 CAS server” procedure later in this topic.</span></span>

    
    </div>

4.  <span data-ttu-id="1f0cb-117">运行“Enable-CsTopology”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1f0cb-117">Run **Enable-CsTopology**.</span></span>

5.  <span data-ttu-id="1f0cb-118">打开拓扑生成器并下载现有拓扑。</span><span class="sxs-lookup"><span data-stu-id="1f0cb-118">Open Topology Builder and download the existing topology.</span></span>

6.  <span data-ttu-id="1f0cb-119">在左窗格中，展开树直至达到“受信任的应用程序服务器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1f0cb-119">In the left pane, expand the tree until you reach **Trusted application servers**.</span></span>

7.  <span data-ttu-id="1f0cb-120">展开“受信任的应用程序服务器”\*\*\*\* 节点。</span><span class="sxs-lookup"><span data-stu-id="1f0cb-120">Expand the **Trusted application servers** node.</span></span>

8.  <span data-ttu-id="1f0cb-121">现在，您应该会看到作为受信任应用程序服务器列出的 Exchange 2013 CAS 服务器。</span><span class="sxs-lookup"><span data-stu-id="1f0cb-121">You should now see the Exchange 2013 CAS server listed as a trusted application server.</span></span>

</div>

<div>

## <a name="to-create-a-trusted-application-for-the-exchange-2013-cas-server"></a><span data-ttu-id="1f0cb-122">为 Exchange 2013 CAS 服务器创建受信任的应用程序</span><span class="sxs-lookup"><span data-stu-id="1f0cb-122">To create a trusted application for the Exchange 2013 CAS server</span></span>

1.  <span data-ttu-id="1f0cb-123">启动 Lync Server 2013 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="1f0cb-123">Start the Lync Server 2013 Management Shell.</span></span>

2.  <span data-ttu-id="1f0cb-124">如果 CAS 服务器 *未* 在运行 Exchange 2013 统一消息 (UM) 的同一台服务器上并置，请运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="1f0cb-124">If your CAS server is *not* collocated on the same server that is running Exchange 2013 Unified Messaging (UM), run the following cmdlet:</span></span>
    
        New-CsTrustedApplication -ApplicationId <AppID String> -TrustedApplicationPoolFqdn <E14 CAS FQDN> -Port <available port number>
    
    <span data-ttu-id="1f0cb-125">有关详细信息，请参阅 Lync Server 2013 命令行管理程序文档中的 " [CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) " 主题。</span><span class="sxs-lookup"><span data-stu-id="1f0cb-125">For details, see the topic [New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) in the Lync Server 2013 Management Shell documentation.</span></span>

3.  <span data-ttu-id="1f0cb-126">运行“Enable-CsTopology”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1f0cb-126">Run **Enable-CsTopology**.</span></span>

4.  <span data-ttu-id="1f0cb-127">从拓扑生成器的左窗格中，展开树直至到达“受信任的应用程序服务器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1f0cb-127">From Topology Builder, in the left pane, expand the tree until you reach **Trusted application servers**.</span></span>

5.  <span data-ttu-id="1f0cb-128">展开“受信任的应用程序服务器”\*\*\*\* 节点。</span><span class="sxs-lookup"><span data-stu-id="1f0cb-128">Expand the **Trusted application servers** node.</span></span>

6.  <span data-ttu-id="1f0cb-129">现在，您应该会看到作为受信任应用程序服务器列出的 Exchange 2013 CAS 服务器。</span><span class="sxs-lookup"><span data-stu-id="1f0cb-129">You should now see the Exchange 2013 CAS server listed as a trusted application server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

