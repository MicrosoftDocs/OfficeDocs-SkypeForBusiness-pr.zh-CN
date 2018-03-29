---
title: tblComplianceParticipant
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant 包含当前参与者每个通道，每个服务器。
ms.openlocfilehash: ba488f377592b48845880acaeed61074bc31ccd2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tblcomplianceparticipant"></a>tblComplianceParticipant
 
tblComplianceParticipant 包含当前参与者每个通道，每个服务器。
  
**列**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|channelUri  <br/> |nvarchar (255) 不为空  <br/> |统一资源标识符 (URI) 的通道。  <br/> |
|用户 Id  <br/> |int，不为空  <br/> |（对应于 tblPrincipal.prinID 表） 的参与者的主体 ID。  <br/> |
|joinedAt  <br/> |bigint，不为空  <br/> |连接事件的时间戳。  <br/> |
|partedAt  <br/> |bigint  <br/> |如果参与者仍加入，则为 null。 如果不为 null，则将事件通道的时间戳。  <br/> 在所有翻译人员处理事件最终删除这些条目。  <br/> |
|userUri  <br/> |nvarchar(255)，不为空  <br/> |用户的 URI。  <br/> |
|serverID  <br/> |int  <br/> |服务器标识 （例如，tblServerIdentity.serverID 表）。  <br/> |
|会话标识符  <br/> |bigint  <br/> |服务器会话。 这是一个随机数生成每次聊天服务启动。 它用来区分会话以便可以标识孤立的参与者。  <br/> |
   
**密钥**

|**列**|**说明**|
|:-----|:-----|
|\<channelUri，用户 Id joinedAt\>  <br/> |为主键。  <br/> |
   

