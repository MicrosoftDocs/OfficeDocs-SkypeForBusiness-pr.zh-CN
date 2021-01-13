---
title: 阻止新连接
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: 3f2ca560f934f5b907d05a1f768a0cadd8435f2a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823462"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a><span data-ttu-id="db730-102">阻止与 Skype for Business Server 的新连接进行服务器维护</span><span class="sxs-lookup"><span data-stu-id="db730-102">Preventing new connections to Skype for Business Server for server maintenance</span></span>


<span data-ttu-id="db730-103">Skype for Business Server 使你能够使服务器脱机 (例如，将软件或硬件升级) 用户不会丢失任何服务。</span><span class="sxs-lookup"><span data-stu-id="db730-103">Skype for Business Server enables you to take a server offline (for example, to apply software or hardware upgrades) without any loss of service to users.</span></span>

<span data-ttu-id="db730-p101">如果指定阻止对池中服务器的新连接或新呼叫的选项，则一旦实现此选项，服务器将停止接收任何新连接和呼叫。这些新的连接和呼叫将通过池中的其他服务器进行路由。阻止新连接的服务器允许其现有连接上的会话继续进行，直至会话自然结束。所有现有会话都结束后，即可将服务器置于脱机状态。</span><span class="sxs-lookup"><span data-stu-id="db730-p101">When you specify the option to prevent new connections or calls to a server in a pool, it stops taking any new connections and calls as soon as you implement this option. These new connections and calls are routed through other servers in the pool. A server that is preventing new connections allows its sessions on existing connections to continue until they naturally end. When all existing sessions have ended, the server is ready to be taken offline.</span></span>

<span data-ttu-id="db730-108">阻止与前端服务器建立新连接时，某些 Skype for Business Server 功能和服务依赖于 DNS 负载平衡以确保其正常工作。</span><span class="sxs-lookup"><span data-stu-id="db730-108">When you prevent new connections to a Front End Server, some Skype for Business Server features and services rely on DNS load balancing to ensure that it functions properly.</span></span> <span data-ttu-id="db730-109">如果在池中没有使用 DNS 负载平衡，则服务器阻止新连接期间，通过这些服务的连接可能不会重新路由到其他服务器，因此将服务器置于脱机状态时，某些会话和呼叫可能会中断。</span><span class="sxs-lookup"><span data-stu-id="db730-109">If you are not using DNS load balancing on the pool, connections through these services may not be re-routed to other servers during the period that the server is preventing new connections, and thus when the server is taken offline some sessions and calls may be interrupted.</span></span> <span data-ttu-id="db730-110">依赖 DNS 负载平衡以确保此选项正常运行的功能如下所示：</span><span class="sxs-lookup"><span data-stu-id="db730-110">The features that rely on DNS load balancing to ensure that this option operates properly are as follows:</span></span>

  - <span data-ttu-id="db730-111">助理版</span><span class="sxs-lookup"><span data-stu-id="db730-111">Attendant</span></span>

  - <span data-ttu-id="db730-112">会议通知应用程序</span><span class="sxs-lookup"><span data-stu-id="db730-112">Conferencing Announcement application</span></span>

  - <span data-ttu-id="db730-113">响应组应用程序</span><span class="sxs-lookup"><span data-stu-id="db730-113">Response Group application</span></span>

  - <span data-ttu-id="db730-114">Announcement application － 通知应用程序</span><span class="sxs-lookup"><span data-stu-id="db730-114">Announcement application</span></span>

  - <span data-ttu-id="db730-115">Call Park 应用程序</span><span class="sxs-lookup"><span data-stu-id="db730-115">Call Park application</span></span>

<span data-ttu-id="db730-116">有关 DNS 负载平衡的详细信息，请参阅 [负载平衡要求](../../plan-your-deployment/network-requirements/load-balancing.md)。</span><span class="sxs-lookup"><span data-stu-id="db730-116">For details about DNS load balancing, see [Load balancing requirements](../../plan-your-deployment/network-requirements/load-balancing.md).</span></span>

<span data-ttu-id="db730-117">除了阻止运行 Skype for Business Server 的服务器上所有服务的新连接之外，还可以阻止各个 Skype for Business Server 服务的新连接。</span><span class="sxs-lookup"><span data-stu-id="db730-117">In addition to preventing new connections for all services on a server running Skype for Business Server, you can also prevent new connections for individual Skype for Business Server services.</span></span> <span data-ttu-id="db730-118">例如，此方法在需要应用不需要关闭整个服务器的 Skype for Business Server 更新的情况下很有用。</span><span class="sxs-lookup"><span data-stu-id="db730-118">For example, this method is useful in a situation where you need to apply a Skype for Business Server update that does not require the whole server to be shut down.</span></span> <span data-ttu-id="db730-119">请注意，阻止一项服务的连时，必须选择 Windows 服务列表中所属和显示的服务。</span><span class="sxs-lookup"><span data-stu-id="db730-119">Note that when you prevent connections for one service, you must select a service as it is grouped and displayed in the Windows list of services.</span></span> <span data-ttu-id="db730-120">例如，Skype for Business Server Front-End 服务和用于监控的数据收集代理是单独的 Skype for Business Server 服务，但在 Windows 服务列表中，它们合并显示为 Skype for Business Server 前端服务。</span><span class="sxs-lookup"><span data-stu-id="db730-120">For example, the Skype for Business Server Front-End service and the data collection agent for Monitoring are separate Skype for Business Server services, but in the Windows services list they are consolidated and shown as the Skype for Business Server Front End service.</span></span> <span data-ttu-id="db730-121">可以阻止 Skype for Business Server 前端服务的新连接，但不能分别阻止这两个基础 Skype for Business Server 服务的新连接。</span><span class="sxs-lookup"><span data-stu-id="db730-121">You can prevent new connections for the Skype for Business Server Front End service, but you cannot prevent new connections for these two individual underlying Skype for Business Server services separately.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="db730-p104">如果将某台服务器设置为阻止新连接，然后重新启动该服务器，则默认情况下，该服务器启动后将立即开始接受新连接。要防止此情况发生，请在重新启动服务器之前，将其设置为仅手动暂停和恢复。</span><span class="sxs-lookup"><span data-stu-id="db730-p104">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts. To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a><span data-ttu-id="db730-124">阻止与 Skype for Business Server 的新连接</span><span class="sxs-lookup"><span data-stu-id="db730-124">To prevent new connections to Skype for Business Server</span></span>

1.  <span data-ttu-id="db730-125">以以下组的成员登录到本地管理员组。</span><span class="sxs-lookup"><span data-stu-id="db730-125">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="db730-126">打开"服务"管理单元控制台：单击"开始"，指向"所有程序"，指向 **"管理工具**"，然后单击"**服务"。**</span><span class="sxs-lookup"><span data-stu-id="db730-126">Open the Services snap-in console: Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="db730-127">在列表中，双击要阻止新连接的 Skype for Business Server Windows 服务。</span><span class="sxs-lookup"><span data-stu-id="db730-127">In the list, double-click the Skype for Business Server Windows service to which you want to prevent new connections.</span></span>

4.  <span data-ttu-id="db730-128">在“属性”对话框的“服务状态: 已启动”下，单击“暂停”。</span><span class="sxs-lookup"><span data-stu-id="db730-128">In the Properties dialog box, under **Service status: Started**, click **Pause**.</span></span>

5.  <span data-ttu-id="db730-129">或者，作为推荐选项，单击“启动类型”旁边的“手动”。</span><span class="sxs-lookup"><span data-stu-id="db730-129">Optionally, but recommended, next to **Startup type**, click **Manual**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="db730-p105">如果将某台服务器设置为阻止新连接，然后重新启动该服务器，则默认情况下，该服务器启动后将立即开始接受新连接。要防止此情况发生，请在重新启动服务器之前，将其设置为仅手动暂停和恢复。</span><span class="sxs-lookup"><span data-stu-id="db730-p105">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts. To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>
