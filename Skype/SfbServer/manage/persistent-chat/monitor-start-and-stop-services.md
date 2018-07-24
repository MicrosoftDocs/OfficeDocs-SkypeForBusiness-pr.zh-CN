---
title: 在 Skype for Business Server 2015 中监视、启动和停止持久聊天服务
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: 摘要： 了解如何启动、 停止和监视 Skype 中使用的持久聊天服务的业务服务器 2015年。
ms.openlocfilehash: 272ea0f4270b1109ff77b5d809472051705b6f10
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20991587"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a><span data-ttu-id="8e0fa-103">在 Skype for Business Server 2015 中监视、启动和停止持久聊天服务</span><span class="sxs-lookup"><span data-stu-id="8e0fa-103">Monitor, start, and stop the Persistent Chat services in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8e0fa-104">**摘要：** 了解如何启动、 停止和监视 Skype 中使用的持久聊天服务的业务服务器 2015年。</span><span class="sxs-lookup"><span data-stu-id="8e0fa-104">**Summary:** Learn how to start, stop, and monitor the Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="8e0fa-105">持久聊天服务和持久聊天合规性服务属于企业服务器拓扑的 Skype 和因此可以监视、 停止和由使用以下 cmdlet 启动：</span><span class="sxs-lookup"><span data-stu-id="8e0fa-105">The Persistent Chat services and Persistent Chat Compliance services are part of the Skype for Business Server topology and can therefore be monitored, stopped, and started by using the following cmdlets:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="8e0fa-106">get CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="8e0fa-106">get-CsWindowsService</span></span>  <br/> |<span data-ttu-id="8e0fa-107">返回有关详细信息 Skype 的业务服务器 2015年组件的运行作为 Windows 服务。</span><span class="sxs-lookup"><span data-stu-id="8e0fa-107">Returns detailed information about Skype for Business Server 2015 components that run as Windows services.</span></span>  <br/> |
|<span data-ttu-id="8e0fa-108">开始 CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="8e0fa-108">start-CsWindowsService</span></span>  <br/> |<span data-ttu-id="8e0fa-109">启动服务。</span><span class="sxs-lookup"><span data-stu-id="8e0fa-109">Starts the service.</span></span>  <br/> |
|<span data-ttu-id="8e0fa-110">停止 CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="8e0fa-110">stop-CsWindowsService</span></span>  <br/> |<span data-ttu-id="8e0fa-111">停止服务。</span><span class="sxs-lookup"><span data-stu-id="8e0fa-111">Stops the service.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="8e0fa-112">持久聊天中的业务服务器 2015 Skype 可用但业务服务器 2019年不再支持在 Skype。</span><span class="sxs-lookup"><span data-stu-id="8e0fa-112">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="8e0fa-113">中团队提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="8e0fa-113">The same functionality is available in Teams.</span></span> <span data-ttu-id="8e0fa-114">有关详细信息，请参阅[从企业对 Microsoft 团队的 Skype 旅程](/microsoftteams/journey-skypeforbusiness-teams)。</span><span class="sxs-lookup"><span data-stu-id="8e0fa-114">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="8e0fa-115">如果您需要使用持久聊天，您的选择是也迁移要求给团队，此功能的用户或继续对业务服务器 2015年使用 Skype。</span><span class="sxs-lookup"><span data-stu-id="8e0fa-115">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

<span data-ttu-id="8e0fa-116">有关如何使用这些 cmdlet 的详细信息，请参阅[Skype 的业务服务器 2015年命令行管理程序](../management-shell.md)。</span><span class="sxs-lookup"><span data-stu-id="8e0fa-116">For detailed information about how to use the cmdlets, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

