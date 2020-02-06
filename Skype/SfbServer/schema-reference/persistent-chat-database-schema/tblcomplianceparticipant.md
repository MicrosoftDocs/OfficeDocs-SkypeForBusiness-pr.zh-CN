---
title: tblComplianceParticipant
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant 包含每个频道和每台服务器的当前参与者。
ms.openlocfilehash: 8f4b90cd7e8949451c2b6c1b9bc3cfabbab826e9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814640"
---
# <a name="tblcomplianceparticipant"></a>tblComplianceParticipant
 
tblComplianceParticipant 包含每个频道和每台服务器的当前参与者。
  
**多**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|channelUri  <br/> |nvarchar （255），not null  <br/> |通道统一资源标识符（URI）。  <br/> |
|userId  <br/> |int，not null  <br/> |参与者的主体 ID （对应于 tblPrincipal 表）。  <br/> |
|joinedAt  <br/> |bigint，not null  <br/> |联接事件的时间戳。  <br/> |
|partedAt  <br/> |bigint  <br/> |如果参与者仍处于加入，则为 Null。 如果 not null，则通道的时间戳会留下事件。  <br/> 这些条目最终会在所有翻译人员处理该事件时被删除。  <br/> |
|userUri  <br/> |nvarchar （255），not null  <br/> |用户 URI。  <br/> |
|serverID  <br/> |int  <br/> |服务器标识（如 tblServerIdentity 表中所示）。  <br/> |
|标识符  <br/> |bigint  <br/> |服务器会话。 这是每次启动聊天服务时生成的随机数字。 它用于为识别孤立参与者的目的而区分会话。  <br/> |
   
**Key**

|**列**|**说明**|
|:-----|:-----|
|\<channelUri、userId、joinedAt\>  <br/> |主键。  <br/> |
   

