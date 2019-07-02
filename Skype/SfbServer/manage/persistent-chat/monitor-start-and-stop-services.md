---
title: 在 Skype for Business Server 2015 中监视、启动和停止持久聊天服务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: '摘要: 了解如何在 Skype for Business Server 2015 中启动、停止和监视持久聊天服务。'
ms.openlocfilehash: 9d2edf0e05a6efcd6e9354696cceade8265abbac
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418689"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a><span data-ttu-id="9e068-103">在 Skype for Business Server 2015 中监视、启动和停止持久聊天服务</span><span class="sxs-lookup"><span data-stu-id="9e068-103">Monitor, start, and stop the Persistent Chat services in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9e068-104">**摘要:** 了解如何在 Skype for Business Server 2015 中启动、停止和监视持久聊天服务。</span><span class="sxs-lookup"><span data-stu-id="9e068-104">**Summary:** Learn how to start, stop, and monitor the Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="9e068-105">持久聊天服务和持久聊天合规性服务是 Skype for Business 服务器拓扑的一部分, 因此可使用以下 cmdlet 进行监控、停止和启动:</span><span class="sxs-lookup"><span data-stu-id="9e068-105">The Persistent Chat services and Persistent Chat Compliance services are part of the Skype for Business Server topology and can therefore be monitored, stopped, and started by using the following cmdlets:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="9e068-106">get-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="9e068-106">get-CsWindowsService</span></span>  <br/> |<span data-ttu-id="9e068-107">返回有关作为 Windows 服务运行的 Skype for Business Server 2015 组件的详细信息。</span><span class="sxs-lookup"><span data-stu-id="9e068-107">Returns detailed information about Skype for Business Server 2015 components that run as Windows services.</span></span>  <br/> |
|<span data-ttu-id="9e068-108">start-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="9e068-108">start-CsWindowsService</span></span>  <br/> |<span data-ttu-id="9e068-109">启动服务。</span><span class="sxs-lookup"><span data-stu-id="9e068-109">Starts the service.</span></span>  <br/> |
|<span data-ttu-id="9e068-110">stop-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="9e068-110">stop-CsWindowsService</span></span>  <br/> |<span data-ttu-id="9e068-111">停止服务。</span><span class="sxs-lookup"><span data-stu-id="9e068-111">Stops the service.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="9e068-112">Skype for business Server 2015 中提供了持久聊天, 但 Skype for business Server 2019 不再支持此功能。</span><span class="sxs-lookup"><span data-stu-id="9e068-112">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="9e068-113">团队中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="9e068-113">The same functionality is available in Teams.</span></span> <span data-ttu-id="9e068-114">有关详细信息, 请参阅[Microsoft 团队升级](/microsoftteams/upgrade-start-here)入门。</span><span class="sxs-lookup"><span data-stu-id="9e068-114">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="9e068-115">如果需要使用持久聊天, 您可以选择将需要此功能的用户迁移到团队, 或继续使用 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="9e068-115">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

<span data-ttu-id="9e068-116">有关如何使用此 cmdlet 的详细信息，请参阅 [Skype for Business Server 2015 Management Shell](../management-shell.md)。</span><span class="sxs-lookup"><span data-stu-id="9e068-116">For detailed information about how to use the cmdlets, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

