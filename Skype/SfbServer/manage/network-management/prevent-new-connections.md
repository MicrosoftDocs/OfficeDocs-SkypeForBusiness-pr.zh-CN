---
title: 防止新连接
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: bc9b4a1e7d6e17f09643ff14ac0e69261c326922
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199018"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a><span data-ttu-id="5da30-102">阻止新的连接到 Skype 业务服务器以进行服务器维护</span><span class="sxs-lookup"><span data-stu-id="5da30-102">Preventing new connections to Skype for Business Server for server maintenance</span></span>


<span data-ttu-id="5da30-103">Skype 业务服务器，您可以向用户不会丢失任何服务使服务器脱机 （例如，若要应用软件或硬件升级）。</span><span class="sxs-lookup"><span data-stu-id="5da30-103">Skype for Business Server enables you to take a server offline (for example, to apply software or hardware upgrades) without any loss of service to users.</span></span>

<span data-ttu-id="5da30-104">当指定的选项，以防止新连接或池中的服务器调用时，停止采取任何新连接和呼叫，只要您实现此选项。</span><span class="sxs-lookup"><span data-stu-id="5da30-104">When you specify the option to prevent new connections or calls to a server in a pool, it stops taking any new connections and calls as soon as you implement this option.</span></span> <span data-ttu-id="5da30-105">这些新连接和呼叫路由到其他池中的服务器。</span><span class="sxs-lookup"><span data-stu-id="5da30-105">These new connections and calls are routed through other servers in the pool.</span></span> <span data-ttu-id="5da30-106">阻止了新连接的服务器上以继续，直到其自然结束的现有连接允许其会话。</span><span class="sxs-lookup"><span data-stu-id="5da30-106">A server that is preventing new connections allows its sessions on existing connections to continue until they naturally end.</span></span> <span data-ttu-id="5da30-107">当所有现有会话已结束时，服务器已准备好脱机。</span><span class="sxs-lookup"><span data-stu-id="5da30-107">When all existing sessions have ended, the server is ready to be taken offline.</span></span>

<span data-ttu-id="5da30-108">当您阻止建立新连接到前端服务器时，业务服务器功能和服务的一些 Skype 依赖于 DNS 负载平衡，以确保其正确运行。</span><span class="sxs-lookup"><span data-stu-id="5da30-108">When you prevent new connections to a Front End Server, some Skype for Business Server features and services rely on DNS load balancing to ensure that it functions properly.</span></span> <span data-ttu-id="5da30-109">如果您不使用 DNS 负载平衡池上，通过这些服务的连接可能无法重新路由到其他服务器期服务器阻止了新的连接，因此当服务器处于脱机状态和一些会话和呼叫可能中断。</span><span class="sxs-lookup"><span data-stu-id="5da30-109">If you are not using DNS load balancing on the pool, connections through these services may not be re-routed to other servers during the period that the server is preventing new connections, and thus when the server is taken offline some sessions and calls may be interrupted.</span></span> <span data-ttu-id="5da30-110">DNS 负载平衡来确保此选项可以正常运行所依赖的功能如下所示：</span><span class="sxs-lookup"><span data-stu-id="5da30-110">The features that rely on DNS load balancing to ensure that this option operates properly are as follows:</span></span>

  - <span data-ttu-id="5da30-111">助理</span><span class="sxs-lookup"><span data-stu-id="5da30-111">Attendant</span></span>

  - <span data-ttu-id="5da30-112">会议通知应用程序</span><span class="sxs-lookup"><span data-stu-id="5da30-112">Conferencing Announcement application</span></span>

  - <span data-ttu-id="5da30-113">响应组应用程序</span><span class="sxs-lookup"><span data-stu-id="5da30-113">Response Group application</span></span>

  - <span data-ttu-id="5da30-114">通知应用程序</span><span class="sxs-lookup"><span data-stu-id="5da30-114">Announcement application</span></span>

  - <span data-ttu-id="5da30-115">呼叫寄存应用程序</span><span class="sxs-lookup"><span data-stu-id="5da30-115">Call Park application</span></span>

<span data-ttu-id="5da30-116">有关 DNS 负载平衡的详细信息，请参阅[负载平衡的要求](../../plan-your-deployment/network-requirements/load-balancing.md)。</span><span class="sxs-lookup"><span data-stu-id="5da30-116">For details about DNS load balancing, see [Load balancing requirements](../../plan-your-deployment/network-requirements/load-balancing.md).</span></span>

<span data-ttu-id="5da30-117">除了防止新业务服务器运行 Skype 的服务器上的所有服务的连接，还可以防止对业务 Server 服务的单个 Skype 的新连接。</span><span class="sxs-lookup"><span data-stu-id="5da30-117">In addition to preventing new connections for all services on a server running Skype for Business Server, you can also prevent new connections for individual Skype for Business Server services.</span></span> <span data-ttu-id="5da30-118">例如，此方法可在需要应用不需要要关闭的整个服务器的企业服务器更新 Skype 的情况下。</span><span class="sxs-lookup"><span data-stu-id="5da30-118">For example, this method is useful in a situation where you need to apply a Skype for Business Server update that does not require the whole server to be shut down.</span></span> <span data-ttu-id="5da30-119">请注意，当您阻止的一个服务连接，您必须选择服务，因为它分组，Windows 服务列表中显示。</span><span class="sxs-lookup"><span data-stu-id="5da30-119">Note that when you prevent connections for one service, you must select a service as it is grouped and displayed in the Windows list of services.</span></span> <span data-ttu-id="5da30-120">例如，业务 Server 前端服务 Skype 和监控的数据集代理是单独 Skype 业务 Server 服务，但是在 Windows 服务列表中合并而且显示为 Skype 的业务 Server 前端服务。</span><span class="sxs-lookup"><span data-stu-id="5da30-120">For example, the Skype for Business Server Front-End service and the data collection agent for Monitoring are separate Skype for Business Server services, but in the Windows services list they are consolidated and shown as the Skype for Business Server Front End service.</span></span> <span data-ttu-id="5da30-121">您可以防止新连接以进行业务 Server 前端服务 Skype，但无法单独阻止业务 Server 服务的以下两个单独基础 Skype 的新连接。</span><span class="sxs-lookup"><span data-stu-id="5da30-121">You can prevent new connections for the Skype for Business Server Front End service, but you cannot prevent new connections for these two individual underlying Skype for Business Server services separately.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5da30-122">设置将阻止建立新连接，然后重新启动服务器的服务器时，默认情况下服务器将立即启动后对其接受新连接。</span><span class="sxs-lookup"><span data-stu-id="5da30-122">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts.</span></span> <span data-ttu-id="5da30-123">若要防止这一点，设置要仅暂停和继续手动之前重新启动服务器, 的服务器。</span><span class="sxs-lookup"><span data-stu-id="5da30-123">To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a><span data-ttu-id="5da30-124">若要防止新连接到 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="5da30-124">To prevent new connections to Skype for Business Server</span></span>

1.  <span data-ttu-id="5da30-125">以 Administrators 组成员的身份登录本地计算机。</span><span class="sxs-lookup"><span data-stu-id="5da30-125">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="5da30-126">打开服务管理单元控制台： 单击**开始**和指向**所有程序**、 都**管理工具**，然后单击**服务**。</span><span class="sxs-lookup"><span data-stu-id="5da30-126">Open the Services snap-in console: Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="5da30-127">在列表中，双击您要阻止建立新连接的业务 Windows 服务器服务 Skype。</span><span class="sxs-lookup"><span data-stu-id="5da30-127">In the list, double-click the Skype for Business Server Windows service to which you want to prevent new connections.</span></span>

4.  <span data-ttu-id="5da30-128">在属性对话框中，在**服务状态： 启动**，单击**暂停**。</span><span class="sxs-lookup"><span data-stu-id="5da30-128">In the Properties dialog box, under **Service status: Started**, click **Pause**.</span></span>

5.  <span data-ttu-id="5da30-129">（可选)，但建议，旁边**启动类型**，单击**手动**。</span><span class="sxs-lookup"><span data-stu-id="5da30-129">Optionally, but recommended, next to **Startup type**, click **Manual**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="5da30-130">设置将阻止建立新连接，然后重新启动服务器的服务器时，默认情况下服务器将立即启动后对其接受新连接。</span><span class="sxs-lookup"><span data-stu-id="5da30-130">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts.</span></span> <span data-ttu-id="5da30-131">若要防止这一点，设置要仅暂停和继续手动之前重新启动服务器, 的服务器。</span><span class="sxs-lookup"><span data-stu-id="5da30-131">To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>
