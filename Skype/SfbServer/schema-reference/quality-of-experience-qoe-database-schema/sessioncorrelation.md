---
title: SessionCorrelation 表
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
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: SessionCorrelation 表是一个支持表。 每条记录表示一个 CorrelationID，用于关联多个会话。
ms.openlocfilehash: 36b617517f3642a2150c72369db858eee62a4a87
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802652"
---
# <a name="sessioncorrelation-table"></a>SessionCorrelation 表
 
SessionCorrelation 表是一个支持表。 每条记录表示一个 CorrelationID，用于关联多个会话。 
  
|**列**|**数据类型**|**键/索引**|**Details**|
|:-----|:-----|:-----|:-----|
|**校验和** <br/> |int  <br/> |||
|**CorrelationKey** <br/> |int  <br/> |主  <br/> |标识此 A/V 会议服务器的唯一编号。  <br/> |
|**CorrelationID** <br/> |nvarchar (256)   <br/> |独特  <br/> |关联的会话将具有相同的关联 ID。  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> | <br/> |仅供内部使用。  <br/> |
   

