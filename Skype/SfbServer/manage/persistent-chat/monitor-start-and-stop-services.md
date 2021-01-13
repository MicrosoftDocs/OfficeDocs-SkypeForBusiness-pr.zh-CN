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
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中监视、启动和停止持久聊天服务
 
**摘要：** 了解如何在 Skype for Business Server 2015 中启动、停止和监视持久聊天服务。
  
持久聊天服务和持久聊天合规性服务是 Skype for Business Server 拓扑的一部分，因此可以使用以下 cmdlet 进行监视、停止和启动：
  
|||
|:-----|:-----|
|get-CsWindowsService  <br/> |返回有关作为 Windows 服务运行的 Skype for Business Server 2015 组件的详细信息。  <br/> |
|start-CsWindowsService  <br/> |启动服务。  <br/> |
|stop-CsWindowsService  <br/> |停止服务。  <br/> |
   
> [!NOTE]
> 持久聊天在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。 Teams 中也提供相同的功能。 有关详细信息，请参阅 [Microsoft Teams](/microsoftteams/upgrade-start-here)升级入门。 如果你需要使用持久聊天，你的选择是：将需要此功能的用户迁移到 Teams，或者继续使用 Skype for Business Server 2015。 

有关如何使用 cmdlet 的详细信息，请参阅 [Skype for Business Server 2015 命令行管理程序](../management-shell.md)。
  

