---
title: Conference 表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: 会议表是一个支持表。每条记录代表一个会议或点对点会话。
ms.openlocfilehash: 3da2ed90cbb55e44d4eb4ff4902898eed6099f2e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58609149"
---
# <a name="conference-table"></a>Conference 表
 
会议表是一个支持表。每条记录代表一个会议或点对点会话。
  
|**列**|**数据类型**|**键/索引**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |int  <br/> |主  <br/> |标识该会议记录的唯一编号。  <br/> |
|**ConfURI** <br/> |nvarchar (450)   <br/> |unique  <br/> |如果是会议，则是会议 URI；如果是点对点会话，则是 DialogID。  <br/> |
|**校验和** <br/> |int  <br/> |index  <br/> |会议 URI 的校验和。该项仅供内部使用。  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||仅供内部使用。  <br/> |
   

