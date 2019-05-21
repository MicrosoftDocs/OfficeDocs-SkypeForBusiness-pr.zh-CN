---
title: tblComplianceState
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState 包含池范围的合规性状态信息。
ms.openlocfilehash: 1c5571d7150c3859978f8d217f0264f67ee993d5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295473"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState 包含池范围的合规性状态信息。
  
**多**

|**列**|**类型**|**说明**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint, not null  <br/> |最新的已处理合规性事件的 ID。  <br/> |
|activeServerID  <br/> |int, not null  <br/> |在数据库上持有独占锁的合规性服务器 ID, 或者, 如果没有, 则为-1。  <br/> |
|lockExpirationTime  <br/> |datetime2, not null  <br/> |锁过期时间 (如果 activeServerID 不是-1)。  <br/> |
   

