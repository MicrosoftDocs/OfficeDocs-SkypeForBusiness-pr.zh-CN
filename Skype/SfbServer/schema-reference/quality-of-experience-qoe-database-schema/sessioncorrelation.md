---
title: SessionCorrelation 表
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: SessionCorrelation 表是一个支持表。 每条记录表示一个 CorrelationID，用于关联多个会话。
ms.openlocfilehash: 3b0e3208ec019d205ab74fec8318e0221b70b8ea
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60771848"
---
# <a name="sessioncorrelation-table"></a>SessionCorrelation 表
 
SessionCorrelation 表是一个支持表。 每条记录表示一个 CorrelationID，用于关联多个会话。 
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**校验和** <br/> |int  <br/> |||
|**CorrelationKey** <br/> |int  <br/> |主  <br/> |标识此 A/V 会议服务器的唯一编号。  <br/> |
|**CorrelationID** <br/> |nvarchar (256)   <br/> |独特  <br/> |关联的会话将具有相同的相关 ID。  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> | <br/> |仅供内部使用。  <br/> |
   

