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
description: 摘要： 了解如何启动、 停止和监视业务服务器 2015 Skype 的持久聊天服务。
ms.openlocfilehash: 47cd6daeca664f7775455818a5690232e92d4c36
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a><span data-ttu-id="17a18-103">在 Skype for Business Server 2015 中监视、启动和停止持久聊天服务</span><span class="sxs-lookup"><span data-stu-id="17a18-103">Monitor, start, and stop the Persistent Chat services in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="17a18-104">**摘要：**了解如何启动、 停止和监视业务服务器 2015 Skype 的持久聊天服务。</span><span class="sxs-lookup"><span data-stu-id="17a18-104">**Summary:** Learn how to start, stop, and monitor the Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="17a18-105">持久聊天服务和持久聊天的法规遵从性服务 Skype 业务服务器拓扑的一部分，因此可以监视、 停止，和使用以下 cmdlet 启动：</span><span class="sxs-lookup"><span data-stu-id="17a18-105">The Persistent Chat services and Persistent Chat Compliance services are part of the Skype for Business Server topology and can therefore be monitored, stopped, and started by using the following cmdlets:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="17a18-106">获得 CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="17a18-106">get-CsWindowsService</span></span>  <br/> |<span data-ttu-id="17a18-107">返回详细信息关于 Skype 业务服务器 2015年组件作为 Windows 服务运行。</span><span class="sxs-lookup"><span data-stu-id="17a18-107">Returns detailed information about Skype for Business Server 2015 components that run as Windows services.</span></span>  <br/> |
|<span data-ttu-id="17a18-108">开始-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="17a18-108">start-CsWindowsService</span></span>  <br/> |<span data-ttu-id="17a18-109">启动服务。</span><span class="sxs-lookup"><span data-stu-id="17a18-109">Starts the service.</span></span>  <br/> |
|<span data-ttu-id="17a18-110">stop CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="17a18-110">stop-CsWindowsService</span></span>  <br/> |<span data-ttu-id="17a18-111">停止服务。</span><span class="sxs-lookup"><span data-stu-id="17a18-111">Stops the service.</span></span>  <br/> |
   
<span data-ttu-id="17a18-112">有关如何使用 cmdlet 的详细信息，请参阅[业务服务器 2015年管理外壳的 Skype](../management-shell.md)。</span><span class="sxs-lookup"><span data-stu-id="17a18-112">For detailed information about how to use the cmdlets, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

