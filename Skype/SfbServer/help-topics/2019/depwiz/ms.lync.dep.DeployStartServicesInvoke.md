---
title: 启动服务（调用）
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployStartServicesInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7992440b-8545-4af9-b3ac-ea200b9de084
ROBOTS: NOINDEX, NOFOLLOW
description: 在正在执行命令窗格的摘要窗格中显示颁发启动的服务的业务服务器角色的服务器，在要部署的 Skype 的任务的状态。
ms.openlocfilehash: db2e0282e15b1995aa6b83bcfdd4ecbecd922207
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32215953"
---
# <a name="start-services-invoke"></a><span data-ttu-id="fd7dc-103">启动服务（调用）</span><span class="sxs-lookup"><span data-stu-id="fd7dc-103">Start Services (Invoke)</span></span>
 
<span data-ttu-id="fd7dc-104">在**正在执行命令**窗格的摘要窗格中显示颁发启动的服务的业务服务器角色的服务器，在要部署的 Skype 的任务的状态。</span><span class="sxs-lookup"><span data-stu-id="fd7dc-104">The summary pane on the **Executing Commands** pane displays the status of the tasks issued to start the services for the Skype for Business Server role server that you are deploying.</span></span> <span data-ttu-id="fd7dc-105">任务窗格中的摘要不代表服务启动状态的实时指示。</span><span class="sxs-lookup"><span data-stu-id="fd7dc-105">The summary in the task pane does not represent a real-time indication of service startup.</span></span> <span data-ttu-id="fd7dc-106">业务 Server 服务的 Skype 的一些可能需要较长的时间开始的初始启动过程。</span><span class="sxs-lookup"><span data-stu-id="fd7dc-106">Some of the Skype for Business Server services may take an extended time to begin the initial startup process.</span></span> <span data-ttu-id="fd7dc-107">任务会发出启动命令，但不等待确定服务是否成功启动。</span><span class="sxs-lookup"><span data-stu-id="fd7dc-107">The tasks are issuing the command to start, but do not wait to determine if the service is successfully started.</span></span> <span data-ttu-id="fd7dc-108">如果必须监控服务启动和服务状态，应使用 Windows 服务 Microsoft 管理控制台 (MMC)。</span><span class="sxs-lookup"><span data-stu-id="fd7dc-108">If you must monitor the service startup and service status, you should use the Windows Services Microsoft Management Console (MMC).</span></span>
  
<span data-ttu-id="fd7dc-p102">任务窗格下方是将显示“**启动服务**”日志文件的下拉列表。要查看日志文件，请单击“**查看日志**”。单击“**完成**”完成任务。</span><span class="sxs-lookup"><span data-stu-id="fd7dc-p102">Under the task pane is a drop-down list that displays the **Start Services** log file. To view the log file, click **View Log**. Click **Finish** to complete the task.</span></span>
  

