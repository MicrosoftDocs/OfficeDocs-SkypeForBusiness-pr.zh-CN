---
title: 阻止新连接
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: c2df1c491384f8a248f70b67880511a2d496c173
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817451"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a><span data-ttu-id="2ec54-102">阻止新连接到 Skype for Business 服务器以进行服务器维护</span><span class="sxs-lookup"><span data-stu-id="2ec54-102">Preventing new connections to Skype for Business Server for server maintenance</span></span>


<span data-ttu-id="2ec54-103">Skype for Business 服务器使你能够使服务器脱机（例如，应用软件或硬件升级），而不会对用户造成任何服务损失。</span><span class="sxs-lookup"><span data-stu-id="2ec54-103">Skype for Business Server enables you to take a server offline (for example, to apply software or hardware upgrades) without any loss of service to users.</span></span>

<span data-ttu-id="2ec54-104">当你指定用于阻止新连接或呼叫池中的服务器的选项时，一旦你执行此选项，它将停止进行任何新的连接和调用。</span><span class="sxs-lookup"><span data-stu-id="2ec54-104">When you specify the option to prevent new connections or calls to a server in a pool, it stops taking any new connections and calls as soon as you implement this option.</span></span> <span data-ttu-id="2ec54-105">这些新连接和呼叫通过池中的其他服务器路由。</span><span class="sxs-lookup"><span data-stu-id="2ec54-105">These new connections and calls are routed through other servers in the pool.</span></span> <span data-ttu-id="2ec54-106">阻止新连接的服务器允许现有连接上的会话继续运行，直到它们自然结束。</span><span class="sxs-lookup"><span data-stu-id="2ec54-106">A server that is preventing new connections allows its sessions on existing connections to continue until they naturally end.</span></span> <span data-ttu-id="2ec54-107">当所有现有会话都已结束时，服务器可以脱机使用。</span><span class="sxs-lookup"><span data-stu-id="2ec54-107">When all existing sessions have ended, the server is ready to be taken offline.</span></span>

<span data-ttu-id="2ec54-108">当您阻止与前端服务器的新连接时，某些 Skype for business 服务器功能和服务依赖于 DNS 负载平衡以确保其正常工作。</span><span class="sxs-lookup"><span data-stu-id="2ec54-108">When you prevent new connections to a Front End Server, some Skype for Business Server features and services rely on DNS load balancing to ensure that it functions properly.</span></span> <span data-ttu-id="2ec54-109">如果你未在池上使用 DNS 负载平衡，则通过这些服务的连接可能无法在服务器阻止新连接期间重新路由到其他服务器，因此当服务器脱机时，可能会中断.</span><span class="sxs-lookup"><span data-stu-id="2ec54-109">If you are not using DNS load balancing on the pool, connections through these services may not be re-routed to other servers during the period that the server is preventing new connections, and thus when the server is taken offline some sessions and calls may be interrupted.</span></span> <span data-ttu-id="2ec54-110">依赖于 DNS 负载平衡以确保此选项正常运行的功能如下所示：</span><span class="sxs-lookup"><span data-stu-id="2ec54-110">The features that rely on DNS load balancing to ensure that this option operates properly are as follows:</span></span>

  - <span data-ttu-id="2ec54-111">助理</span><span class="sxs-lookup"><span data-stu-id="2ec54-111">Attendant</span></span>

  - <span data-ttu-id="2ec54-112">会议通知应用程序</span><span class="sxs-lookup"><span data-stu-id="2ec54-112">Conferencing Announcement application</span></span>

  - <span data-ttu-id="2ec54-113">响应组应用程序</span><span class="sxs-lookup"><span data-stu-id="2ec54-113">Response Group application</span></span>

  - <span data-ttu-id="2ec54-114">通知应用程序</span><span class="sxs-lookup"><span data-stu-id="2ec54-114">Announcement application</span></span>

  - <span data-ttu-id="2ec54-115">呼叫寄存应用程序</span><span class="sxs-lookup"><span data-stu-id="2ec54-115">Call Park application</span></span>

<span data-ttu-id="2ec54-116">有关 DNS 负载平衡的详细信息，请参阅[负载平衡要求](../../plan-your-deployment/network-requirements/load-balancing.md)。</span><span class="sxs-lookup"><span data-stu-id="2ec54-116">For details about DNS load balancing, see [Load balancing requirements](../../plan-your-deployment/network-requirements/load-balancing.md).</span></span>

<span data-ttu-id="2ec54-117">除了阻止运行 Skype for business Server 的服务器上的所有服务的新连接，您还可以阻止单个 Skype for Business 服务器服务的新连接。</span><span class="sxs-lookup"><span data-stu-id="2ec54-117">In addition to preventing new connections for all services on a server running Skype for Business Server, you can also prevent new connections for individual Skype for Business Server services.</span></span> <span data-ttu-id="2ec54-118">例如，在需要应用不需要整个服务器关闭的 Skype for Business 服务器更新的情况下，此方法非常有用。</span><span class="sxs-lookup"><span data-stu-id="2ec54-118">For example, this method is useful in a situation where you need to apply a Skype for Business Server update that does not require the whole server to be shut down.</span></span> <span data-ttu-id="2ec54-119">请注意，当你阻止一个服务的连接时，你必须选择在服务的 Windows 列表中对其进行分组和显示的服务。</span><span class="sxs-lookup"><span data-stu-id="2ec54-119">Note that when you prevent connections for one service, you must select a service as it is grouped and displayed in the Windows list of services.</span></span> <span data-ttu-id="2ec54-120">例如，Skype for Business 服务器前端服务和用于监视的数据收集代理是单独的 Skype for business 服务器服务，但在 Windows 服务列表中，它们将被合并并显示为 Skype for business 服务器前端业务.</span><span class="sxs-lookup"><span data-stu-id="2ec54-120">For example, the Skype for Business Server Front-End service and the data collection agent for Monitoring are separate Skype for Business Server services, but in the Windows services list they are consolidated and shown as the Skype for Business Server Front End service.</span></span> <span data-ttu-id="2ec54-121">你可以阻止 Skype for business Server 前端服务的新连接，但不能单独阻止这两个单独的基础 Skype for Business 服务器服务的新连接。</span><span class="sxs-lookup"><span data-stu-id="2ec54-121">You can prevent new connections for the Skype for Business Server Front End service, but you cannot prevent new connections for these two individual underlying Skype for Business Server services separately.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2ec54-122">如果将服务器设置为阻止新连接，然后重新启动服务器，则默认情况下，服务器将在启动后立即开始接受新连接。</span><span class="sxs-lookup"><span data-stu-id="2ec54-122">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts.</span></span> <span data-ttu-id="2ec54-123">若要防止这种情况，请将服务器设置为仅在重新启动服务器之前暂停和手动恢复。</span><span class="sxs-lookup"><span data-stu-id="2ec54-123">To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a><span data-ttu-id="2ec54-124">阻止新连接到 Skype for Business 服务器</span><span class="sxs-lookup"><span data-stu-id="2ec54-124">To prevent new connections to Skype for Business Server</span></span>

1.  <span data-ttu-id="2ec54-125">以 Administrators 组成员的身份登录本地计算机。</span><span class="sxs-lookup"><span data-stu-id="2ec54-125">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="2ec54-126">打开 "服务" 管理单元控制台：单击 "**开始**"，指向 "**所有程序**"，指向 "**管理工具**"，然后单击 "**服务**"。</span><span class="sxs-lookup"><span data-stu-id="2ec54-126">Open the Services snap-in console: Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="2ec54-127">在列表中，双击要阻止新连接的 Skype for business 服务器 Windows 服务。</span><span class="sxs-lookup"><span data-stu-id="2ec54-127">In the list, double-click the Skype for Business Server Windows service to which you want to prevent new connections.</span></span>

4.  <span data-ttu-id="2ec54-128">在 "属性" 对话框中的 "**服务状态：已开始**" 下，单击 "**暂停**"。</span><span class="sxs-lookup"><span data-stu-id="2ec54-128">In the Properties dialog box, under **Service status: Started**, click **Pause**.</span></span>

5.  <span data-ttu-id="2ec54-129">（可选，但建议在 "**启动类型**" 旁边，单击 "**手动**"。</span><span class="sxs-lookup"><span data-stu-id="2ec54-129">Optionally, but recommended, next to **Startup type**, click **Manual**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="2ec54-130">如果将服务器设置为阻止新连接，然后重新启动服务器，则默认情况下，服务器将在启动后立即开始接受新连接。</span><span class="sxs-lookup"><span data-stu-id="2ec54-130">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts.</span></span> <span data-ttu-id="2ec54-131">若要防止这种情况，请将服务器设置为仅在重新启动服务器之前暂停和手动恢复。</span><span class="sxs-lookup"><span data-stu-id="2ec54-131">To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>
