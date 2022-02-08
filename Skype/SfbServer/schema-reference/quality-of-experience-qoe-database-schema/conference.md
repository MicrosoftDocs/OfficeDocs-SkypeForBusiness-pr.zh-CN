---
title: Conference 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.openlocfilehash: 913bc5affb41c980be0638fa7a1cd2656d1db128
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62394734"
---
# <a name="conference-table"></a>Conference 表
 
会议表是一个支持表。每条记录代表一个会议或点对点会话。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |int  <br/> |主  <br/> |标识该会议记录的唯一编号。  <br/> |
|**ConfURI** <br/> |nvarchar (450)   <br/> |unique  <br/> |如果是会议，则是会议 URI；如果是点对点会话，则是 DialogID。  <br/> |
|**校验和** <br/> |int  <br/> |index  <br/> |会议 URI 的校验和。该项仅供内部使用。  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||仅供内部使用。  <br/> |
   

