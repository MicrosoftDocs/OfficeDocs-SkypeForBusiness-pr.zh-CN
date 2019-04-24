---
title: tblComplianceParticipant
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant 包含每个通道和每台服务器的当前参与者。
ms.openlocfilehash: a3d18c4a78af2892a837e1105a435a3ce46ea14b
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212949"
---
# <a name="tblcomplianceparticipant"></a>tblComplianceParticipant
 
tblComplianceParticipant 包含每个通道和每台服务器的当前参与者。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|channelUri  <br/> |nvarchar (255)，不为 null  <br/> |通道统一资源标识符 (URI)。  <br/> |
|用户 Id  <br/> |int，不为 null  <br/> |（与 tblPrincipal.prinID 表对应） 的参与者的主体 ID。  <br/> |
|joinedAt  <br/> |bigint，不为 null  <br/> |加入事件的时间戳。  <br/> |
|partedAt  <br/> |bigint  <br/> |如果参与者仍加入，则为 null。 如果不为 null 离开事件该频道的时间戳。  <br/> 当所有转换器都处理该事件时，将最终删除这些条目。  <br/> |
|userUri  <br/> |nvarchar （255)，不为 null  <br/> |用户 URI。  <br/> |
|serverID  <br/> |int  <br/> |服务器标识 （与 tblServerIdentity.serverID 表）。  <br/> |
|sessionId  <br/> |bigint  <br/> |服务器会话。 这是生成每次聊天服务启动一个随机数字。 它用于区分以便标识孤立的参与者的会话。  <br/> |
   
**关键字**

|**列**|**说明**|
|:-----|:-----|
|\<channelUri，用户 Id joinedAt\>  <br/> |主键。  <br/> |
   

