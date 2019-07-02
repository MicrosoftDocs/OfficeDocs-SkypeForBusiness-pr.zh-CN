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
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中监视、启动和停止持久聊天服务
 
**摘要:** 了解如何在 Skype for Business Server 2015 中启动、停止和监视持久聊天服务。
  
持久聊天服务和持久聊天合规性服务是 Skype for Business 服务器拓扑的一部分, 因此可使用以下 cmdlet 进行监控、停止和启动:
  
|||
|:-----|:-----|
|get-CsWindowsService  <br/> |返回有关作为 Windows 服务运行的 Skype for Business Server 2015 组件的详细信息。  <br/> |
|start-CsWindowsService  <br/> |启动服务。  <br/> |
|stop-CsWindowsService  <br/> |停止服务。  <br/> |
   
> [!NOTE]
> Skype for business Server 2015 中提供了持久聊天, 但 Skype for business Server 2019 不再支持此功能。 团队中提供了相同的功能。 有关详细信息, 请参阅[Microsoft 团队升级](/microsoftteams/upgrade-start-here)入门。 如果需要使用持久聊天, 您可以选择将需要此功能的用户迁移到团队, 或继续使用 Skype for Business Server 2015。 

有关如何使用此 cmdlet 的详细信息，请参阅 [Skype for Business Server 2015 Management Shell](../management-shell.md)。
  

