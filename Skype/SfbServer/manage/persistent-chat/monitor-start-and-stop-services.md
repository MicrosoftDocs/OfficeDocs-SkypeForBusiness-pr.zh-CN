---
title: 在 Skype for Business Server 2015 中监视、启动和停止持久聊天服务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: 摘要： 了解如何启动、 停止和监视 Skype 中使用的持久聊天服务的业务服务器 2015年。
ms.openlocfilehash: 4303d4cfc950ca7c57b7f16b31bc66e1ae711397
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910352"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a><span data-ttu-id="a6a5c-103">在 Skype for Business Server 2015 中监视、启动和停止持久聊天服务</span><span class="sxs-lookup"><span data-stu-id="a6a5c-103">Monitor, start, and stop the Persistent Chat services in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a6a5c-104">**摘要：** 了解如何启动、 停止和监视 Skype 中使用的持久聊天服务的业务服务器 2015年。</span><span class="sxs-lookup"><span data-stu-id="a6a5c-104">**Summary:** Learn how to start, stop, and monitor the Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="a6a5c-105">持久聊天服务和持久聊天合规性服务属于企业服务器拓扑的 Skype 和因此可以监视、 停止和由使用以下 cmdlet 启动：</span><span class="sxs-lookup"><span data-stu-id="a6a5c-105">The Persistent Chat services and Persistent Chat Compliance services are part of the Skype for Business Server topology and can therefore be monitored, stopped, and started by using the following cmdlets:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="a6a5c-106">get-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="a6a5c-106">get-CsWindowsService</span></span>  <br/> |<span data-ttu-id="a6a5c-107">返回有关详细信息 Skype 的业务服务器 2015年组件的运行作为 Windows 服务。</span><span class="sxs-lookup"><span data-stu-id="a6a5c-107">Returns detailed information about Skype for Business Server 2015 components that run as Windows services.</span></span>  <br/> |
|<span data-ttu-id="a6a5c-108">start-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="a6a5c-108">start-CsWindowsService</span></span>  <br/> |<span data-ttu-id="a6a5c-109">启动服务。</span><span class="sxs-lookup"><span data-stu-id="a6a5c-109">Starts the service.</span></span>  <br/> |
|<span data-ttu-id="a6a5c-110">stop-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="a6a5c-110">stop-CsWindowsService</span></span>  <br/> |<span data-ttu-id="a6a5c-111">停止服务。</span><span class="sxs-lookup"><span data-stu-id="a6a5c-111">Stops the service.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="a6a5c-112">持久聊天中的业务服务器 2015 Skype 可用但业务服务器 2019年不再支持在 Skype。</span><span class="sxs-lookup"><span data-stu-id="a6a5c-112">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="a6a5c-113">中团队提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="a6a5c-113">The same functionality is available in Teams.</span></span> <span data-ttu-id="a6a5c-114">有关详细信息，请参阅[从企业对 Microsoft 团队的 Skype 旅程](/microsoftteams/journey-skypeforbusiness-teams)。</span><span class="sxs-lookup"><span data-stu-id="a6a5c-114">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="a6a5c-115">如果您需要使用持久聊天，您的选择是也迁移要求给团队，此功能的用户或继续对业务服务器 2015年使用 Skype。</span><span class="sxs-lookup"><span data-stu-id="a6a5c-115">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

<span data-ttu-id="a6a5c-116">有关如何使用此 cmdlet 的详细信息，请参阅 [Skype for Business Server 2015 Management Shell](../management-shell.md)。</span><span class="sxs-lookup"><span data-stu-id="a6a5c-116">For detailed information about how to use the cmdlets, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

