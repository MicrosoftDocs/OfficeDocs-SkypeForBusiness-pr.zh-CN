---
title: 在 Skype for Business Server 2015 中监视、启动和停止持久聊天服务
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: 摘要：了解如何在 Skype for Business Server 2015 中启动、停止和监视持久聊天服务。
ms.openlocfilehash: 31285fe5f7eefaa6579f2891a4b29111324de22d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814132"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a><span data-ttu-id="52e28-103">在 Skype for Business Server 2015 中监视、启动和停止持久聊天服务</span><span class="sxs-lookup"><span data-stu-id="52e28-103">Monitor, start, and stop the Persistent Chat services in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="52e28-104">**摘要：** 了解如何在 Skype for Business Server 2015 中启动、停止和监视持久聊天服务。</span><span class="sxs-lookup"><span data-stu-id="52e28-104">**Summary:** Learn how to start, stop, and monitor the Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="52e28-105">持久聊天服务和持久聊天合规性服务是 Skype for Business Server 拓扑的一部分，因此可以使用以下 cmdlet 进行监视、停止和启动：</span><span class="sxs-lookup"><span data-stu-id="52e28-105">The Persistent Chat services and Persistent Chat Compliance services are part of the Skype for Business Server topology and can therefore be monitored, stopped, and started by using the following cmdlets:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="52e28-106">get-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="52e28-106">get-CsWindowsService</span></span>  <br/> |<span data-ttu-id="52e28-107">返回有关作为 Windows 服务运行的 Skype for Business Server 2015 组件的详细信息。</span><span class="sxs-lookup"><span data-stu-id="52e28-107">Returns detailed information about Skype for Business Server 2015 components that run as Windows services.</span></span>  <br/> |
|<span data-ttu-id="52e28-108">start-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="52e28-108">start-CsWindowsService</span></span>  <br/> |<span data-ttu-id="52e28-109">启动服务。</span><span class="sxs-lookup"><span data-stu-id="52e28-109">Starts the service.</span></span>  <br/> |
|<span data-ttu-id="52e28-110">stop-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="52e28-110">stop-CsWindowsService</span></span>  <br/> |<span data-ttu-id="52e28-111">停止服务。</span><span class="sxs-lookup"><span data-stu-id="52e28-111">Stops the service.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="52e28-112">持久聊天在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。</span><span class="sxs-lookup"><span data-stu-id="52e28-112">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="52e28-113">Teams 中也提供相同的功能。</span><span class="sxs-lookup"><span data-stu-id="52e28-113">The same functionality is available in Teams.</span></span> <span data-ttu-id="52e28-114">有关详细信息，请参阅 [Microsoft Teams](/microsoftteams/upgrade-start-here)升级入门。</span><span class="sxs-lookup"><span data-stu-id="52e28-114">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="52e28-115">如果你需要使用持久聊天，你的选择是：将需要此功能的用户迁移到 Teams，或者继续使用 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="52e28-115">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

<span data-ttu-id="52e28-116">有关如何使用 cmdlet 的详细信息，请参阅 [Skype for Business Server 2015 命令行管理程序](../management-shell.md)。</span><span class="sxs-lookup"><span data-stu-id="52e28-116">For detailed information about how to use the cmdlets, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

