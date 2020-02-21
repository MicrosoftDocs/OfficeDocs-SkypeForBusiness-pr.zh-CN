---
title: 阻止与 Lync Server 的新连接进行服务器维护
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prevent new connections to Lync Server for server maintenance
ms:assetid: 22b27adf-a590-43bd-9306-a5789ae108d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520964(v=OCS.15)
ms:contentKeyID: 48183625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc787dee62152e9ace76663a084fe5c1c428b1f2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183565"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prevent-new-connections-to-lync-server-2013-for-server-maintenance"></a><span data-ttu-id="f0fb1-102">阻止与 Lync Server 2013 的新连接进行服务器维护</span><span class="sxs-lookup"><span data-stu-id="f0fb1-102">Prevent new connections to Lync Server 2013 for server maintenance</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0fb1-103">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f0fb1-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f0fb1-104">使用 Lync Server，您可以使服务器脱机（例如，在应用软件或硬件升级时），而不会对用户丢失任何服务。</span><span class="sxs-lookup"><span data-stu-id="f0fb1-104">Lync Server enables you to take a server offline (for example, to apply software or hardware upgrades) without any loss of service to users.</span></span>

<span data-ttu-id="f0fb1-p101">如果指定阻止对池中服务器的新连接或新呼叫的选项，则一旦实现此选项，服务器将停止接收任何新连接和呼叫。这些新的连接和呼叫将通过池中的其他服务器进行路由。阻止新连接的服务器允许其现有连接上的会话继续进行，直至会话自然结束。所有现有会话都结束后，即可将服务器置于脱机状态。</span><span class="sxs-lookup"><span data-stu-id="f0fb1-p101">When you specify the option to prevent new connections or calls to a server in a pool, it stops taking any new connections and calls as soon as you implement this option. These new connections and calls are routed through other servers in the pool. A server that is preventing new connections allows its sessions on existing connections to continue until they naturally end. When all existing sessions have ended, the server is ready to be taken offline.</span></span>

<span data-ttu-id="f0fb1-109">当您阻止与前端服务器的新连接时，某些 Lync Server 功能和服务会依赖于 DNS 负载平衡以确保其正常工作。</span><span class="sxs-lookup"><span data-stu-id="f0fb1-109">When you prevent new connections to a Front End Server, some Lync Server features and services rely on DNS load balancing to ensure that it functions properly.</span></span> <span data-ttu-id="f0fb1-110">如果在池中没有使用 DNS 负载平衡，则服务器阻止新连接期间，通过这些服务的连接可能不会重新路由到其他服务器，因此将服务器置于脱机状态时，某些会话和呼叫可能会中断。</span><span class="sxs-lookup"><span data-stu-id="f0fb1-110">If you are not using DNS load balancing on the pool, connections through these services may not be re-routed to other servers during the period that the server is preventing new connections, and thus when the server is taken offline some sessions and calls may be interrupted.</span></span> <span data-ttu-id="f0fb1-111">依赖 DNS 负载平衡以确保此选项正常运行的功能如下所示：</span><span class="sxs-lookup"><span data-stu-id="f0fb1-111">The features that rely on DNS load balancing to ensure that this option operates properly are as follows:</span></span>

  - <span data-ttu-id="f0fb1-112">随</span><span class="sxs-lookup"><span data-stu-id="f0fb1-112">Attendant</span></span>

  - <span data-ttu-id="f0fb1-113">会议通知应用程序</span><span class="sxs-lookup"><span data-stu-id="f0fb1-113">Conferencing Announcement application</span></span>

  - <span data-ttu-id="f0fb1-114">响应组应用程序</span><span class="sxs-lookup"><span data-stu-id="f0fb1-114">Response Group application</span></span>

  - <span data-ttu-id="f0fb1-115">Announcement application － 通知应用程序</span><span class="sxs-lookup"><span data-stu-id="f0fb1-115">Announcement application</span></span>

  - <span data-ttu-id="f0fb1-116">Call Park 应用程序</span><span class="sxs-lookup"><span data-stu-id="f0fb1-116">Call Park application</span></span>

<span data-ttu-id="f0fb1-117">有关 DNS 负载平衡的详细信息，请参阅规划文档中的[Lync Server 2013 中的 DNS 负载平衡](lync-server-2013-dns-load-balancing.md)。</span><span class="sxs-lookup"><span data-stu-id="f0fb1-117">For details about DNS load balancing, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) in the Planning documentation.</span></span>

<span data-ttu-id="f0fb1-118">除了阻止运行 Lync Server 的服务器上的所有服务的新连接之外，还可以阻止单独的 Lync Server 服务的新连接。</span><span class="sxs-lookup"><span data-stu-id="f0fb1-118">In addition to preventing new connections for all services on a server running Lync Server, you can also prevent new connections for individual Lync Server services.</span></span> <span data-ttu-id="f0fb1-119">例如，在需要应用不要求整个服务器关闭的 Lync Server 更新的情况下，此方法非常有用。</span><span class="sxs-lookup"><span data-stu-id="f0fb1-119">For example, this method is useful in a situation where you need to apply a Lync Server update that does not require the whole server to be shut down.</span></span> <span data-ttu-id="f0fb1-120">请注意，阻止一项服务的连时，必须选择 Windows 服务列表中所属和显示的服务。</span><span class="sxs-lookup"><span data-stu-id="f0fb1-120">Note that when you prevent connections for one service, you must select a service as it is grouped and displayed in the Windows list of services.</span></span> <span data-ttu-id="f0fb1-121">例如，Lync Server 前端服务和用于监视的数据集代理是单独的 Lync Server 服务，但在 Windows 服务列表中，它们将被合并并显示为 Lync Server 前端服务。</span><span class="sxs-lookup"><span data-stu-id="f0fb1-121">For example, the Lync Server Front-End service and the data collection agent for Monitoring are separate Lync Server services, but in the Windows services list they are consolidated and shown as the Lync Server Front End service.</span></span> <span data-ttu-id="f0fb1-122">您可以阻止 Lync Server 前端服务的新连接，但不能单独阻止这两个单独的基础 Lync Server 服务的新连接。</span><span class="sxs-lookup"><span data-stu-id="f0fb1-122">You can prevent new connections for the Lync Server Front End service, but you cannot prevent new connections for these two individual underlying Lync Server services separately.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="f0fb1-p104">如果将某台服务器设置为阻止新连接，然后重新启动该服务器，则默认情况下，该服务器启动后将立即开始接受新连接。要防止此情况发生，请在重新启动服务器之前，将其设置为仅手动暂停和恢复。</span><span class="sxs-lookup"><span data-stu-id="f0fb1-p104">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts. To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>



</div>

<div>

## <a name="to-prevent-new-connections-to-lync-server"></a><span data-ttu-id="f0fb1-125">若要阻止与 Lync Server 的新连接，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f0fb1-125">To prevent new connections to Lync Server:</span></span>

1.  <span data-ttu-id="f0fb1-126">以 Administrators 组成员的身份登录到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="f0fb1-126">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="f0fb1-127">打开 "服务" 管理单元控制台：单击 "**开始**"，依次指向 "**所有程序**"、"**管理工具**"，然后单击 "**服务**"。</span><span class="sxs-lookup"><span data-stu-id="f0fb1-127">Open the Services snap-in console: Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="f0fb1-128">在列表中，双击要阻止与其建立新连接的 Lync Server Windows 服务。</span><span class="sxs-lookup"><span data-stu-id="f0fb1-128">In the list, double-click the Lync Server Windows service to which you want to prevent new connections.</span></span>

4.  <span data-ttu-id="f0fb1-129">在“属性”对话框的“服务状态: 已启动”\*\*\*\* 下，单击“暂停”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f0fb1-129">In the Properties dialog box, under **Service status: Started**, click **Pause**.</span></span>

5.  <span data-ttu-id="f0fb1-130">或者，作为推荐选项，单击“启动类型”\*\*\*\* 旁边的“手动”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f0fb1-130">Optionally, but recommended, next to **Startup type**, click **Manual**.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="f0fb1-p105">如果将某台服务器设置为阻止新连接，然后重新启动该服务器，则默认情况下，该服务器启动后将立即开始接受新连接。要防止此情况发生，请在重新启动服务器之前，将其设置为仅手动暂停和恢复。</span><span class="sxs-lookup"><span data-stu-id="f0fb1-p105">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts. To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>

    
    </div>

6.  <span data-ttu-id="f0fb1-133">完成后，单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f0fb1-133">When you are finished, click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

