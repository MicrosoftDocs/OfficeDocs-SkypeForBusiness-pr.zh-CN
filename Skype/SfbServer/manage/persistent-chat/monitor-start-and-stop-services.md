---
title: 在 Skype for Business Server 2015 中监视、启动和停止持久聊天服务
ms.reviewer: ''
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
ms.openlocfilehash: ee817dc5ed76ca5981ab0429da82f74ee5327583
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890232"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中监视、启动和停止持久聊天服务
 
**摘要：** 了解如何启动、 停止和监视 Skype 中使用的持久聊天服务的业务服务器 2015年。
  
持久聊天服务和持久聊天合规性服务属于企业服务器拓扑的 Skype 和因此可以监视、 停止和由使用以下 cmdlet 启动：
  
|||
|:-----|:-----|
|get-CsWindowsService  <br/> |返回有关详细信息 Skype 的业务服务器 2015年组件的运行作为 Windows 服务。  <br/> |
|start-CsWindowsService  <br/> |启动服务。  <br/> |
|stop-CsWindowsService  <br/> |停止服务。  <br/> |
   
> [!NOTE]
> 持久聊天中的业务服务器 2015 Skype 可用但业务服务器 2019年不再支持在 Skype。 中团队提供了相同的功能。 有关详细信息，请参阅[从企业对 Microsoft 团队的 Skype 旅程](/microsoftteams/journey-skypeforbusiness-teams)。 如果您需要使用持久聊天，您的选择是也迁移要求给团队，此功能的用户或继续对业务服务器 2015年使用 Skype。 

有关如何使用此 cmdlet 的详细信息，请参阅 [Skype for Business Server 2015 Management Shell](../management-shell.md)。
  

