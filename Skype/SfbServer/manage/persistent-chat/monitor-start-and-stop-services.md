---
title: 在 2015 年 10 月中监视、启动和停止Skype for Business Server持久聊天服务
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: 摘要：了解如何在 Skype for Business Server 2015 中启动、停止和监视持久聊天服务。
ms.openlocfilehash: 9d25654a222b956fa5c8a1902e5d3a90674829e8
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60833378"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a>在 2015 年 10 月中监视、启动和停止Skype for Business Server持久聊天服务
 
**摘要：** 了解如何在 2015 年 10 月启动、停止和监视持久Skype for Business Server服务。
  
持久聊天服务和持久聊天合规性服务是 Skype for Business Server 拓扑的一部分，因此可以使用以下 cmdlet 进行监视、停止和启动：
  
|Cmdlet|函数|
|:-----|:-----|
|get-CsWindowsService  <br/> |返回有关作为 Skype for Business Server 服务的 2015 Windows的详细信息。  <br/> |
|start-CsWindowsService  <br/> |启动服务。  <br/> |
|stop-CsWindowsService  <br/> |停止服务。  <br/> |
   
> [!NOTE]
> 持久聊天在 2015 Skype for Business Server可用，但在 2019 年 2 月不再Skype for Business Server支持。 相同的功能在 Teams 中可用。 有关详细信息，请参阅开始[升级Microsoft Teams升级](/microsoftteams/upgrade-start-here)。 如果您需要使用持久聊天，您的选择是迁移需要此功能的用户以Teams或继续使用 Skype for Business Server 2015。 

有关如何使用 cmdlet 的详细信息，请参阅 Skype for Business Server [2015 Management Shell](../management-shell.md)。
  

