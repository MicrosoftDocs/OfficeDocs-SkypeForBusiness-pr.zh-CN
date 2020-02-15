---
title: 移动 Exchange 统一消息联系人对象
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move Exchange Unified Messaging Contact objects
ms:assetid: 35c7e987-41b5-4798-b617-3303f20e52e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688022(v=OCS.15)
ms:contentKeyID: 49733612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c02e391fa66084a27e3790ccaf42753bcaeaa16
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034412"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-exchange-unified-messaging-contact-objects"></a><span data-ttu-id="e14fc-102">移动 Exchange 统一消息联系人对象</span><span class="sxs-lookup"><span data-stu-id="e14fc-102">Move Exchange Unified Messaging Contact objects</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e14fc-103">_**上次修改的主题：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="e14fc-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="e14fc-104">若要将自动助理（AA）和订阅者访问（SA）联系人对象迁移到新的 Lync Server 2013 部署，您首先要使用**CsExUmContact**和**CsExUmContact** cmdlet 将对象从旧版 Office 通信服务器 2007 R2 部署移动到新的 lync server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="e14fc-104">To migrate Auto Attendant (AA) and Subscriber Access (SA) contact objects to the new Lync Server 2013 deployment, you first move the objects from the legacy Office Communications Server 2007 R2 deployment to the new the Lync Server 2013 deployment using the **Get-CsExUmContact** and **Move-CsExUmContact** cmdlets.</span></span> <span data-ttu-id="e14fc-105">在 Exchange 服务器上，您可以运行**Exchucutil.ps1** Windows PowerShell 脚本，为新部署的 Lync pool 执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e14fc-105">On the Exchange Server, you then run the **ExchUCUtil** Windows PowerShell script to do the following for the newly deployed Lync pool:</span></span>

  - <span data-ttu-id="e14fc-106">将其添加到统一消息 IP 网关。</span><span class="sxs-lookup"><span data-stu-id="e14fc-106">Add it to the Unified Messaging IP gateways.</span></span>

  - <span data-ttu-id="e14fc-107">将其添加到统一消息智能寻线。</span><span class="sxs-lookup"><span data-stu-id="e14fc-107">Add it to the Unified Messaging hunt groups.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e14fc-p102">若要使用 <STRONG>Get-CsExUmContact</STRONG> 和 <STRONG>Move-CsExUmContact</STRONG> cmdlet，您必须是 RTCUniversalUserAdmins 组的成员，并且拥有存储联系对象的组织单位 (OU) 的 OU 权限。可以使用 <STRONG>Grant-OUPermission</STRONG> cmdlet 授予 OU 权限。</span><span class="sxs-lookup"><span data-stu-id="e14fc-p102">In order to use the <STRONG>Get-CsExUmContact</STRONG> and <STRONG>Move-CsExUmContact</STRONG> cmdlets, you must be a member of the RTCUniversalUserAdmins group and have organizational unit (OU) permission to the OU where the contacts objects are stored. OU permission can be granted using the <STRONG>Grant-OUPermission</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="to-move-contact-objects-by-using-the-lync-server-management-shell"></a><span data-ttu-id="e14fc-110">使用 Lync Server 命令行管理程序移动联系对象</span><span class="sxs-lookup"><span data-stu-id="e14fc-110">To move contact objects by using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="e14fc-111">打开 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="e14fc-111">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="e14fc-112">对于在 Exchange UM 中注册的每个池（其中 pool1.contoso.net 是 Office 通信服务器 2007 R2 部署中的池，而 pool2.contoso.net 是来自 Lync Server 2013 部署的池），请键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="e14fc-112">For each pool registered with Exchange UM (where pool1.contoso.net is a pool from the Office Communications Server 2007 R2 deployment and pool2.contoso.net is the pool from the Lync Server 2013 deployment) at the command line, type the following:</span></span>
    
        Get-CsExUmContact -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsExUmContact -Target pool02.contoso.net
    
    <span data-ttu-id="e14fc-113">若要验证是否已移动联系对象，请运行 **Get-CsExumContact** cmdlet，并确认“RegistrarPool”\*\*\*\* 现在是否指向新池。</span><span class="sxs-lookup"><span data-stu-id="e14fc-113">To verify that the contact objects are moved, run the **Get-CsExumContact** cmdlet and confirm that **RegistrarPool** is now pointing to the new pool.</span></span>

</div>

<div>

## <a name="to-run-the-exchucutil-windows-powershell-script"></a><span data-ttu-id="e14fc-114">运行 ExchUCUtil Windows PowerShell 脚本</span><span class="sxs-lookup"><span data-stu-id="e14fc-114">To run the ExchUCUtil Windows PowerShell script</span></span>

1.  <span data-ttu-id="e14fc-115">以具有 Exchange 组织管理员权限的用户身份登录到 Exchange UM 服务器。</span><span class="sxs-lookup"><span data-stu-id="e14fc-115">Log on to the Exchange UM Server as a user with Exchange Organization Administrator privileges.</span></span>

2.  <span data-ttu-id="e14fc-116">导航到 Exchucutil.ps1 Windows PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="e14fc-116">Navigate to the ExchUCUtil Windows PowerShell script.</span></span>
    
    <span data-ttu-id="e14fc-117">在 Exchange 2007 中，Exchucutil.ps1 位于： **%\\Program Files%\\Microsoft Exchange Server\\Scripts exchucutil.ps1\\**</span><span class="sxs-lookup"><span data-stu-id="e14fc-117">In Exchange 2007, ExchUCUtil.ps1 is located at: **%Program Files%\\Microsoft\\Exchange Server\\Scripts\\ExchUCUtil.ps1**</span></span>
    
    <span data-ttu-id="e14fc-118">在 Exchange 2010 中，Exchucutil.ps1 位于： **%\\Program Files% Microsoft\\Exchange Server\\V14\\Scripts exchucutil.ps1\\**</span><span class="sxs-lookup"><span data-stu-id="e14fc-118">In Exchange 2010, ExchUCUtil.ps1 is located at: **%Program Files%\\Microsoft\\Exchange Server\\V14\\Scripts\\ExchUCUtil.ps1**</span></span>

3.  <span data-ttu-id="e14fc-119">如果 Exchange 部署在单个林中，请键入：</span><span class="sxs-lookup"><span data-stu-id="e14fc-119">If Exchange is deployed in a single forest, type:</span></span>
    
        exchucutil.ps1
    
    <span data-ttu-id="e14fc-120">否则，如果 Exchange 部署在多个林中，则键入：</span><span class="sxs-lookup"><span data-stu-id="e14fc-120">Or, if Exchange is deployed in multiple forests, type:</span></span>
    
        exchucutil.ps1 -Forest:" <forest FQDN>"
    
    <span data-ttu-id="e14fc-121">其中，林 FQDN 指定在其中部署 Lync Server 2013 的林。</span><span class="sxs-lookup"><span data-stu-id="e14fc-121">where forest FQDN specifies the forest in which Lync Server 2013 is deployed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e14fc-122">运行 exchucutil.ps1 后<EM></EM>，请确保重新启动“Lync Server 前端”<STRONG></STRONG>服务 (rtcsrv.exe)。</span><span class="sxs-lookup"><span data-stu-id="e14fc-122">Be sure to restart the <STRONG>Lync Server Front-End</STRONG> service (rtcsrv.exe) <EM>after</EM> you run exchucutil.ps1.</span></span> <span data-ttu-id="e14fc-123">否则，Lync Server 2013 将不会在拓扑中检测到统一消息。</span><span class="sxs-lookup"><span data-stu-id="e14fc-123">Otherwise, Lync Server 2013 will not detect Unified Messaging in the topology.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

