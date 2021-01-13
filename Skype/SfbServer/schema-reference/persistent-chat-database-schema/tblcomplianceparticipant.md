---
title: tblComplianceParticipant
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant 包含每个通道和每台服务器的当前参与者。
ms.openlocfilehash: c6aae3c1e7b13456708034512c6b68d67d6d1f92
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809742"
---
# <a name="tblcomplianceparticipant"></a>tblComplianceParticipant
 
tblComplianceParticipant 包含每个通道和每台服务器的当前参与者。
  
**Columns**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|channelUri  <br/> |nvarchar (255)，不为 null  <br/> |通道统一资源标识符 (URI)。  <br/> |
|userId  <br/> |int，不为 null  <br/> |参与者的主体 ID（与 tblPrincipal.prinID 表对应）。  <br/> |
|joinedAt  <br/> |bigint，不为 null  <br/> |加入事件的时间戳。  <br/> |
|partedAt  <br/> |bigint  <br/> |如果仍加入参与者，则为 null。如果不为 null，则为通道离开事件的时间戳。  <br/> 当所有转换器处理该事件时，将最终删除这些项。  <br/> |
|userUri  <br/> |nvarchar(255)，不为 null  <br/> |用户 URI。  <br/> |
|serverID  <br/> |int  <br/> |服务器标识（如 tblServerIdentity.serverID 表中所示）。  <br/> |
|sessionId  <br/> |bigint  <br/> |服务器会话。它是每次聊天服务启动时生成的随机数字。它用于区分会话以便标识孤立参与者。  <br/> |
   
**注册表项**

|**列**|**说明**|
|:-----|:-----|
|\<channelUri, userId, joinedAt\>  <br/> |主键。  <br/> |
   

