---
title: SessionCorrelation 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: SessionCorrelation 表是支持表。 每条记录表示一个 CorrelationID，用于关联多个会话。
ms.openlocfilehash: cd9f477ad71b836fb204aab651aceb7bbb5832f8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805740"
---
# <a name="sessioncorrelation-table"></a>SessionCorrelation 表
 
SessionCorrelation 表是支持表。 每条记录表示一个 CorrelationID，用于关联多个会话。 
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**检查** <br/> |int  <br/> |||
|**CorrelationKey** <br/> |int  <br/> |Primary  <br/> |标识此 A/V 会议服务器的唯一号码。  <br/> |
|**True&correlationid** <br/> |nvarchar(256)  <br/> |唯一  <br/> |关联的会话将具有相同的相关性 ID。  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> | <br/> |仅供内部使用。  <br/> |
   

